---
title: GitLens Release Notes
description: GitLens Release Notes
taxonomy:
  category: gitlens
---

Find out what’s new, what’s fixed, or just take a trip down memory lane remembering those bugs of yesterday.

Check out our [Changelog](https://github.com/gitkraken/vscode-gitlens/blob/main/CHANGELOG.md) to see linked issues and past changes.

<a href="https://marketplace.visualstudio.com/items?itemName=eamodio.gitlens" target="_blank" class="button button--basic ">Install Current Version Now</a>

Features marked with a ✨ require a [trial or paid plan](https://www.gitkraken.com/gitlens/pricing) for use on privately hosted repos \
Features marked with a ☁️ require a GitKraken Account, with access level based on your [plan](https://www.gitkraken.com/gitlens/pricing), e.g. Free, Pro, etc

---

<a id="v14-5"></a>

## Version 14.5

#### Monday, November 13, 2023

GitLens 14.5 features the all new Cloud Patches preview ☁️, which allows you to easily share changes with other developers by creating a Cloud Patch from your WIP, commit or stash and sharing the generated link with your teammates. Other notable enhancements include opening multiple tabs of Commit Graph & Focus.

<img src="/wp-content/uploads/gl-14-5-hero.png" class="img-responsive center img-bordered">

### Cloud Patches preview ☁️

[Cloud Patches](https://www.gitkraken.com/solutions/cloud-patches) aim to shift developer collaboration earlier in the process for faster feedback, cleaner pull requests, and overcoming tricky code challenges as a team. Create Cloud Patches from working changes, commits, stashes, or comparisons  &mdash;  then share the patch URL with others to get feedback and iterate on the changes together. It is currently available across GitLens, GitKraken Client, and GitKraken CLI, with plans to add commenting and more capabilities soon.

### Open Multiple Commit Graph & Focus Tabs

Open multiple instances of the Commit Graph, Focus, and Visual File History views, side-by-side, to look at multiple repositories at once or just different visualizations of the same repository.

### Thank you to our contributors

Shout-out to all of our awesome contributors for this release!

- Aidos Kanapyanov ([@aidoskanapyanov](https://github.com/aidoskanapyanov))
- Shashank Shastri ([@Shashank-Shastri](https://github.com/Shashank-Shastri))

### Added

- Adds a preview of [Cloud Patches](https://www.gitkraken.com/solutions/cloud-patches), an all-new ☁️ feature &mdash; engage in early collaboration before the pull request:
  - Share your work with others by creating a Cloud Patch from Working Changes, Commits, Stashes or Comparisons
  - View Cloud Patches from URLs shared to you and apply them to your working tree or to a new or existing branch
  - Manage your Cloud Patches from the new _Cloud Patches_ view in the GitLens side bar
  - Adds a _Share as Cloud Patch..._ command to the command palette and to the _Share_ submenu in applicable GitLens views
  - Adds a `gitlens.cloudPatches.enabled` setting to specificy whether to enable Cloud Patches (defaults to `true`)
- Adds support to open multiple instances of the _Commit Graph_, _Focus_, and _Visual File History_ in the editor area
  - Adds a _Split Commit Graph_ command to the _Commit Graph_ tab context menu
  - Adds a `gitlens.graph.allowMultiple` setting to specify whether to allow opening multiple instances of the _Commit Graph_ in the editor area
  - Adds a _Split Focus_ command to the _Focus_ tab context menu
  - Adds a `gitlens.focus.allowMultiple` setting to specify whether to allow opening multiple instances of the _Focus_ in the editor area
  - Adds a _Split Visual File History_ command to the _Visual File History_ tab context menu
  - Adds a `gitlens.visualHistory.allowMultiple` setting to specify whether to allow opening multiple instances of the _Visual File History_ in the editor area
- Adds a _Generate Commit Message (Experimental)_ button to the SCM input when supported (currently `1.84.0-insider` only)
  - Adds a `gitlens.ai.experimental.generateCommitMessage.enabled` setting to specify whether to enable GitLens' experimental, AI-powered, on-demand commit message generation &mdash; closes [#2652](https://github.com/gitkraken/vscode-gitlens/issues/2652)
- Improves the experience of the _Search Commits_ quick pick menu
  - Adds a stateful authors picker to make it much easier to search for commits by specific authors
  - Adds a file and folder picker to make it much easier to search for commits containing specific files or in specific folders
- Adds ability to sort repositories in the views and quick pick menus &mdash; closes [#2836](https://github.com/gitkraken/vscode-gitlens/issues/2836) thanks to [PR #2991](https://github.com/gitkraken/vscode-gitlens/pull/2991)
  - Adds a `gitlens.sortRepositoriesBy` setting to specify how repositories are sorted in quick pick menus and views by Aidos Kanapyanov ([@aidoskanapyanov](https://github.com/aidoskanapyanov))
- Adds a _[Show|Hide] Merge Commits_ toggle to the Commits\_ view &mdash; closes [#1399](https://github.com/gitkraken/vscode-gitlens/issues/1399) thanks to [PR #1540](https://github.com/gitkraken/vscode-gitlens/pull/1540) by Shashank Shastri ([@Shashank-Shastri](https://github.com/Shashank-Shastri))
- Adds a _Filter Commits by Author..._ commands to the _Commits_ view and comparisons context menus to filter commits in the _Commits_ view by specific authors
- Adds ability to publish to a remote branch to a specific commit using the _Push to Commit_ command
- Adds an _Open Comparison on Remote_ command to comparisons in views
- Adds a _Share > Copy Link to Repository_ command on branches in the views
- Adds _Share > Copy Link to Branch_ and _Share > Copy Link to Repository_ commands on the current branch status in the _Commits_ view
- Adds a _Clear Reviewed Files_ command to comparisons to clear all reviewed files &mdash; closes [#2987](https://github.com/gitkraken/vscode-gitlens/issues/2987)
- Adds a _Collapse_ command to many view nodes
- Adds a `gitlens.liveshare.enabled` setting to specify whether to enable integration with Visual Studio Live Share

### Changed

- Improves accuracy, performance, and memory usage related to parsing diffs, used in _Changes_ hovers, _Changes_ file annotations, etc
- Improves confirmation messaging in the _Git Command Palette_
- Refines merge/rebase messaging when there is nothing to do &mdash; refs [#1660](https://github.com/gitkraken/vscode-gitlens/issues/1660)
- Improves view messaging while loading/discovering repositories
- Honors VS Code's `git.useForcePushWithLease` and `git.useForcePushIfIncludes` settings when force pushing
- Changes _File Heatmap_ annotations to not color the entire line by default. Want it back, add `line` to the `gitlens.heatmap.locations` setting

### Fixed

- Fixes [#2997](https://github.com/gitkraken/vscode-gitlens/issues/2997) - "push to commit" pushes everything instead of up to the selected commit
- Fixes [#2615](https://github.com/gitkraken/vscode-gitlens/issues/2615) - Source Control views disappear after opening a file beyond a symbolic link
- Fixes [#2443](https://github.com/gitkraken/vscode-gitlens/issues/2443) - UNC-PATH: File History changes not displaying any changes when open
- Fixes [#2625](https://github.com/gitkraken/vscode-gitlens/issues/2625) - full issue ref has escape characters that break hover links
- Fixes [#2987](https://github.com/gitkraken/vscode-gitlens/issues/2987) - Unable to remove all marks on reviewed files with a single operation
- Fixes [#2923](https://github.com/gitkraken/vscode-gitlens/issues/2923) - TypeError: Only absolute URLs are supported
- Fixes [#2926](https://github.com/gitkraken/vscode-gitlens/issues/2926) - "Open File at Revision" has incorrect editor label if revision contains path separator
- Fixes [#2971](https://github.com/gitkraken/vscode-gitlens/issues/2971) - \[Regression\] The branch column header text disappears when you have a hidden ref
- Fixes [#2814](https://github.com/gitkraken/vscode-gitlens/issues/2814) - GitLens Inspect: "Files Changed" not following when switching between commits in File History
- Fixes [#2952](https://github.com/gitkraken/vscode-gitlens/issues/2952) - Inline blame not working because of missing ignoreRevsFile
- Fixes issue where _Changes_ hovers and _Changes_ file annotations sometimes weren't accurate
- Fixes intermittent issue where inline blame and other revision-based editor features are unavailable when repository discovery takes a bit
- Fixes intermittent issues where details sometimes get cleared/overwritten when opening the _Commit Details_ view
- Fixes issue when clicking on commits in the Visual File History to open the _Commit Details_ view
- Fixes issue opening stashes in the _Commit Details_ view from the _Stashes_ view
- Fixes issue where GitHub/GitLab enriched autolinks could incorrectly point to the wrong repository
- Fixes issue showing folder history in the _File History_ view when there are uncommitted changes (staged or unstaged)
- Fixes issue when pushing to a remote branch with different name than the local
- Fixes tooltip styling/theming on the _Commit Graph_
- Fixes issues staged files in repositories not "opened" (discovered) by the built-in Git extension


<a id="v14-4"></a>

## Version 14.4

#### Friday, October 13, 2023

GitLens 14.4 is here, featuring new enhancements to _Focus View_, the addition of _Working Changes_ to _Commit Details_ and _Graph Details_, and some performance improvements to _Inline_ and _Status Bar Blame_.

<img src="/wp-content/uploads/gl-14-4-hero.png" class="img-responsive center img-bordered">

### Focus View Enhancements

_Focus View_ now includes the ability to pin and snooze items. These options appear as clickable icons in the new snooze/pin column in the view. Pinned issues and pull requests will always show at the top of the list, while snoozed items will be hidden and moved to the new Snoozed section. To unsnooze an item, simply click on the Snoozed section header and select the unsnooze icon for that item in the pin/snooze column.

<img src="/wp-content/uploads/gl-14-4-focus-view-update.png" class="img-responsive center img-bordered">

### Working Changes Tab

_Commit Details_ and _Graph Details_ now include a separate _Working Changes_ tab. This allows you to view your work-in-progress changes any time without losing context on your current selected change. The tab includes the ability to stage and unstage changes, open files to view changes, and open the changes in the _Commit Graph_ and SCM view.

<img src="/wp-content/uploads/gl-14-4-commit-details-wip.png" class="img-responsive center img-bordered">

### Inline and Status Bar Blame Performance Improvements

Inline blame and status bar blame now appear faster on hover. This performance improvement is especially notable when using connected remote integrations.

### Added

- Adds a _Working Changes_ tab to the _Commit Details_ and _Graph Details_ views to show your working tree changes
  - Adds _Stage Changes_ and _Unstage Changes_ commands to files on the _Working Changes_ tab
- Adds a _[Show|Hide] Merge Commits_ toggle to the _File History_ view &mdash; closes [#2104](https://github.com/gitkraken/vscode-gitlens/issues/2104) & [#2944](https://github.com/gitkraken/vscode-gitlens/issues/2944)
  - Adds a `gitlens.advanced.fileHistoryShowMergeCommits` setting to specify whether merge commits will be show in file histories
- Adds deep link support for workspaces in the _GitKraken Workspaces_ view
  - Deep link format: `https://gitkraken.dev/link/workspaces/{workspaceId}`
  - Adds a _Share_ submenu with a _Copy Link to Workspace_ command to workspaces in the _GitKraken Workspaces_ view

### Changed

- Improves performance of inline blame, status bar blame, and hovers especially when working with remotes with connected integrations
- Changes the _File History_ view to follow renames and filters out merge commits by default &mdash; closes [#2104](https://github.com/gitkraken/vscode-gitlens/issues/2104) & [#2944](https://github.com/gitkraken/vscode-gitlens/issues/2944)
- Changes the _File History_ view to allow following renames while showing history across all branches (which was a previous limitation of Git) &mdash; closes [#2828](https://github.com/gitkraken/vscode-gitlens/issues/2828)
- Changes to use our own implementation of `fetch`, `push`, and `pull` Git operations, rather than delegating to VS Code to avoid limitations especially with GitKraken Workspaces. Please report any issues and you can revert this (for now) by setting `"gitlens.experimental.nativeGit"` to `"false"` in your settings
- Relaxes PR autolink detection for Azure DevOps to use `PR <number>` instead of `Merged PR <number>` &mdash; closes [#2908](https://github.com/gitkraken/vscode-gitlens/issues/2908)
- Changes wording on `Reset Stored OpenAI Key` command to `Reset Stored AI Key` to reflect support for other providers

### Fixed

- Fixes [#2941](https://github.com/gitkraken/vscode-gitlens/issues/2941) - Invalid Request when trying to generate a commit message using Anthropic API
- Fixes [#2940](https://github.com/gitkraken/vscode-gitlens/issues/2940) - Can't use Azure OpenAI model because i can't save the openai key because of the verification
- Fixes [#2928](https://github.com/gitkraken/vscode-gitlens/issues/2928) - Apply Changes should create new files when needed
- Fixes [#2896](https://github.com/gitkraken/vscode-gitlens/issues/2896) - Repositories view stuck in loading state
- Fixes [#2460](https://github.com/gitkraken/vscode-gitlens/issues/2460) - Gitlens Remote provider doesn't work properly in "Commit graph" view
- Fixes issue with "View as [List|Tree]" toggle not working in the _Commit Details_ view
- Fixes an issue with deep links sometimes failing to properly resolve when a matching repository without the remote is found
- Fixes an issue in the _Commit Graph_ where commits not in the history of a merge commit were showing in the same column
- Fixes `Reset Stored AI Key` command to work for the current provider
- Fixes an issue with parsing some renames in log output

<a id="v14-3"></a>

## Version 14.3

#### Thursday, September 7, 2023

This release focuses on quality of life improvements to the _Commit Graph_, _Search & Compare_, and File History as well bug fixes around the deep links and viewing diffs.

<img src="/wp-content/uploads/gl-14-3-hero.png" class="img-responsive center img-bordered">

### Commit Graph Improvements

<img src="/wp-content/uploads/gl-14-3-multiple-open-graphs.png" class="img-responsive center img-bordered">

You can now have a Commit Graph in the bottom Panel and one in the Editor Area open at the same time. This enables viewing more than repo at a time or different areas of the same repo at the same time.

<img src="/wp-content/uploads/gl-14-3-commit-graph-prefers.png" class="img-responsive center img-bordered">

Additionally, you can also set a preference for which mode to use by default, which you can set from the gear icon on the Commit Graph or by adding `gitlens.graph.layout` in settings. _GitLens: Show Commit Graph_ from the command palette will honor that preference.

### Search & Compare Review Checkboxes

<img src="/wp-content/uploads/gl-14-3-search-compare-checkboxes.png" class="img-responsive center img-bordered">

From the _Search & Compare_, you now have checkboxes next to each files to help keep track of files you've reviewed. This was an long sought after request by the community, you asked and we delivered!

### Thank you to our contributors

Shout-out to our awesome contributor for this release!

- Omar Ghazi ([@omarfesal](https://github.com/omarfesal))

### Added

- Adds checkboxes to files in the _Search & Compare_ view to allow for tracking review progress &mdash; closes [#836](https://github.com/gitkraken/vscode-gitlens/issues/836)
- Allows the _Commit Graph_ to be open in the panel and in the editor area simultaneously
- Adds an _Open Changes_ button to commits in the file history quick pick menu &mdash; closes [#2641](https://github.com/gitkraken/vscode-gitlens/issues/2641) thanks to [PR #2800](https://github.com/gitkraken/vscode-gitlens/pull/2800) by Omar Ghazi ([@omarfesal](https://github.com/omarfesal))

### Changed

- Changes the `gitlens.graph.layout` setting to be a default preference rather than a mode change

### Fixed

- Fixes [#2885](https://github.com/gitkraken/vscode-gitlens/issues/2885) - Folder History not show changed files of commit
- Fixes issues with opening changes (diffs) of renamed files
- Fixes issues with deep links including when opening VS Code from the deep link

<a id="v14-2"></a>

## Version 14.2

#### Friday, August 4, 2023

GitLens 14.2 arrives with a few hotly-requested improvements to the Focus View for even greater productivity in your daily workflow.

<img src="/wp-content/uploads/gl-14-2-hero.png" class="img-responsive center img-bordered">

## Focus View

The Focus View has been improved with a new unified experience and includes a few new features to help you navigate pull requests and issues.

<img src="/wp-content/uploads/gl-focus-changes-14-2.png" class="img-responsive center img-bordered">

Pull Requests and Issues have now been combined into a single view with tabs to quickly toggle between showing all items, pull requests, or issues only.

You can also click on a branch name to show the branch on the Commit Graph, and if you don't already have a remote configured for that branch you'll be guided to add it.

<img src="/wp-content/uploads/gl-focus-search-14-2.png" class="img-responsive center img-bordered">

Furthermore, we've added a search bar to the Focus View to help you quickly find pull requests or issues by their title.

### Thank you to our contributors

Shout-out to all of our awesome contributors for this release!

- Victor Hallberg ([@mogelbrod](https://github.com/mogelbrod))

### Added

- Improves the _Focus_ view experience
  - Unifies pull requests and issues into a single view
  - Adds tabs to switch between showing Pull Requests, Issues, or All
  - Adds a filter/search box to quickly find pull request or issues by title
  - Adds ability to click on a branch name to show the branch on the _Commit Graph_
- Adds a new command _Open Changed & Close Unchanged Files..._ to the command palette, the context menu of the _Commit Graph_ work-in-progress (WIP) row, and the SCM group context menu to open all changed files and close all unchanged files.
- Adds a new command _Reset Current Branch to Tip..._ to branch context menus in the _Commit Graph_ and in GitLens views to reset the current branch to the commit at the chosen branch's tip.

### Changed

- Changes _Compact Graph Column Layout_ context menu command to _Use Compact Graph Column_ for better clarity
- Changes _Default Graph Column Layout_ context menu command to _Use Expanded Graph Column_ for better clarity
- Improves remote parsing for better integration support for some edge cases

### Fixed

- Fixes [#2823](https://github.com/gitkraken/vscode-gitlens/issues/2823) - Handle stdout/stderr Buffers in shell run() &mdash; thanks to [PR #2824](https://github.com/gitkraken/vscode-gitlens/pull/2824) by Victor Hallberg ([@mogelbrod](https://github.com/mogelbrod))
- Fixes issues with missing worktrees breaking the Worktrees view and Worktree quick pick menus

<a id="v14-1"></a>

## Version 14.1

### Thursday, July 13, 2023

We're delighted to introduce GitLens 14.1. We've enhanced integration between GitKraken Cloud and VS Code workspaces. You can now link a GitKraken Cloud workspace and VS Code workspace and GitLens can automatically update your VS Code workspace when new repositories are added to its linked counterpart.
Additionally, we've added deep link support for comparisons in the _Search & Compare_ view, coupled with a new _Copy Link to Comparison_ command in a new _Share_ submenu, streamlining review and collaboration.

We've also added support for Anthropic's new Claude 2 model for use with our experimental AI features. You can switch to it using the _Switch AI Model_ command from the Command Palette.

<img src="/wp-content/uploads/gl-14-1-hero.png" class="img-responsive center img-bordered">

## Workspace Linking

When you create a VS Code workspace from a GitKraken Cloud workspace, the two are now linked. You can open a linked VS Code workspace from its cloud workspace using the new _Open VS Code Workspace in New Window_ option (hold <kbd>alt</kbd> to open in the current window).

<img src="/wp-content/uploads/gl-linked-workspaces-14-1.png" class="img-responsive center img-bordered">

When repositories are added to a GitKraken Cloud workspace, you can automatically add those repositories to its linked VS Code workspace when that workspace is opened. You can choose to automatically add new repositories, be prompted to add them, or disable auto-adding repositories altogether for that workspace. You'll be prompted to choose your desired behavior when creating the VS Code workspace, but it can also be changed at any time via the _Change Linked Workspace Auto-Add Behavior..._ context menu command on the _Current Window_ item or its linked workspace in the _GitKraken Workspaces_ view.

<img src="/wp-content/uploads/gl-linked-auto-add-settings-14-1.png" class="img-responsive center img-bordered">

You can also manually add repositories to the VS Code workspace at any time using the new _Add Repositories from Linked Workspace..._ context menu command.

<img src="/wp-content/uploads/gl-linked-add-repositories-14-1.png" class="img-responsive center img-bordered">

## Comparison Deep Links

You can now deep link directly into comparisons in the _Search & Compare_ view. This includes comparisons between branches, tags, and commits. You can also copy a deep link to a comparison to your clipboard using the new _Copy Link to Comparison_ context menu command on the _Share_ submenu.

<img src="/wp-content/uploads/gl-deep-link-comparison-14-1.png" class="img-responsive center img-bordered">

### Thank you to our contributors

Shout-out to all of our awesome contributors for this release!

- Neil Ghosh ([@neilghosh](https://github.com/neilghosh))
- Leo Dan Peña ([@leo9-py](https://github.com/leo9-py))

### Added

- Adds the ability to link a GitKraken Cloud workspace with an associated VS Code workspace
  - Adds ability to automatically add repositories to the current VS Code workspace that were added to its associated GitKraken Cloud workspace, if desired
    - Adds a _Change Linked Workspace Auto-Add Behavior..._ context menu command on the _Current Window_ and linked workspace to control the desired behavior
    - Adds an _Add Repositories from Linked Workspace..._ context menu command on the _Current Window_ item to trigger this manually
  - Adds a new _Open VS Code Workspace_ command to open an existing VS Code workspace associated with a GitKraken Cloud workspace
  - Adds a highlight (green) to the linked GitKraken Cloud workspace when the current VS Code workspace is associated with it in the _GitKraken Workspaces_ view
- Adds deep link support for comparisons in the _Search & Compare_ view
  - Deep link format: `vscode://eamodio.gitlens/r/{repoId}/compare/{ref1}[..|...]{ref2}?[url={remoteUrl}|path={repoPath}]`
  - Adds a _Share_ submenu with a _Copy Link to Comparison_ command to comparisions in the _Search & Compare_ view
- Adds support for Anthropic's Claude 2 AI model
- Adds a progress notification while repositories are being added to a GitKraken Cloud workspace

### Changed

- Improves scrolling performance on the _Commit Graph_
- Renames _Convert to VS Code Workspace_ to _Create VS Code Workspace_ for workspaces in the _GitKraken Workspaces_ view to better reflect the behavior of the action
- Hides _Create VS Code Workspace_ and _Locate All Repositories_ commands on empty workspaces in the _GitKraken Workspaces_ view

### Fixed

- Fixes [#2798](https://github.com/gitkraken/vscode-gitlens/issues/2798) - Improve response from OpenAI if key used is tied to a free account
- Fixes [#2785](https://github.com/gitkraken/vscode-gitlens/issues/2785) - Remote Provider Integration URL is broken &mdash; thanks to [PR #2786](https://github.com/gitkraken/vscode-gitlens/pull/2786) by Neil Ghosh ([@neilghosh](https://github.com/neilghosh))
- Fixes [#2791](https://github.com/gitkraken/vscode-gitlens/issues/2791) - Unable to use contributors link in README.md &mdash; thanks to [PR #2792](https://github.com/gitkraken/vscode-gitlens/pull/2792) by Leo Dan Peña ([@leo9-py](https://github.com/leo9-py))
- Fixes [#2793](https://github.com/gitkraken/vscode-gitlens/issues/2793) - Requesting username change in contributors README page &mdash; thanks to [PR #2794](https://github.com/gitkraken/vscode-gitlens/pull/2794) by Leo Dan Peña ([@leo9-py](https://github.com/leo9-py))
- Fixes some rendering issues when scrolling in the _Commit Graph_
- Fixes an issue with some shared workspaces not showing up in the _GitKraken Workspaces_ view when they should
- Fixes an issue when adding repositories to a workspace in the _GitKraken Workspaces_ view where the added repository would show as missing until refreshing the view

<a id="v14-0"></a>

## Version 14.0 &mdash; GitLens Reimagined

### Wednesday, June 14, 2023

We're thrilled to announce the release of GitLens 14 with a reimagined GitLens experience! We restructured our views layout to better enhance productivity and focus by grouping views contextually, giving you easy access to the right information when you need it. The commit graph has been moved to the (bottom) panel, providing convenient and persistent access to the graph and its details. We've also rethought and rebuilt our Welcome and Walkthrough as well as the Home view to provide a friendlier onboarding experience.

The power of GitKraken Workspaces now in GitLens. Workspaces are an easy way to work with and manage multiple repositories and include the ability to convert to and from a VS Code workspace, with further improvements coming soon. Create workspaces just for yourself or share (coming soon to GitLens) them with your team for faster onboarding and better collaboration.

<img src="/wp-content/uploads/gl-14-0-hero.png" class="img-responsive center img-bordered">

## New Views layout

We've grouped views contextually and introduced GitLens Inspect, giving you easy access to the right information when you need it. We've moved some of our views from their previous home, in Source Control, into either the GitLens or the new GitLens Inspect side bar.

<img src="/wp-content/uploads/gl-views-and-features.png" class="img-responsive center img-bordered">

### GitLens Inspect side bar

The all-new GitLens Inspect is like an x-ray or developer tools inspector into your code, which focuses on providing contextual information and insights to what you're actively working on.

<img src="/wp-content/uploads/gl-inspect-side-bar.png" class="img-responsive center img-bordered">

Views include:

- Commit Details
- Line History
- File History
- Visual File History
- Search & Compare

_Pro tip: you can drag the entire GitLens Inspect Side Bar onto your secondary Side Bar, without needing to arrange views on-by-one._

### GitLens side bar

We've re-focused this to be the home of GitKraken services (e.g. GitKraken Workspaces) as well as discovery, help, and support.

<img src="/wp-content/uploads/gl-side-bar-v14.png" class="img-responsive center img-bordered">

Views include:

- Home view
- GitKraken Workspaces
- GitKraken Account

### Source Control side bar

We've slimmed down this side bar to only contain views that are focused on your repositories.

<img src="/wp-content/uploads/gl-side-bar.png" class="img-responsive center img-bordered">

Views include:

- Commits
- Branches
- Remotes
- Stashes
- Tags
- Worktrees
- Contributors
- Repositories (hidden by default)

### (Bottom) Panel

The new home for the Commit Graph, providing convenient and easy access to the graph and the new Commit Graph Details view.

<img src="/wp-content/uploads/gl-bottom-panel.png" class="img-responsive center img-bordered">

Views include:

- Commit Graph
- Commit Graph Details

_Pro tip: You can toggle the Commit Graph between Panel and Editor layouts by clicking the "cog" icon on the upper right corner of the Graph view._
_Pro tip 2: When the Commit Graph is in the Panel Layout, you can quickly toggle it via the new __Toggle Commit Graph__ and __Toggle Maximized Commit Graph__ commands._

### Adopting the new views layout

Unless you opt into the new layout, which we recommend, your existing views will stay where they are. You can opt in at any time from _Reset Views Layout_ in the Command Palette.

## New Onboarding Experience

The rebuilt welcome goes beyond quick settings and now includes overviews of important features as well as bringing better visibility to the views and functionality GitLens offers. Along the same lines, we consolidated and streamlined our walkthroughs.

Also, we've made significant changes to the home view, with the help of your feedback, to refocus on quick access and discovery of many GitLens features.

## ☁️ GitKraken Workspaces

GitKraken Workspaces are a convenient way to group and manage multiple repositories. Cloud workspaces store the metadata of the grouped repositories and can be accessed across machines and GitKraken products. They can easily be imported into or created from VS Code workspaces.

<img src="/wp-content/uploads/gl-workspaces-sidebar.png" class="img-responsive center img-bordered">

Please note that while using cloud workspaces requires a free account, shared cloud workspaces, which are shared between GitKraken organizations and teams, require a trial or plan. Shared Workspaces functionality is coming soon to GitLens.

Workspaces can be accessed in the new GitKraken Workspaces view in the GitLens side bar.

## ✨ Commit Graph Enhancements

We’ve greatly improved the ease of access to the Commit Graph as well as additional change information and easy-to-use customization options.

### New Home in (Bottom) Panel

The Commit Graph has moved into the (bottom) panel, providing convenient and persistent access to the graph and its details. If you prefer the Graph in the editor area, you can toggle between Panel and Editor layouts by clicking the "cog" icon on the upper right corner of the Graph view.

### Minimap and Markers

The Minimap which shows an overview of commit activity, previously an experimental feature, is now on by default. You can now toggle between 'lines changed' and 'commits' in the minimap display.

With both the Minimap and the Commit Graph scrollbar, you can toggle specific markers on and off, including local branch, remote branch, stash, and tag markers. For the minimap, use the split minimap button, and for the scrollbar use the `Scroll Markers` submenu from the "cog" icon at the top of the scrollbar.

### New Column and Column Layout

The _Changes_ column, which shows the size of commit changes, is now visible by default. The column now also includes a count of the changed files, helping you quickly grasp the scale of each change.

Reset your columns between the _Default_ and the new _Compact_ set via the context menu on the graph column headers, making it easy to toggle into a more minimal experience.

### Added

- Adds an all-new Welcome experience to quickly get started with GitLens and discover features &mdash; even if you are familiar with GitLens, definitely check it out!
- Adds a new streamlined _Get Started with GitLens_ walkthrough
- Adds an all-new _Home_ view for quick access to GitLens features and _GitKraken Account_ for managing your account
- Adds a new reimagined views layout &mdash; see discussion [#2721](https://github.com/gitkraken/vscode-gitlens/discussions/2721) for more details
  - Rearranges the GitLens views for greater focus and productivity, including the new _GitLens Inspect_ and moved some of our views from Source Control into either _GitLens_ or _GitLens Inspect_.
  - Adds a new GitLens Inspect activity bar icon focuses on providing contextual information and insights to what you're actively working on
  - Adds a _Reset Views Layout_ command to reset all the GitLens views to the new default layout
- Adds an all-new _GitKraken Workspaces_ ☁️ feature as a side bar view, supporting interaction with local and cloud GitKraken workspaces, lists of repositories tied to your account.
  - Create, view, and manage repositories on GitKraken cloud workspaces, which are available with a GitKraken account across the range of GitKraken products
  - Automatically or manually link repositories in GitKraken cloud workspaces to matching repositories on your machine
  - Quickly create a GitKraken cloud workspace from the repositories in your current window
  - Open a GitKraken cloud workspace as a local, persisted, VS Code workspace file (further improvements coming soon)
  - Open a cloud workspace or repository in a new window (or your current window)
  - See your currently open repositories in the _Current Window_ section
  - Explore and interact with any repository in a GitKraken cloud workspace, some actions are currently limited to repositories which are open in your current window &mdash; ones highlighted in green
  - (Coming soon) Share your GitKraken cloud workspaces with your team or organization
- Adds new _Commit Graph_ ✨ features and improvements
  - Makes the _Panel_ layout the default for easy access to the Commit Graph with a dedicated details view
  - Adds two new options to the graph header context menu
    - `Reset Columns to Default Layout` - resets column widths, ordering, visibility, and graph column mode to default settings
    - `Reset Columns to Compact Layout` - resets column widths, ordering, visibility, and graph column mode to compact settings
  - Adds a _Toggle Commit Graph_ command to quickly toggle the graph on and off (requires the _Panel_ layout)
  - Adds a _Toggle Maximized Commit Graph_ command to maximize and restore the graph for a quick full screen experience (requires the _Panel_ layout)
  - Enables the _Minimap_ by default, as its no longer experimental, to provide a quick overview of of commit activity above the graph
    - Adds ability to toggle between showing commits vs lines changed in the minimap (note: choosing lines changed requires more computation)
    - Adds a legend and quick toggles for the markers shown on the minimap
    - Defers the loading of the minimap to avoid impacting graph performance and adds a loading progress indicator
    - Adds a `gitlens.graph.minimap.enabled` setting to specify whether to show the minimap
    - Adds a `gitlens.graph.minimap.dataType` setting to specify whether to show commits or lines changed in the minimap
    - Adds a `gitlens.graph.minimap.additionalTypes` setting to specify additional markers to show on the minimap
  - Makes the _Changes_ column visible by default (previously hidden)
    - Defers the loading of the _Changes_ column to avoid impacting graph performance and adds a loading progress indicator to the column header
    - Adds a changed file count in addition to the changed lines visualization
    - Improves the rendering of the changed line visualization and adds extra width to the bar for outlier changes so that they stand out a bit more
  - Adds an _Open Repo on Remote_ button to left of the repo name in the graph header
  - Improves contextual help on the search input as you type
  - Improves tooltips on _Branch/Tag_ icons to be more uniform and descriptive
  - Adds new context menu options to the _Commit Graph Settings_ (cog, above the scrollbar) to toggle which scroll marker to show
  - Improves alignment of scroll markers on the scrollbar, and adds a gap between the last column and the scrollbar
- Adds the ability to choose which AI provider, OpenAI or Anthropic, and AI model are used for GitLens' experimental AI features
  - Adds a _Switch AI Model_ command to the command palette and from the _Explain (AI)_ panel on the _Commit Details_ view
  - Adds a `gitlens.ai.experimental.provider` setting to specify the AI provider to use (defaults to `openai`)
  - Adds a `gitlens.ai.experimental.openai.model` setting to specify the OpenAI model (defaults to `gpt-3.5-turbo`) &mdash; closes [#2636](https://github.com/gitkraken/vscode-gitlens/issues/2636) thanks to [PR #2637](https://github.com/gitkraken/vscode-gitlens/pull/2637) by Daniel Rodríguez ([@sadasant](https://github.com/sadasant))
  - Adds a `gitlens.ai.experimental.anthropic.model` setting to specify the Anthropic model (defaults to `claude-v1`)
- Adds expanded deep link support
  - Adds cloning, adding a remote, and fetching from the target remote when resolving a deep link
  - Adds deep linking to a repository with direct file path support
- Adds the automatic restoration of all GitLens webviews when you restart VS Code
- Adds ability to control encoding for custom remote configuration &mdash; closes [#2336](https://github.com/gitkraken/vscode-gitlens/issues/2336)
- Improves performance and rendering of the _Visual File History_ and optimizes it for usage in the side bars
  - Adds a _Full history_ option to the _Visual File History_ &mdash; closes [#2690](https://github.com/gitkraken/vscode-gitlens/issues/2690)
  - Adds a loading progress indicator
- Adds _Reveal in File Explorer_ command to repositories
- Adds _Copy SHA_ command to stashes
- Adds new icons for virtual repositories

### Changed

- Changes header on _GitLens Settings_ to be consistent with the new Welcome experience
- Reduces the visual noise of currently inaccessible ✨ features in the side bars
- Performance: Improves rendering of large commits on the _Commit Details_ view
- Performance: Defers possibly duplicate repo scans at startup and waits until repo discovery is complete before attempting to find other repos
- Security: Disables Git access in Restricted Mode (untrusted)
- Security: Avoids dynamic execution in string interpolation

### Fixed

- Fixes [#2728](https://github.com/gitkraken/vscode-gitlens/issues/2728) - Submodule commit graph will not open in the panel layout
- Fixes [#2734](https://github.com/gitkraken/vscode-gitlens/issues/2734) - 🐛 File History: Browse ... not working
- Fixes [#2671](https://github.com/gitkraken/vscode-gitlens/issues/2671) - Incorrect locale information provided GitLens
- Fixes [#2689](https://github.com/gitkraken/vscode-gitlens/issues/2689) - GitLens hangs on github.dev on Safari
- Fixes [#2680](https://github.com/gitkraken/vscode-gitlens/issues/2680) - Git path with spaces is not properly quoted in the command
- Fixes [#2677](https://github.com/gitkraken/vscode-gitlens/issues/2677) - Merging branch produces path error
- Fixes an issue with comparison commands on File/Line History views
- Fixes an issue with stale state on many webviews when shown after being hidden
- Fixes an issue with fetch/push/pull on the _Commit Graph_ header
- Fixes an issue where _Branch / Tag_ items on the _Commit Graph_ sometimes wouldn't expand on hover
- Fixes an issue where some command were showing up on unsupported schemes
- Fixes an issue where the file/line history views could break because of malformed URIs

<a id="v13-6"></a>

## Version 13.6

### Thursday, May 11, 2023

GitLens 13.6 brings a range of enhancements and additions to the Commit Graph and refinements to our context menus. We've made improvements to the layout, condensing author names and column titles into avatars and icons when sized to minimums, and added flexibility of rearranging and moving columns as desired. This allows for a more streamlined and personalized GitLens experience. We have also updated the Commit Graph's toolbar to dynamically show a Push or Pull action, depending on a branch's state in relation to its upstream remote.

<img src="/wp-content/uploads/gl-13-6-hero.png" class="img-responsive center img-bordered">

## Context Menu Updates

<img src="/wp-content/uploads/gl-13-6-context-menu-update.gif" class="img-responsive center img-bordered">

To improve structure and findability of our menu options, we’ve made several changes to our context menus. Many Copy Remote URL commands, which were previously in a Copy As submenu, have been moved to a Share submenu within GitLens views, which aligns with VS Code menus. And once [microsoft/vscode#176316](https://github.com/microsoft/vscode/issues/176316) lands we will move the rest of the Copy Remote URL commands into the appropriate Share submenu. This reorganization consolidates related commands and makes it easier to locate and utilize them.

Similarly, the Copy SHA and Copy Message commands, previously nested in submenus, have been promoted to the root of the context menu. This elevates their visibility and enables quick access for performing actions on commits. Additionally, the Copy Relative Path command has been relocated to the root of the context menu. These adjustments enhance convenience when working with file paths.

### ✨ Commit Graph Enhancements

We’ve made it easier to customize your Commit Graph experience as well as improvements for better readability when in compact layouts.

#### Compact Graph Improvements

<img src="/wp-content/uploads/gl-13-6-graph-customize-columns.gif" class="img-responsive center img-bordered">

Previously unmovable columns within the Commit Graph can now be rearranged and customized according to your preferences. This flexibility enables you to arrange the columns in a way that best suits their workflow and priorities.

In addition, we have implemented a more compact layout by removing the commit icon when avatars are hidden. This optimization maximizes the utilization of screen space and results in a cleaner and more streamlined visual representation.

Moreover, the Author column now displays avatars instead of text when sized to its minimum width. That combined with the compact layout for the Graph column provide a nice compact experience with no loss of fidelity.

#### Column Headers

<img src="/wp-content/uploads/gl-13-6-graph-show-hide-columns.gif" class="img-responsive center img-bordered">

Commit Graph column headers have received dynamic behavior for enhanced readability. When the Commit Graph columns are compacted, the column headers seamlessly switch from displaying text to icons. This adaptation ensures that crucial information remains visible, even in constrained display settings.

### Stash Improvements

We've added the ability to rename stashes. If you are like me and often stash changes in a rush with very poor names, e.g. "wip" and then kick yourself later for not providing a more descriptive name, the this feature is for you. You can now rename any stash at any time.

You can now search within stashes using the Commit Graph, the Search & Compare view, or the Search Commits command. This improvement facilitates efficient navigation and retrieval of specific stash entries.

### Added

- Adds the ability to rename stashes &mdash; closes [#2538](https://github.com/gitkraken/vscode-gitlens/issues/2538)
  - Adds a new _Rename Stash..._ command to the _Stashes_ view
- Adds new _Commit Graph_ features and improvements
  - Adds a _Push_ or _Pull_ toolbar button depending the current branch being ahead or behind it's upstream
  - Adds support for the _Commit Graph_ over [Visual Studio Live Share](https://visualstudio.microsoft.com/services/live-share/) sessions
  - Adds the ability to move all of the columns, including the ones that were previously unmovable
  - Automatically switches column headers from text to icons when the column's width is too small for the text to be useful
  - Automatically switches the Author column to shows avatars rather than text when the column is sized to its minimum width
- Adds the ability to search stashes when using the commit search via the _Commit Graph_, _Search & Compare_ view, or the _Search Commits_ command
- Adds an _Open Visual File History_ command to the new _File History_ submenu on existing context menus
- Allows the _Repositories_ view for virtual repositories
- Honors the `git.repositoryScanIgnoredFolders` VS Code setting
- Adds _Share_, _Open Changes_, and _Open on Remote (Web)_ submenus to the new editor line numbers (gutter) context menu
- Adds an _Open Line Commit Details_ command to the _Open Changes_ submenus on editor context menus
- Adds an _Open Changes_ submenu to the row context menu on the _Commit Graph_

### Changed

- Refines and reorders many of the GitLens context menus and additions to VS Code context menus
  - Moves _Copy Remote \* URL_ commands from the _Copy As_ submenu into the _Share_ submenu in GitLens views
  - Adds a _Share_ submenu to Source Control items
  - Moves _Copy SHA_ and _Copy Message_ commands on commits from the _Copy As_ submenu into the root of the context menu
  - Moves _Copy Relative Path_ command on files from the _Copy As_ submenu into the root of the context menu
  - Moves file history commands into a _File History_ submenu
  - Moves _Open \* on Remote_ commands into _Open on Remote (Web)_ submenu
  - Renames the _Commit Changes_ submenu to _Open Changes_
  - Renames _Show Commit_ command to _Quick Show Commit_ and _Show Line Commit_ command to _Quick Show Line Commit_ for better clarity as it opens a quick pick menu
- Changes the file icons shown in many GitLens views to use the file type's theme icon (by default) rather than the status icon
  - Adds a `gitlens.views.commits.files.icon` setting to specify how the _Commits_ view will display file icons
  - Adds a `gitlens.views.repositories.files.icon` setting to specify how the _Repositories_ view will display file icons
  - Adds a `gitlens.views.branches.files.icon` setting to specify how the _Branches_ view will display file icons
  - Adds a `gitlens.views.remotes.files.icon` setting to specify how the _Remotes_ view will display file icons
  - Adds a `gitlens.views.stashes.files.icon` setting to specify how the _Stashes_ view will display file icons
  - Adds a `gitlens.views.tags.files.icon` setting to specify how the _Tags_ view will display file icons
  - Adds a `gitlens.views.worktrees.files.icon` setting to specify how the _Worktrees_ view will display file icons
  - Adds a `gitlens.views.contributors.files.icon` setting to specify how the _Contributors_ view will display file icons
  - Adds a `gitlens.views.searchAndCompare.files.icon` setting to specify how the _Search & Compare_ view will display file icons
- Renames _Delete Stash..._ command to _Drop Stash..._ in the _Stashes_ view
- Removes the commit icon when hiding avatars in the _Commits_ view to allow for a more compact layout
- Limits Git CodeLens on docker files &mdash; closes [#2153](https://github.com/gitkraken/vscode-gitlens/issues/2153)
- Shows progress notification for deep links earlier in the process &mdash; closes [#2662](https://github.com/gitkraken/vscode-gitlens/issues/2662)

### Fixed

- Fixes [#2664](https://github.com/gitkraken/vscode-gitlens/issues/2664) - Terminal run Git command can be "corrupted" if there is previous text waiting in the terminal
- Fixes [#2660](https://github.com/gitkraken/vscode-gitlens/issues/2660) - Commands executed in the terminal fail to honor found Git path
- Fixes [#2654](https://github.com/gitkraken/vscode-gitlens/issues/2654) - Toggle zen mode not working until you restart vscode
- Fixes [#2629](https://github.com/gitkraken/vscode-gitlens/issues/2629) - When on VSCode web, add handling for failing repo discovery
- Fixes many issues with using GitLens over [Visual Studio Live Share](https://visualstudio.microsoft.com/services/live-share/) sessions
- Fixes mouse scrubbing issues with the minimap on the _Commit Graph_
- Fixes _Refresh Repository Access_ and _Reset Repository Access Cache_ commands to always be available
- Fixes state not being restored on the Home webview
- Fixes getting the oldest unpushed commit when there is more than 1 remote
- Fixes an issue with the quick input on the _Git Command Palette_ unexpectedly going back to the previous step
- Fixes GitLens access tooltip not being visible when hovering in the _Commit Graph_

### Removed

- Removes "Open Commit on Remote" command from the VS Code Timeline view as it can no longer be supported &mdash; see [microsoft/vscode#177319](https://github.com/microsoft/vscode/issues/177319)

<a id="v13-5"></a>

## Version 13.5

### Thursday, Apr 6, 2023

With 13.5, we've added the ability to switch to an alternate panel layout for the Commit Graph, which moves the Commit Graph into the bottom panel and adds a new Commit Graph Details view alongside on the right, for more convenient and persistent access. You can now also switch to a compact layout for the Graph column and shrink the Branch / Tag column to a single icon to reduce the space and allow you to focus on what you deem most important. You can now take action on your pull requests in the Focus View, with the new ability to create or switch branches or worktrees. We've also heard your feedback that the Commit Details view pinning was confusing and hard to work with, so 13.5 includes many improvements to make that experience better. We've also continued our quest to reduce the size and improve performance of GitLens and have shaved another ~7% off the GitLens bundle.

<img src="/wp-content/uploads/gl-13-5-hero.png" class="img-responsive center img-bordered">

### ✨ Commit Graph Layouts

<img src="/wp-content/uploads/gl-commit-graph-panel-layout-view.png" class="img-responsive center img-bordered">

The new panel layout brings even more flexibility and customization options to GitLens. While using the panel layout, GitLens moves the Commit Graph into the bottom panel and adds a new Commit Graph Details view alongside on the right. If the layout in the bottom panel doesn't suit your needs you can move the Commit Graph around to other locations (side bar, secondary side bar, etc) to suit your preferences. Whether you prefer to have the Commit Graph in the editor or in a separate panel, GitLens makes it easy to switch and find the layout that works best for you.

<img src="/wp-content/uploads/gl-commit-graph-panel-layout-change.gif" class="img-responsive center img-bordered">

To switch to the panel layout, simply click on the Commit Graph settings cog located at the top right of the Commit Graph. From there, select the "Switch Commit Graph to Panel Layout" option, and if you want to switch back follow the same steps and choose "Switch Commit Graph to Editor Layout".

#### Compact Graph Column Layout

<img src="/wp-content/uploads/gl-commit-graph-compact-graph.gif" class="img-responsive center img-bordered">

With the new compact Graph column layout, GitLens provides a more streamlined and compact layout to reduce the space required to visualize the commit history and branch relationships.

To enable the new compact Graph Column layout, right click on the Graph column header, and select the "Compact Graph Column Layout" option. If you want to switch back follow the same steps and choose "Default Graph Column Layout".

#### Pull Requests on Local Branches

You can now see pull requests (PRs) for your local branch upstreams directly on the local branches themselves. You no longer have to hunt for the local branch's upstream on the Commit Graph to see the associated PR.

#### Publish Local Branches from Commit Graph

Publishing local branches directly from the Commit Graph is a nice productivity boost. You can quickly and easily publish your local changes without having to switch to the Branches view or use the command line.

### ✨ Focus View Pull Request Actions

<img src="/wp-content/uploads/gl-focus-view-create-worktree-create-branch.png" class="img-responsive center img-bordered">

The Focus View is no longer read-only! We've introduced new actions within Focus View, aimed at enhancing your workflow and productivity. You can now easily create a branch or worktree, or switch/open an existing one, for a PR directly from the Focus View page, streamlining the process of reviewing or contributing to pull requests. As a quick worktree refresher, creating a worktree from the PR will let you review or contribute to multiple PRs simultaneously without affecting your current branch and working tree.

### Commit Details Interaction Improvements

<img src="/wp-content/uploads/gl-commit-details-pinned-commit-deets.png" class="img-responsive center img-bordered">

We've heard your feedback on the Commit Details view and the confusion and difficulty with using the pinning feature. We updated the visual appearance of the pinned state, so its easier to know when Commit Details is pinned. Additionally, we've introduced navigation controls that enable you to move back and forth through the commits you've recently viewed, helping to avoid losing context as you navigate through your code.

### Thank you to our contributors

Shout-out to all of our awesome contributors for this release!

- WofWca ([@WofWca](https://github.com/WofWca))

### Added

- Adds the ability to switch to an alternate panel layout for the _Commit Graph_ &mdash; closes [#2602](https://github.com/gitkraken/vscode-gitlens/issues/2602) and [#2537](https://github.com/gitkraken/vscode-gitlens/issues/2537)
  - Adds a new context menu from the _Commit Graph Settings_ (cog) to switch between the "Editor" and "Panel" layouts
  - Adds a `gitlens.graph.layout` setting to specify the layout of the _Commit Graph_
    - `editor` - Shows the _Commit Graph_ in an editor tab
    - `panel` - Shows the _Commit Graph_ in the bottom panel with an additional _Commit Graph Details_ view alongside on the right
- Adds new _Commit Graph_ features and improvements
  - Adds a compact layout to the Graph column of the _Commit Graph_
    - Adds a context menu option to the header to toggle between the "Compact" and "Default" layouts &mdash; closes [#2611](https://github.com/gitkraken/vscode-gitlens/pull/2611)
  - Shows pull request icons on local branches when their upstream branch is associated with a pull request
  - Adds tooltips to work-in-progress (WIP) and stash nodes
  - Adds a "Publish Branch" context menu action to local branches without an upstream branch &mdash; closes [#2619](https://github.com/gitkraken/vscode-gitlens/pull/2619)
  - Lowers the minimum width of the "Branch / Tag" column
- Adds actions to _Focus View_ Pull Requests
  - Switch to or create a local branch
  - Create or open a worktree from the branch
- Adds a _Generate Commit Message (Experimental)..._ command to the SCM context menus

### Changed

- Reduces the size of the GitLens (desktop) bundle which reduces memory usage and improves startup time &mdash; ~7% smaller (1.21MB -> 1.13MB)
  - Consolidates the "extension" side of all the GitLens webviews/webview-views into a unified controller and code-splits each webview/webview-view into its own bundle
    - Allows for very minimal code to be loaded for each webview/webview-view until its used, so if you never use a webview you never "pay" the cost of loading it
- Changes _Open Associated Pull Request_ command to support opening associated pull requests with the current branch or the HEAD commit if no branch association was found &mdash; closes [#2559](https://github.com/gitkraken/vscode-gitlens/issues/2559)
- Improves the "pinning" of the _Commit Details_ view
  - Avoids automatically pinning
  - Changes the pinned state to be much more apparent
- Changes _Commit Details_ to always open diffs in the same editor group as the currently active editor &mdash; closes [#2537](https://github.com/gitkraken/vscode-gitlens/issues/2537)

### Fixed

- Fixes [#2597](https://github.com/gitkraken/vscode-gitlens/issues/2597) - Allow disabling "Open worktree for pull request via GitLens..." from repository context menu
- Fixes [#2612](https://github.com/gitkraken/vscode-gitlens/issues/2612) - Clarify GitLens telemetry settings
- Fixes [#2583](https://github.com/gitkraken/vscode-gitlens/issues/2583) - Regression with _Open Worktree for Pull Request via GitLens..._ command
- Fixes [#2252](https://github.com/gitkraken/vscode-gitlens/issues/2252) - "Copy As"/"Copy Remote File Url" copies %23 instead of # in case of Gitea &mdash; thanks to [PR #2603](https://github.com/gitkraken/vscode-gitlens/pull/2603) by WofWca ([@WofWca](https://github.com/WofWca))
- Fixes [#2582](https://github.com/gitkraken/vscode-gitlens/issues/2582) - _Visual File History_ background color when in a panel
- Fixes [#2609](https://github.com/gitkraken/vscode-gitlens/issues/2609) - If you check out a branch that is hidden, GitLens should show the branch still
- Fixes tooltips sometimes failing to show in _Commit Graph_ rows when the Date column is hidden
- Fixes [#2595](https://github.com/gitkraken/vscode-gitlens/issues/2595) - Error when stashing changes

<a id="v13-4"></a>

## Version 13.4

### Thursday, Mar 16, 2023

With 13.4, we've introduced an experimental new AI feature to assist with writing commit messages, improved GitLens performance by reducing its size, made improvements to the ✨Commit Graph, and accepted community contributions as well as many bug fixes from community feedback.

<img src="/wp-content/uploads/gl-13.4-banner.png" class="img-responsive center img-bordered">

### AI-Generated Commit Messages (Experimental)

<img src="/wp-content/uploads/gl-ai-generated-commit-message.gif" class="img-responsive center img-bordered">

We’ve introduced a new experimental feature to assist with writing commit messages by leveraging OpenAI. To start, stage some changes you want to commit and generate a commit message for and then run the “Generate Commit Message (Experimental)” command from the Command Palette. From there you will be guided through the process of accepting to send the diff of your staged changes to OpenAI and the entry of your OpenAI key. Once completed, the generated commit message will be entered into the commit input box on the Source Control sidebar. You can also enter additional context about your changes in the commit box and those will also be sent to help generate a better message.

Additionally, you can customize the `gitlens.experimental.generateCommitMessagePrompt` setting to control the prompt used to structure and format the generated commit message. You could have it structure commit messages in the conventional commit style, or you can have fun with it and make your commit messages in the style of a pirate, Shakespeare, etc.

This is a very early peek into features and ideas that can leverage AI – look forward to much more in the near future!

### GitLens Size Reduction

Over the last couple releases we’ve made significant progress on optimizing the footprint of GitLens. We’ve focused a lot on the bundle sizes to allow for faster start-up times of both the extension itself and all of our webviews. These optimizations also help reduce our memory usage. We are continually looking for opportunities to optimize and reduce our footprint so look for more progress in the future!

Here are some numbers:

- GitLens desktop bundle has been reduced by ~37% from 1.91MB to 1.21MB
- GitLens web bundle (for vscode.dev / github.dev) has been reduced by ~39% from 2.05MB to 1.24MB
- GitLens Commit Graph webview has been reduced by ~27% from 1.03MB to 758KB and that is including the new minimap and rich scroll markers
- GitLens Home view has been reduced by ~41% from 267KB to 160KB
- GitLens Visual File History view has been reduced by ~9% from 508KB to 461KB

### ✨ Commit Graph Enhancements

##### Upstream Tracking

<img src="/wp-content/uploads/gl-upstream-tracking.png" class="img-responsive center img-bordered">

It's now possible to effortlessly keep track of upstreams of your local branches in the commit graph. The upstreams of visible local branches, along with their corresponding commit history, will be displayed in the graph even if other remote branches are filtered out from your settings.

We've also revised the wording of the remote filter setting to "Hide Remote-only Branches.

#### Graph Alignment

<img src="/wp-content/uploads/gl-graph-alignment.png" class="img-responsive center img-bordered">

The graph column is now more left-aligned, making it easier to read and follow the history of a branch at a glance.

#### Branches and Tags on Remote Repositories

<img src="/wp-content/uploads/gl-remote-ref-tracking.png" class="img-responsive center img-bordered">

You can now see the tips of your branches and tags in the Commit Graph on remote repositories! Previously, opening a remote repository in the graph would show only the current branch. Currently, we are still limited to only showing commits for the current branch, so the included branches and tags are ones pointing to commits in the current branch’s commit history.

### Sunsetting GitLens Insiders (Replaced with Pre-release)

<img src="/wp-content/uploads/gl-sunsetting-insiders.gif" class="img-responsive center img-bordered">

We’ve deprecated the GitLens Insiders edition in favor of a Pre-release version which is directly supported inside VS Code and is much easier to opt-in to and out of. Existing users of GitLens Insiders should have been automatically migrated to the Pre-release version. The Pre-release version of GitLens is a nightly build of GitLens, just as the GitLens Insiders edition was.

To opt-in to the Pre-release edition, select GitLens from the extensions sidebar and press “Switch to Pre-Release Version”.

### Thank you to our contributors

Shout-out to all of our awesome contributors for this release!

- Nafiur Rahman Khadem ([@ShafinKhadem](https://github.com/ShafinKhadem))
- Skyler Dawson ([@foxwoods369](https://github.com/foxwoods369))
- haha ([@hahaaha](https://github.com/hahaaha))

### Added

- Adds an experimental _Generate Commit Message (Experimental)_ command to use OpenAI to generate a commit message for staged changes
  - Adds a `gitlens.experimental.generateCommitMessagePrompt` setting to specify the prompt to use to tell OpenAI how to structure or format the generated commit message &mdash; can have fun with it and make your commit messages in the style of a pirate, etc
- Adds auto-detection for `.git-blame-ignore-revs` files and excludes the commits listed within from the blame annotations
- Adds a _Open Git Worktree..._ command to jump directly to opening a worktree in the _Git Command Palette_
- Adds a _Copy Relative Path_ context menu action for active editors and file nodes in sidebar views
- Adds the ability to see branches and tags on remote repositories (e.g. GitHub) on the _Commit Graph_
  - Currently limited to only showing them for commits on the current branch, as we aren't yet able to show all commits on all branches

### Changed

- Improves the display of items in the _Commit Graph_
  - When showing local branches, we now always display the upstream branches in the minimap, scrollbar markers, and graph rows
  - When laying out lanes in the Graph column, we now bias to be left aligned when possible for an easier to read and compact graph visualization
- Improves _Open Worktree for Pull Request via GitLens..._ command to use the qualified remote branch name, e.g. `owner/branch`, when creating the worktree
- Removes Insiders edition in favor of the pre-release edition
- Reduces the size of the GitLens bundle which improves startup time
  - GitLens' extension bundle for desktop (node) is now ~24% smaller (1.58MB -> 1.21MB)
  - GitLens' extension bundle for web (vscode.dev/github.dev) is now ~6% smaller (1.32MB -> 1.24MB)

### Fixed

- Fixes [#2550](https://github.com/gitkraken/vscode-gitlens/issues/2550) - Related pull request disappears after refresh
- Fixes [#2549](https://github.com/gitkraken/vscode-gitlens/issues/2549) - toggle code lens does not work with gitlens.codeLens.enabled == false
- Fixes [#2553](https://github.com/gitkraken/vscode-gitlens/issues/2553) - Can't add remote url with git@ format
- Fixes [#2083](https://github.com/gitkraken/vscode-gitlens/issues/2083), [#2539](https://github.com/gitkraken/vscode-gitlens/issues/2539) - Fix stashing staged changes &mdash; thanks to [PR #2540](https://github.com/gitkraken/vscode-gitlens/pull/2540) by Nafiur Rahman Khadem ([@ShafinKhadem](https://github.com/ShafinKhadem))
- Fixes [#1968](https://github.com/gitkraken/vscode-gitlens/issues/1968) & [#1027](https://github.com/gitkraken/vscode-gitlens/issues/1027) - Fetch-> fatal: could not read Username &mdash; thanks to [PR #2481](https://github.com/gitkraken/vscode-gitlens/pull/2481) by Skyler Dawson ([@foxwoods369](https://github.com/foxwoods369))
- Fixes [#2495](https://github.com/gitkraken/vscode-gitlens/issues/2495) - Cannot use gitlens+ feature on public repo in some folders
- Fixes [#2530](https://github.com/gitkraken/vscode-gitlens/issues/2530) - Error when creating worktrees in certain conditions
- Fixed [#2566](https://github.com/gitkraken/vscode-gitlens/issues/2566) - hide context menu in output panel &mdash; thanks to [PR #2568](https://github.com/gitkraken/vscode-gitlens/pull/2568) by hahaaha ([@hahaaha](https://github.com/hahaaha))
- Fixes [#2533](https://github.com/gitkraken/vscode-gitlens/issues/2533) - Current Branch Only graph filter sometimes fails
- Fixes [#2504](https://github.com/gitkraken/vscode-gitlens/issues/2504) - Graph header theme colors were referencing the titlebar color properties
- Fixes [#2527](https://github.com/gitkraken/vscode-gitlens/issues/2527) - shows added files for Open All Changes
- Fixes an issue where trial status can be shown rather than a purchased license
- Fixes graph issue where scroll markers do not update until mouseover when changing the `gitlens.graph.scrollMarkers.additionalTypes` setting.

---

<a id="v13-3"></a>

## Version 13.3

### Thursday, Feb 23, 2023

Supercharge your Git game with GitLens 13.3: the latest update to help you master Git like a pro. With 13.3 we’re introducing Workspace Focus View, Deep Linking Support, and Commit Graph Improvements featuring the new (experimental) minimap and changes column.

<img src="/wp-content/uploads/glrn-13.3.png" class="img-responsive center img-bordered">

GitLens also just got a whole lot faster with the release of version 13.3! Thanks to some serious bundle slimming, the startup times have significantly improved.

- GitLens' extension bundle for desktop (node) is now ~18% smaller
- GitLens' extension bundle for web (vscode.dev/github.dev) is now ~37% smaller
- GitLens' Commit Graph webview bundle is now ~31% smaller

### ✨Focus View (Preview)

<img src="/wp-content/uploads/glrn-focus-view.png" class="img-responsive center img-bordered">

With the preview of GitLens Focus View, you can streamline your workflow and prioritize your tasks with ease. The Focus View feature gives you a comprehensive list of all your most important work across all your GitHub repos. No more jumping back and forth between multiple pages or repos - GitLens Focus View makes it simple and efficient to keep track of and manage your work progress.

The new Focus View will provide you with a summary of Pull Requests and Issues relevant to you for the repositories grouped in your Workspace.

- My Pull Requests: shows all GitHub PRs opened by you, assigned to you, or awaiting your review
- My Issues: shows all issues created by you, assigned to you, or that mention you.

Instead of hunting for these pieces of information separately, you can get a holistic view of what you’re working on.

\*_Note Focus View is currently in a Preview Only state, it is subject to change in the future._

### ✨ Commit Graph improvements

#### Minimap (Experimental)

<img src="/wp-content/uploads/glrn-minimap.png" class="img-responsive center img-bordered">

Click the Toggle Minimap icon in the right corner of the Commit Graph top bar to toggle the Minimap on and off. As this is an experimental feature, it is off by default – and we would love to hear your feedback and suggestions.

The idea behind the Minimap is to provide a whole new dimension to the Commit Graph. You can quickly see the activity of the repo, see HEAD/upstream, branches (local and remote), and easily jump to them.

The <span style="color:green">green line</span> showcases HEAD while search results are depicted by <span style="color:yellow">yellow lines</span>. The highlighted region shows the Commit Graph area that is in view. Markers are arranged in two rows of stacked blocks:

- In the upper row, the <span style="color:green">blue blocks</span> signify remote branches, while the <span style="color:brown">brown blocks</span> refer to tags.
- Within the lower row, the <span style="color:pink">pink blocks</span> denote stashes, and the <span style="color:blue">blue blocks</span> represent local branches.

We really want to hear your feedback - this is still a very early feature and we're currently still playing with colors, and additional features. To leave us feedback such as what do you think, is this useful, what does it have that you like, what is it missing, etc. reach out to us on the GitLens, [GitHub Discussion board](https://github.com/gitkraken/vscode-gitlens/discussions/2477#discussion-4807133).

#### Changes column (lines added/deleted)

<img src="/wp-content/uploads/glrn-changes-column.png" class="img-responsive center img-bordered">

Reduce time and effort required to navigate through code changes, with the changes column in GitLens. The changes column provides a visual representation of changes made to files in each commit, with green bars indicating added lines and red bars indicating deleted lines.

This visual display allows you to quickly identify the extent of changes made to files across multiple commits, making it easier to pinpoint specific areas of code that have been modified.

You can toggle the Change Column by right clicking the graph header and clicking "Show Changes".

#### Scroll Markers (Rich scrollbar)

<img src="/wp-content/uploads/glrn-rich-scrollbar.png" class="img-responsive center img-bordered">

Scroll Markers adds a rich layer of information to the Commit Graph scrollbar. Now you can quickly find and jump to checked-out branches, selected rows, search results, as well as important points such as HEAD and refs. Similar to Overview Ruler in VS Code, Scroll Markers provide a visual indicator on the scrollbar.

Our intention with Scroll Markers is to save you time and effort by allowing you to quickly identify and jump to the relevant sections of your Git history. It's a powerful new addition to the Commit Graph to help streamline workflow.

#### Branch upstream status

<img src="/wp-content/uploads/glrn-branch-upstream.png" class="img-responsive center img-bordered">

The Commit Graph now shows the upstream status of local branches with an upstream. You'll be able to quickly identify when your local branch is out of sync with its upstream branch with the new indicator, which shows how many commits are ahead or behind your upstream branch.

You can also double-click on the upstream indicator, to pull or push the pending commits to bring your local branch back in sync with its upstream. This makes it easy to keep track of upstream changes to your local branches and keep them up to date.

#### Work In Progress Row improvements

<img src="/wp-content/uploads/glrn-wip.png" class="img-responsive center img-bordered">

With the latest Work In Progress Row improvements, with a single right click, you can access the WIP contextual menu. Giving you access to a range of useful options, including Stash All Changes, Open Details, and Open Source Control. These features allow you to more effectively manage your WIP.

### Deep linking support

Deep linking provides you with the ability to easily share specific remote repositories, commits, branches, and tags by copying the link to your clipboard and pasting it into a Jira issue or a Slack conversation for example.

The link will then open in the Commit Graph and can be used to quickly access and review relevant artifacts. With deep linking support, you can improve collaboration and communication by seamless sharing of important information related to your Git repos.

### Added

- Adds new _Commit Graph_ features and improvements
  - Adds a new experimental minimap of commit activity to the _Commit Graph_
  - Adds a new experimental _Changes_ column visualizing commit changes
  - Adds markers to the _Commit Graph_ scroll area indicating the location of the selected row, search results, current branch, upstream, and more
  - Adds the ability to show upstream (ahead/behind) status on local branches with an upstream
    - Adds a double-click action on the status to pull (when behind) or push (when ahead) pending changes
    - Adds context menu actions to _Push_, _Pull_, and _Fetch_ the local branch
    - Adds a `gitlens.graph.showUpstreamStatus` setting to toggle upstream (ahead/behind) indicators on branches
  - Adds the ability to show any associated pull requests with branches
    - Adds a double-click action on the PR icon to open the PR in the browser
    - Adds context menu actions to _Open Pull Request on Remote_ and _Copy_ the PR URL
    - Adds a `gitlens.graph.pullRequests.enabled` setting to toggle PR icons &mdash; closes [#2450](https://github.com/gitkraken/vscode-gitlens/issues/2450)
  - Adds a context menu to the WIP row &mdash; closes [#2458](https://github.com/gitkraken/vscode-gitlens/issues/2458)
  - Adds a double-click action on commit rows to open the _Commit Details_ view
  - Improves Author and Avatar tooltips to now also show the contributor's email address, if available
  - Improves Date tooltips to now always show both the absolute and relative date
- Adds the ability to copy and share links directly to repositories, branches, commits, and tags in the _Commit Graph_
  - Adds context menu actions to copy direct links in the _Share_ submenu
- Improves the Worktree creation experience
  - Adds a prompt after the worktree is created to choose how to open the worktree
    - Adds a `worktrees.openAfterCreate` setting to specify how and when to open a worktree after it is created
  - Ensures new worktrees are created from the "main" repo, if already in a worktree
- Adds a new _remote_ command to the _Git Command Palette_ to add, prune, and remove remotes
- Adds a _Open Worktree for Pull Request via GitLens..._ context menu command on pull requests in the _GitHub Pull Requests and Issues_ extension's views
  - Opens an associated worktree, if one exists, otherwise it creates a new worktree for the pull request
- Adds settings to control the format of commits in the GitLens views

### Changed

- Greatly reduces the size of many of GitLens' bundles which improves startup time
  - GitLens' extension bundle for desktop (node) is now ~18% smaller
  - GitLens' extension bundle for web (vscode.dev/github.dev) is now ~37% smaller
  - GitLens' Commit Graph webview bundle is now ~31% smaller
- Changes the _Contributors_ view to be shown by default on the _GitLens_ sidebar

### Removed

- Removes the use of an external color library for the _File Heatmap_ annotations and webview themes &mdash; reduces the bundled extension size

### Fixed

- Fixes [#2355](https://github.com/gitkraken/vscode-gitlens/issues/2355) - Search by changes stops working in version 13.x.x
- Fixes [#2473](https://github.com/gitkraken/vscode-gitlens/issues/2473) - Commit graph status bar show wrong last fetched date
- Fixes [#2409](https://github.com/gitkraken/vscode-gitlens/issues/2409) - Commit Graph Show Current Branch Only shows unrelated commits from other branches
- Fixes an issue where pinning not being respected in Commit Details view
- Fixes graph issue where search results that are merge commits are not highlighted when the `gitlens.graph.dimMergeCommits` setting is enabled
- Fixes graph issue where rows with tags belonging to a hovered branch are not highlighted when the `gitlens.graph.highlightRowsOnRefHover` setting is enabled

---

<a id="v13-2"></a>

## Version 13.2

### Tuesday, Dec 20th, 2022

Since the release of [GitLens 13](https://www.gitkraken.com/blog/gitlens-13), we know how the power of GitLens+ features like the Commit Graph, have been helping supercharge your dev workflow. That’s why we’re excited to present GitLens 13.2, with all new (and highly requested) Graph improvements like filtering, to quickly focus on what is most important to you. We've also streamlined the Commit Graph interface with a new header bar, providing context and quick access to switch between repositories or branches, and even fetch to keep up to date. Get ready to level up your Git game with GitLens 13.2!

<img src="/wp-content/uploads/gitlens-13.2-hero.png" class="img-responsive center img-bordered">

### Filtering

GitLens 13.2 introduces filtering , which allows you to display a subset of your graph’s information and helps you hone in on specific details of your graph that matter the most.

<img src="/wp-content/uploads/gitlens-filter-options.gif" class="img-responsive center img-bordered">

#### Filtering Capabilities

Use graph filtering in GitLens to get laser focused on the branch you're working on and its remote:

- Only Show the Current Branch

  - Display only the branch that you’re currently working on and it’s remote. In order to focus your attention on the things landing in this branch, and then quickly unfilter to "zoom" back out and see everything in flight.

- Hide Remote Branches

  - Hides commits from the graph view that are only on remote branches.

- Hide Tags

  - Hides all tags that point to commit rows.

- Hide Stashes

  - Hides all stash rows.

- Dim Merge Commit Rows
  - Deemphasizes merge commit rows.

### Graph UX Improvements

We've updated the user interface, so you can get to all your favorite features even faster. Now, you can access change repo, account status, and filtering from the top of the Commit Graph page.

<img src="/wp-content/uploads/graph-ux-improvements.png" class="img-responsive center img-bordered">

### Header Updates

By merging the contextual information from the footer into the header, including the new Branch Picker and Fetch Action we’ve made it easier for you to manage your branches and work more effectively.

<img src="/wp-content/uploads/drop-down.png" class="img-responsive center img-bordered">

- Branch Picker

  - Save time, by easily selecting the branch you want from the drop down branch picker.

- Fetch Action
  - Easily keep your local repo up-to-date and in sync with the fetch action.

### Shortcut Keys

Using the new keyboard shortcuts, `SHIFT+UP` and `SHIFT+DOWN` on the Commit Graph helps you locate what you need more efficiently and effectively by staying within the branch and moving between graph rows. This can be particularly useful if you are working on a complex project with many branches.

<img src="/wp-content/uploads/shift-up-down.gif" class="img-responsive center img-bordered">

### Added

- Adds many all-new _Commit Graph_ features and improvements
  - Adds the ability to filter commits, branches, stashes, and tags
    - Adds a new _Filter Graph_ dropdown button at the start of the search bar
    - Adds ability to quickly switch between _Show All Local Branches_ and _Show Current Branch Only branch_ filtering options
      - _Show All Local Branches_ — displays all local branches (default)
      - _Show Current Branch Only_ — displays only the current branch and it's upstream remote (if exists and _Hide Remote Branches_ isn't enabled)
    - Adds ability to hide all remote branches, stashes, and tags
    - Adds the ability to dim (deemphasize) merge commits
  - Adds a new header bar to provide quick access to common actions
    - Shows the currently selected repository with the ability to switch repositories when clicked (if multiple repositories are open)
    - Shows the current branch with the ability to switch branches when clicked
    - Provides a fetch action which also shows the last fetched time
    - Also moves GitLens+ feature status and feedback links to the top right
  - Adds new ability to reorder columns by dragging and dropping column headers (not all columns are reorderable)
  - Adds new keyboard shortcuts
    - Use `shift+down arrow` and `shift+up arrow` to move to the parent/child of the selected commit row
    - Holding the `ctrl` key with a commit row selected will highlight rows for that commit's branch
  - Adds new settings
    - Adds a `gitlens.graph.dimMergeCommits` setting to specify whether to dim (deemphasize) merge commit rows
    - Adds a `gitlens.graph.scrollRowPadding` setting to specify the number of rows from the edge at which the graph will scroll when using keyboard or search to change the selected row

### Changed

- In the _Commit Graph_, increases the time to highlight associated rows when hovering over a branch to 1s
- Removes the status bar from the _Commit Graph_ as it was replaced by the new header bar

### Fixed

- Fixes [#2394](https://github.com/gitkraken/vscode-gitlens/issues/2394) - Work in progress file diff compares working tree with working tree, instead of working tree with head
- Fixes [#2207](https://github.com/gitkraken/vscode-gitlens/issues/2207) - Error when trying to push individual commit
- Fixes [#2301](https://github.com/gitkraken/vscode-gitlens/issues/2301) - Create Worktree button doesn't work in certain cases
- Fixes [#2382](https://github.com/gitkraken/vscode-gitlens/issues/2382) - commits disappearing from commit details view when they shouldn't
- Fixes [#2318](https://github.com/gitkraken/vscode-gitlens/issues/2318) - GitLens need to login again after VS Code insiders upgrade every day
- Fixes [#2377](https://github.com/gitkraken/vscode-gitlens/issues/2377) - Missing Azure Devops Icon
- Fixes [#2380](https://github.com/gitkraken/vscode-gitlens/issues/2380) - Autolink fails with curly braces
- Fixes [#2362](https://github.com/gitkraken/vscode-gitlens/issues/2362) - Visual File History becomes unavailable when the workspace contains private repo
- Fixes [#2381](https://github.com/gitkraken/vscode-gitlens/issues/2381) - can't use scrollbar in 'Commit Graph' view
- Fixes an issue where focusout hides toolbar actions for the graph
- Fixes an issue where _Switch to Another Branch..._ doesn't work in the Graph editor toolbar
- Fixes graph issue with row highlighting/dimming sticking when the graph loses focus
- Fixes graph issue with branches remaining hovered/extended when the mouse leaves the graph

---

<a id="v13-1"></a>

## Version 13.1

### Thursday, November 17th, 2022

With GitLens 13, we released the power of GitLens+ features like the Commit Graph, Visual File History, and Worktrees to ALL users on local and public repos. No account required. Learn more about the changes happening with GitLens in this [article](https://www.gitkraken.com/blog/gitlens-13).

<img src="/wp-content/uploads/GitLens-13-1-Hero.png" class="img-responsive center img-bordered">

## Commit Graph Enhancements

### Search History

Find what you seek with ease! Quickly navigate through your search history by using the UP⇧ or DOWN⇩ arrow keys.

<img src="/wp-content/uploads/New-Search-History.gif" class="img-responsive center img-bordered">

### New Search Filter @me

Want to see only your commits? Search For @me to highlight only your commits.

<img src="/wp-content/uploads/atmegif.gif" class="img-responsive center img-bordered">

## Faster Interactive Rebase Editor

With GitLens 13.1, we overhauled the Interactive Rebase Editor. It is now dramatically faster, especially for large rebases. We also streamlined the user experience with a persistent header and footer to ensure you always have important context visible and can quickly start or abort the rebase. Also, anytime the commit author and committer are different, you will see both of their avatars.

<img src="/wp-content/uploads/Faster-Interactive-Rebase-Editor.png" class="img-responsive center img-bordered">

### Commit Details View Usage

Need additional details to complete your rebase more efficiently? Now, as you navigate commits, we show the selected commit details in the Commit Details view.

## Commit Details View Improvements

### Custom Autolinks

Custom and basic provider-based autolinks are now shown in the Autolinks section.

### Customizable Settings

You can now customize the Commit Details view from the GitLens Settings editor to personalize how it looks and behaves so you can focus on the most important details.

<img src="/wp-content/uploads/commit-details-view-1.png" class="img-responsive center img-bordered">

## Terminal Links Can Use the Commit Details View

Terminal Links for commits in VS Code’s integrated terminal now use the Commit Details view to provide rich details about the selected commit.

## GitLens Home View Updates

Keeping a home tidy is important! We’ve streamlined the Home view to make it even easier to get started with GitLens, learn about its features, and how to personalize your experience.

<img src="/wp-content/uploads/New-Home-Side-Panel.png" class="img-responsive center img-bordered">

## Added

- Adds Commit Graph enhancements
  - Adds the ability to set keyboard shortcuts to commits and stashes on the Commit Graph — closes [#2345](https://github.com/gitkraken/vscode-gitlens/issues/2345) - Keyboard shortcuts can be applied to many of the gitlens.graph.\* commands and should use gitlens:webview:graph:focus && !gitlens:webview:graph:inputFocus for their "When Expression" to only apply when the Commit Graph is focused - For example, add the following to your keybindings.json to allow Ctrl+C to copy the selected commit's SHA to the clipboard
    {
    "key": "ctrl+c",
    "command": "gitlens.graph.copySha",
    "when": "gitlens:webview:graph:focus && !gitlens:webview:graph:inputFocus"
    }
- Automatically selects the HEAD commit in the Commit Graph when switching branches
- Improves performance of updating the Commit Graph when the repository changes
- Improves performance by avoiding unnecessary updates to the Commit Details view when selection changes
- Adds a @me search filter to the search box
- Adds history navigation to the search box in the Commit Graph
  - When the search field is focused, use the up arrow and down arrow to navigate through any previous searches that yielded results
  - Adds ability to reset to any commit in the Commit Graph and GitLens views — closes [#2326](https://github.com/gitkraken/vscode-gitlens/issues/2326)
- Adds Interactive Rebase Editor performance and UX improvements
  - Changes the header and footer to always be visible
  - Shows the Commit Details view on commit selection
    - Adds a gitlens.rebaseEditor.showDetailsView setting to specify when to show the Commit Details view for the selected row in the Interactive Rebase Editor
  - Adds full (multiline) commit message
  - Adds the f fixup shortcut key to UI
  - Consolidates the UI for author and committer information into a stack of avatars
  - Adds emoji support for commit messages — closes [#1789](https://github.com/gitkraken/vscode-gitlens/issues/1789)
  - Ensures that large rebases show rich commit details
- Adds Commit Details view improvements
  - Adds custom and non-rich integration-based autolinks and improves autolink display
  - Improves performance by avoiding unnecessary updates
  - Avoids "pinning" commits by default when opened from the Commit Graph, Visual File History, quick picks, etc
  - Adds a Open in Commit Graph button even when showing uncommitted changes
- Adds new sections and settings to the GitLens Interactive Settings
  - Adds a new Commit Details view section
  - Adds a new Terminal Links section
  - Adds autolink configuration to the Hovers section
- Adds a @me search filter to commit search in the Search & Compare view and quick pick
- Adds product usage telemetry
  - Honors the overall VS Code telemetry settings and add a gitlens.telemetry.enabled setting opt-out specifically for GitLens

## Changed

- Changes the Home view to always be available and polishes the experience
- Changes SHA terminal links to use the Commit Details view — closes [#2320](https://github.com/gitkraken/vscode-gitlens/issues/2320)
  - Adds a gitlens.terminalLinks.showDetailsView setting to specify whether to show the Commit Details view when clicking on a commit link
- Changes to uses VS Code as Git's core.editor for terminal run commands — closes [#2134](https://github.com/gitkraken/vscode-gitlens/issues/2134) thanks to PR [#2135](https://github.com/gitkraken/vscode-gitlens/pull/2135) by Nafiur Rahman Khadem [@ShafinKhadem](https://github.com/ShafinKhadem)
  - Adds a gitlens.terminal.overrideGitEditor setting to specify whether to use VS Code as Git's core.editor for GitLens terminal commands
- Polishes webview (Commit Graph, Interactive Rebase Editor, etc) scroll bars to match VS Code's style and behavior

## Fixed

- Fixes [#2339](https://github.com/gitkraken/vscode-gitlens/issues/2339) - Commit details "Autolinks" group shows wrong count
- Fixes [#2346](https://github.com/gitkraken/vscode-gitlens/issues/2346) - Multiple cursors on the same line duplicate inline annotations; thanks to PR [#2347](https://github.com/gitkraken/vscode-gitlens/pull/2347) by Yonatan Greenfeld [@YonatanGreenfeld](https://github.com/YonatanGreenfeld)
- Fixes [#2344](https://github.com/gitkraken/vscode-gitlens/issues/2344) - copying abbreviated commit SHAs is not working
- Fixes [#2342](https://github.com/gitkraken/vscode-gitlens/issues/2342) - Local remotes are incorrectly treated as private
- Fixes [#2052](https://github.com/gitkraken/vscode-gitlens/issues/2052) - Interactive Rebase fails to start when using xonsh shell due to command quoting
- Fixes [#2141](https://github.com/gitkraken/vscode-gitlens/issues/2141) - GitLens' rebase UI randomly fails loading interactive rebase when performed outside of VSC
- Fixes [#1732](https://github.com/gitkraken/vscode-gitlens/issues/1732) - Phantom rebase-merge directory (rm -rf ".git/rebase-merge")
- Fixes [#1652](https://github.com/gitkraken/vscode-gitlens/issues/1652) - Closing interactive rebase editor after "git rebase --edit" aborts rebase-in-progress
- Fixes [#1549](https://github.com/gitkraken/vscode-gitlens/issues/1549) - Fetch does not work when local branch name differs from remote branch name
- Fixes [#2292](https://github.com/gitkraken/vscode-gitlens/issues/2292) - Push button in BranchTrackingStatusNode of non-current branch does not trigger "Push force"
- Fixes [#1488](https://github.com/gitkraken/vscode-gitlens/issues/1488) - Open Folder History not working with non-English language pack
- Fixes [#2303](https://github.com/gitkraken/vscode-gitlens/issues/2303) - "Googlesource" gerrit only supports two levels of domain — thanks to PR [#2304](https://github.com/gitkraken/vscode-gitlens/pull/2304) by Matt Buckley [@Mattadore](https://github.com/Mattadore)
- Fixes [#2315](https://github.com/gitkraken/vscode-gitlens/issues/2315) - Commit details secondary side bar banner doesn't stay dismissed
- Fixes [#2329](https://github.com/gitkraken/vscode-gitlens/issues/2329) - Remember UI settings in Commit Details panel
- Fixes [#1606](https://github.com/gitkraken/vscode-gitlens/issues/1606) - Adjusts capitalization of "URL" — thanks to PR [#2341](https://github.com/gitkraken/vscode-gitlens/pull/2341) by Dave Nicolson [@dnicolson](https://github.com/dnicolson)
- Fixes issue where we weren't honoring the default gravatar style (gitlens.defaultGravatarsStyle) in certain cases
- Fixes graph issue where stashes are sometimes assigned the wrong column
- Fixes graph issue with commit rows being incorrectly hidden in some cases
- Fixes graph issue with merge commits not being hidden correctly in some cases
- Fixes some graph issues with hover on branch/tag labels

---

<a id="v13-0"></a>

## Version 13.0

### Monday, October 17th, 2022

Find what you seek.

<img src="/wp-content/uploads/gitlens-13-social-3x.png" class="img-responsive center img-bordered">

## ✨GitLens+ Features for All on Local & Public Repos

With GitLens 13.0, we are excited to bring the power of GitLens+ features like the Commit Graph, Visual File History, and Worktrees to ALL users on local and public repos. No account required. Learn more about the changes happening with GitLens in this [article](https://www.gitkraken.com/blog/gitlens-13).

Here’s how to get started with each of the GitLens+ features with your local or public repos:

- [Commit Graph](https://help.gitkraken.com/gitlens/gitlens-plus/#commit-graph)
- [Worktrees](https://help.gitkraken.com/gitlens/gitlens-plus/#worktrees)
- [Visual File History](https://help.gitkraken.com/gitlens/gitlens-plus/#visual-file-history)

## ✨Commit Graph - Now out of Preview!

We’re delighted to announce that the Commit Graph is out of Preview, and is full featured! This means you may now interact with the Commit Graph directly and take actions like:

- Interact with branches, commits, tags and more with right-click context menus
- Double click a branch to checkout a branch
- Search and filter for commits
- Get information about Pull Requests

### Full context menu support

Interact with your branches, commits, and more! Context menus are now available when you right click on any branch, tag, commit, or author in the Commit Graph. You may even interact with the Commit Graph column headers to the author, date or SHA columns. So much power!

<img src="/wp-content/uploads/Commit-Search-Context-Menus.gif" class="img-responsive center img-bordered">

Context menu actions include but are not limited to:

- Switch to Branch
- Revert Commit
- Switch to Commit
- Create Branch
- Merge
- Rebase
- Create Worktree
- Create Pull Request

### Rich commit search

Find exactly what you are looking for with the rich search on the powerful new Commit Graph.

Whether searching for a specific commit, message, author, a changed file or files, or even a specific code change, the Commit Graph will highlight matching results across your entire repository. Use shortcut keys or the up/down arrows on the search bar to navigate the search results; `F3` (also `Cmd+G` on macOS) goes to the next result from your selection while `Shift+F3` ( also `Shift+Cmd+G` on macOS) goes to the previous. Additionally you can quickly jump to the first or last result, by holding `Shift` while clicking on the up/down arrows respectively – to make it easy to see when a file or change was introduced into the codebase.

<img src="/wp-content/uploads/Rich-Commit-Search.png" class="img-responsive center img-bordered">

Once you type search filtering criteria, use the arrow icons to move through each result.

<img src="/wp-content/uploads/Commit-Search-Moving-Arrow-Keys.gif" class="img-responsive center img-bordered">

### PR information in form of icon

Wait, which branch has that PR?

If connected to one of the rich integrations with GitHub or GitLab, the Commit Graph will display a PR icon for any branch currently in PR. Right-click on the PR icon to open the PR on the GitHub or GitLab, or copy the URL.

<img src="/wp-content/uploads/PR-Icon.png" class="img-responsive center img-bordered">

### Hiding remotes, branches or tags

Need to focus and have too many remotes or just want to curate how much is shown in your Commit Graph? Now you can hide entire remotes, or specific branches and tags. Hover over any branch or tag to access the “Hide” button or right-click to hide the whole remote, or just the local or remote branch, to help focus your Commit Graph.

<img src="/wp-content/uploads/Branch-Hide.png" class="img-responsive center img-bordered">

### All new home view

It’s a homecoming! Our GitLens home view has a new look, with quick links to our Getting Started guides, Integrations, Trial info, and Feature spotlights.

<img src="/wp-content/uploads/GitLens-Home.png" class="img-responsive center img-bordered">

### List or tree view in Commit Details View

The Commit Details View, which gives you contextual change info about your code, got a new toggle for List and Tree view.

<img src="/wp-content/uploads/view-as-list.png" class="img-responsive center img-bordered">

To open the Commit Details view, open the command palette using <kbd>Cmd+Shift+P</kbd> and type: Show Commit Details view or navigate to the Commit Details view in the Side Bar.

# Change Log

### Added

- ✨ All GitLens+ features on public and local repos are now available to everyone -- no account required!
  - We want to bring the power of GitLens+ features to more people without any gates.
- ✨ Commit Graph is out of preview!
  - Rich search features to find exactly what you're looking for:
    - Powerful filters to search by commit, message, author, a changed file or files, or even a specific code change
    - Searches look at ALL commits in a repository, not just what's shown in the graph
  - PR support for connected rich integrations (GitHub/GitLab)
  - Contextual right-click menus with popular actions for commits, branches, tags, and authors
  - Personalization of your graph experience
    - Show and hide branches and columns
    - Settings UI for easy fine-grain control over advanced settings
- Adds `View as Tree` option for changed files in the _Commit Details_ view
- Adds an `Open in Commit Graph` action to the hovers and commit quick pick menus

### Changed

- Updates the `Home View` with all new design and content
- Changes the `Show Commit` action in the hovers to `Show Details` and opens the _Commit Details_ view

### Fixed

- Fixes [#2203](https://github.com/gitkraken/vscode-gitlens/issues/2203) - Autolinks missing under commit details
- Fixes [#2230](https://github.com/gitkraken/vscode-gitlens/issues/2230) - j and k are inverted in ascending rebase order
- Fixes [#2195](https://github.com/gitkraken/vscode-gitlens/issues/2195) - Cannot open new files from commit details
- Fixes Commit Details view showing incorrect diffs for certain commits
- Fixes Commit Details view showing incorrect actions for uncommitted changes
- Fixes prioritization of multiple PRs associated with the same commit to choose a merged PR over others
- Fixes Graph not showing account banners when access is not allowed and trial banners were previously dismissed

---

<a id="v12-2"></a>

## Version 12.2

### Tuesday, August 30th, 2022

The new Commit Graph 🎨 in GitLens 12.2 will fix all your commitment problems...in your code 🥁 👩‍💻

<div class='embed-container embed-container--16-9'>
    <iframe width="560" height="315" src="https://www.youtube.com/embed/EsnA4zIUvWY?controls=1&modestbranding=1" frameborder="0" allowfullscreen></iframe>
</div>

## ✨Commit Graph - Preview

Users may now view the Commit Graph of their repository through GitLens.

This beloved feature from GitKraken Client helps visualize your repo commit history and give you information about branches, commits, and collaborators all in one view — making it easier to see contributions and help you make faster, more informed decisions.

<img src="/wp-content/uploads/1-commit-graph.png" class="img-responsive center img-bordered">

To open the Commit Graph, open the command palette using the keyboard shortcut <kbd>Cmd</kbd> <kbd>Shift</kbd> <kbd>P</kbd> and type `Show Commit Graph`.

<img src="/wp-content/uploads/2-commit-graph.gif" class="img-responsive center img-bordered">

This will open a new tab and render your current repo’s commit history, where you may scroll through your history and resize any of the columns widths.

You may also access the Commit Graph by clicking this graph icon from the Source Control view in the Sidebar or Status Bar.

<img src="/wp-content/uploads/How-to-open-commit-graph-B.png" class="img-responsive center img-bordered">

The Commit Graph is available to all users working on public repositories, and requires no account. Additionally, users with a paid GitLens+ subscription can use the Commit Graph with private repos.

For those on [vscode.dev](vscode.dev) or [github.dev](github.dev), this also means you can open the Commit Graph on a web browser.

The Commit Graph is in `Preview` mode, and we’d love to hear your feedback in the [Commit Graph discussion on GitHub](https://github.com/gitkraken/vscode-gitlens/discussions/2158).

## Commit Details View

GitLens 12.2 also ships with a `Commit Details View`, which gives you contextual change info about your code.

<img src="/wp-content/uploads/3-commit-details-view.png" class="img-responsive center img-bordered">

To open the `Commit Details View`, open the command palette using <kbd>Cmd</kbd> <kbd>Shift</kbd> <kbd>P</kbd> and this time type: `Show Commit Details View` or navigate to the Commit Details View in the Sidebar.

<img src="/wp-content/uploads/4-commit-details-view.gif" class="img-responsive center img-bordered">

The `Commit Details View` updates as you move your cursor throughout the file with information about the commit that modified that line of code. Get quick information about the commit author, commit ID, links to Pull Requests, files modified in the commit, and more.

Click on a file to open the diff, and see what changed. You may also hover over the file name to access options like Open File, Open Changes with Working File, and Open Remote.

## ✨ GitHub Enterprise Integration

Next, GitLens+ now offers a richer integration with GitHub Enterprise.

Once authenticated, GitLens will enrich GitHub autolinks in the hovers. You’ll see your GitHub Enterprise avatar, links to related pull requests, along with a footnote of the pull request or issue details.

<img src="/wp-content/uploads/6-GitHub-Enterprise.png" class="img-responsive center img-bordered">

You’ll see similar details from the Sidebar views for any commit or branch associated with a pull request or issue.

## ✨ Single Sign On

Single Sign On is here, providing GitLens+ users with a more secure sign in method!

### Requirements and configuration

Your GitKraken account may now initiate an Oauth authentication flow with the following supported Identity Providers (IdPs):

- Azure Active Directory
- Okta
- Google Identity Platform
- Ping Identity

<img src="/wp-content/uploads/SSO-setup.png" class="img-responsive center img-bordered">

Please note that your IdP will first need to be configured before setting up the connection in your GitKraken account. For assistance, please contact your IdP administrator or consult the IdP documentation for help.

Additional requirements: - Configurable only by GitKraken Owner or Admin of an organization - Subscribed to either the Teams or Enterprise plan

→ [Documentation: How to set up SSO in GitKraken](https://help.gitkraken.com/gitkraken-client/single-sign-on/)

### Signing in with SSO

GitLens+ users should see a new option to Sign in with SSO from the login screen.

<img src="/wp-content/uploads/9-GitLens-SSO.png" class="img-responsive center img-bordered">

After clicking `Sign in with SSO`, the SSO form will open and ask for an email address to use for SSO login. The app will then check the email and determine whether the email address belongs to a single IdP for SSO. When the email address is successfully identified, the user will be taken to that IdP to login.

Once authenticated, the user may use GitLens+

## More improvements

### Stash naming defaults

When applying or popping a stash, GitLens will default the commit message input to the stash message.

<img src="/wp-content/uploads/10-stash-commit-message.gif" class="img-responsive center img-bordered">

And when stashing changes, the stash name will now default to any entry in the commit message input.

### Stats in comparisons

There are now stats about additions & deletions in files nodes in comparisons. To get these stats, navigate to the `Search & Compare` view in the Sidebar and create a comparison between commits.

<img src="/wp-content/uploads/11-comparison-stats.png" class="img-responsive center img-bordered">

### Search for text in Interactive Rebase Editor

And users may now search for text on the `Interactive Rebase Editor` using <kbd>Ctrl</kbd> <kbd>F</kbd>.

<img src="/wp-content/uploads/12-interactive-rebase-text-search.png" class="img-responsive center img-bordered">

## Change Log

### Added

- Adds Commit Graph
- Adds Commit Details View
- Adds [**rich integration**](https://github.com/gitkraken/vscode-gitlens#remote-provider-integrations-) with GitHub Enterprise &mdash; closes [#1210](https://github.com/gitkraken/vscode-gitlens/issues/1210)
  - Adds associated pull request to line annotations and hovers
    ![Pull requests on line annotation and hovers](https://raw.githubusercontent.com/gitkraken/vscode-gitlens/main/images/docs/hovers-current-line-details.png)
  - Adds associated pull request to status bar blame
    ![Pull requests on status bar](https://raw.githubusercontent.com/gitkraken/vscode-gitlens/main/images/docs/status-bar.png)
  - Adds GitHub avatars
  - Adds associated pull requests to branches and commits in GitLens views
  - Adds rich autolinks for GitHub issues and merge requests, including titles, status, and authors
  - Adds rich support to _Autolinked Issues and Pull Requests_ within comparisons to list autolinked GitHub issues and merge requests in commit messages
- Adds new stash behaviors to use the Source Control (commit message) input box &mdash; closes [#2081](https://github.com/gitkraken/vscode-gitlens/issues/2081)
  - When a stash is applied or popped and the Source Control input is empty, we will now update the Source Control input to the stash message
  - When stashing changes and the Source Control input is not empty, we will now default the stash message input to the Source Control input value
- Adds the ability to search (<kbd>Ctrl</kbd>+<kbd>F</kbd>) for text on the Interactive Rebase Editor &mdash; closes [#2050](https://github.com/gitkraken/vscode-gitlens/issues/2050)
- Adds stats (additions & deletions) to files nodes in comparisons &mdash; closes [#2078](https://github.com/gitkraken/vscode-gitlens/issues/2078) thanks to help via [PR #2079](https://github.com/gitkraken/vscode-gitlens/pull/2079) by Nafiur Rahman Khadem ([@ShafinKhadem](https://github.com/ShafinKhadem))
- Adds the ability to uniquely format uncommitted changes for the current line blame annotations &mdash; closes [#1987](https://github.com/gitkraken/vscode-gitlens/issues/1987)
  - Adds a `gitlens.currentLine.uncommittedChangesFormat` setting to specify the uncommitted changes format of the current line blame annotation. **NOTE**: Setting this to an empty string will disable current line blame annotations for uncommitted changes
- Adds variable expansion support to the `gitlens.worktrees.defaultLocation` setting
  - `${userHome}` &mdash; the path of the user's home folder
  - `${workspaceFolder}` &mdash; the path of the folder opened in VS Code containing the specified repository
  - `${workspaceFolderBasename}` &mdash; the name of the folder opened in VS Code containing the specified repository without any slashes (/)
- Adds owner avatars to remotes in the _Remotes_ view for GitHub remotes

### Changed

- Greatly improves performance of many view interactions when connected to a rich integration and pull request details are enabled, including:
  - Showing and refreshing the _Commits_ view
  - Expanding commits, branches, and worktrees
- Remembers chosen filter on files nodes in comparisons when refreshing
- Changes display of filtered state of files nodes in comparisons
- Improves diff stat parsing performance and reduced memory usage
- Disallows comparisons with the working tree on the right-side (left-side still works as expected) and disables swapping
- Uses VS Code as `core.editor` in rebase &mdash; closes [#2084](https://github.com/gitkraken/vscode-gitlens/issues/2084) thanks to [PR #2085](https://github.com/gitkraken/vscode-gitlens/pull/2085) by Nafiur Rahman Khadem ([@ShafinKhadem](https://github.com/ShafinKhadem))

### Fixed

- Fixes [#2156](https://github.com/gitkraken/vscode-gitlens/issues/2156) - Reduce extension package size
- Fixes [#2136](https://github.com/gitkraken/vscode-gitlens/issues/2136) - Search & Compare quickpick shouldn't select the mode text when opening
- Fixes [#1896](https://github.com/gitkraken/vscode-gitlens/issues/1896) - Cannot read property 'fsPath' of undefined
- Fixes [#1550](https://github.com/gitkraken/vscode-gitlens/issues/1550) - Push button in commit widget does not trigger "Push force" when ALT is pressed.
- Fixes [#1991](https://github.com/gitkraken/vscode-gitlens/issues/1991) - Git lens status bar entry has an incomprehensible accessibility label
- Fixes [#2125](https://github.com/gitkraken/vscode-gitlens/issues/2125) - "git log" command in version 12.x is very slow
- Fixes [#2121](https://github.com/gitkraken/vscode-gitlens/issues/2121) - Typo in GitLens header &mdash; thanks to [PR #2122](https://github.com/gitkraken/vscode-gitlens/pull/2122) by Chase Knowlden ([@ChaseKnowlden](https://github.com/ChaseKnowlden))
- Fixes [#2082](https://github.com/gitkraken/vscode-gitlens/issues/2082) - GitLens Home view unreadable in certain themes
- Fixes [#2070](https://github.com/gitkraken/vscode-gitlens/issues/2070) - Quoted HTML / JSX syntax is not escaped correctly
- Fixes [#2069](https://github.com/gitkraken/vscode-gitlens/issues/2069) - Heatmap - incorrect behavior of gitlens.heatmap.fadeLines with gitlens.heatmap.ageThreshold
- Fixes an issue where choosing "Hide Current Branch Pull Request" from the _Commits_ view overflow menu wouldn't hide the PR node
- Fixes an issue where stashes without a message aren't displayed properly
- Fixes an issue where the _Stashes_ view empty state isn't displayed properly when there are no stashes
- Fixes typos via [PR #2086](https://github.com/gitkraken/vscode-gitlens/pull/2086) by stampyzfanz ([@stampyzfanz](https://github.com/stampyzfanz)), and [PR #2043](https://github.com/gitkraken/vscode-gitlens/pull/2043), [PR #2040](https://github.com/gitkraken/vscode-gitlens/pull/2040), [PR #2042](https://github.com/gitkraken/vscode-gitlens/pull/2042) by jogo- ([@jogo-](https://github.com/jogo-))
