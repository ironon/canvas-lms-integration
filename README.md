# Canvas LMS Integration

This is a plugin designed to integrate tasks and assignments from Canvas LMS to Obsidian, helping you manage your academic workload more efficiently. Forked from [this Canvas LMS importer](https://github.com/jordaeday/canvas-task-importer), credit to [Jordan Day](https://github.com/jordaeday) where credit is due.

## Installation and Setup

1. **Install the plugin:**
  - Download the `.zip` file, unzip it, and place the extracted folder into your vault's `.obsidian/plugins` directory.
2. **Configure the plugin:**
  - Go to the plugin's settings within Obsidian.
  - Enter your school's Canvas link (it should look like this: https://YOURSCHOOL.instructure.com).
  - Enter your personal access token (instructions on how to do so can be found [HERE](https://community.canvaslms.com/t5/Student-Guide/How-do-I-manage-API-access-tokens-as-a-student/ta-p/273)). You should leave the expiration date on the access token blank.


## Features
This plugin is designed to work with [Tasks](https://github.com/obsidian-tasks-group/obsidian-tasks), [Dataview](https://github.com/blacksmithgu/obsidian-dataview), and [FullCalendar](https://github.com/obsidian-community/obsidian-full-calendar). It also injects an API at `.canvas_lms` into the global app namespace (commonly found at `this.app.canvas_lms`), so that plugins like [Templater](https://github.com/SilentVoid13/Templater?tab=readme-ov-file) can use it.

This plugin can be configured so that FullCalendar can interpret it's data and display it on a calendar, but it is still up to you to configure FullCalendar to do so.

## Usage

There are a couple different mode of operation for this plugin, all of which are off by default, and must be explictly turned on. Multiple modes can be on at the same time. *The Dataview and Templater integrations will work fine, even with all of the modes off, all these modes do is just find different ways to import as-text the contents of your Canvas assignments, without the use of Dataview or Templater.*

### Mirror Assignments into Folder (Recommended) 
This mode, for every assignment on Canvas, will mirror all assignments into the specified folder.




### Daily Note Inject
This mode, for every assignment on Canvas, will go to the corrosponding daily note for when that assignment is due, and insert a Task under the specified header in the daily note with the name of the assignment.
Example:

```
# 8-28-2025 Daily Note


## Tasks Today
- [ ] workout
- [ ] Drink Matcha while listing to Radiohead with wired earbuds
- [ ] [[Assignments/New Historicism Essay]]

```
(Note: if the ``Mirror Assignments into Folder`` feature is turned off, instead of linking to the obsidian note for that assignment, it will link to the Canvas URL for that assignment.)

Options:
- **Daily Note Header**: Defaults to "". meaning assignments won't be inserted at all. This is header where the canvas assignment will be placed under the daily note.

- **Assignment Offsets**: Defaults to a list with a single entry of zero. This option can be used to allow the user to put the same exact assignment in multiple daily notes, relative to its actual due date. For example, if the list contains a single entry, which is -7, the Canvas assignment will only show up in the daily note exactly 7 days before the assignment is due. If this option is set to [-7.-6,-5,-4,-3,-2,-1,0,1], the assignment will show up in every daily note a week prior to the due date, and show up in the daily note 1 day after the due date.
  
- **Daily Note Insert Point**: Takes priority over *Daily Note Header*, and instead of inserting the assignments at a header, it will search for whatever text placeholder is put inside this field, and place the assignments in place of that placeholder.




