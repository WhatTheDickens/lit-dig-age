# Simple pattern searching from the command line

We've seen that Voyant produces some highly sophisticated analytics on a text. We can also do some simple pattern searching right from the command line with tools like `wc` and `grep`. Here are some searches we can do.

To begin, make sure you're in the folder that has your `walden.txt` file and your `Walden_in_Chapters` folder.

## Count the words in *Walden*

`$  grep -Eo '\b\w+\b' walden.txt | wc -l`

## Many words in *Walden* are used more than once. How many unique words are there?

`$ grep -Eo '\b\w+\b' walden.txt | sort -uf | wc -l`

## Let's print these words to a file

`$ grep -Eo '\b\w+\b' walden.txt | sort -uf > walden_words.txt`

## Find all occurrences of "read" and highlight them in red.

`$ grep -E --color=always 'read' walden.txt`

Too much information!

## Let's narrow to "read" as a word.

`$ grep -E --color=always '\bread\b' walden.txt`

## But what about "reader(s)" and "reading"? And what about, say, "Reading"?

`$ grep -E --color=always '\b(R|r)ead\b|\b(R|r)eaders?\b|\b(R|r)eading\b' walden.txt`

## Do the same showing line numbers, so we can find some particular occurrence.

`$ grep -En --color=always '\b(R|r)ead\b|\b(R|r)eaders?\b|\b(R|r)eading\b' walden.txt`

## Let's do some counting.

`$ grep -Eo '\b(R|r)ead\b|\b(R|r)eaders?\b|\b(R|r)eading\b' walden.txt | wc -l`

## Print the 12-letter words in *Walden*.

`$ grep -Eo '\b\w{12}\b' walden.txt`

## Count them.

`$ grep -Eo '\b\w{12}\b' walden.txt | wc -l`

## How many words that are 14 letters or longer?

`$ grep -Eo '\b\w{14,}\b' walden.txt | wc -l`

## 15 letters or longer?

`$ grep -Eo '\b\w{15,}\b' walden.txt | wc -l`

## 16 letters or longer?

`$ grep -Eo '\b\w{16,}\b' walden.txt | wc -l`

## What are the 16-or-longer-letter words?

`$ grep -Eo '\b\w{16,}\b' walden.txt`

## Are there any one-word sentences in *Walden*?

[Walter Harding says](https://commons.digitalthoreau.org/walden/the-ponds/the-ponds-18-34/#comment-27) that "Sky water" is the shortest sentence in *Walden*. Is he right?

`$ grep -Eon '\.\s\w+[\.|?|!]' walden.txt`

## Let's do some comparing across chapters

Make sure you're in the directory that *contains* the directory `Walden_in_Chapters`.

### Occurrences of "read".

`$ grep -Ern --color=always 'read' Walden_in_Chapters`

### Occurrences of "read" and related words.

$ `grep -Ern --color=always '\b(R|r)ead\b|\b(R|r)eaders?\b|\b(R|r)eading\b' Walden_in_Chapters`

### Occurrences of "I"

`$ grep -Ern --color=always '\bI\b' Walden_in_Chapters`