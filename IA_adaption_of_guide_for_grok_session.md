<!-- Path: /guide_for_grok_session.md -->
<!-- Created: 2025-03-24 -->
<!-- Last Updated: 2025-03-25 17:00:00 -->

# Guide for Grok Session: Organizing Your Projects with Grok

Hi! This guide helps you organize your projects using a Table of Contents (TOC) with Grok, an AI assistant. Whether you’re jotting down notes or managing a big project, it’s simple to start and flexible to use. Plus, it lets you share resources like images or assets in one place for all your projects—perfect for keeping everything tidy and reusable!

## Purpose and Audience
This guide is all about **organizing projects using a TOC with an AI assistant like Grok**. It’s beginner-friendly, so anyone can use it to keep track of files, drafts, or ideas. It also supports **resource sharing**, letting you store things like images or assets in one place. 
- **Who’s it for?**: Anyone from students to developers—whether you’re new to AI tools or building something like a Vue 2 project (e.g., `wbcUi2`). It works best with Grok but can adapt to other AIs like ChatGPT with a tweak.

## Getting Started: Initialization
1. **Upload Files**:
   - Send both files to Grok:
     ```
     Hi! Start a new session with these files: `guide_for_grok_session.md` and `starting_point.md`.
     ```
   - Grok parses `/starting_point.md` to load the TOC if it has one. If absent or no TOC, defaults to the structure below.

2. **TOC Scenarios**:
   - **TOC from `starting_point.md`**:
     - Example:
       ```
       [Upload: starting_point.md]
       # Table of Contents
       ├── wbcUi2
       │   ├── installation.md
       ---
       # Content
       <!-- ====== ./wbcUi2/installation.md ====== -->
       Install WBC-UI2 here...
       ```
       - Result: `/wbcUi2/installation.md`.
   - **Default TOC**:
     - If no `starting_point.md` or no TOC:
       ```
       /
       ├── shared
       │   ├── images  // e.g., tc_monastir_logo.jpg
       │   ├── assets  // empty
       │   ├── styles  // empty
       ├── guide_for_grok_session.md
       ├── user_guide.md  // generated
       ├── public  // empty
       ├── starting_point.md  // if uploaded, empty or ignored if no TOC
       ├── draftInputFiles  // e.g., draft_20250325.md
       ├── userInteractions  // empty
       ```
     - Use: `set_default_toc`.
   - **Manual Building**:
     - Start empty: `clear_toc` → `<Empty TOC>`.
     - Build: `add_to_toc wbcUi2/installation.md`.

3. **Merging**:
   - `reset starting_point`: Updates TOC with `/starting_point.md`.

## Rules and Conventions
1. **Default TOC Structure**:
   - Root (`/`):
     ```
     ├── shared
     │   ├── images  // e.g., tc_monastir_logo.jpg
     │   ├── assets  // empty
     │   ├── styles  // empty
     ├── guide_for_grok_session.md
     ├── user_guide.md  // generated
     ├── public  // empty
     ├── starting_point.md  // optional
     ├── draftInputFiles  // e.g., draft_20250325.md
     ├── userInteractions  // empty
     ```
   - **Custom TOC**: Updates default if `/starting_point.md` has a TOC.

2. **Path Aliases**:
   - `#` → `/`.
   - `@<3first_chars>` → Project (e.g., `@wbc` for `wbcUi2`).
   - `~` → `shared/images/`.

3. **Commands**:
   - **TOC Management**:
     - `set_default_toc`: Loads default TOC.
     - `set_toc <structure>`: Defines a custom TOC (e.g., `set_toc ├── wbcUi2 │ ├── files`).
     - `clear_toc`: Resets to `<Empty TOC>`.
     - `add_to_toc <path>`: Adds incrementally (e.g., `add_to_toc wbcUi2/notes.md`).
     - `finalize_toc`: Locks TOC (e.g., marks as final).
     - `propose_toc`: Suggests a TOC (e.g., `├── wbcUi2 ├── newProject`).
     - `add_project <path/to/project>`:
       - Creates:
         ```
         ├── <project_name>
         │   ├── images  // empty
         │   ├── public  // empty
         │   ├── starting_point.md  // empty
         │   ├── draftInputFiles  // empty
         ```
       - Example: `add_project wbcUi2`.
     - `add_module <project> <module_name>`:
       - Creates:
         ```
         ├── <module_name>
         │   ├── <module_name>.md
         │   ├── <module_name>_tmp.md
         │   ├── <module_name>_state.md
         │   ├── <module_name>_init.md
         ```
       - Example: `add_module wbcUi2 gettingStarted`.
   - **Content Management**:
     - `get_toc_content <name_file_with_path> | <name1> [<name2> ...] | <specific_folder>/`:
       - `.md`: ````markdown, ``` → ````.
       - Limit: 10 files; `"get_toc_content: only 10 files can be displayed, additional files omitted"`.
       - Example: `get_toc_content /wbcUi2/`.
     - `get_content <name_file>`:
       - Alias, ``` → ````.
     - `Update <path> with: <content>`:
       - Drafts in `<path>_tmp.md`. Example: `Update wbcUi2/installation.md with: New text` → `installation_tmp.md`.
     - `approve <file>`:
       - Moves `<file>_tmp.md` to `<file>.md`. Example: `approve installation.md`.
     - `add_resource <type> <path/to/resource>`:
       - Adds to `shared/`. Example: `add_resource image logo.jpg`.
     - `link_resource <project> <module> <resource_type> <resource_name>`:
       - Links, e.g., `link_resource wbcUi2 gettingStarted image logo.jpg`.
     - `init_module_doc <project> <module> <doc_type>`:
       - Initializes doc, e.g., `init_module_doc wbcUi2 gettingStarted main`.
   - **Navigation**:
     - `show_toc_paths [<specific_folder>/]`:
       - Lists paths, e.g., `/shared/images/logo.jpg`.
     - `get_toc_paths [<specific_folder>/]`:
       - Array, e.g., `["logo.jpg"]="shared/images/"`.
     - `show_toc_names [<specific_folder>/]`:
       - Names only.
     - `get_toc_names [<specific_folder>/]`:
       - Array of names.
     - `list_projects`:
       - Lists projects, e.g., `Projects: - wbcUi2`.
     - `Show me the TOC`:
       - Displays TOC, e.g., `├── wbcUi2`.

## Workflow
1. **Start**: Upload files or `set_default_toc`.
2. **Build**: Use `add_project`, `add_to_toc`, etc.
3. **Edit**: Draft with `Update`, confirm with `approve`.

