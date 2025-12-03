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

tracked untracked staged unstaged


## lab4

Summary
Congratulations, master of the multiverse! You've just completed your crash course in Git branch wizardry. Let's recap the incredible feats you've accomplished:

You created a hub for infinite possibilities (a new Git repository).
You opened a portal to an alternate reality (created a new branch).
You learned to jump between different dimensions (switch branches using git checkout or git switch).
You made groundbreaking discoveries in a parallel universe (committed changes in a separate branch).
You merged two realities, bringing your discoveries into the main timeline (merged branches).
Finally, you learned how to close dimensional portals you no longer need (delete branches).
These multiversal skills are crucial for any time-traveling developer. By using branches, you can:

Work on different features or bug fixes in parallel universes, without disrupting the main timeline.
Experiment with wild ideas in safe, alternate realities.
Collaborate with other dimension-hopping developers, each working in their own reality.
Keep your main timeline stable and glitch-free, only merging in new features when they're ready.
Happy dimension hopping, and may your merges always be conflict-free!

## lab5
Secure the Artifact and Document Your Findings
Tasks
Create a new branch called artifact-study from the master branch.
In the artifact-study branch, create a file named temporal-artifact.txt with a brief description of the artifact.
Update the README.md file to include a section about your ongoing artifact study.
Commit your changes in the artifact-study branch.
Merge the artifact-study branch back into master.
Requirements
All operations must be performed in the /home/labex/project/time-travel-hub repository.
The temporal-artifact.txt file must contain at least one line describing the artifact, you can use the following text: "A glowing orb that seems to distort time around it. Further study is needed to understand its full capabilities and potential risks."
The README.md file must have a new section titled "## Temporal Artifact Study" with at least one line of information.
Use meaningful commit messages for all your commits.
Ensure you're on the master branch after completing all operations.
The artifact-study branch should still exist after merging.

#### Summary
In this challenge, you've put your Git branch wizardry to the test in a high-stakes time travel scenario. You created a separate reality (branch) to study a powerful temporal artifact, documented your findings, and successfully merged this critical information back into the main timeline. By using Git branches, you were able to experiment safely without risking the integrity of the main timeline.

This exercise demonstrated the practical application of creating branches, making and committing changes, and merging branches. These skills are crucial for managing complex projects and collaborating with other developers, allowing you to work on features or experiments in isolation before integrating them into the main project.

By keeping the artifact-study branch after merging, you've maintained a record of this separate line of investigation. This can be useful for future reference or if you need to continue your study of the temporal artifact.

Remember, with great power comes great responsibility. Use your Git branch skills wisely as you continue your adventures through time and code!


## lab6
this command appends a new line to our "hello.txt" file. Let's understand the >> operator:  

`>` would overwrite the entire file with the new content.  
`>>` appends the new content to the end of the existing file, preserving the original content.  
So, after running this command, "hello.txt" will contain two lines:

>Bilkul sahi, bhai. git commit --amend sirf aur sirf LAST commit par apply hota hai.

#### Reverting a Commit
Sometimes, you make a commit and later realize it introduced a bug or you simply want to undo those changes. You might think of using git reset to go back in time and remove the commit. However, git reset can be destructive, especially if you've already pushed your changes or if others are working on the same branch. A safer and more collaborative way to undo changes is using git revert.

git revert creates a new commit that undoes the changes introduced by a specific commit. It doesn't erase the original commit from history; instead, it adds a new commit that effectively reverses the effects of the unwanted commit. This preserves the history and is much safer for shared repositories.


![alt text](image-1.png)

lets use amend cmd


