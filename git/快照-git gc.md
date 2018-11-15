---


---

<h1 id="git-快照-与-git-gc">Git 快照 与 git gc</h1>
<h4 id="git-snapshot">Git snapshot</h4>
<p>有一个gitTest仓库 ，管理了两个文件</p>
<ul>
<li>a.txt (文件内容为‘aaaaa’）</li>
<li>b.txt（文件内容为‘bbbbb’）<br>
如下图<br>
<img src="https://raw.githubusercontent.com/Aheadboy/img_all/master/a-b%E4%B8%A4%E4%B8%AA%E6%96%87%E4%BB%B6%E8%A2%ABgit%E7%AE%A1%E7%90%86.png" alt="两个被git管理的文件"></li>
</ul>
<p>commit之后生成四个对象</p>
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

