# **Feature Branch Workflow Guide**

**A guide to the standard development workflow using Git and platforms like GitHub/GitLab.**

## 1. Purpose

This document aims to standardize the development process for new features and bug fixes. Adhering to this workflow provides several core benefits:

* **Clarity & Traceability:** Every code change is linked to a specific requirement (an Issue), making it easy to understand *why* a change was made.
* **Quality Assurance:** The `main` branch is always kept in a stable, deployable state. All changes must pass a review and testing process before integration.
* **Effective Team Collaboration:** The process creates a consistent workflow, enabling team members to collaborate easily, review code, and minimize merge conflicts.
* **Fostering Professional Habits:** It cultivates an organized, responsible, and industry-standard way of working.

## 2. Key Concepts

* **`main` Branch:** The "Source of Truth." This branch contains the official, most stable version of the project's codebase. **Never commit directly to the `main` branch.**
* **Issue:** The "Blueprint." This defines a unit of work to be done (a new feature, a bug to be fixed).
* **`feature`/`bugfix` Branch:** The "Isolated Development Environment." Each Issue is developed in its own separate branch, completely isolated from `main`.
* **Pull Request (PR):** The "Quality Gate." This is a formal request to merge code from a feature branch into the `main` branch and is where the code review process takes place.

## 3. Detailed Workflow

### Step 1: Define Work with an Issue

* **Purpose:** To clearly define the requirements, scope, and acceptance criteria for a task.
* **Actions:**
    1.  On GitHub/GitLab, navigate to the **"Issues"** tab.
    2.  Create a **"New Issue"**.
    3.  **Title:** Use a clear, prefixed title for categorization, e.g., `[Feature] User Login`, `[Bug] Fix button alignment on homepage`.
    4.  **Description:** Describe the task in as much detail as possible, including:
        * An overview of the feature/bug.
        * Steps to reproduce (for bugs).
        * **Acceptance Criteria:** Specific conditions that must be met for the task to be considered complete.
* **Note:** Remember the Issue number (e.g., `#12`).

### Step 2: Create a Working Branch

* **Purpose:** To create an isolated environment for development without affecting the `main` branch.
* **Actions (on your local machine):**
    1.  Always start from a clean and updated `main` branch:
        ```bash
        git checkout main
        git pull origin main
        ```
    2.  Create a new branch from `main` and switch to it. Use a descriptive naming convention:
        ```bash
        # Syntax: git checkout -b <branch-name>
        # Convention: type/issue-id-short-description
        git checkout -b feature/12-user-login
        ```
### Step 3: Develop and Commit

* **Purpose:** To write the code that fulfills the requirements defined in the Issue.
* **Actions:**
    1.  Implement the required code changes on your new feature branch.
    2.  **Commit frequently!** Each time you complete a small, logical chunk of work, create a commit.
        ```bash
        git add .
        git commit -m "feat: Add user entity and repository" 
        ```
* **Key Points:**
    * **Write meaningful commit messages:** The message should clearly describe the change. (Advanced: Look into `Conventional Commits`).
    * **Push your branch regularly:** This backs up your work and allows others (if any) to see your progress.
        ```bash
        git push origin feature/12-user-login
        ```

### Step 4: Self-Review and Sync

* **Purpose:** To ensure your code works correctly and is up-to-date with the latest project changes before requesting a review.
* **Actions:**
    1.  **Run all tests** (unit tests, integration tests).
    2.  **Manually test** your new functionality.
    3.  **Sync with `main`** to resolve any potential conflicts early:
        ```bash
        git fetch origin # Get the latest info from the remote
        git merge origin/main # Merge the latest changes from main into your branch
        ```

### Step 5: Create a Pull Request (PR)

* **Purpose:** To formally propose the integration of your code into the `main` branch and to initiate the review process.
* **Actions (on GitHub/GitLab):**
    1.  Navigate to your repository. You will likely see a prompt to create a PR for your recently pushed branch.
    2.  Fill out the PR form:
        * **Title:** A clear title that summarizes the changes.
        * **Description:**
            * Briefly describe what the PR does.
            * **Link the Issue:** Use keywords like `Closes #12` or `Fixes #12`. When the PR is merged, this will automatically close the linked Issue.
            * Add testing notes if necessary.
    3.  Assign reviewers. If you are working solo, assign yourself.

### Step 6: Review, Discuss, and Refine

* **Purpose:** To ensure code quality, share knowledge, and find the best possible solution.
* **Actions:**
    1.  The reviewer(s) (or yourself) will go to the **"Files changed"** tab in the PR to see the code.
    2.  Leave comments directly on lines of code for questions or improvement suggestions.
    3.  If changes are requested, the author goes back to **Step 3**: codes the changes on the same feature branch and pushes the new commits. The PR will update automatically.
    4.  This cycle repeats until all reviewers have approved the changes.

### Step 7: Merge and Clean Up

* **Purpose:** To integrate the approved code into `main` and keep the repository tidy.
* **Actions:**
    1.  Once the PR is approved and all automated checks (CI) have passed (are green):
    2.  Click the **"Merge pull request"** button.
    3.  Confirm the merge.
    4.  Click the **"Delete branch"** button to remove the feature branch from the remote repository, as its job is done.
    5.  Update your local `main` branch:
        ```bash
        git checkout main
        git pull origin main
        ```

## 4. Workflow Summary Diagram

`Start` -> `Create Issue` -> `Create Branch` -> `(Code -> Commit -> Push)` -> `Create PR` -> `(Review -> Refine)` -> `Merge PR` -> `Delete Branch` -> `End`