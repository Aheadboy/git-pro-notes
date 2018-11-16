---


---

<h2 id="tag（标签）">Tag（标签）</h2>
<h4 id="标签？">标签？</h4>
<ul>
<li>Git 可以给历史中的某一个提交打上标签，以示重要</li>
<li>标记发布结点（v1.0 等等）</li>
<li>在 Git 中你并不能真的检出一个标签</li>
</ul>
<h4 id="使用">使用</h4>
<ul>
<li>列出标签</li>
<li>创建标签
<ul>
<li>lightweight（轻量标签）</li>
<li>annotated（附注标签）</li>
</ul>
</li>
<li>对指定提交（commit） 打标签</li>
<li>push标签</li>
</ul>
<ol>
<li>列出标签</li>
</ol>
<pre class=" language-console"><code class="prism  language-console">$ git tag
//或者带过滤条件
$ git tag -l 'v1.8.5*'
//显示指定tag的详细信息
$ git show tagName
</code></pre>
<ol start="2">
<li>创建标签</li>
</ol>
<pre class=" language-console"><code class="prism  language-console">//轻量
$ git tag tagName
//附注
$ git tag -a tagName -m 'messageContents'
</code></pre>

