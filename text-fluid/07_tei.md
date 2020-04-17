## TEI for data analysis

If you still have the file `05.xml` on your computer, open it up and have a look at this bit of marked-up text, beginning around line 87. (If you don't still have it, [revisit it on GitHub](https://github.com/milnegeneseo/fluid_text/blob/master/tei/05.xml)):

```
<p n="1" change="#wc_0a">
    <note type="header" resp="#clapper">
        <ab type="string">Solitude 1 written: A; rewritten: B , D.</ab>
            <ab type="parsed">
                <seg type="chapterNum">5</seg>
                <seg type="chapterTitle">Solitude</seg>
                <seg type="paragraph">1</seg>
                <seg type="written">A</seg>
                <seg type="rewritten">B, D</seg>
```
Each paragraph of *Walden* in the fluid-text edition is marked up with descriptive information like this. An important part of that information, enclosed in the `<seg>` element, is the version history for the paragraph. In this case: written in version, rewritten in versions B and D.

Now head over to the page ["Written and Re-Written in *Walden*"](https://digitalthoreau.org/written-and-re-written/) on the fluid-text site. The table there makes it possible to sort the paragraphs and sub-paragraphs ("segments") of *Walden* in order to better understand the how Thoreau's work grew across the seven versions.

Taking that same data and putting it in a spreadsheet yields the perspective offered in numbers and two different charts on the page "The Growth of *Walden*."

Click ahead to offer some thoughts on what these visualizations reveal about the evolution of *Walden*.