**Closes #[issue_number]**

---

### 🎯 Summary
**[Required]**
***Why this matters:*** *This is your "elevator pitch." It must immediately answer: "What does this PR do, and why?" The reviewer reads this first to get oriented.*

---

### 🧪 How to Test
**[Required for any functional or UI changes]**
***Why this matters:*** *This is the most important section for the reviewer. It respects their time by providing a clear script to verify your work. Without this, you are shifting the burden of figuring out how to test onto the reviewer.*

*Provide a clear, numbered list of steps:*
1.
2.
3.
*Expected Result:*

---

### 📸 Evidence & Demo
**[Required for UI changes]**
***Why this matters:*** *A picture is worth a thousand words. For any visual change, this provides undeniable proof that your solution works and looks as expected.*

**Before:**
*(Screenshot or GIF)*

**After:**
*(Screenshot or GIF)*

---

### 📖 Key Changes
**[Optional, but Recommended for non-trivial PRs]**
***Why this matters:*** *Provides a quick, scannable overview of the important changes. Helps the reviewer know where to focus their attention.*

- Updated `[Component Name]` to handle new state.
- Added new service `[Service Name]` for API calls.
- Modified `[Configuration File]` to include new variables.

---

### 🧠 Technical Approach & Trade-offs
**[Optional - Use for complex changes or new architecture]**
***Why this matters:*** *This section demonstrates your technical diligence. It explains your thought process, why you chose this specific solution, and what alternatives you considered. It is a crucial piece of technical documentation for the future.*

- **Approach:** *[Describe your technical solution]*
- **Trade-offs:** *[Explain other options you considered and why you didn't choose them]*

---

### 🧐 Notes for Reviewer / Questions
**[Optional]**
***Why this matters:*** *This turns the review into a dialogue. Use this to guide the reviewer's attention to specific areas you are unsure about or want a second opinion on.*

- I'm not sure if the error handling in `[File Name]` is robust enough. Could you please take a close look?
- Should we add a loading spinner for this action?

---

### ✅ Pre-Merge Checklist
**[Recommended as a team standard]**
***Why this matters:*** *This is a final safety check for you, the author. It ensures you have done your due diligence before handing off the work.*

- [ ] I have self-reviewed my own code.
- [ ] My PR is small and focused on a single issue.
- [ ] I have run the test suite locally and all tests have passed.
- [ ] I have ensured no sensitive information (keys, passwords) is committed.