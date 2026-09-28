## Commits
```
56b101c (HEAD -> master, origin/master, origin/HEAD) Update StatHat.cs to test 'git add' behavior (1)
8f83c79 Use '* text' in .gitattributes
e98cce1 Update StatHat.cs to test 'git add' behavior
4231832 Use '* text=auto' in .gitattributes
f932e60 Add '* -text' .gitattributes + CRLF file StatHat.cs
34ae17a Initial commit
```

## `* -text`
```diff
 AlanLaptop% git switch --detach f932e60 && git ls-files --eol
 HEAD is now at f932e60 Add '* -text' .gitattributes + CRLF file StatHat.cs
 i/lf    w/lf    attr/-text              .gitattributes
 i/lf    w/lf    attr/-text              LICENSE
@@ "git add" uses core.autocrlf setting @@
 i/crlf  w/crlf  attr/-text              StatHat.cs
```

## `* text=auto`
```diff
 AlanLaptop% git switch --detach e98cce1 && git ls-files --eol
 Previous HEAD position was f932e60 Add '* -text' .gitattributes + CRLF file StatHat.cs
 HEAD is now at e98cce1 Update StatHat.cs to test 'git add' behavior
 i/lf    w/lf    attr/text=auto          .gitattributes
 i/lf    w/lf    attr/text=auto          LICENSE
@@ "git add" makes best guess, but won't overstep index @@
 i/crlf  w/crlf  attr/text=auto          StatHat.cs
```

## `* text`
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
