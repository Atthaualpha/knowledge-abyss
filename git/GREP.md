# Grep

*[:arrow_left: Go back to Git](./GIT.md)*


Grep is a useful tool to search specific words that match in your files.

The most simple way is just specify the word you want to search.

> `git grep foo`

If you want to see the lines where the match were found just add `-n` before the word you are searching for.

> `git grep -n foo`

## Formatting the output

Some useful options to view the output more readable is adding `--break` to add breaking lines and `--heading` to separate blocks of text.

> `git grep --break --heading foo`
