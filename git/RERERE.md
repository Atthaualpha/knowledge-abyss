# RERERE

*[:arrow_left: Go back to Git](./GIT.md)*

Reuse Recorded Resolution (rerere) is a feature that git allow as to use in order to make a bit more easy to deal with merge conflicts.

This feature when is enabled will record how the conflicts are resolved and the next time that the same conflict appears it will used the recorded resolution used the last time.

**To enable it use following commands**:

> `git config --global rerere.enabled true`

The next that a conflict shows up, in merge, rebase or cherry-pick, will record your decisions.


To removed the recorded resolutions you can delete the folder where they are stored. The folder is in the root of your repository in the path `.git/.rr-cache`, this can be done with `git rm -rf .git/rr-cache`