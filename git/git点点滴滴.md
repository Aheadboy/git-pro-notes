---


---

<ol>
<li>
<blockquote>
<p>在 Git 中任何 <em>已提交的</em> 东西几乎总是可以恢复的。 甚至那些被删除的分支中的提交或使用 <code>--amend</code>选项覆盖的提交也可以恢复。然而，任何你未提交的东西丢失后很可能再也找不到了</p>
</blockquote>
</li>
<li></li>
</ol>
<pre class=" language-console"><code class="prism  language-console">$ git push origin master
</code></pre>
<blockquote>
<p>只有当你有所克隆服务器的写入权限，并且之前没有人推送过时，这条命令才能生效。<br>
当你和其他人在同一时间克隆，他们先推送到上游然后你再推送到上游，你的推送就会毫无疑问地被拒绝。<br>
你必须先将他们的工作拉取下来并将其合并进你的工作后才能推送。</p>
</blockquote>
<ol start="3">
<li>git 就是快照加指针，谁说的？我说的！！！</li>
</ol>

