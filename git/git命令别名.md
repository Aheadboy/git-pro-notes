---


---

<h2 id="为git-命令起外号">为Git 命令起’外号’</h2>
<h3 id="why？">WHY？</h3>
<p>有些git命令较长、较难记忆或很常用，你可以为这样的命令起简单（方便输入），好记的别名，以方便自己的使用</p>
<h3 id="举例">举例</h3>
<ol>
<li></li>
</ol>
<pre class=" language-console"><code class="prism  language-console">$ git config --global alias.co checkout
$ git config --global alias.br branch
$ git config --global alias.ci commit
$ git config --global alias.st status
</code></pre>
<p>当要输入 <code>git commit</code> 时，只需要输入 <code>git ci</code>。<br>
随着你继续不断地使用 Git，可能也会经常使用其他命令，所以创建别名时不要犹豫。</p>
<ol start="2">
<li></li>
</ol>
<pre class=" language-console"><code class="prism  language-console">$ git config --global alias.unstage 'reset HEAD --'
</code></pre>
<p>这会使下面的两个命令等价：</p>
<pre class=" language-console"><code class="prism  language-console">$ git unstage fileA
$ git reset HEAD -- fileA
</code></pre>
<ol start="3">
<li></li>
</ol>
<p>通常也会添加一个  <code>last</code>  命令，像这样：</p>
<pre class=" language-console"><code class="prism  language-console">$ git config --global alias.last 'log -1 HEAD'
</code></pre>
<p>这样，可以轻松地看到最后一次提交</p>
<pre class=" language-console"><code class="prism  language-console">git last
</code></pre>
<p>可以看出，Git 只是<strong>简单地将别名替换为对应的命令</strong></p>

