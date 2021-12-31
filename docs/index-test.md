---
layout: default
title: Markdown kitchen sink
nav\_order: 99
nav_exclude: true_
---

Text can be **bold**, _italic_, or \~\~strikethrough\~\~.

[Link to another page][1].

There should be whitespace between paragraphs.

There should be whitespace between paragraphs. We recommend including a README, or a file with information about your project.

# [][2]Header 1

This is a normal paragraph following a header. GitHub is a code hosting platform for version control and collaboration. It lets you and others work together on projects from anywhere.

## [][3]Header 2

> This is a blockquote following a header.
> 
> When something is important enough, you do it even if the odds are not in your favor.

### [][4]Header 3

```js
// Javascript code with syntax highlighting.
var fun = function lang(l) {
  dateformat.i18n = require('./lang/' + l)
  return true;
}
```

```ruby
# Ruby code with syntax highlighting
GitHubPages::Dependencies.gems.each do |gem, version|
  s.add_dependency(gem, "= #{version}")
end
```

#### [][5]Header 4 `with code not transformed`

*   This is an unordered list following a header.
*   This is an unordered list following a header.
*   This is an unordered list following a header.

##### [][6]Header 5

1.  This is an ordered list following a header.
2.  This is an ordered list following a header.
3.  This is an ordered list following a header.

###### [][7]Header 6

| head1        | head two          | three |
|:-------------|:------------------|:------|
| ok           | good swedish fish | nice  |
| out of stock | good and plenty   | nice  |
| ok           | good `oreos`      | hmm   |
| ok           | good `zoute` drop | yumm  |

### There's a horizontal rule below this.

---- 

### Here is an unordered list:

*   Item foo
*   Item bar
*   Item baz
*   Item zip

### And an ordered list:

1.  Item one
1.  Item two
1.  Item three
1.  Item four

### And a nested list:

- level 1 item
  - level 2 item
  - level 2 item
	- level 3 item
	- level 3 item
- level 1 item
  - level 2 item
  - level 2 item
  - level 2 item
- level 1 item
  - level 2 item
  - level 2 item
- level 1 item

### Nesting an ol in ul in an ol

- level 1 item (ul)
  - level 2 item (ol)
  - level 2 item (ol)
	- level 3 item (ul)
	- level 3 item (ul)
- level 1 item (ul)
  - level 2 item (ol)
  - level 2 item (ol)
	- level 3 item (ul)
	- level 3 item (ul)
  - level 4 item (ol)
  - level 4 item (ol)
	- level 3 item (ul)
	- level 3 item (ul)
- level 1 item (ul)

### And a task list

- [ ] Hello, this is a TODO item
- [ ] Hello, this is another TODO item
- [x] Goodbye, this item is done

### Small image

![][image-1]

### Large image

![][image-2]


### Definition lists can be used with HTML syntax.

<dl>
<dt>Name</dt>
<dd>Godzilla</dd>
<dt>Born</dt>
<dd>1952</dd>
<dt>Birthplace</dt>
<dd>Japan</dd>
<dt>Color</dt>
<dd>Green</dd>
</dl>

#### Multiple description terms and values

Term
: Brief description of Term

Longer Term
: Longer description of Term,
  possibly more than one line

Term
: First description of Term,
  possibly more than one line

: Second description of Term,
  possibly more than one line

Term1
Term2
: Single description of Term1 and Term2,
  possibly more than one line

Term1
Term2
: First description of Term1 and Term2,
  possibly more than one line

: Second description of Term1 and Term2,
  possibly more than one line
  
### More code

```
Long, single-line code blocks should not wrap. They should horizontally scroll if they are too long. This line should be long enough to demonstrate this.
```

```
The final element.
```

[1]:	another-page
[2]:	#header-1
[3]:	#header-2
[4]:	#header-3
[5]:	#header-4
[6]:	#header-5
[7]:	#header-6

[image-1]:	https://assets-cdn.github.com/images/icons/emoji/octocat.png
[image-2]:	https://guides.github.com/activities/hello-world/branching.png