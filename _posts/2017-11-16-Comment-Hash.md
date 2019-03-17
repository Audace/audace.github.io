---
layout: post
title: A proposal for keeping code comments up-to-date
comments: true
---

A common issue with codebases is documentation. This can range from from lacking
documentation altogether to having outdated documentation that stills claims the
world is flat. It's difficult, if not impossible, to enforce routine doc updates.
There are frameworks for unit and integration tests. There are linters for enforcing
style guidelines. But I have yet to see a systematic way for enforcing documentation
practices.

# Documentation Today

Code documentation can come in a few forms. Many projects will at least have a README file
that will include sections like *Getting Started* or *How to Install*. Other projects
will go one step further with in depth API docs complete with examples. Sites like
[readthedocs.io](http://readthedocs.io) enable packages to host such elaborate documentation.

Another form of documentation comes by way of docstrings and in-line comments. This
is documentation that sits within the source code and refers to specific classes,
functions or blocks of code. This type of documentation is useful as it helps
the reader understand how the code works, what the intended functionality is, and
any behavior that may not be obvious.

When diving into a codebase, it's most common to start with the former type of
documentation. README's provide a high-level overview of how the codebase is
structured. When users want to peel back a layer of abstraction, they can examine
the docstrings and in-line comments for more clarity.

# Room for Improvement

Unfortunately, the intended workflow of high-level documentation supported by
granular code-level comments falls apart as the codebase evolves over-time. The
in-line comments are the first to go outdated. Next are the class and function-level
docstrings. Sometimes the functionality evolves enough that certain behavior described
in the README no longer exists, or at least not in the way originally specified. Developers
will begin by scanning the docs looking for an explanation of an API call. They'll run
into issues at the README level and scan the in-line comments, only to find that they
too are no longer correct. They resort to reading through the code itself to understand
how things work. A few files and a couple hundred lines later, they have either
found what they were looking for or given up and moved on.

In the open-source community, this can mean developers migrate to a better maintained
project or at least one where the functionality works as described. In the context
of company codebases, moving on isn't an option and every minute pouring through
a codebase is wasted productivity.

# A Way Forward

There are two fights here: one against no documentation and one against outdated
documentation. This proposal focuses on the latter.

An intuitive solution for outdated docs would be to link documentation to the
relevant lines of code. The state could be stored such that when the code changes,
the documentation can be marked as outdated. Upon commit or pull request, the
programmer would be prompted to confirm the documentation is still correct or
update the documentation.

#### Potential Workflow
1. A programmer writes a few files, each with a class and its docstring as well as
a few methods, all of which have a corresponding docstring and a few inline comments.
2. Upon commit, each file is parsed for comments. Docstrings are related to the
function or class which they describe. In-line comments are related to the following
lines of code until the next in-line comment or the end of the code block.
3. Each piece of documentation is now identified by the filename, start
line number and source code. In order to save the state, the source code is hashed
and stored into a file in the root of the project. This would be a hidden file
such as .documentation. Each line of the file includes the filename, start line number,
code hash, and comment.
4. Now the programmer wants to change a class. He decides to add a few attributes. He
saves the file and attempts to commit. Upon commit, each line in .documentation undergoes
a verification process. If the code in the given filename from the start
line number until end line number can be hashed and match the output
as before, then the documentation is still valid. If the output is a different
hash than before, then the documentation is now out of date.

This workflow would be quite easy to automate by hooking into Github. If the verification
process for all code checks out, then the PR is ready. If the verification process for any
line fails, then the PR is blocked. The developer is then prompted for each failed
line from the .documentation file. The developer can either override a given line or
update the corresponding documentation.

# Issues to Address
This is by no means a finalized proposal and would need a fair amount of work and
protoyping to get to something useful. A few initial hurdles:

- If there is a marginal change, such as improving styling, it would be annoying
to be constantly prompted for verifying the documentation. If there were a way to ignore such
changes or to have a margin of change that is allowed without verification failing,
that would be ideal.
- It would be great to have flags for when there is insufficient documentation. Maybe
there could be a setting for the average number of lines per comment per file?
- There would need to be some type of API for overriding or updating comments
from Github interface. It would probably be more streamlined to have this as a command-line
tool or editor plugin. Warnings on the editor level and prompts on the CLI.
- This post focuses on documentation that lives in the code. Something similar
could be done on the README level.
- How can developers be prompted to update documentation? How can we avoid people
ignoring warnings and clicking override until they are no longer prevented from
committing their poorly documented code?
- If we're parsing docstrings and in-line comments, we'd need per-language parsers
to know when a class or function definition is finished.
