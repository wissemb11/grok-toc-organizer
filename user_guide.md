<!-- Path: /user_guide.md -->
<!-- Created: 2025-03-24 -->
<!-- Last Updated: 2025-03-27 00:23:00 -->

# User Guide: Managing Your Projects with a Table of Contents (TOC) System

## Table of Contents
- [User Guide: Managing Your Projects with a Table of Contents (TOC) System](#user-guide-managing-your-projects-with-a-table-of-contents-toc-system)
  - [Table of Contents](#table-of-contents)
  - [What You Need](#what-you-need)
    - [Example `starting_point.md`](#example-starting_pointmd)
  - [Initializing the TOC: All Cases](#initializing-the-toc-all-cases)
    - [1. Initial TOC Loading via `starting_point.md`](#1-initial-toc-loading-via-starting_pointmd)
    - [2. Manual TOC Setup](#2-manual-toc-setup)
    - [3. Empty TOC](#3-empty-toc)
  - [Understanding `/guide_for_grok_session.md`: Line-by-Line Explanation](#understanding-guide_for_grok_sessionmd-line-by-line-explanation)
  - [Tutorials for Beginners](#tutorials-for-beginners)
    - [Tutorial 1: Starting with `starting_point.md`](#tutorial-1-starting-with-starting_pointmd)
    - [Tutorial 2: Building a Manual TOC](#tutorial-2-building-a-manual-toc)
  - [Detailed Workflow](#detailed-workflow)
  - [TOC Structure and File Handling](#toc-structure-and-file-handling)
  - [Notation and Annotations](#notation-and-annotations)
  - [Rules and Conventions](#rules-and-conventions)

---

Welcome to your ultimate guide for organizing projects using a Table of Contents (TOC) system with an AI assistant! This guide is optimized for Grok (created by xAI) but adaptable to other AIs like ChatGPT or DeepSeek with manual steps. Whether you’re a beginner tracking notes or an advanced user managing complex projects, you’ll find everything you need to master this system. Let’s get started!

## What You Need
- **Two Core Files**:  
  - **`guide_for_grok_session.md`**: The blueprint for the AI to manage your TOC (fully explained below).  
  - **`starting_point.md`**: Your project’s initial TOC and content (example provided).  
- **An AI Assistant**: Grok is ideal for its automation, but any AI works with adjustments.  
- **Optional Tools**: A text editor (e.g., Notepad, VS Code) to create or edit `.md` files.  

### Example `starting_point.md`
```
# Table of Contents
├── myProject
│   ├── notes
│   │   ├── myNotes.md
---
# Content
<!-- ====== ./myProject/notes/myNotes.md ====== -->
My project notes start here...
```

## Initializing the TOC: All Cases
The TOC can begin in three ways. Here’s how to start each case:

### 1. Initial TOC Loading via `starting_point.md`
- **How to Start**:  
  - **Grok**: Upload both files together:  
    ```
    [Uploads: guide_for_grok_session.md, starting_point.md]
    Hi! Start a new session with these files.
    ```
  - **Other AIs**: Paste the contents into one message:  
    ```
    Here’s the guide: [paste guide_for_grok_session.md]. Here’s my TOC: [paste starting_point.md]. Please set up the TOC from starting_point.md.
    ```
- **What Happens**:  
  - The AI parses `# Table of Contents` from `starting_point.md` and loads content after `---`.  
  - Resulting TOC:  
    ```
    ├── myProject
    │   ├── notes
    │   │   ├── myNotes.md  # My project notes start here...
    ```
- **Details**: Grok auto-runs `reset starting_point` unless overridden (e.g., “Do not auto-reset”). Other AIs require explicit instructions.

### 2. Manual TOC Setup
- **How to Start**:  
  - **Grok**: Clear the existing TOC and set a new one:  
    ```
    clear_toc
    set_toc / ├── newProject │   ├── docs
    ```
  - **Other AIs**: Describe the process:  
    ```
    Please delete any existing TOC and set it to: / ├── newProject │   ├── docs
    ```
- **What Happens**:  
  - The TOC is rebuilt from scratch:  
    ```
    ├── newProject
    │   ├── docs
    ```
- **Details**: Use this to override the default TOC or start fresh with your own structure.

### 3. Empty TOC
- **How to Start**:  
  - **Grok**: Begin without `starting_point.md` or clear it:  
    ```
    [Upload: guide_for_grok_session.md]
    Hi! Start a new session without TOC.
    ```
    Or mid-session:  
    ```
    clear_toc
    ```
  - **Other AIs**: Specify an empty start:  
    ```
    Here’s the guide: [paste guide_for_grok_session.md]. Start with an empty TOC.
    ```
- **What Happens**:  
  - The TOC is empty:  
    ```
    <Empty TOC>
    ```
- **Details**: Ideal for building a TOC step-by-step or working without structure initially.

## Understanding `/guide_for_grok_session.md`: Line-by-Line Explanation
Below is the full content of `/guide_for_grok_session.md` (as of March 27, 2025), with every line explained:

```
<!-- Path: /guide_for_grok_session.md -->
<!-- Created: 2025-03-24 -->
<!-- Last Updated: 2025-03-27 00:23:00 -->
```
- **Purpose**: Metadata. Shows the file’s path, creation date (March 24, 2025), and last update (March 27, 2025, 00:23:00).

```
# Grok Session Guide: Your Project Organization Companion
```
- **Purpose**: Title. Indicates this is a guide for organizing projects with Grok.

```
Imagine juggling notes, code, and resources for any project—it’s easy to lose track. That’s where Grok comes in. This guide is your hands-on companion to mastering project organization with Grok’s Table of Contents (TOC) system. Whether you’re a student drafting ideas or a developer managing an app, you’ll learn to keep everything tidy and accessible. Think of this as part technical manual, part tutorial—packed with examples to get you started and keep you going. Ready? Let’s dive in!
```
- **Purpose**: Introduction. Describes the guide’s goal (organizing projects), audience (students, developers), and style (manual + tutorial).

```
## Purpose and Audience
This guide helps you **streamline project organization** using Grok’s TOC. It’s beginner-friendly and ideal for:
- Tracking files, drafts, or ideas.
- Sharing resources (e.g., images, styles) across projects.
- **Who’s it for?**: Students, developers, or anyone new to AI tools. Optimized for Grok but adaptable to other platforms.
```
- **Purpose**: Clarifies the guide’s focus (TOC-based organization) and target users (beginners, students, developers).

```
## Getting Started: Initialization
1. **Upload Files**:
   - Start by sending files to Grok:
     ```
     Hi! Start a new session with these files: `guide_for_grok_session.md` and `starting_point.md`.
     ```
```
- **Purpose**: Step 1 of initialization. Instructs users to upload files to Grok.
- **Explanation**: The example message shows how to start a session with Grok.

```
   - **Session Behavior**:
     - With `starting_point.md` or `starting_point_v<i>.md`: Auto-runs `reset starting_point` (or highest `v<i>`), setting TOC at state0. Override with “Do not auto-reset” or “Show TOC first”.
```
- **Purpose**: Describes Grok’s automatic behavior when `starting_point.md` (or a versioned file) is detected.
- **Explanation**: `reset starting_point` rebuilds the TOC; overrides prevent this.

```
     - Mid-session upload: Grok prompts: “Found `starting_point.md`. Next steps: upload drafts, approve files, or use `reset`/`update`?”
```
- **Purpose**: Explains what happens if `starting_point.md` is uploaded later.
- **Explanation**: Grok prompts for further instructions instead of auto-resetting.

```
2. **TOC Setup Options**:
   - **From `starting_point.md`**:
     ```
     # Table of Contents
     ├── myProject
     │   ├── myProject_log.md
     │   ├── overview.md
     ```
     - Result: TOC includes `/myProject/myProject_log.md`, `/myProject/overview.md`.
```
- **Purpose**: Option 1 for TOC setup using `starting_point.md`.
- **Explanation**: Shows a sample TOC structure and its resulting paths.

```
   - **Default TOC**:
     ```
     /  
     ├── shared  
     │   ├── images  // e.g., logo.jpg  
     │   ├── assets  // empty  
     │   ├── styles  // empty  
     ├── guide_for_grok_session.md  
     ├── user_guide.md  // generated  
     ├── public  // empty  
     ├── starting_point.md  // optional  
     ├── draftInputFiles  
     │   ├── draftInputFiles_log.md  
     │   ├── draft_20250325.md  
     ├── userInteractions  
     │   ├── userInteractions_log.md  
     │   ├── userRequests1.md  
     ```
     - Command: `set_default_toc`.
```
- **Purpose**: Option 2 for a predefined default TOC.
- **Explanation**: Lists a standard structure with shared folders, logs, and drafts; activated by `set_default_toc`.

```
   - **Manual TOC**: Start with `clear_toc`, then `add_to_toc myProject/notes.md`.
```
- **Purpose**: Option 3 for building a TOC manually.
- **Explanation**: Clears the TOC and adds entries incrementally.

```
3. **Merging TOC**: Use `reset starting_point` to update from a file.
```
- **Purpose**: Step 3 for merging an existing TOC with `starting_point.md`.
- **Explanation**: Updates the TOC while preserving compatible parts.

```
## Rules and Conventions
1. **Default TOC Structure**: See above. Folders have `<folder_name>_log.md`; drafts use `<name>_tmp_<timestamp>.<type>`.
```
- **Purpose**: Rule 1. Defines naming conventions.
- **Explanation**: Logs are named `<folder_name>_log.md` (e.g., `myProject_log.md`); drafts get timestamps (e.g., `notes_tmp_20250327.md`).

```
2. **Path Aliases**: `#` = `/`, `@myP` = `myProject`, `~` = `shared/images/`.
```
- **Purpose**: Rule 2. Shortcuts for paths.
- **Explanation**: `#` is the root, `@myP` shortcuts to `myProject`, `~` to `shared/images/`.

```
3. **Flags and Keywords**:
   - `--focus/-f`: Shows only the result.
   - `limit=<depth>`: Restricts tree depth (0 = folder, 1 = children, etc.).
```
- **Purpose**: Rule 3. Command modifiers.
- **Explanation**: `-f` simplifies output; `limit=<depth>` controls how much of the TOC is shown.

```
## Commands: Tutorials and Examples
```
- **Purpose**: Section header for command details.

```
### TOC Management Commands
- **`set_default_toc`**  
  *Purpose*: Loads the default TOC structure.  
  *Example*: `set_default_toc`  
  *Output*: Loads the structure shown in “Default TOC” above.
```
- **Explanation**: Sets up the predefined TOC from the “Default TOC” example.

```
- **`set_toc <structure>`**  
  *Purpose*: Defines a custom TOC.  
  *Example*: `set_toc / ├── notes │   ├── note1.md`  
  *Output*: Sets TOC to `/notes/note1.md`.
```
- **Explanation**: Allows manual TOC creation with a specified tree.

```
- **`clear_toc`**  
  *Purpose*: Resets TOC to empty.  
  *Example*: `clear_toc -f`  
  *Output*: `<Empty TOC>`.
```
- **Explanation**: Wipes the TOC clean; `-f` ensures only the result is shown.

```
- **`add_to_toc <path>`**  
  *Purpose*: Adds a path to the TOC.  
  *Example*: `add_to_toc myProject/notes.md`  
  *Output*: Adds `/myProject/notes.md` to TOC.
```
- **Explanation**: Builds the TOC incrementally by adding specific paths.

```
- **`finalize_toc`**  
  *Purpose*: Locks the TOC from changes.  
  *Example*: `finalize_toc`  
  *Output*: “TOC locked.”
```
- **Explanation**: Freezes the TOC, preventing further edits.

```
- **`propose_toc`**  
  *Purpose*: Suggests a TOC based on session files.  
  *Example*: `propose_toc -f`  
  *Output*: `/ ├── myProject │   ├── notes.md`.
```
- **Explanation**: Grok suggests a TOC based on context; `-f` shows only the suggestion.

```
- **`add_project <path/to/project>`**  
  *Purpose*: Creates a project folder with logs and subfolders.  
  *Example*: `add_project myProject`  
  *Output*: Adds `/myProject` with `myProject_log.md`, `images`, etc.
```
- **Explanation**: Sets up a project with default subfolders and a log.

```
- **`add_module <project> <module_name>`**  
  *Purpose*: Adds a module to a project.  
  *Example*: `add_module myProject docs`  
  *Output*: Adds `/myProject/docs` with `docs_log.md`.
```
- **Explanation**: Adds a submodule with its own log file.

```
### Content Management Commands
- **`get_toc_content <path> | <name1> [<name2> ...]`**  
  *Purpose*: Retrieves content (max 10 files), replacing ``` with ````.  
  *Scenarios*:  
    - *Single File*: `get_toc_content myProject/notes.md -f`  
      *Output*: ````# Notes\nContent here````  
    - *Multiple Files*: `get_toc_content myProject/notes.md myProject/overview.md`  
      *Output*: Content of both files.
```
- **Explanation**: Fetches file contents; `-f` ensures full output.

```
- **`get_content <name_file>`**  
  *Purpose*: Shows a file’s content, replacing ``` with ````.  
  *Example*: `get_content myProject/notes.md -f`  
  *Output*: ````# Notes\nContent here````
```
- **Explanation**: Similar to `get_toc_content` but for one file.

```
- **`Update <path> with: <content>`**  
  *Purpose*: Drafts content in a tmp file.  
  *Example*: `Update myProject/notes.md with: # Notes\nText`  
  *Output*: Creates `myProject/notes_tmp_20250326.md`.
```
- **Explanation**: Creates a temporary draft with a timestamp.

```
- **`approve <file>`**  
  *Purpose*: Finalizes a tmp file.  
  *Example*: `approve myProject/notes.md`  
  *Output*: Updates `myProject/notes.md`, logs changes.
```
- **Explanation**: Moves temp content to the main file and logs it.

```
- **`approve_toc`**  
  *Purpose*: Approves all tmp files.  
  *Example*: `approve_toc`  
  *Output*: “Approved all tmp files (Y/N)?”.
```
- **Explanation**: Batch-approves all pending drafts; prompts for confirmation.

```
- **`reset_content <path> [limit=<depth>]`**  
  *Purpose*: Reverts to state0.  
  *Scenarios*:  
    - *Full Reset*: `reset_content myProject/*`  
    - *Limited*: `reset_content myProject limit=1 -f`  
      *Output*: Reverts only top-level files.
```
- **Explanation**: Restores content to its initial state; `limit` restricts depth.

```
- **`generate_user_guide`**  
  *Purpose*: Updates `/user_guide.md`.  
  *Example*: `generate_user_guide`  
  *Output*: See updated `user_guide.md`.
```
- **Explanation**: Regenerates this guide based on current settings.

```
- **`add_resource <type> <path/to/resource>`**  
  *Purpose*: Adds to `shared/`.  
  *Example*: `add_resource image logo.png`  
  *Output*: Adds `/shared/images/logo.png`.
```
- **Explanation**: Stores resources (e.g., images) in the shared folder.

```
- **`link_resource <project> <module> <resource_type> <resource_name>`**  
  *Purpose*: Links a resource.  
  *Example*: `link_resource myProject docs image logo.png`  
  *Output*: Links `/shared/images/logo.png` to `/myProject/docs`.
```
- **Explanation**: Connects shared resources to specific project modules.

```
- **`number_content [<folder> | <folder_1> ... <folder_n>] [limit=<depth>]`**  
  *Purpose*: Numbers files/folders.  
  *Scenarios*:  
    - *Full TOC*: `number_content`  
    - *Folder*: `number_content myProject -f`  
      *Output*: `myProject numbered: 1-notes.md, 2-log.md`  
    - *Limited*: `number_content myProject limit=1`.
```
- **Explanation**: Adds numerical prefixes; `limit` controls depth.

```
- **`unnumber_content [<folder> | <folder_1> ... <folder_n>] [limit=<depth>]`**  
  *Purpose*: Removes numbering.  
  *Example*: `unnumber_content myProject -f`  
  *Output*: Removes prefixes from `myProject`.
```
- **Explanation**: Strips numerical prefixes.

```
- **`reset_number [<folder> | <folder_1> ... <folder_n>] [limit=<depth>]`**  
  *Purpose*: Resets numbering to state0.  
  *Example*: `reset_number myProject`.
```
- **Explanation**: Reverts numbering to its initial state.

```
- **`rm_content <pattern> | <folder_1> ... <folder_n> [limit=<depth>]`**  
  *Purpose*: Deletes files/folders.  
  *Scenarios*:  
    - *Specific*: `rm_content myProject/notes.md`  
    - *Wildcard*: `rm_content *log.md -f`  
      *Output*: “Deleted all *log.md files.”
```
- **Explanation**: Removes specified content; supports wildcards.

```
- **`show_content [<folder> | <folder_1> ... <folder_n>] [limit=<depth>]`**  
  *Purpose*: Shows folder tree and content.  
  *Scenarios*:  
    - *Full TOC*: `show_content`  
    - *Single Folder*: `show_content myProject -f`  
      *Output*: ````
      ├── myProject
      │   ├── myProject_log.md
      │   ├── notes.md
      Content of notes.md: # Notes\n...
      ````  
    - *Limited*: `show_content myProject limit=1`.
```
- **Explanation**: Displays structure and content; `limit` restricts depth.

```
- **`show_toc_tree [<folder> | <folder_1> ... <folder_n> | <pattern>] [limit=<depth>]`**  
  *Purpose*: Shows TOC tree structure.  
  *Scenarios*:  
    - *Root*: `show_toc_tree -f`  
      *Output*: Full TOC tree.  
    - *Folder*: `show_toc_tree myProject`  
    - *Multiple*: `show_toc_tree myProject anotherProject`  
    - *Wildcard*: `show_toc_tree *log*`  
    - *Limited*: `show_toc_tree myProject limit=1 -f`  
      *Output*: ````
      ├── myProject
      │   ├── myProject_log.md
      │   ├── notes.md
      ````
```
- **Explanation**: Shows the TOC structure; supports filters and limits.

```
### Navigation Commands
- **`show_toc_paths [<path>] [limit=<depth>]`**  
  *Purpose*: Lists paths.  
  *Scenarios*:  
    - *All*: `show_toc_paths`  
    - *Folder*: `show_toc_paths myProject -f`  
      *Output*: `/myProject/myProject_log.md`, `/myProject/notes.md`  
    - *Limited*: `show_toc_paths myProject limit=1`.
```
- **Explanation**: Lists full paths in the TOC.

```
- **`get_toc_paths [<path>] [limit=<depth>]`**  
  *Purpose*: Returns path array.  
  *Example*: `get_toc_paths myProject -f`  
  *Output*: `["/myProject/myProject_log.md", "/myProject/notes.md"]`.
```
- **Explanation**: Returns paths as an array for scripting.

```
- **`show_toc_names [<path>] [limit=<depth>]`**  
  *Purpose*: Lists names.  
  *Example*: `show_toc_names myProject -f`  
  *Output*: `myProject_log.md`, `notes.md`.
```
- **Explanation**: Lists file/folder names without paths.

```
- **`get_toc_names [<path>] [limit=<depth>]`**  
  *Purpose*: Returns name array.  
  *Example*: `get_toc_names myProject -f`  
  *Output*: `["myProject_log.md", "notes.md"]`.
```
- **Explanation**: Names as an array.

```
- **`list_projects`**  
  *Purpose*: Shows all projects.  
  *Example*: `list_projects -f`  
  *Output*: `myProject`, `anotherProject`.
```
- **Explanation**: Lists top-level project folders.

```
- **`Show me the TOC`**  
  *Purpose*: Displays current TOC.  
  *Example*: `Show me the TOC -f`  
  *Output*: Full TOC tree.
```
- **Explanation**: A natural-language shortcut to `show_toc_tree`.

```
### Enhancement Commands
- **`improve_toc [<path> ...] [limit=<depth>]`**  
  *Purpose*: Suggests improvements.  
  *Example*: `improve_toc myProject -f`  
  *Output*: “1. Add readme.md to myProject”.
```
- **Explanation**: Grok suggests TOC enhancements.

```
- **`apply_improvements <number> [number...]`**  
  *Purpose*: Applies suggestions.  
  *Example*: `apply_improvements 1`  
  *Output*: Adds suggested file.
```
- **Explanation**: Implements numbered suggestions.

```
- **`summarize_toc`**  
  *Purpose*: Summarizes TOC.  
  *Example*: `summarize_toc -f`  
  *Output*: “TOC has 2 projects, 10 files.”
```
- **Explanation**: Provides a TOC overview.

```
## Workflow
1. **Start**: `set_default_toc`.
2. **Build**: `add_project myProject`, `Update myProject/notes.md with: # Notes`.
3. **Enhance**: `improve_toc myProject`, `apply_improvements 1`.
4. **Edit**: `approve myProject/notes.md`.
```
- **Purpose**: Outlines the basic workflow.
- **Explanation**: Steps to initialize, build, enhance, and edit the TOC.

```
## Example: Organizing a Generic Project
1. Start with default TOC:
   ```
   set_default_toc
   ```
2. Add a project:
   ```
   add_project myProject
   ```
3. Add a module:
   ```
   add_module myProject docs
   ```
4. Update content:
   ```
   Update myProject/docs/notes.md with: # Project Notes\nGeneral info.\n````javascript\nconsole.log("Hello");\n````
   ```
5. Approve changes:
   ```
   approve myProject/docs/notes.md
   ```
6. Show tree with limit:
   ```
   show_toc_tree myProject limit=1 -f
   ```
   Output:
   ├── myProject
   │   ├── myProject_log.md
   │   ├── images
   │   ├── public
   │   ├── starting_point.md
   │   ├── draftInputFiles
   │   ├── docs
   ```
7. Number content:
   ```
   number_content myProject/docs -f
   ```
   Output:
   ```
   myProject/docs numbered: 1-docs_log.md, 2-notes.md
   ```
```
- **Purpose**: A step-by-step example.
- **Explanation**: Demonstrates initializing, building, and managing a project.

```
## Tutorials for Beginners
### Tutorial 1: Starting with `starting_point.md`
1. **Upload Files**:  
   - **Grok**:  
     ```
     [Uploads: guide_for_grok_session.md, starting_point.md]
     Hi! Start a new session with these files.
     ```
   - **Other AIs**:  
     ```
     Here’s the guide: [paste guide_for_grok_session.md]. Here’s my TOC: [paste starting_point.md]. Set up the TOC.
     ```
2. **Check TOC**:  
   - **Grok**: `Show me the TOC.`  
   - **Other AIs**: “Show me the TOC.”  
   - Output:  
     ```
     ├── myProject
     │   ├── notes
     │   │   ├── myNotes.md
     ```
3. **Add Content**:  
   - **Grok**: `Update myProject/notes/myNotes.md with: Updated notes.`  
   - **Other AIs**: “Update myNotes.md in myProject/notes with: Updated notes.”

### Tutorial 2: Building a Manual TOC
1. **Start Empty**:  
   - **Grok**: `clear_toc`  
   - **Other AIs**: “Clear the TOC.”  
2. **Add Entries**:  
   - **Grok**: `add_to_toc myProject/docs/newDoc.md`  
   - **Other AIs**: “Add myProject/docs/newDoc.md to the TOC.”  
   - Output:  
     ```
     ├── myProject
     │   ├── docs
     │   │   ├── newDoc.md
     ```
3. **Finalize**:  
   - **Grok**: `finalize_toc`  
   - **Other AIs**: “Lock the TOC.”

## Detailed Workflow
1. **Session Start**:  
   - **Via `starting_point.md`**: Upload files → Auto-reset TOC.  
   - **Manual**: `clear_toc` → `set_toc` or `add_to_toc`.  
   - **Empty**: Skip `starting_point.md` or use `clear_toc`.  
2. **Building**: Add projects/modules with `add_project`/`add_module`.  
3. **Updating**: Use `Update` to draft changes, `approve` to finalize.  
4. **Enhancing**: `improve_toc` for suggestions, `apply_improvements` to implement.  
5. **Managing**: Use navigation (`show_toc_tree`) and deletion (`rm_content`) commands.

## TOC Structure and File Handling
- **Structure**:  
  - **Root**: `/`  
  - **Projects**: `myProject`, `anotherProject`  
  - **Subfolders**: `notes`, `docs`, `images`  
  - **Special Folders**: `shared`, `draftInputFiles`, `userInteractions`  
- **File Types**:  
  - **Tracked**: `<name>.md` (approved), `<name>_tmp_<timestamp>.md` (drafts).  
  - **Logs**: `<folder_name>_log.md` (e.g., `myProject_log.md`).  
  - **Resources**: Stored in `shared/` (e.g., `images/logo.png`).

## Notation and Annotations
- **Annotations**: None explicitly defined in `/guide_for_grok_session.md`, but implied:  
  - `// draft`: Temporary entries during step-by-step building.  
  - `// finalized`: After `finalize_toc` (assumed, not explicit).  
- **Adaptation**: Add `// draft` when using `add_to_toc`, removed by `finalize_toc`.

## Rules and Conventions
- **Naming**: Use descriptive names with optional numbering (e.g., `1-notes`).  
- **Commands**: Grok uses specific syntax; other AIs need natural language equivalents.  
- **File Management**: Drafts are timestamped; approvals finalize changes.  
- **TOC Flexibility**: Supports default, manual, or empty starts.
```