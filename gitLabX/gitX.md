## Git

### lab1


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