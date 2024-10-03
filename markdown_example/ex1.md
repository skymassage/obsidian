# Heading
For heading level one, there is an alternate “underline” style using `=`  
`Heading 1`  
`=========`
## Heading 1-1
For heading level two, there is an alternate “underline” style using `-`  
`Heading 2`  
`---------`

### Heading 1-1-1

#### Heading 1-1-1-1

##### Heading 1-1-1-1-1

###### Heading 1-1-1-1-1-1

# Emphasis
To create bold or italic, wrap with asterisks `*` or underscores `_`. To avoid creating bold or italic, place a backslash in front `\*` or `\_`.

Ex:
**Bold**   or   __Bold__
*Italics*   or   _Italics_
***Bold and italic***   or   ___Bold and italic___
**Bold text and _nested italic_ text**
==Highlight==
~~Strikethrough~~
This is a <sup>superscript</sup> text
This is a <sub>subscript</sub> text


# Blockquotes
To create a blockquote, start a line with greater than `>` followed by an optional space. 

Ex:
> Here is the **Quote**.
> Here is the **Quote**

---

Blockquotes can be nested, and can also contain other formatting.
Ex:
> Here is the **Quote**.
> > Here is the **Quote**.
> >  Here is the **Quote**.
> >> Here is the **Quote**.

# Code
To create inline code, wrap with backticks `` ` ``.

Ex:
When `x = 3`, that means `x + 2 = 5`

---

To create a code block, either indent each line by 4 spaces (one tab), or place 3 backticks ` ``` ` on a line above and below the code block.
 
Ex:
```
print("Here is the code.")
```

    print("Here is the code.")
# Lists

Unordered lists can use either asterisks `*`, plus `+`, or hyphens `-` as list markers.  
+ List 1
- List 2
* List 3

---

Ordered lists use numbers followed by period `.` or right paren `)`.
1. List 1
2) List 2


# Nested Lists
To nest one list within another, indent each item in the sublist by four spaces. You can also nest other elements like paragraphs, blockquotes or code blocks. To nest a **paragraph** or **blockquote**, indent by either 4 spaces or one tab. 

Ex:

1. First list item
   - First nested list item
     - Second nested list item

2. Nest a **paragraph**

	Bring water to boil, add a pinch of salt and spaghetti. Cook until pasta is **tender**.

3. Nest a **blockquote**
   > No man is lonely eating spaghetti; it requires so much attention.



# Links
Use `<>` to turn this URL into a link: <https://www.google.com.tw>

---

Link text is enclosed by square brackets `[]`, and for inline links, the link URL is enclosed by parens `()`: [Google](https://www.google.com)

---

Internal link:
[example_image](/example.png)

Use `[[markdown_file]]` to link to another markdown file: [[ex2]]
Or use text as the link another markdown file: [Click here](\ex2.md)

---

Reference-style links:
```
[text][label]  
⋮  
[label]: URL
```
`[label]: URL` can be placed anywhere after a blank line, but is generally near the bottom. Label names must not be repeated, including images and hyperlinks. Labels may consist of letters, numbers, spaces, and punctuation. They are not case sensitive. You must switch to the reading mode and then click on the `[text]` to go to its link. Also, yon don't see the reference `[label]: URL` in the reading mode.
Ex: [Hurricane][link_1] Erika was the strongest and longest-lasting tropical cyclone in the 1997 Atlantic [hurricane][link_1] season. 
(Note that you need to switch to the reading mode to see this effect, otherwise you will be taken to an empty page titled `[`.)

[link_1]: https://w.wiki/qYn
 
# Images
Images are almost identical to links, but an image starts with an exclamation point `!`.
```
![alt](URL)
```
Alternate (alt) text is displayed when the image can't be shown, or for the visually impaired. It's fine to leave this blank but the `[]` is required.

Ex: 
![Markdown](C:\Main\Projects\GitHub\note\markdown_example\example.png)
If the URL is invalid, it will show the alt: ![Markdown](/example.png)

---

```
![alt][label]  
⋮  
[label]: URL
```
Here is almost identical to links part. 

Ex:
Also, you must switch to the reading mode to see the image, otherwise you will be taken an empty page.
![Logo][image_1]

[image_1]: https://commonmark.org/help/images/favicon.png 

# Callouts
Use callouts to include additional content without breaking the flow of your notes. To create a callout, add `[!info]` to the first line of a blockquote, where `info` is the _type identifier_. The type identifier determines how the callout looks and feels. There are many types of callouts, such as:

> [!note]

> [!tip]

> [!IMPORTANT]

>[!hint]

> [!WARNING]

> [!CAUTION]

>[!attention]

>[!summary]

>[!abstract]

>[!todo]

