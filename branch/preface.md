---


---

<h2 id="git-分支-git-的杀手级特性">Git 分支-Git 的杀手级特性</h2>
<ul>
<li>Git 鼓励在工作流程中频繁地使用分支与合并，哪怕一天之内进行许多次。</li>
<li>Git 的分支，其实本质上仅仅是指向提交对象的可变指针</li>
<li>Git 的默认分支名字是 <code>master</code></li>
<li>指向最后那个提交对象的 <code>master</code> 分支，它会在每次的提交操作中自动向前移动。</li>
<li><img src="https://raw.githubusercontent.com/Aheadboy/img_all/master/git%E5%88%86%E6%94%AF.png" alt="enter image description here"></li>
</ul>
<h4 id="创建分支">创建分支</h4>
<ul>
<li>它只是为你创建了一个可以移动的新的指针</li>
</ul>
<pre class=" language-console"><code class="prism  language-console">$ git branch newBranchName
//这会在当前所在的提交对象上创建一个指针
//仅仅创建一个分支不会自动切换到新分支上
</code></pre>
<p>img</p>
<h4 id="head-指针">HEAD 指针</h4>
<ul>
<li>指向当前所在的本地分支</li>
</ul>
<h4 id="切换分支">切换分支</h4>
<pre class=" language-console"><code class="prism  language-console">$ git checkout testing
</code></pre>
<ul>
<li>本质就是HEAD指针的值进行了变化。</li>
<li>切换分支前好像是要先commit的，有待progit解释还未阅读到。</li>
</ul>

