↻ [Home](README.md)&nbsp;&nbsp;&nbsp;|&nbsp;&nbsp;&nbsp;← [9.Why TEI?](09_why-tei.md)&nbsp;&nbsp;&nbsp;|&nbsp;&nbsp;&nbsp;[11. TEI for data analysis](11_tei-for-data-analysis.md) →

# 10. Machines that read

What’s the value in describing texts so that machines can read our descriptions? A full answer to that question would take up a lot of — pages? screens? (take your pick) — but here’s a partial one. For one thing, a machine-readable description enables a computer program to *display* the marked-up text in multiple ways. We’re not locked into any one way of displaying the text. The program simply needs to understand our metalanguage — TEI in this case — and follow whatever instructions we’ve given it for *transforming* the contents into a display-oriented metalanguage that a browser will understand, such as HTML.

For another thing, in adding all this descriptive markup to a text, we make it possible for a computer program to traverse the document systematically looking for certain tags, and to pull out particular tags for analysis.

We can appreciate both these advantages by looking back at the fluid text of *Walden*.

Head over to the [“Solitude” chapter of *Walden: A Fluid-Text Edition*](http://digitalthoreau.org/walden/fluid/text/05.html) and click the “New Version” button (upper left) until it turns gray. Scroll to the right, and you should see a panel for each of the seven manuscript drafts of *Walden*. The leftmost panel, showing “Princeton\_Ed” in the dropdown at the top, is the published text of *Walden* (1854) as edited by J. Lyndon Shanley for the Princeton University Press. As you move rightward, each panel shows a draft version from A to G. The inserted and deleted text in these panels indicates changes Thoreau made within a given version. If you mouse over the “n” next to the chapter title or over any of the paragraph numbers, you’ll see notes pop up that provide additional information.

Now head over to the [GitHub repository that houses the TEI files for the 18 chapters of *Walden*](https://github.com/milnegeneseo/fluid_text/tree/master/tei). Click on the file `05.xml` to see the contents of the file that contains all the information about “Solitude” that’s being represented in the fluid-text edition.

Download this file to your computer. You can do this by right-clicking the <kbd>Raw</kbd> button and saving the file to your computer. But why not use your command-line skills for this? Open a terminal window, `cd` to the location where you'd like to save the file, and type the following at the prompt:

```console    
    curl https://raw.githubusercontent.com/milnegeneseo/fluid_text/master/tei/05.xml > 05.xml
```

Now go to where you saved the file — whatever method you chose — and open it in VS Code. Next, open it in a browser such as Firefox, Chrome, Safari, or Edge. You won’t see the panels or the pop-ups or any of the features included in the fluid-text edition. All you’ll see is the same XML/TEI code.

Scroll through the code — on GitHub, in VS Code, or in your browser window - until you get to the first paragraph of “Solitude.”

Now take a moment to complete an assignment in which you try to identify what some of the different TEI tags are saying about the paragraph.

## Assignment: Fluid-text TEI

Look over the TEI file for the "Solitude" chapter that you downloaded from GitHub. It's chock full of markup, and it makes for pretty intimidating reading at first. Don't be scared off. Scroll down to the first paragraph. Compare what you see there with [the rendered text of the paragraph in Digital Thoreau's fluid-text edition of](http://digitalthoreau.org/walden/fluid/text/05.html) *[Walden](http://digitalthoreau.org/walden/fluid/text/05.html).* Then record some thoughts here about what the different tags mean. This exercise isn't about getting anything right. You're just seeing what you can figure out without having any expertise in this new language.

Record your thoughts by 11:59 p.m. on Wednesday, April 22.
