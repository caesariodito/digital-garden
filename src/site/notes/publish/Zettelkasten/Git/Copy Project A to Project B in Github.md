---
{"dg-publish":true,"dg-path":"Zettelkasten/Git/Copy Project A to Project B in Github.md","permalink":"/zettelkasten/git/copy-project-a-to-project-b-in-github/","dgHomeLink":true,"dgShowBacklinks":true,"dgShowLocalGraph":true,"dgShowInlineTitle":true,"dgShowFileTree":true,"dgEnableSearch":true,"dgShowToc":true,"dgLinkPreview":true,"dgShowTags":true,"noteIcon":1}
---


created:: 2023-09-24T17:25:51
up:: [[publish/Zettelkasten/Git/Github\|Github]]
tags:: #🌱 #git #hacks 

- If you want to copy project A to project B in different repository, you need to:
    - push both of them
    - go to project B git repository
    - add remote with project A url
    - I suggest creating a new branch so it safer to manage conflicts
    - git fetch, pull, and merge with:
    - `git pull upstream-smthin newbranch --allow-unrelated-histories`
    - and resolve conflicts if exists

## Related:

- [[publish/Zettelkasten/Git/Github\|Github]]
- [[publish/Zettelkasten/Git/Git\|Git]]

---
# Resources

- <% tp.file.cursor(4) %>