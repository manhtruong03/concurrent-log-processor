---
name: "📐 Template issue"
about: Create a new issue with template.
title: '[Type]: '
labels: ''
assignees: ''

---

### 📝 Description
**[Required]**
***Why this matters:*** *This section clearly defines the work. Use the appropriate format below based on the issue type.*

**For a Bug (Problem Description):**
State what is wrong, what you expected to happen, and the negative impact.
> *Example: The "Upload Picture" button on the user profile page shows a success message, but the new picture never appears. This prevents users from personalizing their profiles.*

**For a Feature (User Story):**
Follow the "As a..., I want to..., so that..." format.
> *Example: **As a** User, **I want to** reset my password via email **so that** I can regain access to my account if I forget my password.*

---

### Reproduction Steps
**[Required for Bugs]**
***Why this matters:*** *This is the most critical part of a bug report. A bug that cannot be reliably reproduced cannot be fixed.*

1. Navigate to the `/profile` page.
2. Click the "Edit Profile" button.
3. Click "Upload Picture" and select a valid JPG file.
4. **Observe:** A "Success!" message appears, but the profile picture does not update.

---

### ✅ Acceptance Criteria
**[Required]**
***Why this matters:*** *This is the contract that defines "done." It makes testing objective and eliminates misunderstandings.*

- [ ] When the user successfully resets their password, they are redirected to the login page.
- [ ] An email with a unique password reset link is sent to the user's registered email address.
- [ ] If the email address does not exist in the system, a generic message "If an account with that email exists, a reset link has been sent" is shown.

---

### 🖥️ Environment
**[Required for Bugs]**
***Why this matters:*** *Bugs can be specific to a certain browser, operating system, or application version. This information is vital for debugging.*

- **OS:** [e.g., macOS, Windows 11]
- **Browser:** [e.g., Chrome 125, Firefox 124]
- **App Version:** [e.g., v1.2.3, Staging environment]

---

### 💬 Context & Background
**[Optional, but Recommended for Features]**
***Why this matters:*** *This justifies the issue's existence. It answers, "Why should we spend time on this?" and aligns the team on the business or user value.*

> *Example: Regaining account access is a fundamental user journey. Lacking this feature increases user frustration and support ticket volume.*

---

### 🖼️ References & Mockups
**[Optional, but Recommended for anything visual]**
***Why this matters:*** *Visuals eliminate ambiguity. Attach anything that helps visualize the task.*

- Link to Figma designs: [link]
- Screenshot of the bug: [file]
- Video/GIF of the incorrect behavior: [file]

---

### 💡 Technical Notes / Implementation Suggestions
**[Optional]**
***Why this matters:*** *A space for technical guidance. This can significantly speed up development by providing a starting point for the implementer.*

- This might be related to the `ImageUploaderService.js` file.
- We should consider using the `express-validator` library for input validation on the server.
- The API endpoint `/api/users/reset-password` will need to be created.

---
### 🏷️ Labels
**[Required]**
- `type: bug` / `type: feature`
- `priority: high` / `priority: medium` / `priority: low`
- *[Other relevant labels like `area: frontend`, `area: auth`]*