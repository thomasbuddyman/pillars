#Style

##Git

* Avoid merge commits by using a [rebase workflow].
* Squash multiple trivial commits into a single commit.
* Write a [good commit message].

[rebase workflow]: https://github.com/thoughtbot/guides/tree/master/protocol/git#merge
[good commit message]: http://tbaggery.com/2008/04/19/a-note-about-git-commit-messages.html


##Formatting

* Avoid inline comments.
* Break long lines after 80 characters.
* Delete trailing whitespace.
* Don't include spaces after `(`, `[` or before `]`, `)`.
* Don't misspell.
* Don't vertically align tokens on consecutive lines.
* If you break up an argument list, keep the arguments on their own lines and
  closing parenthesis on its own line.
* If you break up a hash, keep the elements on their own lines and closing curly
  brace on its own line.
* Indent continued lines two spaces.
* Use an empty line between methods.
* Use empty lines around multi-line blocks.
* Use spaces around operators, after commas, after colons and semicolons, around
  `{` and before `}`.


##Naming

* Avoid abbreviations.
* Avoid object types in names (`user_array`, `email_method` `CalculatorClass`, `ReportModule`).
* Name the enumeration parameter the singular of the collection.
* Name variables, methods, and classes to reveal intent.
* Treat acronyms as words in names (`XmlHttpRequest` not `XMLHTTPRequest`),
  even if the acronym is the entire name (`class Html` not `class HTML`).
* Name variables holding a factory with `_factory` (`user_factory`).
* Name variables created by a factory after the factory (`user_factory`
  creates `user`).

##Organization

* Order methods so that caller methods are earlier in the file than the methods they call.
* Order methods so that methods are as close as possible to other methods they call.