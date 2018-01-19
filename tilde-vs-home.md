# ~ vs. $home in bash
## tags
#bash #script

## explanation
While writing bash scripts I've noticed the `$home` variable being used instead of `~` . to reference the user's home directory. It turns out that `~` is just being expanded by the terminal into the `$home` variable anyway. Because of this, it appears to be more robust to use `$home` in scripts as it's not guaranteed the tilde will be properly expanded (even though it will be in most cases).

## sources
https://stackoverflow.com/questions/11587343/difference-between-home-and-tilde
http://pubs.opengroup.org/onlinepubs/9699919799/utilities/V3_chap02.html#tag_18_06_01
