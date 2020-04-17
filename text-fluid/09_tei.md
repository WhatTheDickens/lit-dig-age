
## Trying your hand at TEI

Encoding textual variants of a fluid text using the method described on the previous page is difficult work. We won't attempt it here. But we will try to do is to encode some of the changes we might see on a single manuscript page from just one of the draft versions of *Walden*. To do this, we'll need to employ just a handful of elements.

### <del>

The `<del>` element is used to indicate deleted text. For example, to represent a bit of writing on a manuscript page where the author originally wrote

`She bought the apples on Wednesday, April 16.`

but then drew a line through the word "Wednesday," we would write:

```
<p>She bought the apples on <del>Wednesday,</del> April 16.</p>
```
### <add>

Let's say the author didn't just delete (or, to use the technical editorial term, *cancel*) "Wednesday" but also inserted "Thursday" above or beside the canceled text. We would represent that change this way:

```
<p>She bought the apples on <del>Wednesday,</del> <add>Thursday</del> April 16.</p>
```
Notice that our mark up doesn't try to represent *how* the canceled text was canceled. If "Wednesday" had been canceled with a squiggly line or heavy cross-hatching, our encoding wouldn't change. Similarly, the `<add>` element doesn't tell us by itself whether the inserted text was added above, below, or beside the canceled text, or off in a margin somewhere connected by a long line.

TEI gives us ways to capture that kind of information about manuscript text, but we're not going to get into those here.

Finally, notice that insertions that take place inside deletions, and deletions that take place inside insertions, can be captured through nested elements.

```
 <p>I should not presume to talk so much about myself and my affairs as I
 shall in this <del>lecture</del><del><add>book</add></del><del><add>work</add></del><add>book</add> ...</p>
```

In this example, our markup says, in effect: On the page, "lecture" is canceled, "book" is inserted and then canceled, "work" is inserted and then canceled, and "book" is again inserted.