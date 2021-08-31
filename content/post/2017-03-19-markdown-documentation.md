---
title: Markdown documentation
subtitle: 
date: 2017-03-19
tags: ["example", "markdown"]
---

<!-- more -->

This page is an overview of the formatting features offered by Markdown.
It can be use as a Cheatsheet or a test page for your Markdown based app


 ## New to Markdown?

If you are completly new to Markdown, you can get an overview of the key features [in the Markdown Guide](https://www.markdownguide.org/getting-started/) and test the basics online with this [interactive tutorial](https://commonmark.org/help/tutorial/), or [this other one](http://markdowntutorial.com/).


**Note**: the source of this page is [available online](https://framagit.org/roneo/roneo.frama.io/-/raw/master/content/page/hugo-demo-markdown-overview-test-showcase.md)


## Inline text formatting

### **Bold** text

Use `**two asterisks**` →  **two asterisks**

or `__two underscores__` →  __two underscores__

### *Italic*

Use `*single asterisk*` → *single asterisk*

or `_single underscore_` → _single underscore_

### ***Bold and italic***

Three stars for `***bold and italic***` → ***bold and italic***

### ~~Strikethrough~~

Use `~~two tilde~~` →  ~~two tildes~~



## Blockquotes

	> blockquote


> blockquote

### Nested blockquotes

	> First level
	>> Second level

> First level
>> Second level    

### Markdown in blockquotes

```
> **Markdown** can be used *inside quotes*
> 1.   This is the first list item.
> 1.   This is the second list item.
> 
> ~~strikethrough~~
>
> Here's some example code:
>
>     return shell_exec("echo $input | $markdown_script");
```

**Output:**

> **Markdown** can be used *inside quotes*
> 1.   This is the first list item.
> 1.   This is the second list item.
> 
> ~~strikethrough~~
>
> Here's some example code:
>
>     return shell_exec("echo $input | $markdown_script");


## Lists


### Unordered list

Cant be marked with `-`, `+` or `*`

```markdown
- First item
* Second item
+ Third item
```

**Output:**

- First item
* Second item
+ Third item

### Ordered lists

Incrementation is automatic, you can simply use `1.` everywhere

```
1. First item
1. Second item
1. Third item
```

**Output:**

1. First item
1. Second item
1. Third item



### Nested list

```
- First item
- Second item
- Third item
  1. Indented item
  1. Indented item
- Fourth item
```

**Output:**

- First item
- Second item
- Third item
	1. Indented item
	1. Indented item
- Fourth item


## Paragraphs & breaks

If you hit **enter just once** between two lines, both lines will be joined into a single paragraph, which is called [wrapping text](https://about.gitlab.com/2016/10/11/wrapping-text/#do-wrap-it).

But, if you **leave a blank line between them**, they will split into two paragraphs.

**Demonstration**:

```
This text is a paragraph.
This won't be another paragraph, it will join the line above it.

This will be another paragraph, as it has a blank line above it.
```

**Output**

This text is a paragraph. This won't be another paragraph, it will join the line above it.

This will be another paragraph, as it has a blank line above it.

## Line breaks

To force a line break, end a line with two or more whitespaces, and then type return.

```
This is the first line.··
Second line
```

**Output:**

This is the first line.  
Second line

## Horizontal lines

Can be inserted with four `*`, `-` or `_`

```
----
****
____
```

**Output:**

----
****
____




## Links


### Basic links

```
[Semantic description](https://www.example.com)
<address@example.com>  
<https://example.com> works too. Must be used for explicit links.
```

**Output:**

[Semantic description](https://www.example.com)  
<address@example.com>  
<https://example.com> works too. Must be used for explicit links.


### Links with text reference

```
[I'm a link][Reference text]

[This link] will do the same as well. It works as the identifier itself.


[reference text]: https://www.mozilla.org
[this link]: http://example2.com
```
**Output:**

[I'm a link][Reference text]

[This link] will do the same as well. It works as the identifier itself.


[reference text]: https://www.mozilla.org
[this link]: http://example2.com

**Note:** The reference text is case *in*sensitive


### Link with a title on hover

```
[Another text][another-identifier].  
Hover the mouse over it to see the title.

[another-identifier]: https://example.com "This example has a title"
```

**Output:**

[Another text][another-identifier]. Hover the mouse over it to see the title.

[another-identifier]: https://example.com "This example has a title"


### Links with Markdown style

To ***emphasize*** links, add asterisks before and after the brackets and parentheses.  

	I love supporting the **[EFF](https://eff.org)**.
	This is the *[Markdown Guide](https://www.markdownguide.org)*.

To denote links as `code`, add backticks *inside* the brackets:

	See the section on [`code`](#code).

**Output:**

I love supporting the **[EFF](https://eff.org)**.  
This is the *[Markdown Guide](https://www.markdownguide.org)*.  
See the section on [`code`](#code).

----

### Add custom anchor to a title

Anchors are automatically generated based on the title's content. You can customize the anchor this way:

	### Heading {#custom-id}

**Output:**

#### Heading {#custom-id}



## Code formatting {#code}


### Inline

Wrap with single backticks to highlight as`` `code` `` → `code`

### Codeblocks

Create a code block with three backticks `` ``` `` before and after your block of code.

**Output:**


```
sudo apt hello
cat /etc/apt/sources.list
```

Also possible with a tabulation / four empty spaces at the beginning of the lines:

**Tabulation**

	sudo apt hello
	echo "hi"

**Four whitespaces**

    sudo apt hello

Let's test the wrapping of a long line:

	apt install test apt install test apt install test apt install test apt install test apt install test apt install test apt install test apt install test apt install test apt install test apt install test apt install test apt install test 

### Codeblocks with syntax highlighting

Set the language right after the first backticks (for example `` ```html  ``) to get syntax highlighting

**Samples:**


#### HTML

```html
<!DOCTYPE html>
<html lang="fr" itemscope itemtype="http://schema.org/WebPage">
  <head>
  <meta charset="utf-8" />
  <meta http-equiv="X-UA-Compatible" content="IE=edge">
  <meta name="viewport" content="width=device-width, initial-scale=1.0, maximum-scale=1.0">
```

#### CSS

```css
/* Comment */
.blog-post h2, h3 {
  margin-top: 1.6em;
  margin-bottom: 0.8em;
}
```

#### Bash

```bash
# Comment

if [[ ! $system =~ Linux|MacOS|BSD ]]; then
	echo "This version of bashtop does not support $system platform."

sudo apt install test
```

#### Diff

```diff
- red
+ green
! test
# gray
```


## Images

### Basic syntax

```
![Semantic description of the image](/img/ok.png)
```

![Semantic description of the image](/img/ok.png)

**Note:** The text inside the square brackets is the image attribute called `ALT`, which stands for _alternative text_. [Including descriptive alt text](https://webaim.org/techniques/alttext/) helps maintain accessibility for every visitor and should always be included with an image. When you add alt text be sure to describe the content and function of the picture.  
In addition to the accessibility benefits, `ALT` is useful for SEO, and it is displayed when, for some reason, that image is not loaded by the browser.


### Image with title and caption

```
![Semantic description](/img/ok.png "Your title")*Your caption*
```
![Semantic description](/img/ok.png "Your title")*Your caption*


### Clickable images

For clickable images, simply wrap the image markup into a [link markup](#links):

```
[![Semantic description](/img/ok.png "Your title")](http://roneo.org)
```

**Output:**

[![Semantic description](/img/ok.png "Your title")](http://roneo.org/en)



### Image with an identifier

You can call the image with an identifier as we do for [links](#links)

```
![Semantic desc.][image identifier]

Lorem ipsum dolor sit amet consectetur adipisicing elit [...]

[image identifier]: /img/ok.png "Title"
```

![Semantic desc.][image identifier]

[image identifier]: /img/ok.png "Title"


## Task List

```
- [X] Write the press release
- [ ] Update the website
```

- [X] Write the press release
- [ ] Update the website

## Tables


```
| Syntax    | Description |
| --------- | ----------- |
| Header    | Title       |
| Paragraph | Text        |
```

or

```
| Syntax | Description |
| - | - |
| Header | Title |
| Paragraph | Text |
```

will render the same way:

| Syntax    | Description |
| --------- | ----------- |
| Header    | Title       |
| Paragraph | Text        |


### Text alignment in tables


```
| Syntax    | Description |   Test Text |
| :-------- | :---------: | ----------: |
| Header    |    Title    | Here's this |
| Paragraph |    Text     |    And more |
```
See the way the text is aligned

| Syntax    | Description |   Test Text |
| :-------- | :---------: | ----------: |
| Header    |    Title    | Here's this |
| Paragraph |    Text     |    And more |


<div class="boxInfo"> <strong>Need a Table generator?</strong>

You can generate Markdown tables easily with this [Table Generator](https://www.tablesgenerator.com/markdown_tables)
</div>



## Footnotes

```
Here's a sentence with a footnote[^1].
Lorem ipsum dolor, sit amet consectetur adipisicing

[^1]: This is the first footnote.
```

**Output:**

Here's a sentence with a footnote[^1].  
Lorem ipsum dolor, sit amet consectetur adipisicing

[^1]: This is the first footnote.

### Long footnote

```
Here's a longer one.[^bignote]

Lorem ipsum dolor sit,

[^bignote]: Here's one with multiple paragraphs and code.
	
	Indent paragraphs to include them in the footnote.
	
	`{ my code }`
	
	Note that you can place the footnote anywhere you want in your article
```

**Output:**

Here's a longer one.[^bignote]

Lorem ipsum dolor sit,

[^bignote]: Here's one with multiple paragraphs and code.
	
	Indent paragraphs to include them in the footnote.
	
	`{ my code }`
	
	Note that you can place the footnote anywhere you want in your article



## Definition List

```
term
: definition

second term
: meaning
```

**Output:**

term
: definition

second term
: meaning

## Headings:

Add `##` at the beginning of a line to set as Title.  
You can use until 6 `#` for different Titles levels


```
# Title One

## Title Two
[...]

###### Title 6
```


# Title One

**Note:** We don't use `h1` headings, as they already are displayed on every page as its title, and we should not apply more than one `h1` per page.
    
> When you use a top level heading `<h1>` with a single `#`, you’re setting up a semantic relationship between that heading and the remainder of the content on a page, describing what it is about.  
> If you then use a second `<h1>` on the same page, you’re creating some potential confusion, for someone with a screen reader or for a search engine scrapping your page
>
> Moreover, Level 1 titles simply do not appear in alternative readers like Wallabag
    
**Conclusion** →  Always start with `##`

## Title *Two*

pedit quia voluptates atque nobis, perspiciatis deserunt perferendis, nostrum, voluptatem voluptas dolorem iure voluptatum? Accusantium a dolores dicta?Pariatur voluptates quam ut, cum aliquid eum, officiis laudantium totam suscipit, ducimus odit nobis! Corrupti, doloremque sed optio voluptatibus deserunt quas repellat eius minus quasi, ipsam unde esse sequi deleniti.


### Title 3 ##################################

pedit quia voluptates atque nobis, perspiciatis deserunt perferendis, nostrum, voluptatem voluptas dolorem iure voluptatum? Accusantium a dolores dicta?Pariatur voluptates quam ut, cum aliquid eum, officiis laudantium totam suscipit, ducimus odit nobis! Corrupti, doloremque sed optio voluptatibus deserunt quas repellat eius minus quasi, ipsam unde esse sequi deleniti.

#### Title 4

pedit quia voluptates atque nobis, perspiciatis deserunt perferendis, nostrum, voluptatem voluptas dolorem iure voluptatum? Accusantium a dolores dicta?Pariatur voluptates quam ut, cum aliquid eum, officiis laudantium totam suscipit, ducimus odit nobis! Corrupti, doloremque sed optio voluptatibus deserunt quas repellat eius minus quasi, ipsam unde esse sequi deleniti.

##### Title 5

pedit quia voluptates atque nobis, perspiciatis deserunt perferendis, nostrum, voluptatem voluptas dolorem iure voluptatum? Accusantium a dolores dicta?Pariatur voluptates quam ut, cum aliquid eum, officiis laudantium totam suscipit, ducimus odit nobis! Corrupti, doloremque sed optio voluptatibus deserunt quas repellat eius minus quasi, ipsam unde esse sequi deleniti.

###### Title 6

pedit quia voluptates atque nobis, perspiciatis deserunt perferendis, nostrum, voluptatem voluptas dolorem iure voluptatum? Accusantium a dolores dicta?Pariatur voluptates quam ut, cum aliquid eum, officiis laudantium totam suscipit, ducimus odit nobis! Corrupti, doloremque sed optio voluptatibus deserunt quas repellat eius minus quasi, ipsam unde esse sequi deleniti.


## References

- [Basic Syntax | Markdown Guide](https://www.markdownguide.org/basic-syntax)
- [Extended Syntax | Markdown Guide](https://www.markdownguide.org/extended-syntax)
- [Daring Fireball: Markdown Syntax Documentation](https://daringfireball.net/projects/markdown/syntax)
- [Markdown Guide at Gitlab.com](https://about.gitlab.com/handbook/markdown-guide/)
- [CommonMark Spec](https://spec.commonmark.org/0.29/)

This website uses [Hugo](https://gohugo.io/), which implements [the Goldmark](https://github.com/yuin/goldmark) markdown parser. Goldmark adheres to the [CommonMark specification.](https://spec.commonmark.org/) - [Source](https://discourse.gohugo.io/t/markdown-mixed-with-html-stops-links-from-being-rendered/27993/6)

## Further reading

- [CommonMark Discussions](https://talk.commonmark.org/)
- [A clever way to Style Images With Markdown](https://www.xaprb.com/blog/how-to-style-images-with-markdown/)
