#Sass

"[Sass](http://sass-lang.com/) is the most mature, stable, and powerful professional grade CSS extension language in the world." -- and we love it.


##Organisation

#####File structure

* Prefer the same file structure that is found in a Rails app/views. At the very least, try logically splitting up your CSS into smaller modules -- `global.scss`, `app.scss`, `typography.scss`, `ie.scss`, `mixins.scss`, `hacks.scss`, `animations.scss`, etc -- as stylesheets tend to become quite long on bigger projects.

#####Within a stylesheet
* Use HTML structure for ordering of selectors. Don't just put styles at the bottom of the Sass file.


##Formatting

* Use the [*SCSS* syntax](http://sass-lang.com/documentation/file.SCSS_FOR_SASS_USERS.html).
* Use only lowercase letters.
* Use hyphens when naming mixins, extends, non-BEM classes, functions & variables: `fiesta-red`, not `fiesta_red` or `fiestaRed`.

===

* Use a space between selector and `{`.
* When grouping selectors, keep individual selectors to a single line.
* **Example:**

          .panel,
          .panel--framed,
          .panel__footer {
            ..
          }

===

* Indent declarations.
* Each declaration should appear on its own line.
* Place closing brackets of declaration blocks on a new line.
* Separate rule sets with a blank line.
* **Example:**

          .panel {
            property: value;
            property: value;
          }

          .panel--framed {
            property: value;
            property: value;
          }

===

* Use shorthand declarations.
* Use single quotation marks for attribute selectors and property values: `input[type='text']`, `background: url('..')`.
* Use space between property and value: `width: 20px`, not `width:20px`.
* Use space after a `,` when declaring a value: `rgba(255, 255, 255, 0.4)`, not `rgba(255,255,255,0.5)`;
* Don't add a unit specification after `0` values: `box-shadow: 0 0 5px 2px #eee`, not `box-shadow: 0px 0px 5px 2px #eee`.
* Don't omit a `0` in decimal values: `opacity: 0.5`, not `opacty: .5`.
* Use space around operands: `$vertical-spacing * 1.5`, not `$vertical-spacing*1.5`.
* Use parentheses around individual operations in shorthand declarations:
  * `padding: ($vertical-spacing * 1.5) ($horizontal-spacing * 2);`.

===

* When using BEM classes, avoid nesting *element* and *modifier* rule sets within their *block* rule set. Indent *element* rule to show relation and improve readability and scannability of the document:

          .panel {
            padding: 2rem;
            border-radius: 3px;
            background: $panel-background-colour;
          }

            .panel__header {

              h2,
              h3 {
                margin-bottom: 1rem;
                color: $panel-title-colour;
              }

              p { color: $panel-text-colour; }
            }

            .panel__footer {
              margin-top: 1rem;
              padding-top: 1rem;
              border-top: 1px solid $panel-border-colour;
            }

          .panel--framed {
            border: 2px solid $panel-border-colour;
          }

* In short, if you've used BEM naming conventions, then nesting the rules themselves just creates over-specificity.

===
* Avoid unnecessary nesting.
* Don't nest more than 2 selectors deep.
* Place Media Queries directly within a rule set, do not create a separate `@media` sections to dump your responsive CSS in.
* Don't nest within a Media Query.
* **Example:**
  * **Yes**:

          .hero {
            padding: 3rem 0;
            text-align: center;

            @media .. {
              padding: 6rem 0;
            }

            @media .. {
              padding: 12rem 0;
            }

            h2 {
              margin-bottom: 1rem;
              color: #000;

              @media .. {
                margin-bottom: 2rem;
              }

              @media .. {
                margin-bottom: 4rem;
              }
            }
          }
  * **No**:

          .hero {
            padding: 3rem 0;
            text-align: center;

            h2 {
              margin-bottom: 1rem;
              color: #000;
            }

            @media .. {
              padding: 6rem 0;

              h2 {
                margin-bottom: 1rem;
              }
            }

            @media .. {
              padding: 12rem 0;

              h2 {
                margin-bottom: 4rem;
              }
            }
          }
  * PS: Check out these [useful tips on Media Query with Sass](http://davidwalsh.name/write-media-queries-sass).

===

* Use `//` for comment blocks not `/* */`. (`//` at the beginning of a line marks a comment in Sass. It won't go into the processed and minified stylesheet which we put to production.)
* Avoid inline comments--use new lines for comments.


##Variables and such

* Always use variables for colours and font stacks (at least):
  * `$fiesta-red: #dd1923;`
  * `$font-sans-serif: 'proxima nova', helvetica, arial, sans-serif;`
* Use meaningful names: `$panel-background-colour` not `$nice-colour` or `$pnl-bg`.
* Prefer hex color codes `#000` (over `rgb`, `hsl` and colour names).
* Use SCSS [(HSL) functions](http://sass-lang.com/documentation/Sass/Script/Functions.html) to tweak the base colours rather than declaring random colour values all over the place:

          .panel {
            background: $panel-background-colour;
          }

            .panel__footer {
              background: $darken($panel-background-colour, 5%);
            }
* And if you use an HSL function to create a new colour variant, which you're going to use more than once or twice, please save that further variant into another variable. i.e. don't use `$darken($panel-background-colour, 5%)` in 10 places across your stylesheet.


##PX vs EM vs REM

* Use `px` for borders, box-shadows, text-shadows, etc.
* Use `rem` for consistent margins and paddings, if needed.
* *Prefer* `em` for everything else.
* **Always** use `em` to control font-size (set base font-size to 100%, rather than 16px, to prevent your stylesheet from overriding user's browser settings).
* **Always** use `em` in Media Queries for better scaling.


##Specificity / Performance

* Don't use #IDs for styling. Use classes instead.
* Use #IDs as little as possible
* **Strongly avoid** using `!important`. It should be used only in exceptional circumstances.
* If you do use `!important`, add a comment to explain why you're doing this. If necessary, prefix that comment with FIXME or TODO for future editors. e.g. `FIXME: Forced this display mode for now, to fix a roadblock bug preventing handover, but this should be fixed later on and will probably cause issues with other navigation styling`
* Don't use the HTML tag in the class name: `header.home` not `header.header--home`; `section.news` not `section.news-section`.
* Avoid using HTML tags on classes with specific class names: `.twitter-testimonials`, `.dropdown`; not `div.twitter-testimonials`, `ul.dropdown`.
* Consider using [quasi-qualified selectors](http://cssguidelin.es/#quasi-qualified-selectors) to avoid specificity issues.
* Use the prefix `js__` for classes that JavaScript uses to trigger behaviour. These classes should never be used for styling purposes.
* **Example:** `js__accordion` would trigger an accordion behaviour, but a separate `accordion` class would be used for styling.
