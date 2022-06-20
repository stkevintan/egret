---
{"dg-publish":true,"permalink":"/git/about-eol/","dgHomeLink":true,"dgPassFrontmatter":false}
---


## autocrlf
> If you’re programming on Windows and working with people who are not (or vice-versa), you’ll probably run into line-ending issues at some point. This is because Windows uses both a carriage-return character and a linefeed character for newlines in its files, whereas macOS and Linux systems use only the linefeed character. This is a subtle but incredibly annoying fact of cross-platform work; many editors on Windows silently replace existing LF-style line endings with CRLF, or insert both line-ending characters when the user hits the enter key.

1. convert to platform specific eol (windows: CRLF, linux/mac: LF) when checkout  &&  convert to LF on commit:
```shell
git config --global core.autocrlf true
```

2. keep as-is when checkout && convert to LF on commit:
```shell
git config --global core.autocrlf input
```
3. keep as-is both in checkout and commit (turn off):
```shell
git config --global core.autocrlf false
```

### refresh local
If you already pulled the code to local file system, then modified the `autocrlf` setting, you can try the following steps to refresh the existing files:

> [!NOTE]
> Consider stashing your changes before do it! 

```shell
git rm --cached -r .
git reset --hard
```
