## Commits
```
56b101c (HEAD -> master, origin/master, origin/HEAD) Update StatHat.cs to test 'git add' behavior (1)
8f83c79 Use '* text' in .gitattributes
e98cce1 Update StatHat.cs to test 'git add' behavior
4231832 Use '* text=auto' in .gitattributes
f932e60 Add '* -text' .gitattributes + CRLF file StatHat.cs
34ae17a Initial commit
```

Each time the default `.gitattributes` setting changed, I modified `StatHat.cs` and then ran `git add`. These are the `git ls-files` results.

## `* -text` (unset)
<https://git-scm.com/docs/gitattributes#Documentation/gitattributes.txt-Set-1>

This is _sort of_ similar to "[unspecified](https://git-scm.com/docs/gitattributes#Documentation/gitattributes.txt-Unspecified)", but unspecified will honor `.gitconfig`'s `core.autocrlf` setting.
```diff
 AlanLaptop% git switch --detach f932e60 && git ls-files --eol
 HEAD is now at f932e60 Add '* -text' .gitattributes + CRLF file StatHat.cs
 i/lf    w/lf    attr/-text              .gitattributes
 i/lf    w/lf    attr/-text              LICENSE
@@ "git add" takes the bytes from the file as they are @@
 i/crlf  w/crlf  attr/-text              StatHat.cs
```

## `* text=auto`
<https://git-scm.com/docs/gitattributes#Documentation/gitattributes.txt-Settostringvalueauto>
```diff
 AlanLaptop% git switch --detach e98cce1 && git ls-files --eol
 Previous HEAD position was f932e60 Add '* -text' .gitattributes + CRLF file StatHat.cs
 HEAD is now at e98cce1 Update StatHat.cs to test 'git add' behavior
 i/lf    w/lf    attr/text=auto          .gitattributes
 i/lf    w/lf    attr/text=auto          LICENSE
@@ "git add" makes best guess, but won't overstep index @@
 i/crlf  w/crlf  attr/text=auto          StatHat.cs
```

## `* text` (set)
<https://git-scm.com/docs/gitattributes#Documentation/gitattributes.txt-Set-1>
```diff
 AlanLaptop% git switch master && git ls-files --eol
 Previous HEAD position was e98cce1 Update StatHat.cs to test 'git add' behavior
 Switched to branch 'master'
 Your branch is up to date with 'origin/master'.
 i/lf    w/lf    attr/text               .gitattributes
 i/lf    w/lf    attr/text               LICENSE
@@ "git add" renormalizes to LF automatically @@
-i/crlf  w/crlf  attr/text               StatHat.cs
+i/lf    w/lf    attr/text               StatHat.cs
```
