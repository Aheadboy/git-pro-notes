---


---

<h1 id="git-快照-与-git-gc">Git 快照 与 git gc</h1>
<h3 id="git-snapshot？commit之后发生了什么？">Git snapshot？commit之后发生了什么？</h3>
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
<li>解释了<strong>s.n.a.p.s.h.o.t</strong></li>
<li>剖析了git commit之后发生了什么</li>
</ol>

