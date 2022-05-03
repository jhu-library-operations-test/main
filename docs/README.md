# Documentation

All documentation should be written within this [main repo](https://github.com/eclipse-pass/main),
or referenced here.  For example, please include links (with a small description) to
any relevant websites, external references, and other cloud storages (e.g. Google Docs).

## Components

| Component | Summary |
| --- | --- |
| Playground | A collection of small `hello-world` like applications written in the technologies being used with eclipse-pass. <ul><li>Repo: [/eclipse-pass/playground](https://github.com/eclipse-pass/playground)</li><li>Docs: [/docs/playground.md](/docs/playground.md)</li></ul> |

Learn more about the [code delivery pipeline](/docs/pipeline.md) as we go from
source code to deployed application.

## Troubleshooting

### Committer Email Address

For official committers, make sure that you configure all eclipse-pass
repos against your contributor email.

For example (please replace with your email)

```bash
git config user.email "jane.url@eclipse-foundation.org"
```

If you already have commits against a separate email address, then you
can rebase those commits and change the email

```bash
git rebase -i origin/main
```

This will show all commits

```bash
pick bb697d0 Migrate playground docs into main

# Rebase 8d61ffa..bb697d0 onto 8d61ffa (1 command)
#
# Commands:
# p, pick <commit> = use commit
# r, reword <commit> = use commit, but edit the commit message
# e, edit <commit> = use commit, but stop for amending
# s, squash <commit> = use commit, but meld into previous commit
# f, fixup <commit> = like "squash", but discard this commit's log message
# x, exec <command> = run command (the rest of the line) using shell
# b, break = stop here (continue rebase later with 'git rebase --continue')
# d, drop <commit> = remove commit
# l, label <label> = label current HEAD with a name
# t, reset <label> = reset HEAD to a label
# m, merge [-C <commit> | -c <commit>] <label> [# <oneline>]
# .       create a merge commit using the original merge commit's
# .       message (or the oneline, if no original merge commit was
# .       specified). Use -c <commit> to reword the commit message.
#
# These lines can be re-ordered; they are executed from top to bottom.
#
# If you remove a line here THAT COMMIT WILL BE LOST.
#
# However, if you remove everything, the rebase will be aborted.
#
```

Change `pick` to `edit`.  In the example above

```bash
edit bb697d0 Migrate playground docs into main
```

And then for each commit change the email (please replace with your email).

```bash
git commit --amend --no-edit --author="Jane Url <jane.url@eclipse-foundation.org>"
git rebase --continue
```

And finally, push your changes

```bash
git push --force-with-lease
```