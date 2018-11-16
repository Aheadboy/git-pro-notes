---


---

<h1 id="git-快照-与-git-gc">Git 快照 与 git gc</h1>
<h2 id="git-snapshot？commit之后发生了什么？">Git snapshot？commit之后发生了什么？</h2>
<h4 id="有一个gittest仓库-，管理了两个文件">有一个gitTest仓库 ，管理了两个文件</h4>
<ul>
<li>a.txt (文件内容为‘aaaaa’）</li>
<li>b.txt（文件内容为‘bbbbb’）<br>
如下图<br>
<img src="https://raw.githubusercontent.com/Aheadboy/img_all/master/a-b%E4%B8%A4%E4%B8%AA%E6%96%87%E4%BB%B6%E8%A2%ABgit%E7%AE%A1%E7%90%86.png" alt="两个被git管理的文件"></li>
</ul>
<h4 id="commit之后生成四个对象">commit之后生成四个对象</h4>
<ol>
<li>提交对象</li>
<li>树对象</li>
<li>两个blob对象分别代表a.txt,b.txt<br>
如下图<br>
<img src="https://raw.githubusercontent.com/Aheadboy/img_all/master/commit%E4%B9%8B%E5%90%8Egit%E7%94%9F%E6%88%90%E7%9A%84%E5%AF%B9%E8%B1%A1.png" alt=""></li>
</ol>
<p>这四个对象就是<strong>S.N.A.P.S.H.O.T</strong></p>
<h4 id="通过命令分析">通过命令分析</h4>
<p><img src="https://raw.githubusercontent.com/Aheadboy/img_all/master/%E5%88%86%E6%9E%90%E8%BF%99%E5%9B%9B%E4%B8%AA%E5%AF%B9%E8%B1%A1.png" alt="enter image description here"></p>
<ul>
<li>1个 commit object存储了 指向 tree object的引用</li>
<li>1个 tree object 存储了 指向两个blob的引用</li>
<li>2个 blob对象分别存储各自文件内容</li>
</ul>
<h4 id="修改a.txt后commit">修改a.txt后commit</h4>
<p>在a.txt文件内容中追加一个字母b使内容变成：‘aaaaab’<br>
b.txt文件不改动<br>
再次commit</p>
<p><img src="https://raw.githubusercontent.com/Aheadboy/img_all/master/%E6%96%B0%E5%A2%9E%E4%BA%863%E4%B8%AA%E5%AF%B9%E8%B1%A1.png" alt=""></p>
<h4 id="分析这三个对象">分析这三个对象</h4>
<p><img src="https://raw.githubusercontent.com/Aheadboy/img_all/master/%E5%88%86%E6%9E%90%E4%B8%89%E4%B8%AA%E5%AF%B9%E8%B1%A1.png" alt="enter image description here"></p>
<ul>
<li>1个  commit object 存储了新的tree引用 以及 父提交的引用</li>
<li>1个  tree object 还是存储了两个引用
<ul>
<li>一个是新的指向本次修改的文件（a.txt）</li>
<li>一个是旧的，本次未修改的文件（b.txt）</li>
</ul>
</li>
<li>1 个 新生成的blob文件代表了本次修改的a.txt，没有生成代表b.txt的blob，因为b.txt本次未修改。</li>
</ul>
<h3 id="总结">总结</h3>
<ol>
<li>解释了<strong>s.n.a.p.s.h.o.t</strong>
<ul>
<li>快照就是<strong>文件内容加</strong>上信息头，经过<strong>zlib压缩</strong>后存盘的一个文件</li>
<li>一种松散的格式（<strong>loose</strong> object format）</li>
</ul>
</li>
<li>剖析了git commit之后发生了什么</li>
</ol>
<h2 id="git-打包git-gc">Git 打包(git gc)</h2>
<p>相比其他vcs，存储文件各个版本的差异性<br>
git这种commit 之后存储快照流的方式较为浪费空间<br>
哪怕就是添加了一个字母也重新存储一份新的快照。</p>
<ul>
<li><img src="https://raw.githubusercontent.com/Aheadboy/img_all/master/ZE9J0%7DV@LEIU@2W9SN0$7%251.png" alt="修改前快照的大小"><br>
修改前a.txt的快照大小</li>
<li><img src="https://raw.githubusercontent.com/Aheadboy/img_all/master/D%5D%7B%25P6$%7BEFFI~YYRTIG~38R.png" alt="修改后快照的大小"><br>
修改后a.txt快照大小。</li>
</ul>
<p>为了解决这个问题git会进行打包操作（即<strong>git gc</strong>命令）</p>
<h4 id="打包的时间点">打包的时间点</h4>
<ul>
<li>时不时</li>
<li>手动git gc</li>
<li>push到远程仓库时</li>
</ul>
<h4 id="打包的结果">打包的结果</h4>
<p>在.git/objects/pack路径下</p>
<ul>
<li>一个 *.idx文件</li>
<li>一个或多个 *.pack文件
<ul>
<li>存储文件最新版本（因为最新版本的使用率更改）完整内容的快照，以及其他版本的差异</li>
</ul>
</li>
</ul>
<h4 id="手动git-gc">手动git gc</h4>
<ul>
<li>
<p>执行前<img src="https://raw.githubusercontent.com/Aheadboy/img_all/master/%E6%9C%AAgit-gc.png" alt=""></p>
</li>
<li>
<p>执行命令<img src="https://raw.githubusercontent.com/Aheadboy/img_all/master/git-gc.png" alt=""></p>
</li>
<li>
<p>执行后<img src="https://raw.githubusercontent.com/Aheadboy/img_all/master/git-gc-pack.png" alt=""><br>
<img src="https://raw.githubusercontent.com/Aheadboy/img_all/master/%60F9XP%29Z5WLY1S$9IAXM%60R84.png" alt="enter image description here"></p>
</li>
</ul>
<h4 id="打包细节">打包细节</h4>
<blockquote>
<p>Git 是如何做到这点的？ Git 打包对象时，会查找命名及大小相近的文件，并只保存文件不同版本之间的差异内容。 你可以查看包文件，观察它是如何节省空间的。 git verify-pack 这个底层命令可以让你查看已打包的内容：</p>
</blockquote>
<p><img src="https://raw.githubusercontent.com/Aheadboy/img_all/master/pack-verify.png" alt="enter image description here"></p>
<p><img src="https://raw.githubusercontent.com/Aheadboy/img_all/master/git-pro-book%E5%8E%9F%E6%96%87%E4%BE%8B%E5%AD%90.png" alt=""></p>
<p>上图是pro git这本书的例子，上面我们自己的例子好像并没有体现出差异性存储，新a.txt6个字节（aaaaab）旧a.txt5个字节（aaaaa）并且没有引用。<br>
我知道了，之所以会出现这样的情况是因为这两个文件的内容在同一行，<br>
你在aaaaa后面追加了一个b变成aaaaab，在git看来不是加了一个b而是删除了一行aaaaa，然后在添加一行aaaaab，两个版本不存在增量delta（δ）<br>
如果想像书的作者那种结果，你应该在a.txt文件中增加一行内容。</p>

