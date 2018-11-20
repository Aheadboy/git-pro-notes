---


---

<h2 id="git-分支-git-的杀手级特性">Git 分支-Git 的杀手级特性</h2>
<ul>
<li>Git 鼓励在工作流程中频繁地使用分支与合并，哪怕一天之内进行许多次。</li>
<li>Git 的分支，实质上仅是
<ul>
<li>包含所指对象校验和（长度为 40 的 SHA-1 值字符串）的文件，所以它的创建和销毁都异常高效。</li>
<li>创建一个新分支就相当于往一个文件中写入 41 个字节（40 个字符和 1 个换行符）</li>
</ul>
</li>
<li>Git 的默认分支名字是 <code>master</code></li>
<li>指向最后那个提交对象的 <code>master</code> 分支，它会在每次的提交操作中自动向前移动。</li>
<li><img src="https://raw.githubusercontent.com/Aheadboy/img_all/master/git%E5%88%86%E6%94%AF.png" alt="enter image description here"></li>
</ul>
<h4 id="创建分支">创建分支</h4>
<ul>
<li>它只是为你创建了一个可以移动的新的<strong>指针</strong></li>
</ul>
<pre class=" language-console"><code class="prism  language-console">$ git branch newBranchName
//这会在当前所在的提交对象上创建一个指针
//仅仅创建一个分支不会自动切换到新分支上
</code></pre>
<p><img src="https://raw.githubusercontent.com/Aheadboy/img_all/master/%E6%96%B0%E5%BB%BA%E6%8C%87%E9%92%88.png" alt=""></p>
<h4 id="head-指针">HEAD 指针</h4>
<ul>
<li>指向<strong>当前</strong>所在的<strong>本地</strong>分支<br>
<img src="https://raw.githubusercontent.com/Aheadboy/img_all/master/head%E6%8C%87%E9%92%88.png" alt="enter image description here"></li>
</ul>
<h4 id="切换分支">切换分支</h4>
<pre class=" language-console"><code class="prism  language-console">$ git checkout testing
</code></pre>
<p><img src="https://raw.githubusercontent.com/Aheadboy/img_all/master/%E5%88%87%E6%8D%A2%E5%88%86%E6%94%AF.png" alt="enter image description here"></p>
<ul>
<li>本质就是HEAD指针的值进行了变化。</li>
<li>切换分支前是要先commit的。保持一个干净的状态</li>
</ul>
<blockquote>
<p>但是，在你这么做之前<br>
要留意你的工作目录和暂存区里那些还没有被提交的修改<br>
它可能会和你即将检出的分支产生冲突从而阻止 Git 切换到该分支。<br>
在切换分支之前， 最好保持一个干净的状态<br>
有一些方法可以绕过这个问题（即，保存进度（stashing） 和 修补提交（commit amending））<br>
我们会在 <a href="https://git-scm.com/book/zh/v2/ch00/r_git_stashing">储藏与清理</a> 中看到关于这两个命令的介绍。</p>
</blockquote>

