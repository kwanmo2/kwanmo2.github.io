---
layout: default
title: Buttons
parent: UI쓰기
nav\_order: 2
---

# Buttons
{: .no\_toc }

## Table of contents
{: .no\_toc .text-delta }

1. TOC
{:toc}

---

## Basic button styles

### Links that look like buttons

<div class="code-example" markdown="1">
[Link button][1]{: .btn }

[Link button][2]{: .btn .btn-purple }
[Link button][3]{: .btn .btn-blue }
[Link button][4]{: .btn .btn-green }

[Link button][5]{: .btn .btn-outline }
</div>
```markdown
[Link button](http://example.com/){: .btn }

[Link button](http://example.com/){: .btn .btn-purple }
[Link button](http://example.com/){: .btn .btn-blue }
[Link button](http://example.com/){: .btn .btn-green }

[Link button](http://example.com/){: .btn .btn-outline }
```

### Button element

GitHub Flavored Markdown does not support the `button` element, so you'll have to use inline HTML for this:

<div class="code-example">
<button type="button" name="button" class="btn">Button element</button>
</div>
```html
<button type="button" name="button" class="btn">Button element</button>
```

---

## Using utilities with buttons

### Button size

Wrap the button in a container that uses the [font-size utility classes]({{ site.baseurl }}{% link docs/utilities/typography.md %}) to scale buttons:

<div class="code-example" markdown="1">
<span class="fs-6">
[Big ass button][6]{: .btn }
</span>

<span class="fs-3">
[Tiny ass button][7]{: .btn }
</span>
</div>
```markdown
<span class="fs-8">
[Link button](http://example.com/){: .btn }
</span>

<span class="fs-3">
[Tiny ass button](http://example.com/){: .btn }
</span>
```

### Spacing between buttons

Use the [margin utility classes]({{ site.baseurl }}{% link docs/utilities/layout.md %}#spacing) to add spacing between two buttons in the same block.

<div class="code-example" markdown="1">
[Button with space][8]{: .btn .btn-purple .mr-2 }
[Button ][9]{: .btn .btn-blue .mr-2 }

[Button with more space][10]{: .btn .btn-green .mr-4 }
[Button ][11]{: .btn .btn-blue }
</div>
```markdown
[Button with space](http://example.com/){: .btn .btn-purple .mr-2 }
[Button ](http://example.com/){: .btn .btn-blue }

[Button with more space](http://example.com/){: .btn .btn-green .mr-4 }
[Button ](http://example.com/){: .btn .btn-blue }
```

[1]:	http://example.com/
[2]:	http://example.com/
[3]:	http://example.com/
[4]:	http://example.com/
[5]:	http://example.com/
[6]:	http://example.com/
[7]:	http://example.com/
[8]:	http://example.com/
[9]:	http://example.com/
[10]:	http://example.com/
[11]:	http://example.com/