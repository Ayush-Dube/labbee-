## Git

## lab1


this output tells us that hello.py is now in the staging area, ready to be committed.

Why do we need a staging area? Imagine you're packing for a trip. The staging area is like your suitcase - you can add items (changes) to it, remove items if you change your mind, and when you're happy with everything in the suitcase, you zip it up (make a commit). This allows you to carefully curate what goes into each commit, making your project history more organized and meaningful.

#### Ignoring Files with .gitignore

Ignoring Files with .gitignore

#### git diff

```
diff --git a/hello.py b/hello.py
index ed51d3f..1385fe3 100644
--- a/hello.py
+++ b/hello.py
@@ -1 +1 @@
-print('Hello, Git!')
+print('Hello, Git! Welcome to the staging area.')

```


## lab2

- git add filename
- .gitignore file
- `echo "print('Hello, Git!')" > hello.py`
- `echo "print('Hello, Git! Welcome to the staging area.')" > hello.py`
- git diff

- Sometimes, you might add a file to the staging area and then change your mind. Git allows you to unstage changes easily.

- Now, let's say we've changed our mind and don't want to include these changes in our next commit. We can unstage the file using the git restore command:
 
- `git restore --staged hello.py`

1. How to add files to the staging area using git add
2. How to ignore files you don't want to track using .gitignore
3. How to view changes in your files before committing with git diff
4. How to unstage changes using git restore --staged


## lab3



❓❓❓
`echo -e 'print("Initializing Chrono-Gadget...")\nprint("Warning: Temporal flux detected!")\nprint("Calibrating time circuits...")\nprint("Ready for time travel!")' > chrono_gadget.py
`

Congratulations, master of temporal inspection! You've successfully prepared your chrono-gadget and demonstrated your ability to review its contents in the staging area before embarking on your time-travel adventure. In this challenge, you've shown proficiency in:

1. Initializing a new Git repository for your time travel preparations.
2. Creating a file with essential information for your journey.
3. Using the Git staging area to prepare changes for commit.
4. Employing git diff --staged to review changes in the staging area.  

This skill of reviewing staged changes is crucial for any serious time traveler. By mastering the `git diff --staged` command, you've gained the ability to carefully inspect your temporal payload before each leap through time. This meticulous approach ensures that you're always aware of exactly what changes you're about to commit to the timeline.

Remember, a well-inspected staging area is the key to successful chrono-exploration. As you continue your journey through the Git-time continuum, this reviewing skill will prove invaluable. It will help you maintain a clean and organized timeline, catch potential temporal anomalies before they cause paradoxes, and always know exactly what changes you're about to cement into the fabric of space-time.

Keep exploring, keep staging, and most importantly, keep reviewing! The future (and past) of code awaits your carefully inspected commits. Safe travels, Chrono-Coder!   

#### Tracked and Staged are different things
