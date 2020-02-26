# Simple pattern searching from the command line

We've seen that Voyant produces some highly sophisticated analytics on a text. We can also do some simple pattern searching right from the command line with tools like `wc` and `grep`. Here are some searches we can do.

To begin, make sure you're in the folder that has your `walden.txt` file and your `Walden_in_Chapters` folder.

## Count the words in *Walden*

`$  grep -Eo '\b\w+\b' walden.txt | wc -l`

## Count the number of unique words in *Walden*

## Many words in *Walden* are used more than once. How many unique words are there?

`$ grep -Eo '\b\w+\b' walden.txt | sort -uf | wc -l`

## Let's print these words to a file

`$ grep -Eo '\b\w+\b' walden.txt | sort -uf | wc -l > walden_words.txt`

## Find all occurrences of "pond" and highlight them in red.

`$ grep -E --color=always 'pond' walden.txt`

## Do the same showing line numbers, so we can find some particular occurrence.

`$ grep -En --color=always 'pond' walden.txt`

## Count occurrences of "Pond" and "pond".

`$ grep -Eo '(P|p)ond' walden.txt | wc -l`

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

### Occurrences of "pond"

`$ grep -Ern --color=always 'pond' Walden_in_Chapters`

### Occurrences of "I"

`$ grep -Ern --color=always '\bI\b' Walden_in_Chapters`