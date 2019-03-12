# Changelog
All notable changes to this project will be documented in this file.

The format is based on [Keep a Changelog](https://keepachangelog.com/en/1.0.0/),
and this project adheres to [Semantic Versioning](https://semver.org/spec/v2.0.0.html).

## [2.0.0-beta.9]
### Fixed
 - Upgraded to [brightscript-language@0.1.20](https://github.com/TwitchBronBron/brightscript-language/tree/v0.1.20) which fixed an npm issue that was loading the wrong version of `brs`.



## [2.0.0-beta.8]
### Added
 - support specifying `brsconfig.json` path as a vscode setting under the `brightscript.configFile` setting.
 - reload workspace if brsconfig.json has changed
 - When launching debug session, read values from brsconfig.json when available
### Changed
 - Don't show brightscript log on workspace open (still support option to show on debug-start)
### Fixed
  - Upgraded to [brightscript-language@0.1.19](https://github.com/TwitchBronBron/brightscript-language/tree/v0.1.19)) which fixes:
 - RHS boolean assignment parse errors (see [this issue](https://github.com/sjbarag/brs/issues/156))
 - hover bug in multi-root workspace that was only showing hovers for the first workspace



## [2.0.0-beta.7]
### Added
 - All changes from 1.8.4 and 1.8.5
### Fixed
 - Upgraded to [brightscript-language@0.1.17](https://github.com/TwitchBronBron/brightscript-language/tree/v0.1.17)) which fixes:
   - Regression issue where mixed case `then` statements showed up as parse errors (fixed by
   - Parse errors related to assignment operators (i.e. `+=`, `-=`, `*=`, etc.)
   - issue where only top-level variables were being found. Now all variables are found throughout the entire function scope.
   - runtime error when getting hover result.
   - issue with hover that would not find top-level function parameter types.



## [2.0.0-beta.6]
### Added
 - All changes from [1.8.3](#183---2019-03-04)
### Fixed
 - syntax highlighting bug related to `then` not colorizing when containing any upper case character
 - the `MaxListenersExceededWarning` warning by upgrading to [brightscript-language@0.1.15](https://github.com/TwitchBronBron/brightscript-language/tree/v0.1.15)



## [2.0.0-beta.5]
### Changed
 - Upgraded to [brightscript-language@0.1.14](https://github.com/TwitchBronBron/brightscript-language/tree/v0.1.14) that brings syntax fixes for using `then` as an object property name and now allows `function` as an argument type.
### Fixed
 - textmate grammar related to `run`, `stop`, and `then` when used as object property names



### [2.0.0-beta.4]
### Changed
 - Upgraded to [brightscript-language@0.1.13](https://github.com/TwitchBronBron/brightscript-language/tree/v0.1.13) which fixes duplicate diagnostic reporting



## [2.0.0-beta.3]
### Fixed
 - bugs with errors showing up for script imports inside of comments.



## [2.0.0-beta.2]
### Changed
 - Upgraded to latest `brightscript` project, which fixes bitshift assignment operators and `stop` and `run` keywords on object literals.



## [2.0.0-beta.1]
### Added
 - Experimental language validation support. Catches most parse errors and a few basic language errors.



## [1.8.6] - 2019-03-09
### Fixed
 - launching debug session without a `launch.json` works again.



## [1.8.5] - 2019-03-07
### Fixed
 - Re-added the log commands that somehow got dropped in a previous release



## [1.8.4] - 2019-03-04
### Fixed
 - Regression syntax highlighting issue that was not correctly colorizing `then` in conditional statements if it contains any uppercase letters.



## [1.8.3] - 2019-03-04
### Fixed
 - Several textmate grammar issues and added more variety in the captured tokens to provide better colorization



## [1.8.2] - 2019-01-27
### Changed
 - Upgraded to [roku-deploy](https://www.npmjs.com/package/roku-deploy)@2.0.0 which brings support for dereferencing symbolic links, and copying files located outside of rootDir.



## [1.8.1] - 2019-01-25
### Fixed
 - Issue in `Go to definition` that would not find functions/subs with a space between the name and the opening parenthesis ([#85](https://github.com/TwitchBronBron/vscode-brightscript-language/issues/85))



## [1.8.0] - 2019-01-25
### Added
 - Support for reading variables from a `.env` file in `launch.json` (see [this section](https://github.com/TwitchBronBron/vscode-brightscript-language#config-file-for-user-specific-launch-settings) of the readme for more information)
### Fixed
 - Bug in `Go to definition` that wasn't finding function declarations with leading whitespace



## [1.7.0] - 2019-01-22
### Added
 - Ability to click on `pkg:/` links in BrightScript output window to open that file at the specified line number.



## [1.6.1] - 2019-01-20
### Fixed
 - Bug where the debugger would hang indefinitely on certain deployment errors.



## [1.6.0] - 2019-01-15
### Added
 - Ability to filter log output
 - Ability to clear log output

### Changed
 - Included `not searchViewletVisible` as part of the roku keyboard remote keybindings so the search panel is more usable in the output window.
 - Prevent adding entry breakpoint when `stopOnEntry` is `false` in launch.json.
 - Updated textmate grammar to include `step` as reserved word.

### Fixed
 - Upgraded to [roku-deploy](https://www.npmjs.com/package/roku-deploy)@2.0.0-beta2 which fixes some file path regression issues introduced in 1.0.0



## [1.5.0] - 2019-01-03
### Added
 - Ability to send remote control commands from the keyboard. See readme for more details.



## [1.4.2] - 2018-12-19
### Changed
 - Upgraded to [roku-deploy](https://www.npmjs.com/package/roku-deploy) version 1.0.0 which brings `glob-all` support for negating globs.



## [1.4.1] - 2018-12-14
### Fixed
 - Bug that was preventing debugger from working.



## [1.4.0] - 2018-12-10
### Added
 - Basic goto declaration support in xml documents
 - Inline errors for compilation failures
 - BrightScript Log output window, which can have colors/searches applied to it
 - Basic message signature support
 - `Find usage` support for brs documents



## [1.3.2] - 2018-12-07
### Fixed
 - Bug that was preventing using `function Main` as an entry function.



## [1.3.1] - 2018-12-05
### Changed
 - Upgraded to [brightscript-formatter](https://www.npmjs.com/package/brightscript-formatter) version `1.5.0` which brings support for overriding keywordCase for specific keywords.

### Fixed
 - Bug introduced in [1.3.0](#130---2018-11-20) that was preventing a debug session from starting due to incorrect "out" path.



## [1.3.0] - 2018-11-20
### Added
 - Support for declarations and symbols
 - Support for go to definition
 - Ability to format hightlighted code without formatting the whole document
 - A new launch setting called `debugRootDir` that allows deploying a build file while still debugging a source file
 - Command for switching between xml and brs files for a component.
 - Support for conditional statements without the `then`.

### Changed
 - Upgraded to [brightscript-formatter](https://www.npmjs.com/package/brightscript-formatter) version `1.4.0` which brings better support for multi-line if statements without the trailing then.

### Fixed
 - Breakpoints added after a debug session is launched are now correctly show as disabled.



 ## [1.2.2] - 2018-09-26
 ### Changed
 - Upgraded to [brightscript-formatter](https://www.npmjs.com/package/brightscript-formatter) version `1.3.0` which brings support for formatting conditional compile statements.



## [1.2.1] - 2018-09-26
### Changed
 - Upgraded to [roku-deploy](https://www.npmjs.com/package/roku-deploy) version `0.2.1` which removed some packages containing security vulnerabilities.



## [1.2.0] - 2018-09-26
### Changed
 - Upgraded to [roku-deploy](https://www.npmjs.com/package/roku-deploy) version `0.2.0` which adds support for moving and renaming files during the packaging process (see [the files property](https://github.com/TwitchBronBron/roku-deploy#options) for more details).



## [1.1.0] - 2018-07-11
### Changed
 - Upgraded [brightscript-formatter](https://www.npmjs.com/package/brightscript-formatter) to version `1.2.0` which enables removing trailing whitespace when formatting.



## [1.0.1] - 2018-04-04
### Fixed
 - Issue in debugger that was not properly handling truncated file paths received from Roku.



## 1.0.0 - 2018-03-16
### Added
- Remote debugging support
- Code formatter

### Fixed
- Issues with language colorization


[2.0.0-beta.8]: https://github.com/TwitchBronBron/vscode-brightscript-language/compare/v2.0.0-beta.7...v2.0.0-beta.8
[2.0.0-beta.7]: https://github.com/TwitchBronBron/vscode-brightscript-language/compare/v2.0.0-beta.6...v2.0.0-beta.7
[2.0.0-beta.6]: https://github.com/TwitchBronBron/vscode-brightscript-language/compare/v2.0.0-beta.5...v2.0.0-beta.6
[2.0.0-beta.5]: https://github.com/TwitchBronBron/vscode-brightscript-language/compare/v2.0.0-beta.4...v2.0.0-beta.5
[2.0.0-beta.4]: https://github.com/TwitchBronBron/vscode-brightscript-language/compare/v2.0.0-beta.3...v2.0.0-beta.4
[2.0.0-beta.3]: https://github.com/TwitchBronBron/vscode-brightscript-language/compare/v2.0.0-beta.2...v2.0.0-beta.3
[2.0.0-beta.2]: https://github.com/TwitchBronBron/vscode-brightscript-language/compare/v2.0.0-beta.1...v2.0.0-beta.2
[2.0.0-beta.1]: https://github.com/TwitchBronBron/vscode-brightscript-language/compare/v1.8.2...v2.0.0-beta.1
[1.8.6]: https://github.com/TwitchBronBron/vscode-brightscript-language/compare/v1.8.5...v1.8.6
[1.8.5]: https://github.com/TwitchBronBron/vscode-brightscript-language/compare/v1.8.4...v1.8.5
[1.8.4]: https://github.com/TwitchBronBron/vscode-brightscript-language/compare/v1.8.3...v1.8.4
[1.8.3]: https://github.com/TwitchBronBron/vscode-brightscript-language/compare/v1.8.2...v1.8.3
[1.8.2]: https://github.com/TwitchBronBron/vscode-brightscript-language/compare/v1.8.1...v1.8.2
[1.8.1]: https://github.com/TwitchBronBron/vscode-brightscript-language/compare/v1.8.0...v1.8.1
[1.8.0]: https://github.com/TwitchBronBron/vscode-brightscript-language/compare/v1.7.0...v1.8.0
[1.7.0]: https://github.com/TwitchBronBron/vscode-brightscript-language/compare/v1.6.1...v1.7.0
[1.6.1]: https://github.com/TwitchBronBron/vscode-brightscript-language/compare/v1.6.0...v1.6.1
[1.6.0]: https://github.com/TwitchBronBron/vscode-brightscript-language/compare/v1.5.0...v1.6.0
[1.5.0]: https://github.com/TwitchBronBron/vscode-brightscript-language/compare/v1.4.2...v1.5.0
[1.4.2]: https://github.com/TwitchBronBron/vscode-brightscript-language/compare/v1.4.1...v1.4.2
[1.4.1]: https://github.com/TwitchBronBron/vscode-brightscript-language/compare/v1.4.0...v1.4.1
[1.4.0]: https://github.com/TwitchBronBron/vscode-brightscript-language/compare/v1.3.2...v1.4.0
[1.3.2]: https://github.com/TwitchBronBron/vscode-brightscript-language/compare/v1.3.1...v1.3.2
[1.3.1]: https://github.com/TwitchBronBron/vscode-brightscript-language/compare/v1.3.0...v1.3.1
[1.3.0]: https://github.com/TwitchBronBron/vscode-brightscript-language/compare/v1.2.2...v1.3.0
[1.2.2]: https://github.com/TwitchBronBron/vscode-brightscript-language/compare/v1.2.1...v1.2.2
[1.2.1]: https://github.com/TwitchBronBron/vscode-brightscript-language/compare/v1.2.0...v1.2.1
[1.2.0]: https://github.com/TwitchBronBron/vscode-brightscript-language/compare/v1.1.0...v1.2.0
[1.1.0]: https://github.com/TwitchBronBron/vscode-brightscript-language/compare/v1.0.1...v1.1.0
[1.0.1]: https://github.com/TwitchBronBron/vscode-brightscript-language/compare/v1.0.0...v1.0.1