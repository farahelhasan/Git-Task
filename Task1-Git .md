# Git 

    Contents:
>- Introduction to Git
>- The Lifecycle of a File **[Git Stages]**
>- Example of Git Commands

## Introduction to Git
is a **Distributed Version Control** that tracks versions of  files. It is often used to control source code by programmers who are developing software collaboratively. It allows teams to collaborate efficiently while maintaining a history of changes.

### Key Features of Git: 
- **Version Control:**
   Tracks changes and allows reverting to previous versions. 
- **Collaboration:**
  Multiple developers can work on the same project.
 - **Branching & Merging:**
 Work on different features simultaneously. 
- **Distributed System:** 
Every developer has a full copy of the repository.

## The Lifecycle of a File **[Git Stages]**
A file in Git goes through **three main stages**:

 1. **Working Directory (Untracked/Modified)** 
The stage where a file is untracked by Git. 

 2. **Staging Area (Staged)** 
The stage where the file is added to Git's tracking system and prepared for the next commit.
using :
 `git add`
  
 3. **Committed (Versioned & Stored in Repository)** 
 The file is permanently saved in the local repository.
 using:
  `git commit`
  
**Example:**
```
>git add file.txt               # Moves the file to the Staging Area
>git commit -m"first commit"    # Moves it to the Committed stage
```
	

## Example of Git Commands
### 1. `git reset` 

The `git reset` command is used to move file back to previous states. Its like - Undo Changes.

**Common Uses:**
-   Unstage a file:
    ```
    >git reset <file_name>
    ```  
-   Undo the last commit (Keep changes in the working directory):
    
    ```
    >git reset --soft HEAD~1
    ```
    
-    Remove the last commit completely :
		```
		>git reset --hard HEAD~1
		```

### 2. `git cherry-pick` 

The `git cherry-pick` command allows you to copy or apply specific commits from one branch to another.

**Example:**

```
>git checkout target-branch     # Switch to the branch where you want to apply the commit
>git cherry-pick <commit-hash>  # Apply the selected commit
```


**Use Case:**  
You made a bug fix in a different branch and want to apply it to the main branch without merging everything.


### 3. `git rebase` 
Git **rebase** moves a branch to a new base commit, keeping a cleaner history.

**Example:**

```
>git checkout feature-branch
>git rebase main
```

This applies the changes from `feature-branch`  **on top of** the latest `main` branch.

**Rebase vs Merge:**
merge and rebase combine commits from two branch, but in different way. 
-   **Merge** keeps the history of branches and creates a new merge commit.
    
-   **Rebase** rewrites history, making it appear as if all changes happened sequentially.
    
![Rebase vs Merge](https://media.licdn.com/dms/image/v2/D5612AQGyC_mc4CnaAw/article-cover_image-shrink_720_1280/article-cover_image-shrink_720_1280/0/1677768475192?e=1746057600&v=beta&t=g_HAvOAvkPb8Ls_Bz9unp94xJRTlfPEdyCwcrkW3pqQ)

**Interactive Rebase:** Modify commit history with:

```
git rebase -i HEAD~3
```

This lets you **squash, edit, or drop commits** interactively.

