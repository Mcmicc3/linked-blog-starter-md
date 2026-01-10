UNDERSTANDING GITHUB
--------------------

[ Working Directory ]  →  [ Staging Area ]  →  [ Local Repository ]  →  [ GitHub ]
   (your files)             (selection)          (history)             (remote)

GITHUB STEPS
------------
git pull --rebase (Before you open Obsidian)
git add {., or whatever you want to push}
git commit -m "{Explain changes}"
git push
git reset   (If you want to erase commits and start over)

**On any other PC that hasn't been updated yet, run these commands**
- git config --global user.name "Mario Canales"
- git config --global user.email "mcmicc3@gmail.com"

**RULES FOR USING GIT ON ANY COMPUTER** 
When starting Obsidian, type git status,

If you see:
`Your branch is ahead of 'origin/main'`
→ **Push first**

If you see:
`Your branch is behind 'origin/main'`
→ **Pull first**

If clean → proceed.

NEXT STEPS
---------

If you want next steps, I recommend:

Setting up the Obsidian Git plugin safely (now that .deb is installed)

Adding a .gitignore tuned for Obsidian

Creating a “new computer checklist” so future setups take 5 minutes

Adding an i3 keybinding to open Obsidian instantly


RESOURCES
---------
https://chatgpt.com/g/g-p-691d352dab1481919d65e8ff32853ea6/c/6940910a-ff84-8331-b9dd-ced3710449fa