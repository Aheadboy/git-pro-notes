---


---

<h1 id="git-快照-与-git-gc">Git 快照 与 git gc</h1>
<h4 id="git-snapshot">Git snapshot</h4>
<p>有一个gitTest仓库 ，管理了两个文件</p>
<ul>
<li>a.txt (文件内容为‘aaaaa’）</li>
<li>b.txt（文件内容为‘bbbbb’）</li>
</ul>
<p><img src="https://raw.githubusercontent.com/Aheadboy/img_all/master/a-b%E4%B8%A4%E4%B8%AA%E6%96%87%E4%BB%B6%E8%A2%ABgit%E7%AE%A1%E7%90%86.png" alt="两个被git管理的文件"></p>
<p>commit之后生成四个对象</p>
<ol>
<li>提交对象</li>
<li>树对象</li>
<li>两个blob对象分别代表a.txt,b.txt</li>
</ol>

