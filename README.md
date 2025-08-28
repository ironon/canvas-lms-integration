# Canvas LMS Integration

This is a plugin designed to integrate tasks and assignments from Canvas LMS to Obsidian, helping you manage your academic workload more efficiently. Forked from [this Canvas LMS importer](https://github.com/jordaeday/canvas-task-importer), credit to [Jordan Day](https://github.com/jordaeday) where credit is due.

## Installation and Setup

1. **Install the plugin:**
  - Download the `.zip` file, unzip it, and place the extracted folder into your vault's `.obsidian/plugins` directory.
2. **Configure the plugin:**
  - Go to the plugin's settings within Obsidian.
  - Enter your school's Canvas link (it should look like this: https://YOURSCHOOL.instructure.com).
  - Enter your personal access token (instructions on how to do so can be found [HERE](https://community.canvaslms.com/t5/Student-Guide/How-do-I-manage-API-access-tokens-as-a-student/ta-p/273)). You should leave the expiration date on the access token blank.


## Usage
This plugin is designed to work with [Tasks](https://github.com/obsidian-tasks-group/obsidian-tasks), [Dataview](https://github.com/blacksmithgu/obsidian-dataview), and [FullCalendar](https://github.com/obsidian-community/obsidian-full-calendar). It also injects an API at `.canvas_lms` into the global app namespace (commonly found at `this.app.canvas_lms`), so that plugins like [Templater](https://github.com/SilentVoid13/Templater?tab=readme-ov-file) can use it.

Dataview and Templater integration work out of the box, while FullCalendar and Tasks require some configuring of the settings to work.
