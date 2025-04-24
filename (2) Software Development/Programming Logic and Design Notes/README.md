
---
# 🧱 Project Blueprint Template (SDLC)

> [!info] **Purpose:** Use this template to plan, design, implement, test, and document every practice project as a professional software endeavor.

---

## 1. 🗂️ Planning & Requirements
- **Project Name:** 📌
- **Description:** 📝 Short summary of what it does
- **Goals & Success Criteria:**
  - Feature 1
  - Feature 2
  - Feature 3

### 1.1 👤 User Stories
- As a user, I want to ... so that ...
- As an admin, I need ... in order to ...
> [!tip] Write at least 3 user stories to capture core functionality.

### 1.2 🛠 Tech Stack & Tools
- **Languages & Frameworks:** JavaScript, HTML, CSS, (React later)
- **Storage:** localStorage / REST API
- **Dev Tools:** Obsidian, VSCode, Git/GitHub, Browser DevTools

---

## 2. 🎨 Design

### 2.1 🖼 Wireframes / Mockups

![[wireframe.png]]

### 2.2 🧬 Data Model

```js
// Example: To-Do Task object
type Task = {
  id: string;
  text: string;
  completed: boolean;
  createdAt: string;
}

```

### 2.3 🧩 Component / Module Breakdown
- **UI Modules:** InputForm, ItemList, Item
- **Logic Modules:** storage.js, renderer.js, events.js

---

## 3. 🏗 Setup & Architecture

```bash
# Initialize your project
git init
npm init -y
```

### Folder Structure

```text
📁 todo-app/
├─ index.html
├─ css/
│  └─ styles.css
├─ js/
│  ├─ app.js       # Main logic
│  ├─ storage.js   # localStorage wrapper
│  └─ ui.js        # UI rendering
└─ README.md
```

- **.gitignore:** `node_modules/`, `dist/`, `.DS_Store`
- **Note location in vault:** `Templates/Project Blueprint Template`

---

## 4. 🧪 Development (Implementation)

Work in **short sprints** (30–60 min) with clearly defined goals.

```markdown
- [ ] Sprint 1: Render static list
- [ ] Sprint 2: Add & save tasks
- [ ] Sprint 3: Toggle complete state
- [ ] Sprint 4: Delete tasks & persist
- [ ] Sprint 5: Style & polish UI
```

> [!warning] Commit after each sprint. Use clear commit messages.

---

## 5. 🧫 Testing

### Manual Tests
- ✅ Add tasks
- ✅ Mark complete/uncomplete
- ✅ Delete tasks
- ✅ Data persists on reload

### Optional: Unit Testing (e.g. with Jest)
- storage.js functions

---

## 6. 🚀 Deployment

### Options:
- **Static Site:** GitHub Pages / Vercel

```bash
npm install -g serve
serve .
```

---

## 7. 📄 Documentation

- **README.md**
    - Project overview
    - Run instructions
    - Features
    - Known issues / TODOs
- **CHANGELOG.md** (optional)
- **In-code comments:** for non-obvious logic

---

## 8. 🔍 Maintenance & Review
- Track issues/enhancements in GitHub
- Plan future features (e.g., Edit, Filter)
- **Post-mortem Note**
    - ✅ What went well?
    - ❌ What was challenging?
    - 🔄 Improvements for next time.

---

> [!note] **Use in Obsidian:**
> 
> - Save this as `Project Blueprint Template.md` in your vault.
>     
> - Use with the **Templates plugin** to quickly insert into new notes.
>     
> - Customize icons, tags, or fields per project.
>     

---

## 📐 Example: To-Do App Breakdown

### 1. Planning:
- _Project_: To-Do App
- _Goals_: Add, complete, delete, persist tasks
- _Success Criteria_: 10+ tasks added, states saved on reload

### 2. Design:
- _Wireframe_: Input at top, list in middle, filters at bottom
- _Data Model_:

```js
{
  id: 'uuid-v4',
  text: 'Buy milk',
  completed: false,
  createdAt: '2025-04-23T14:00:00Z'
}
```

### 3. Setup:
- Folder as above
- `git init`, `.gitignore`, scaffold files

### 4. Development:
- S1: Static list render
- S2: Add task + storage
- S3: Mark complete/delete
- S4: Persist/reload

### 5. Testing:
- Manual testing per user story
- Optional Jest tests for storage

### 6. Deployment:
- GitHub Pages (gh-pages branch)

### 7. Documentation:
- Fill in `README.md` with all core info

### 8. Maintenance:
- Post-mortem note
- Add “Edit task” or filter features later

---

## 🏁 Next Steps
1. **Pick a project** (e.g. To-Do List)
2. **Duplicate this template** into your vault or repo
3. **Start with Planning** – write stories, goals
4. **Wireframe your UI**
5. **Begin first sprint!**

---
