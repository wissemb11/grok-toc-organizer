<!-- Path: /guide_for_grok_session.md -->
<!-- Created: 2025-03-24 -->
<!-- Last Updated: 2025-03-27 00:23:00 -->

# Grok Session Guide: Your Project Organization Companion

Imagine juggling notes, code, and resources for any project—it’s easy to lose track. That’s where Grok comes in. This guide is your hands-on companion to mastering project organization with Grok’s Table of Contents (TOC) system. Whether you’re a student drafting ideas or a developer managing an app, you’ll learn to keep everything tidy and accessible. Think of this as part technical manual, part tutorial—packed with examples to get you started and keep you going. Ready? Let’s dive in!

## Purpose and Audience
This guide helps you **streamline project organization** using Grok’s TOC. It’s beginner-friendly and ideal for:
- Tracking files, drafts, or ideas.
- Sharing resources (e.g., images, styles) across projects.
- **Who’s it for?**: Students, developers, or anyone new to AI tools. Optimized for Grok but adaptable to other platforms.

## Getting Started: Initialization
1. **Upload Files**:
   - Start by sending files to Grok:
     ```
     Hi! Start a new session with these files: `guide_for_grok_session.md` and `starting_point.md`.
     ```
   - **Session Behavior**:
     - With `starting_point.md` or `starting_point_v<i>.md`: Auto-runs `reset starting_point` (or highest `v<i>`), setting TOC at state0. Override with “Do not auto-reset” or “Show TOC first”.
     - Mid-session upload: Grok prompts: “Found `starting_point.md`. Next steps: upload drafts, approve files, or use `reset`/`update`?”

2. **TOC Setup Options**:
   - **From `starting_point.md`**:
     ```
     # Table of Contents
     ├── myProject
     │   ├── myProject_log.md
     │   ├── overview.md
     ```
     - Result: TOC includes `/myProject/myProject_log.md`, `/myProject/overview.md`.
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
   - **Manual TOC**: Start with `clear_toc`, then `add_to_toc myProject/notes.md`.

3. **Merging TOC**: Use `reset starting_point` to update from a file.

## Rules and Conventions
1. **Default TOC Structure**: See above. Folders have `<folder_name>_log.md`; drafts use `<name>_tmp_<timestamp>.<type>`.
2. **Path Aliases**: `#` = `/`, `@myP` = `myProject`, `~` = `shared/images/`.
3. **Flags and Keywords**:
   - `--focus/-f`: Shows only the result.
   - `limit=<depth>`: Restricts tree depth (0 = folder, 1 = children, etc.).

## Commands: Tutorials and Examples

### TOC Management Commands
- **`set_default_toc`**  
  *Purpose*: Loads the default TOC structure.  
  *Example*: `set_default_toc`  
  *Output*: Loads the structure shown in “Default TOC” above.

- **`set_toc <structure>`**  
  *Purpose*: Defines a custom TOC.  
  *Example*: `set_toc / ├── notes │   ├── note1.md`  
  *Output*: Sets TOC to `/notes/note1.md`.

- **`clear_toc`**  
  *Purpose*: Resets TOC to empty.  
  *Example*: `clear_toc -f`  
  *Output*: `<Empty TOC>`.

- **`add_to_toc <path>`**  
  *Purpose*: Adds a path to the TOC.  
  *Example*: `add_to_toc myProject/notes.md`  
  *Output*: Adds `/myProject/notes.md` to TOC.

- **`finalize_toc`**  
  *Purpose*: Locks the TOC from changes.  
  *Example*: `finalize_toc`  
  *Output*: “TOC locked.”

- **`propose_toc`**  
  *Purpose*: Suggests a TOC based on session files.  
  *Example*: `propose_toc -f`  
  *Output*: `/ ├── myProject │   ├── notes.md`.

- **`add_project <path/to/project>`**  
  *Purpose*: Creates a project folder with logs and subfolders.  
  *Example*: `add_project myProject`  
  *Output*: Adds `/myProject` with `myProject_log.md`, `images`, etc.

- **`add_module <project> <module_name>`**  
  *Purpose*: Adds a module to a project.  
  *Example*: `add_module myProject docs`  
  *Output*: Adds `/myProject/docs` with `docs_log.md`.

### Content Management Commands
- **`get_toc_content <path> | <name1> [<name2> ...]`**  
  *Purpose*: Retrieves content (max 10 files), replacing ``` with ````.  
  *Scenarios*:  
    - *Single File*: `get_toc_content myProject/notes.md -f`  
      *Output*: 
      ````# Notes\nContent here````  
    - *Multiple Files*: `get_toc_content myProject/notes.md myProject/overview.md`  
      *Output*: Content of both files.

- **`get_content <name_file>`**  
  *Purpose*: Shows a file’s content, replacing ``` with ````.  
  *Example*: `get_content myProject/notes.md -f`  
  *Output*: 
  ````# Notes\nContent here````

- **`Update <path> with: <content>`**  
  *Purpose*: Drafts content in a tmp file.  
  *Example*: `Update myProject/notes.md with: # Notes\nText`  
  *Output*: Creates `myProject/notes_tmp_20250326.md`.

- **`approve <file>`**  
  *Purpose*: Finalizes a tmp file.  
  *Example*: `approve myProject/notes.md`  
  *Output*: Updates `myProject/notes.md`, logs changes.

- **`approve_toc`**  
  *Purpose*: Approves all tmp files.  
  *Example*: `approve_toc`  
  *Output*: “Approved all tmp files (Y/N)?”.

- **`reset_content <path> [limit=<depth>]`**  
  *Purpose*: Reverts to state0.  
  *Scenarios*:  
    - *Full Reset*: `reset_content myProject/*`  
    - *Limited*: `reset_content myProject limit=1 -f`  
      *Output*: Reverts only top-level files.

- **`generate_user_guide`**  
  *Purpose*: Updates `/user_guide.md`.  
  *Example*: `generate_user_guide`  
  *Output*: See updated `user_guide.md`.

- **`add_resource <type> <path/to/resource>`**  
  *Purpose*: Adds to `shared/`.  
  *Example*: `add_resource image logo.png`  
  *Output*: Adds `/shared/images/logo.png`.

- **`link_resource <project> <module> <resource_type> <resource_name>`**  
  *Purpose*: Links a resource.  
  *Example*: `link_resource myProject docs image logo.png`  
  *Output*: Links `/shared/images/logo.png` to `/myProject/docs`.

- **`number_content [<folder> | <folder_1> ... <folder_n>] [limit=<depth>]`**  
  *Purpose*: Numbers files/folders.  
  *Scenarios*:  
    - *Full TOC*: `number_content`  
    - *Folder*: `number_content myProject -f`  
      *Output*: `myProject numbered: 1-notes.md, 2-log.md`  
    - *Limited*: `number_content myProject limit=1`.

- **`unnumber_content [<folder> | <folder_1> ... <folder_n>] [limit=<depth>]`**  
  *Purpose*: Removes numbering.  
  *Example*: `unnumber_content myProject -f`  
  *Output*: Removes prefixes from `myProject`.

- **`reset_number [<folder> | <folder_1> ... <folder_n>] [limit=<depth>]`**  
  *Purpose*: Resets numbering to state0.  
  *Example*: `reset_number myProject`.

- **`rm_content <pattern> | <folder_1> ... <folder_n> [limit=<depth>]`**  
  *Purpose*: Deletes files/folders.  
  *Scenarios*:  
    - *Specific*: `rm_content myProject/notes.md`  
    - *Wildcard*: `rm_content *log.md -f`  
      *Output*: “Deleted all *log.md files.”

- **`show_content [<folder> | <folder_1> ... <folder_n>] [limit=<depth>]`**  
  *Purpose*: Shows folder tree and content.  
  *Scenarios*:  
    - *Full TOC*: `show_content`  
    - *Single Folder*: `show_content myProject -f`  
      *Output*: 
      ````
      ├── myProject
      │   ├── myProject_log.md
      │   ├── notes.md
      Content of notes.md: # Notes\n...
      ````  
    - *Limited*: `show_content myProject limit=1`.

- **`show_toc_tree [<folder> | <folder_1> ... <folder_n> | <pattern>] [limit=<depth>]`**  
  *Purpose*: Shows TOC tree structure.  
  *Scenarios*:  
    - *Root*: `show_toc_tree -f`  
      *Output*: Full TOC tree.  
    - *Folder*: `show_toc_tree myProject`  
    - *Multiple*: `show_toc_tree myProject anotherProject`  
    - *Wildcard*: `show_toc_tree *log*`  
    - *Limited*: `show_toc_tree myProject limit=1 -f`  
      *Output*: 
      ````
      ├── myProject
      │   ├── myProject_log.md
      │   ├── notes.md
      ````

### Navigation Commands
- **`show_toc_paths [<path>] [limit=<depth>]`**  
  *Purpose*: Lists paths.  
  *Scenarios*:  
    - *All*: `show_toc_paths`  
    - *Folder*: `show_toc_paths myProject -f`  
      *Output*: `/myProject/myProject_log.md`, `/myProject/notes.md`  
    - *Limited*: `show_toc_paths myProject limit=1`.

- **`get_toc_paths [<path>] [limit=<depth>]`**  
  *Purpose*: Returns path array.  
  *Example*: `get_toc_paths myProject -f`  
  *Output*: `["/myProject/myProject_log.md", "/myProject/notes.md"]`.

- **`show_toc_names [<path>] [limit=<depth>]`**  
  *Purpose*: Lists names.  
  *Example*: `show_toc_names myProject -f`  
  *Output*: `myProject_log.md`, `notes.md`.

- **`get_toc_names [<path>] [limit=<depth>]`**  
  *Purpose*: Returns name array.  
  *Example*: `get_toc_names myProject -f`  
  *Output*: `["myProject_log.md", "notes.md"]`.

- **`list_projects`**  
  *Purpose*: Shows all projects.  
  *Example*: `list_projects -f`  
  *Output*: `myProject`, `anotherProject`.

- **`Show me the TOC`**  
  *Purpose*: Displays current TOC.  
  *Example*: `Show me the TOC -f`  
  *Output*: Full TOC tree.

### Enhancement Commands
- **`improve_toc [<path> ...] [limit=<depth>]`**  
  *Purpose*: Suggests improvements.  
  *Example*: `improve_toc myProject -f`  
  *Output*: “1. Add readme.md to myProject”.

- **`apply_improvements <number> [number...]`**  
  *Purpose*: Applies suggestions.  
  *Example*: `apply_improvements 1`  
  *Output*: Adds suggested file.

- **`summarize_toc`**  
  *Purpose*: Summarizes TOC.  
  *Example*: `summarize_toc -f`  
  *Output*: “TOC has 2 projects, 10 files.”

## Workflow
1. **Start**: `set_default_toc`.
2. **Build**: `add_project myProject`, `Update myProject/notes.md with: # Notes`.
3. **Enhance**: `improve_toc myProject`, `apply_improvements 1`.
4. **Edit**: `approve myProject/notes.md`.

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
   ```
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