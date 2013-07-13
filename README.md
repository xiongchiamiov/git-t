Using tmux to make git better.

# Rationale

Ever wanted to see a *full* comparison of two branches - that is, the
difference A and B, with a clear view of which commits are in each branch?
`git-tlog` uses tmux to view a comparison log in two columns: you get the order
you specified on the left, and the reverse order on the right.

Here's the [master..client-side] and [client-side..master] comparison for [one
of my repos][Jellylorum]:

    [$]> git-tlog --oneline master client-side

![git-tlog example screenshot](git-tlog.png)

[master..client-side]: https://github.com/xiongchiamiov/jellylorum/compare/master...client-side
[client-side..master]: https://github.com/xiongchiamiov/jellylorum/compare/client-side...master
[Jellylorum]: https://github.com/xiongchiamiov/jellylorum/

Already using tmux?  No problem - `git-tlog` identifies that and splits inside
your current pane:

![git-tlog example screenshot](git-tlog-2.png)

`git-tdiff` is pretty much the same thing, but for `git-diff`.  The other major
difference is that it uses [three dots], showing you what has changed on each
branch since their most-recent common commit.

[three dots]: http://matthew-brett.github.io/pydagogue/git_diff_dots.html#diff-with-three-dots

