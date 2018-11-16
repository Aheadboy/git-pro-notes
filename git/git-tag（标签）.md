---


---

<h2 id="tag（标签）">Tag（标签）</h2>
<h4 id="标签？">标签？</h4>
<ul>
<li>Git 可以给历史中的某一个提交打上标签，以示重要</li>
<li>标记发布结点（v1.0 等等）</li>
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
<li>检出（checkout）</li>
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
<ol start="3">
<li>对指定提交（历史提交）打标签</li>
</ol>
<pre class=" language-console"><code class="prism  language-console">$ git tag -a tagName SHA-1
//在命令的末尾指定提交的校验和（或部分校验和）
//上述打了一个附注标签(annotated tag)
</code></pre>
<ol start="4">
<li>推送tag到远程仓库</li>
</ol>
<ul>
<li>默认情况下 git push 命令并不会推送tag到远程服务器上</li>
<li>必须显示推送tag到远程仓库</li>
</ul>
<pre class=" language-console"><code class="prism  language-console">$ git push remoteName  tagName//推送tagName到remoteName远程仓库
$ git push remoteName  --tags//推送不在远程仓库的所有标签
</code></pre>
<ol start="5">
<li>checkout tag</li>
</ol>
<ul>
<li>在 Git 中你并不能真的检出一个标签</li>
</ul>
<pre class=" language-console"><code class="prism  language-console">$ git checkout -b [branchname] [tagname]
//在指定标签上新建分支 ，checkout该tag的历史版本到新建的分支上，switch to new branch
</code></pre>
<p>这个方法，如果你修改了这个checkout的内容再次提交，那么内容就提交就到了新建的分支上面，这个要注意。</p>

