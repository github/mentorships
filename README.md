# Google Summer of Code

GitHub is the world's largest code repository and home to countless open source projects, including many that we actively participate in.

These ideas are suggestions that we think would make good Google Summer of Code projects. They are only meant to be a starting point. Feel free to [open an issue](https://github.com/github/gsoc/issues/new) to ask questions or discuss other ideas.

## [Atom](https://atom.io)

### Improve Atom's parser performance

Summary: Make the Atom parser faster and better at handling large files and long lines.
This includes identifying bottlenecks, developing benchmarks, and possibly
re-writing parts of the existing code base in C++ if needed.

Expected Outcome: Improved speed opening files and the 2MB file limit can be increased or removed.

Skills: CoffeeScript, JavaScript, C, C++

Mentors: [@kevinsawicki](https://github.com/kevinsawicki)

### Implement support for non-US keyboard layouts in Atom

Summary: Investigate and implement ways to better support non-US keyboard layouts
in the Atom text editor. This would greatly improve the editing experience for
anyone using a non-US keyboard layout. This will include engaging with the
community to identify the root problem and working through multiple solutions
from patching Chromium to crowd-sourcing custom keybinding layouts.

Expected Outcome: Using Atom with a non-US keybaord layout will be a better experience.

Skills: CoffeeScript, JavaScript

Mentors: [@kevinsawicki](https://github.com/kevinsawicki)

### Improve text rendering in Atom

Summary: Solve editing and rendering problems in Atom for files containing
Chinese, Japanese, Korean, and Devanagari characters. This will greatly improve
the editing experience in Atom.

Expected Outcome: People writing in any language can use Atom as their text editor.

Skills: CoffeeScript, JavaScript

Mentors: [@kevinsawicki](https://github.com/kevinsawicki)

### Implement scripts to generate source tarball of Atom and its sibling projects

Summary: Currently the Linux packages of Atom are built on GitHub's own machines, however in the ideal Linux world we should use services like PPA or OBS to build packages for each Linux distribution. This requires us to provide source tarballs that can be built without the internet. The source talls need to be generated for Atom, Atom Shell and libchromiumcontent, and scripts should be provided to build packages from the source tarballs.

Expected Outcome: Packages can be built for each Linux distribution from a source tarball.

Skills: Shell scripting, Python, familiarity with Linux packaging on popular distributions.

Mentors: [@zcbenz](https://github.com/zcbenz)

### IDE and editor integrations to develop Atom Shell apps

Summary: We would like to make developing Atom Shell apps easier by providing integrations with popular IDEs and editors, it should able users to create and debug Atom Shell apps without leaving the developing environment. Examples are like Atom package, Visual Studio extension, and WebStorm plugins.

Expected Outcome: A working Atom package or IDE plugin for developing Atom Shell apps.

Skills: JavaScript, experience of developing editor plugins or IDE extensions

Mentors: [@zcbenz](https://github.com/zcbenz)

### Improve printing support of Atom Shell

Summary: The printing feature of Atom Shell only works on Mac and Linux, we would like to implement it on Windows by porting the printing code of Chromium, and also add more printing options.

Expected Outcome: The printing works on Windows, and probably with some new printing related features.

Skills: C++, Win32 APIs

Mentors: [@zcbenz](https://github.com/zcbenz)

### Implement secure native node modules

Implement a secure native module loader for Node.js based on Google NaCl's toolchain and validator. As a first step, make it possible for native module authors to explicitly target an NaCl sandboxed container in npm modules. In this mode, authors would be forced to communicate with the main Node process through NaCl's built-in messaging system. As a stretch goal, enable sandboxing of native modules directly in the Node process without modifications by their authors. The requiring Node process should be able to white-list system call APIs, and the V8 extension API should function correctly while restricting memory access that would compromise security.

Expected outcome: A viable mechanism for loading native code in Node applications while maintaining security.

Skills: C++, Assembly, Theoretical understanding of NaCl, V8, and Node.js internals

Mentors: [@nathansobo](https://github.com/nathansobo)

## [Hub](https://github.com/github/hub)

Hub is a command-line tool that wraps git to provide an enhanced workflow for repos that are hosted on GitHub. For example, you can checkout, merge, and open new pull requests right from the terminal. For many of its operations hub uses the GitHub API.

### Establish a true hypermedia client for consuming API resources

Summary: Hub uses [go-octokit](https://github.com/octokit/go-octokit), a Go library for communicating with GitHub API. The idea of go-octokit was that it would be a [hypermedia](http://en.wikipedia.org/wiki/HATEOAS) client, but it's not there yet. Ideally, a hypermedia API client would start "browsing" an API from its root resource and follow the links until it reaches the resource it's interested in. However, using go-octokit today still requires a lot of manual operations involving passing around URLs, and the library itself hardcodes a lot of URLs which is contrary to how hypermedia should work.

Expected Outcome: go-octokit would be a better hypermedia client, preferrably by extracting a Go library that could be re-used to implement clients for other hypermedia APIs.

Skills: Go, HTTP

Mentor: [@mislav](https://github.com/mislav)

### Create support for defining extensible shell completions

Summary: When using `git` on the command line, shell completions are useful to save keystrokes when expanding long branch names, git remote names, and flags for various git commands. Since hub wraps git, it tries to expand git completion support with its own specific arguments and extra commands, but this doesn't work perfectly on some systems. This project would be developing a unified way to define shell completions for bash, zsh, and fish in a manner that could also be used to extend existing completion scripts for git.

Expected Outcome: A generator that could take a simple declarative markup for content of completions that a particular command should have and output working completion scripts for bash, zsh and fish that implement the described logic.

Skills: shell scripting

Mentor: [@mislav](https://github.com/mislav)

## [Linguist](https://github.com/github/linguist)

### Use grammar bundles to tokenize languages

Summary: Linguist uses a bayesian classifier to detect the language of a file. A [generic tokenizer](https://github.com/github/linguist/blob/master/lib/linguist/tokenizer.rb) is currently used for all languages to extract significant symbols. We would like to explore tokenizing contents for each language using the [grammar bundles](https://github.com/github/linguist/blob/master/grammars.yml) that are currently used for syntax highlighting.

Expected Outcome: A proof of concept that increases the accuracy of Linguist's classifier.

Mentors: [@arfon](https://github.com/arfon), [@bkeepers](https://github.com/bkeepers)

Skills: C++, Ruby, language learning

### Weighted scoring for detection strategies

Summary: Linguist currently uses multiple strategies to detect the language of a file, including matching on file name, heuristics, and bayesian classification. Each strategy is relatively independent, making it difficult to aggregate them into a more probable match. We would like to explore an algorithm that combines all strategies into a confidence score.

Expected Outcome: Increased accuracy in language detection and the ability to return "unknown" if the confidence score is not above a threshold.

Mentors: [@arfon](https://github.com/arfon), [@bkeepers](https://github.com/bkeepers)

Skills: Ruby, language learning

References:
- https://github.com/github/linguist/issues/1571
- http://link.springer.com/chapter/10.1007%2F978-3-319-08979-9_39

## [Homebrew](https://github.com/Homebrew/homebrew)

Mentor: [@mikemcquaid](https://github.com/mikemcquaid)

### Allow prioritisation of taps

Summary: Taps (3rd-party Homebrew package repositories) currently just add new formulae to the list of those available. Instead of symlinking into `Library/Formula` taps should be searched for formulae and allow prioritisation and overriding of packages in the core repository.

Expected Outcome: Taps can be prioritized.

Skills: Ruby, Unix

### Handle formula renames and deletions

Summary: Currently Homebrew formulae cannot be renamed as packages are installed into e.g. `Cellar/package/1.2.3`. Provide a way of renaming formulae using Git history as a guide and handling existing installed packages.

Expected Outcome: Formulae can be renamed without causing issues for users.

Skills: Ruby, Unix, Git

### Officially support using Homebrew without Xcode/CLT

Summary: Homebrew requires developer tools (Xcode and/or the CLT) to install most software. Even when binary packages are available some developer tools are needed to fix them up after installation and Homebrew will try to compile software even with a missing compiler.

Expected Outcome: Improve the usability and tooling to fix these issues.

Skills: Ruby, Unix

### Application packages should include all their dependencies

Summary: When installing e.g. `mysql` from a binary package all runtime dependencies (e.g. `openssl`) should be included within the `Cellar/mysql/1.2.3` folder. This means that a single file should be all that's needed to be downloaded for `mysql` to have its dependencies and a manual `upgrade` or `uninstall` of `openssl` should not affect the `mysql` formula. This is inspired by the way `.app` bundles package all their dependencies.

Expected Outcome: Binary packages will include all of their dependencies.

Skills: Ruby, Unix
