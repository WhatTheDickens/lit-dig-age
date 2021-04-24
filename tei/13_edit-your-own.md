# Edit your own TEI file

This assignment is due by 11:59 p.m. on  Monday, April 27.

Download the template TEI file named <a href="https://canvas.geneseo.edu/courses/17027/files/1001787/download?wrap=1" class="instructure_file_link instructure_scribd_file" title="sample.xml">sample.xml</a> together with <a href="https://canvas.geneseo.edu/courses/17027/files/1001790/download?wrap=1" class="instructure_file_link instructure_scribd_file" title="sample_text_for_tei.pdf">the pdf containing a short sample of handwritten text</a>.

-   Select a manuscript page of *Walden* from [the Google sheet previously shared with you](https://docs.google.com/spreadsheets/d/1pevP6Jmc40QP0g8b4JMgPQMRhi6rfCRdaJoV8NhYlzU/edit#gid=1938909689).
-   Select a portion of that page for encoding. The passage should contain some changes Thoreau made: words, phrases, or sentences added or deleted. *The passage doesn't have to be long*: a short paragraph or even just a portion of a paragraph is fine. *You don't have to encode the entire page.*
-   Determine
    -   what draft version the page belongs to (A-G) — that information is in the spreadsheet;
    -   what chapter of *Walden* the page belongs to — that's in the spreadsheet, too;
    -   what paragraph or paragraph segment the passage belongs to (e.g., 3, 4b) within the chapter — you can figure this out by comparing the passage content to Digital Thoreau's fluid-text edition of *Walden.*
-   Encode the passage following the instructions in the template file you downloaded.
-   Validate your encoding by using [the validator tool on the TEI by Example website](https://teibyexample.org/xquery/TBEvalidator.xq).
-   Do your best to get the file to validate. Once it's complete and validated, upload the file to Canvas. If you can't get it to validate by the deadline, upload what you've got.

The template contains a number of TEI tags we haven't looked at before. Some of these are explained in the template file. Others should be fairly self-explanatory. (For example, the `msDesc` element encloses a description of a manuscript, including the repository — such as a library or archive — that holds it.) You can learn the meaning of any tag and see examples of its use by looking it up on the website of the [TEI consortium](https://tei-c.org/release/doc/tei-p5-doc/en/html/index.html).

The template includes some comments as placeholders for text that you'll add yourself. When you replace a comment, replace the entire thing, including the angle brackets enclosing the comment. For example, you would replace *all* of

```xml
    <!-- Replace with Chapter title, e.g. "Spring" -->
```

with the title of the chapter that your passage comes from.

Some comments are adjacent to the text where you have to make modifications. You can leave these comments in your document unchanged. For example, where you see

```xml
    <surface xml:id="hm924v1n232"> <!-- This is just an example. Replace the id with actual xml:id of your image. -->
```

on line 35, you'll be replacing the `hm924v1n232` in

```xml
    <surface xml:id="hm924v1n232">
```

with the actual identifier for the image you've selected. (Column A in the spreadsheet.) You'll put the identifier inside the quotation marks, leaving those in place. You can leave the comment in place, too, or you can delete it.

Note that whereas the basic TEI file shared with you earlier in this module has two main parts — `teiHeader` and `text` — this template is instead divided into `teiHeader` and `sourceDoc`. We can use `sourceDoc` here in place of `text`because we're encoding a manuscript rather than a printed text. This manuscript is the source document for our transcription: hence "sourceDoc".

Finally, note the encoding of the final word in the handwritten sample. I purposely tried to make that word unreadable to illustrate how you can encode anything in Thoreau's handwriting that you can't make out. You can treat the unreadable word or words as a "gap" in your transcription and provide a reason for the gap, as in the example:

```xml
    <gap reason="illegible" />
```

The `gap` element is "self-closing"; that is, there's no second closing tag `</gap >` because there's no content for the tags to surround. But you still need that `/`: you simply include it in the single, self-closing tag.

After I did the encoding, I looked back at my handwriting and thought, "Hmmm, that scribble kind of looks like it *might* be the word "fun." (I really just intended it to be an illegible scribble.) Sometimes you come across words in a manuscript that you *think* you can make out but not with complete certainty. And there's a tag for that!

The last word could have been encoded this way:

```xml
    <unclear cert="low">fun</unclear>
```

With this approach, we include what we *think* the word is, documenting our uncertainty with the `unclear` element, and using both opening and closing tags to surround the unclear word. Alternative values to "low," in indicating certainty, are "high" and "medium."
