---
layout: post
title: "Bash Script that get rids of squiglies"
date:   2017-12-2 12:06:00
categories: script, bash, linux
comments: true
---

Here is a quick bash script that I use to get rid of those annoying temporary files. 

---
```
#Function for removing ‘~’ files
rm~() {
    case “$1” in
    “--dry-run”)
        find . -name “*~” -type f -printf “[dry-run] Removing file %p\n”
        ;;
    “”)
        find . -name “*~” -type f -printf “Removing file %p\n” -delete
        ;;
    *)
        echo “Unsupported option \`$1'. Did you mean --dry-run?”
        ;;
    esac
}

#End of function.
```

Paste the function inside your ~/.bashrc and invoke with rm~ . Have fun :)
