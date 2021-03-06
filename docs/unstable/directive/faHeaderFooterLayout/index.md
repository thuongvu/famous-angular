---
layout: "docs_api"
version: "unstable"
versionHref: "/docs/unstable"
path: "api/directive/faHeaderFooterLayout/"
title: "fa-header-footer-layout"
header_sub_title: "Directive in module famous.angular"
doc: "faHeaderFooterLayout"
docType: "directive"
---

<div class="improve-docs">
  <a href='https://github.com/Famous/famous-angular/edit/master/src/scripts/directives/fa-header-footer-layout.js#L1'>
    Improve this doc
  </a>
</div>





<h1 class="api-title">

  fa-header-footer-layout



</h1>





This directive will create a Famo.us HeaderFooterLayout containing
a Header, Content, and Footer based on the order of its child elements.
 See [https://famo.us/docs/views/HeaderFooterLayout]






  
<h2 id="usage">Usage</h2>
  
```html
<fa-header-footer-layout>
  <!-- header rendernode -->
  <!-- content rendernode -->
  <!-- footer rendernode -->
</fa-header-footer-layout>
```
  
  

  



<h2 id="example">Example</h2><p><code>Fa-header-footer</code> is a View that arranges three renderables into a header and footer area with defined sizes, and a content area that fills up the remaining space.</p>
<p>To use it, declare it in the html and nest 3 renderables inside.  In the example below, there are three direct children elements: a Modifier (with an <code>fa-surface</code> nested inside), a Surface, and another Modifier (with an <code>fa-surface</code> nested inside).  The order that they are declared in the html determines whether each corresponds to a header, content, and footer.</p>
<p>Since the header and footer Modifiers have fixed heights of <code>[undefined, 75]</code> (fill the parent container horizontally, 75 pixels vertically), the content will fill the remaining height of the parent modifier or context.</p>
<pre><code class="lang-html">&lt;fa-header-footer-layout&gt;
  &lt;!-- header --&gt;
  &lt;fa-modifier fa-size=&quot;[undefined, 75]&quot;&gt;
    &lt;fa-surface fa-background-color=&quot;&#39;red&#39;&quot;&gt;Header&lt;/fa-surface&gt;
  &lt;/fa-modifier&gt;

  &lt;!-- content --&gt;
  &lt;fa-surface fa-background-color=&quot;&#39;blue&#39;&quot;&gt;Content&lt;/fa-surface&gt;

  &lt;!-- footer --&gt;
  &lt;fa-modifier fa-size=&quot;[undefined, 75]&quot;&gt;
    &lt;fa-surface fa-background-color=&quot;&#39;green&#39;&quot;&gt;Footer&lt;/fa-surface&gt;
  &lt;/fa-modifier&gt;
&lt;/fa-header-footer-layout&gt;</code></pre>
<h2 id="ng-repeat-inside-a-fa-header-footer">ng-repeat inside a fa-header-footer</h2>
<p><code>Fa-header-footer</code> works with ng-repeat&#39;ed renderables:</p>
<pre><code class="lang-html">&lt;fa-header-footer-layout&gt;
  &lt;fa-modifier ng-repeat=&quot;view in views&quot; fa-size=&quot;view.size&quot; &gt;
    &lt;fa-surface fa-background-color=&quot;view.bgColor&quot;&gt;
      {{view.text}}
    &lt;/fa-surface&gt;
  &lt;/fa-modifier&gt;
&lt;/fa-header-footer-layout&gt;</code></pre>
<pre><code class="lang-javascript">$scope.views = [
{bgColor: &quot;red&quot;, text: &quot;header&quot;, size: [undefined, 100]},
{bgColor: &quot;green&quot;, text: &quot;content&quot;, size: [undefined, undefined]},
{bgColor: &quot;blue&quot;, text: &quot;footer&quot;, size: [undefined, 100]}
];</code></pre>
<p>In the example above, 3 renderables are generated through an ng-repeat.  The header and footer <code>Modifier</code>s generated by the ng-repeat have defined sizes of <code>[undefined, 100]</code> (they will fill their parent container horizontally, and be 100 pixels vertically).  The content has a size of <code>[undefined, undefined]</code>, and it will fill the remaining heght and width of its container.</p>
<p>Note: If more than 3 renderables are nested inside an <code>fa-header-footer-layout</code>, it will throw an error: <code>fa-header-footer-layout can accept no more than 3 children.</code></p>



