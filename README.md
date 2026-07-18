# TwoDo-List

A minimalist, self-contained to-do list as a single `index.html` file – no build process, no dependencies, no server. Just open the file in a browser and go.

## Table of Contents

- [Core Idea](#core-idea)
- [Features](#features)
  - [Managing Tasks](#managing-tasks)
  - [Sooner / Later](#sooner--later)
  - [Archive](#archive)
  - [Projects (`#Project`)](#projects-project)
  - [Due Dates (Automatic Recognition)](#due-dates-automatic-recognition)
  - [Minimalist Mode](#minimalist-mode)
  - [Appearance](#appearance)
  - [Keyboard Shortcuts](#keyboard-shortcuts)
  - [Language](#language)
- [Settings Overview](#settings-overview)
- [Data Storage & Privacy](#data-storage--privacy)
  - [Advantages](#advantages)
  - [Risks](#risks)
- [Usage](#usage)

## Core Idea

TwoDo-List splits tasks into two time horizons – **Sooner** and **Later** – instead of complex lists, projects, or priority levels. Anyone who wants more structure can optionally turn on projects (`#tag`) and automatically recognized due dates; anyone who prefers it plain can stay in minimalist mode with the original, simple view.

## Features

### Managing Tasks

- **Add**: The plus button at the bottom, or the `+`/`Enter` key, opens the input field.
- **Edit**: Tap the task text, change it, confirm with `Enter` or cancel with `Esc`.
- **Complete**: Tap the checkbox – the task moves to the archive automatically with a short animation (if the archive is enabled), otherwise it's deleted permanently right away.
- **Reorder**: Drag tasks by the handle (☰) to rearrange them, even across Sooner/Later.
- **Move**: The arrow button moves a task between Sooner and Later.
- **Expand/collapse**: Lists with more than 3 entries are collapsed by default; the arrow button on the top right expands them fully.

### Sooner / Later

Two fixed sections instead of freely definable lists – deliberately kept simple. Every task belongs to exactly one of the two.

### Archive

- Completed tasks land in the archive (if enabled) and can be restored or deleted permanently from there.
- "Delete all" empties the entire archive after a confirmation prompt.
- Can be disabled in settings – checked-off tasks are then deleted immediately and permanently, without a stop in the archive.

### Projects (`#Project`)

- Typing `#ProjectName` strips the tag from the visible text and shows it instead as a small badge under the task.
- Typing `#` again shows a suggestion list of previously used projects (clickable with the mouse, or selectable via arrow keys + `Enter` without touching the mouse).
- Clicking the "TwoDo-List" title at the top reveals a tab bar with all active projects, letting you filter the list down to a single project.
- Projects with no active task left automatically disappear from suggestions and tabs – there's no separate project management, everything is derived from the tasks themselves.
- Clicking a project badge removes the project from that task again.

### Due Dates (Automatic Recognition)

While typing, a deliberately limited, well-defined set of phrases is recognized, stripped from the text, and shown as a colored badge:

- Weekdays: `Tuesday`, `next Tuesday` / `Dienstag`, `nächsten Dienstag`
- Relative terms: `today`, `tomorrow`, `day after tomorrow` / `heute`, `morgen`, `übermorgen`
- Time spans: `in 3 days`, `in 2 weeks` / `in 3 Tagen`, `in 2 Wochen`
- Fixed dates: `21.07.` or `21.07.2027` (without a year, the next matching year is assumed automatically if the date would otherwise fall in the past)

Badge color coding: **green** = due today, **red** = overdue, **grey** = in the future. Clicking the badge removes the date again. Free-text recognition ("sometime next week") is deliberately *not* supported – it would have become unreliable.

### Minimalist Mode

A switch in settings that resets the app to its original, simple feature set: no projects, no date recognition, no clickable title – just Sooner/Later with tasks. Enabled by default on mobile devices, disabled on desktop devices (detected via a device heuristic); can be switched manually at any time.

### Appearance

- **Light/Dark mode**: On the very first visit, the device setting (`prefers-color-scheme`) is picked up automatically; freely switchable afterwards.
- **Accent color**: six color options (green, blue, red, orange, white, grey).

### Keyboard Shortcuts

| Key | Effect |
|---|---|
| `+` | Opens the input field for a new task (when not currently typing in a field) |
| `Enter` | Adds the task / confirms an edit / confirms a highlighted project suggestion |
| `Esc` | Closes the currently open panel, or cancels an edit |
| `↓` / `↑` | Navigates through project suggestions while typing `#` |

### Language

The interface automatically detects the browser language and shows German or English – no manual setting required.

## Settings Overview

| Section | Setting | Effect |
|---|---|---|
| Appearance | Light Mode | Toggles light/dark |
| Appearance | Accent color | Six color options |
| Archive | Use archive | Off = completed tasks are deleted permanently right away |
| Mode | Minimalist mode | Disables projects and date recognition entirely, app behaves like its original state |
| Projects | Use projects | Master switch: turns the entire `#project` feature on/off |
| Projects | Show project tasks on home | Only relevant when projects are enabled: hides tasks with a project from the "All" view (they remain visible in their own project view) |
| Date | Use date recognition | Master switch: turns automatic date recognition while typing on/off |
| Date | Show due date | Only relevant when date recognition is enabled: hides the date badges without turning off recognition itself (dates keep being captured in the background) |

## Data Storage & Privacy

**All data – tasks, projects, settings – is stored exclusively in the local `localStorage` of the respective browser.** There is no server, no backend, no analytics or tracking scripts, no account, and no synchronization. Nothing ever leaves the computer or device.

### Advantages

- **Full privacy**: No one but the person at the device sees the data; nothing is ever transmitted to third parties.
- **Works offline**: Once the file has been opened once, no internet connection is needed anymore.
- **No account needed**: No registration, no email address, no password.
- **Fast**: No network round-trip, everything runs directly in the browser.

### Risks

- **No device/browser switching**: The data is tied to exactly this one browser on exactly this one device. Opening the file in a different browser or on a different device shows an empty list – there is (currently) no export/import or sync feature.
- **Erasable through browser actions**: Clearing the browser cache/storage ("clear browsing data"), using private/incognito mode, or resetting the profile permanently deletes the data.
- **No automatic backup**: There is no cloud copy. Losing or damaging the device, or reinstalling the operating system, typically means losing the data.
- **Not shared across browsers**: Even multiple browsers on the same device (e.g. Chrome and Safari) each have their own, separate set of data.

**Recommendation**: For important, long-term content, consider occasional manual backups until an export feature exists – and deliberately stick to the same browser on the same device for ongoing use.

## Usage

1. Download `index.html`, or leave it in the repository folder.
2. Open the file in a browser by double-clicking it or via "Open File" (works directly over `file://`, no server required).
3. Optionally, host the file on any simple web server or hosting service (e.g. GitHub Pages) to access it via a URL – this doesn't change the storage behavior (still local to the respective browser).
