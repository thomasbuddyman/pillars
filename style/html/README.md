#HTML

##General rules

* Avoid using inline styles as they'll override any other CSS you write and are a nightmare to refactor. Styles belong in stylesheets, and if you want to quickly test a concept without polluting the main stylesheet(s), create a separate one called '*hacks*' if someone before you hasn't done that already.
* Always use double quotes for attributes: `header class="hero hero--home"` not `header class=hero hero--home`
* Separate independent HTML snippets with an empty line to keep your markup easily scannable:

        <body>
      
          <nav class="navbar">
        
            <a href="/" class="navbar__logo">
              <img src="/assets/images/logo.svg">
            </a>
        
            <a href="/features">Features</a>
            <a href="/pricing">Pricing</a>
        
            <form>
              <input type="search" placeholder="Search...">
            </form>
        
          </nav>
      
        </body>
* Comments are helpful and therefore commenting is encouraged. However, be sensible and avoid obvious comments. Eg: Comments next to closing tags indicating a thematic break in your markup are usually helpful in long documents.

##Naming conventions

We're using a [BEM](https://en.bem.info/)-like naming convention. If you've never heard of it or need to quickly refresh your knowledge, CSSWizardry's Harry Roberts has written a very straightforward [overview](http://cssguidelin.es/#bem-like-naming) that covers everything you need to know.

We also follow these rules in order to keep our code easy to read, understand and maintain:

* Use names that are as short as possible but as long as necessary.
* Use the prefix `js__` for classes that JavaScript uses to trigger behaviour. These classes should never be used for styling purposes.
  * Example: `js__accordion` would trigger an accordion behaviour, but a separate `accordion` class would be used for styling.
* Group related class names. Prefer separating groups of classes with a double space:
  * **Yes:** `div class="panel panel--framed jumbotron__panel  product product--featured"`
  * **No**: `div class="jumbotron__panel panel product panel--framed product--featured"`
  * **Yes:** `div class="columns  medium-10 medium-centered  large-8 large-uncentered"`
  * **No:** `div class="medium-10 columns large-8 medium-centered large-uncentered"`


**To BEM or not to BEM?**

"When you are using BEM.., it is important to remember that you don’t need to use it for everything..." -- Harry Roberts answers it very well [here](http://csswizardry.com/2013/01/mindbemding-getting-your-head-round-bem-syntax/#to-bem-or-not-to-bem).
  
