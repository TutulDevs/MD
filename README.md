# Mastering Markdown

## Paragraph

<!-- This is comment -->

This is a demo paragraph with no styling. While MD keep a line space after any line for breaking.

If you
write without
spacing, it'll be
a single paragraph.

__Two sets of _ or * make bold__

*One set of * makes it italic*

Two sets of ~ (tilda) make ~~strike through~~

## Headers & linkers

# Heading 1

## Heading 2

### Heading 3

*GitHub or some other tools make this # sings as ID like an HTML page.*

## Linking

There're many ways to make links.

www.all-js.netlify.app    *shows w/o anything*

<http://all-js.netlify.app>  *use <> to display, but use http://. Otherwise it'll display the <> as well*

[My GitHub Acc](http://github.com/TutulDevs) *For nicer display*

[My Twitter](http://twitter.com/TutulDevs "My Twitter") *This link has a title w/ it*

You can use token to store a [link][1] so that you can use it anywhere w/o being verbose. The [token][1] is more like a varible. It's very handy.

[1]: http://twitter.com/TutulDevs

## MD Images

![woohoo](http://unsplash.it/300/100?random)

Make a small picture linked to the bigger version of it by using nested MD.

[![Big Img](http://unsplash.it/50/50?image=10)](http://unsplash.it/500/300?image=10)

[<img src="http://unsplash.it/50/50?image=15">](http://unsplash.it/500/300?image=15)

*The ! menas it's going to be an image. [] for alt text(skippable).() for linking.*

*You can use token to link w/ title. No problem*

*__Pro Tip__: if you can't figure out anything on MD, just use regular in HTML inside <> 😎*

## Regular HTML & CSS

<p class="para">
    This is in a p tag & styled by CSS.
</p>

🔷 GitHub is not showing the custom CSS edits. Boo!
<style>

    p.para {
        color: #ddd;
        font-size: 20px;
        background: salmon;
        padding: 5px;
        transform: skew(20deg);
    }
    h2 {
        color: teal;
        border-bottom: 1px solid crimson;
        padding-bottom: 5px;
    }
    blockquote {
        border-left: 3px solid #ddd;
        padding-left: 5px;
    }
</style>

## List (ordered, unordered, bullet, nested)

* For unordered list
- or bullet list
+ use */ - / + before the item.
+ The parser knows it's an unordered list.

1. This is ordered list .
2. Just put a number & . (1.) to start
3. ✌️
3. Your ordered list.
4. Don't worry about the serial number for later changes.
5. The parser will display as from 1 - n. Just like the #3 item.

* This is nested link
* Nesting inside.

This is a para inside the nested list. Add image or anything here.
* Nesting off.


# Code Block

```js
const x = 5 - 3 ;
```

## Line Break, Horizontal Rule

For line break, use **br** tag of HTML or use line space.

For horizontal rule use 3 dashes(-) or 3 equal signs(=). But make sure those are not below any text. Otherwise the text will be H1. <br>
The = is not working in this app 😐

---

⬆ is an example of horizontal line(---). Doesn't working in (===).

## Blockquote

> Put a right chevron before the line to quote.
>
> This parser is not showing the left border. Damn!
>
> So I added that in CSS 😎


## Tables

*Tables are just basically done by using pipes(|)*

| Name | Age |
|:------:|------:|
| John | 25 |
| Mia | 22 |
| Tutul | 27 |

## Checkbox

[ ] Watch WesBos' Tutorial

[x] Post them in Twitter

[ ] Be awesome 😎

My parser is not showing checkboxes 😐

<mark>This file is made with the help of **WesBos'** tutorial. Many thanks to him. </mark>