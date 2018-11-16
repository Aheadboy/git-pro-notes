---


---

<h4 id="提交对象">提交对象</h4>
<p>在进行提交操作时，Git 会保存一个提交对象（commit object）。知道了 Git 保存数据的方式，我们可以很自然的想到</p>
<ul>
<li>该提交对象会包含一个指向暂存内容快照的指针。</li>
<li>还包含了
<ul>
<li>作者的姓名和邮箱</li>
<li>提交时输入的信息</li>
<li>指向它的父对象的指针。</li>
</ul>
</li>
<li><strong>首次</strong>提交产生的提交对象<strong>没有</strong>父对象。</li>
<li><strong>普通</strong>提交操作产生的提交对象有<strong>一个</strong>父对象。</li>
<li>由多个分支<strong>合并</strong>产生的提交对象有<strong>多个</strong>父对象。</li>
</ul>

