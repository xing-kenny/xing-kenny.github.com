---

---

# Markdown For Typora

*Outline*
[TOC]

## Block Elements
### Blockquotes

> This is a blockquote with two paragraphs. This is first paragraph.
>
> This is second pragraph.Vestibulum enim wisi, viverra nec, fringilla in, laoreet vitae, risus.

### Lists

``` markdown
## un-ordered list
*   Red
*   Green
*   Blue

## ordered list
1.  Red
2. 	Green
3.	Blue
```

### Task List 
- [ ] a task list item
- [ ] list syntax required
- [ ] normal **formatting**, @mentions, #1234 refs
- [ ] incomplete
- [x] completed

### (Fenced) Code Blocks

Here's an example:

```
function test() {
  console.log("notice the blank line before this function?");
}
```

syntax highlighting:
```ruby
require 'redcarpet'
markdown = Redcarpet.new("Hello World!")
puts markdown.to_html
```
###Math Blocks

$$
\mathbf{V}_1 \times \mathbf{V}_2 =  \begin{vmatrix} 
\mathbf{i} & \mathbf{j} & \mathbf{k} \\
\frac{\partial X}{\partial u} &  \frac{\partial Y}{\partial u} & 0 \\
\frac{\partial X}{\partial v} &  \frac{\partial Y}{\partial v} & 0 \\
\end{vmatrix}
$$

### Tables

| First Header | Second Header |
| ------------ | ------------- |
| Content Cell | Content Cell  |
| Content Cell | Content Cell  |

### Footnotes

You can create footnotes like this[^footnote].

[^footnote]: Here is the *text* of the **footnote**.

###Horizontal Rules   

Input *** or --- on a blank line and press return will draw a horizontal line.

---
***

###YAML 



###TOC

## Span Elements
### Links

``` markdown
This is [an example](http://example.com/ "Title") inline link.

[This link](http://example.net/) has no title attribute.
```

This is [an example](http://example.com/"Title") inline link. (`<p>This is <a href="http://example.com/" title="Title">`)

This is [an example](http://example.com/"Title") inline link.

###URLs



### Images
![图片名](http://www.tigu.cn/images/bigimages/logo.png)

### Strikethrough

~~Mistaken text.~~

###Underline

<u>Underline</u>

###Emoji

:happy: 
:sad:
:cry:

### Inline Math
$lim_{x \to \infty} \ exp(-x)=0$

###Subscript

H~2~O

###Superscript

y[^2].

###Highlight

==highlight==

==hign light==


