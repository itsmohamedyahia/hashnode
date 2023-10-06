---
title: "How to delete files in the terminal safely"
datePublished: Fri Oct 06 2023 16:46:30 GMT+0000 (Coordinated Universal Time)
cuid: clneu9bxe000i0ai5cr04go1z
slug: how-to-delete-files-in-the-terminal-safely
tags: tutorial, programming-blogs, terminal, cli, programming-tips

---

To mitigate the problem of deletion by mistake. Two options were introduced to the `rm` command

`-i` option shows an interactive prompt asking you if you want to delete that item, for several items or a folder it will ask for every file and folder if you want it to be deleted.

`-I` option is less intrusive and will ask only if you were to delete more than 3 files or a folder and it will give only one prompt for all.

Try it and tell me what you think.
