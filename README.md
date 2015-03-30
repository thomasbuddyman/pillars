#Pillars

These are the frontend code standards that are used by the whole Hanno team while working on projects. If a client has their own internal code standards in an existing product, these can, of course, override our own.

But in all other cases, we should stick to standards here, so thar we can get just a little closer to producing great code, all day long.

For more information about how we work together, check out our [Playbook](http://playbook.hanno.co/)!


#Global Standards

Keep your code simple and DRY, optimise for readability and maintainability.
If you feel like a comment would help your fellow developers understand what a snippet your wrote is doing and why -- add a comment to it.


##General formatting rules

* Use soft-tabs with 4 spaces for indentation. In Sublime Text menu, View > Indentation, check 'Indent using spaces' and 'Tab width: 4'.
* Break long lines after 80 characters so your code is more comfortable to read and easy to scan.
* Check for, and delete, trailing whitespace. [TrailingSpaces](https://github.com/SublimeText/TrailingSpaces) plugin for Sublime Text is your best friend here.
* Avoid inline comments.
* Don't include spaces after opening brackets `(`, `[` or before closing brackets `]`, `)`.
* Don't misspell ;)


##Git

* Avoid merge commits by using a [rebase workflow](https://www.atlassian.com/git/tutorials/merging-vs-rebasing/workflow-walkthrough).
* Squash multiple trivial commits into a single commit.
* Write a [good commit message](https://robots.thoughtbot.com/5-useful-tips-for-a-better-commit-message).


##Testing and debugging

Always make use of [CSS Source Maps](https://developer.chrome.com/devtools/docs/css-preprocessors#toc-how-css-source-maps-work)


##Code Reviews

Refer to [code review guide by Thoughtbot](https://github.com/thoughtbot/guides/tree/master/code-review)



##Contributing

To force a modification:

* Create an issue for the team and explain why you wish to make the change
* Gain consensus
* Create a PR with the modification


##Credit

For the sake of standardisation and not inventing the wheel, Pillars are partially built upon elements borrowed from [Thoughtbot](https://github.com/thoughtbot/guides), [GitHub](https://github.com/styleguide/css) and [Isobar](http://isobar-idev.github.io/code-standards/), updated and adapted in accordance with Hanno team's own preferences.
