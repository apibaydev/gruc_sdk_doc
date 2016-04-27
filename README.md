# Welcome to MarkdownPad 2  #

**MarkdownPad** is a full-featured Markdown editor for Windows.

### Built exclusively for Markdown ###

Enjoy first-class Markdown support with easy access to  Markdown syntax and convenient keyboard shortcuts.

Give them a try:

- **Bold** (`Ctrl+B`) and *Italic* (`Ctrl+I`)
- Quotes (`Ctrl+Q`)
- Code blocks (`Ctrl+K`)
- Headings 1, 2, 3 (`Ctrl+1`, `Ctrl+2`, `Ctrl+3`)
- Lists (`Ctrl+U` and `Ctrl+Shift+O`)

### See your changes instantly with LivePreview ###

Don't guess if your [hyperlink syntax](http://markdownpad.com) is correct; LivePreview will show you exactly what your document looks like every time you press a key.

### Make it your own ###

Fonts, color schemes, layouts and stylesheets are all 100% customizable so you can turn MarkdownPad into your perfect editor.

### A robust editor for advanced Markdown users ###

MarkdownPad supports multiple Markdown processing engines, including standard Markdown, Markdown Extra (with Table support) and GitHub Flavored Markdown.

With a tabbed document interface, PDF export, a built-in image uploader, session management, spell check, auto-save, syntax highlighting and a built-in CSS management interface, there's no limit to what you can do with MarkdownPad.
<table>
    <tr>
        <td>FooS</td>
    </tr>
</table>
http://images.google.com/images?num=30&amp;q=larry+bird
&copy;
AT&T
AT&amp;T
4 < 5
4 &lt; 5
This is an H1
=============

This is an H2
---------------

> This is a blockquote with two paragraphs. Lorem ipsum dolor sit amet,
> consectetuer adipiscing elit. Aliquam hendrerit mi posuere lectus.
> Vestibulum enim wisi, viverra nec, fringilla in, laoreet vitae, risus.
> 
> Donec sit amet nisl. Aliquam semper ipsum sit amet velit. Suspendisse
>
> id sem consectetuer libero luctus adipiscing.

> ## 这是一个标题。
> 
> 1.   这是第一行列表项。
> 2.   这是第二行列表项。
> 
> 给出一些例子代码：
> 
>     return shell_exec("echo $input | $markdown_script");

###无序列表，可用*、+、-表示###

*   Red
*   Green
*   Blue
+   Red
+   Green
+   Blue
-   Red
-   Green
-   Blue

###有序列表则使用数字接着一个英文句点###

1.  Bird
2.  McHale
3.  Parish

####有序列表转换为html后不会输出上述的数字，如下：####

<ol>
<li>Bird</li>
<li>McHale</li>
<li>Parish</li>
</ol>

####有序列表还可以写为如下形式，效果一样，若懒得很^_^####

1.  Bird
1.  McHale
1.  Parish
#####
3. Bird
1. McHale
8. Parish

####其它例子效果####

*   Lorem ipsum dolor sit amet, consectetuer adipiscing elit.
    Aliquam hendrerit mi posuere lectus. Vestibulum enim wisi,
    viverra nec, fringilla in, laoreet vitae, risus.
*   Donec sit amet nisl. Aliquam semper ipsum sit amet velit.
    Suspendisse id sem consectetuer libero luctus adipiscing.

*   Lorem ipsum dolor sit amet, consectetuer adipiscing elit.
Aliquam hendrerit mi posuere lectus. Vestibulum enim wisi,
viverra nec, fringilla in, laoreet vitae, risus.
*   Donec sit amet nisl. Aliquam semper ipsum sit amet velit.
Suspendisse id sem consectetuer libero luctus adipiscing.

*   Bird
*   Magic

*   Bird

*   Magic

1.  This is a list item with two paragraphs. Lorem ipsum dolor
	sit amet, consectetuer adipiscing elit. Aliquam hendrerit
    mi posuere lectus.

   	Vestibulum enim wisi, viverra nec, fringilla in, laoreet
    vitae, risus. Donec sit amet nisl. Aliquam semper ipsum
    sit amet velit.

2.  Suspendisse id sem consectetuer libero luctus adipiscing.

####列表项目中放进引用####

*   A list item with a blockquote:

    > This is a blockquote  
    > inside a list item.  
    > nice done！

*   一列表项包含一个列表区块：

        <代码写在这>
		Script=java

####注意下面的区别####

1986. What a great season.

1986\. What a great season.

\.  What a great season.

  \.  What a great season.

####建立代码区块很简单，只要简单地缩进 4 个空格或是 1 个制表符就可以，例如####

这是一个普通段落：

    这是一个代码区块。

####上例MarkDown会转换为：####
<p>这是一个普通段落：</p>

<pre><code>这是一个代码区块。
</code></pre>

####缩进4个空格（或一个制表符），直接写成代码区块####
	<div class="footer">
        &copy; 2004 Foo Corporation
    </div>

###分隔符###

* * *

***

*****

- - -

---------------------------------------

###链接###

* 行内式

This is [an example](http://example.com/ "Title") inline link.

[This link](http://example.net/) has no title attribute.

####链接到本地地址的相对路径：local://base_request.html/about/####

See my [About](/about/) page for details.

* 参考式

This is [an example][id] reference-style link.
[id]: http://example.com/  "Optional Title Here"

* 隐式链接

[Google][]
[Google]: http://google.com.sg/

Visit [Daring Fireball][] for more information.
[Daring Fireball]: http://daringfireball.net/

####参考式和行内式链接比较####
* I get 10 times more traffic from [Google] [1] than from
  [Yahoo] [2] or [MSN] [3].

  [1]: http://google.com/        "Google"
  [2]: http://search.yahoo.com/  "Yahoo Search"
  [3]: http://search.msn.com/    "MSN Search"

* I get 10 times more traffic from [Google][] than from
  [Yahoo][] or [MSN][].

  [google]: http://google.com/        "Google"
  [yahoo]:  http://search.yahoo.com/  "Yahoo Search"
  [msn]:    http://search.msn.com/    "MSN Search"

* I get 10 times more traffic from [Google](http://google.com/ "Google")
  than from [Yahoo](http://search.yahoo.com/ "Yahoo Search") or
  [MSN](http://search.msn.com/ "MSN Search").

###强调###

*single asterisks*

_single underscores_

**double asterisks**

__double underscores__

###代码：如果要标记一小段行内代码，你可以用反引号把它包起来###

Use the `printf()` function.

``There is a literal backtick (`) here.``

A single backtick in a code span: `` ` ``

A backtick-delimited string in a code span: `` `foo` ``

Please don't use any `<blink>` tags.

`&#8212;` is the decimal-encoded equivalent of `&mdash;`.

###图片###

* 行内式

![Alt text](/path/to/img.jpg)

![Alt text](/path/to/img.jpg "Optional title")

* 参考式

![Alt text][id]

[id]: url/to/image  "Optional title attribute"

###自动链接###

<http://example.com/>

<address@example.com>

###反斜杠：加在其它符号前面，以显示这些符号###

\*literal asterisks\*

\("test \ okay!")\\

####这些符号还可以是：####
	\   反斜线
	`   反引号
	*   星号
	_   底线
	{}  花括号
	[]  方括号
	()  括弧
	#   井字号
	+   加号
	-   减号
	.   英文句点
	!   惊叹号

