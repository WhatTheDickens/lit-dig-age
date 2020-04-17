## Why TEI?

You came here (if you've been reading the module pages in order) from a page that ended with the words, "We'll consider those questions on the next page."

Of course, you're not looking at a page. You're looking at a screen. (Unless you've printed the screen contents to paper. But why would you?) So you didn't go to the *next* anything. You stayed right where you were, looking at the same two-dimensional surface. The word *page* in this context is a hold-over from an older vocabulary belonging to a different reading experience in which you do, in fact, advance from one two-dimensional surface to another. It belongs to the vocabulary that was being discussed a moment ago, when there were different words on your screen: words like *title*, *line*, and *stanza*.

The human mind is very adept at understanding terms flexibly, adjusting how a term is understood to fit the circumstances. You're fine with "next page" sometimes meaning "really, next page" and sometimes meaning "a new set of words on your screen," and you know when you're dealing with each.

Computers aren't so good at this.

If we want to describe what's happening in a text so that a computer can understand what we've said, we need a precise metalanguage and we need to use it with consistency. TEI meets these needs.

## Machines that read

What's the value in describing texts so that machines can read our descriptions? A full answer to that question would take up a lot of — pages? screens? (take your pick) — but here's a partial one. For one thing, a machine-readable description enables a computer program to *display* the marked-up text in multiple ways. We're not locked into any one way of displaying the text. The program simply needs to understand our metalanguage — TEI in this case — and follow whatever instructions we've given it for *transforming* the contents into a display-oriented metalanguage that a browser will understand, such as HTML.

For another thing, in adding all this descriptive markup to a text, we make it possible for a computer program to traverse the document systematically looking for certain tags, and to pull out particular tags for analysis.

We can appreciate both these advantages by looking back at the fluid text of *Walden*.

Head over to the ["Solitude" chapter of *Walden: A Fluid-Text Edition*](http://digitalthoreau.org/walden/fluid/text/05.html) and click the "New Version" button (upper left) until it turns gray. Scroll to the right, and you should see a panel for each of the seven manuscript drafts of *Walden*. The leftmost panel, showing "Princeton_Ed" in the dropdown at the top, is the published text of *Walden* (1854) as edited by J. Lyndon Shanley for the Princeton University Press. As you move rightward, each panel shows a draft version from A to G. The inserted and deleted text in these panels indicates changes Thoreau made within a given version. If you mouse over the "n" next to the chapter title or over any of the paragraph numbers, you'll see notes pop up that provide additional information.

Now head over to the [GitHub repository that houses the TEI files for the 18 chapters of *Walden*](https://github.com/milnegeneseo/fluid_text/tree/master/tei). Click on the file `05.xml` to see the contents of the file that contains all the information about "Solitude" that's being represented in the fluid-text edition.

Download this file to your computer and open it in VS Code. Now open it in a browser such as Firefox, Chrome, Safari, or Edge. You won't see the panels or the pop-ups or any of the features included in the fluid-text edition. All you'll see is the same XML/TEI code.

Scroll through the code — on GitHub, in VS Code, or in your browser window - until you get to the first paragraph of "Solitude." 

Now take a moment to complete an assignment in which you try to identify what some of the different TEI tags are saying about the paragraph.