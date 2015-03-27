#JS
This document describes a few rules for the use of JavaScript inside Hanno projects. Please read them carefully and try to follow these rules for better and more consistent code across all files in a project.

##General rules
We use two spaces for indentation. If you prefer using tabs, then editors like Sublime Text offer an option to automatically to two spaces whenever you use tab instead. Please make use of this when working on Hanno projects to have consistent indentation across all files.

##Loading JS
Avoid using inline JavaScript in `<script></script>` tags and create a separate JavaScript file whenever possible. The goal this approach of unobtrusive is to properly separate logic from representation. 
In some cases such as with AngularJS the logic is defined in the markup itself (usually as HTML attributes) which is OK for adding behaviour such as showing and hiding attributes. Resist the urge however to write business logic inside of the markup itself and keep it a separate Angular module.

###File names
The naming of files and folders usually depends on the kind of framework you're using, and you should follow the convention that suits your purpose most.

* There are no specific rules to naming files and folders
* You should use camelCase (`productController.js` instead of `product_controller.js`) 
* Give descriptive names such as `controllers` and `views` instead of cryptic ones such as `ctrls` or `vws`.

You should also separate js files logically by purpose and not overload them with functionality. It's better to have many files and a clear purpose for each of them rather than few files and not knowing what each of them is for. Keep it as simple as possible. Also look at the next section about AMD for a cleaner structure and better separation of concerns.

###AMD (Asynchronous Module Definition)
Tools like require.js allow for a cleaner separation of concerns and a better JavaScript performance because they load files only when they're needed. 

In this way, we can organize our files by modules, and create dependencies between them so that each module knows which other files need to be loaded for it to work. This is what require.js and other module loaders take care of so that we only have to define the dependencies at the beginning of the file and expose only those methods to the app that are supposed to be public.

We highly encourage the use of Asynchronous Module Definition.

###Browserify
In order to use the AMD capabilities of node.js in the browser we recommend using 

##Objects
Objects can be created with JavaScript object literal {}.

##Functions

###Function names

* Functions should be defined in camelCase.
* Function names should be descriptive and contain the purpose of function (e.g. `checkProductAvailability` instead of `check`)
* Be consistent in naming functions, and follow the convention of verb+object (e.g. `checkProductAvailability` instead of `availabilityForProduct`) 
* Use the `is` prefix for functions that return a boolean value (e.g. `isProductAvailable`)

###Modules and closures
Use modules in order to encapsulate behaviour. 

###Parameters
...

##Variables

###the `var` keyword
Always use the var keyword when defining a new variables, otherwise you'll clutter the global namespace.
So use `var myVariable = 'amazing'` instead of `myVariable = 'amazing'`

###Private vs. public
When defining variables inside of a function scope, they become private. Private variable definitions are encouraged for better encapsulation.

In order to encapsulate a variable for an object, you can wrap it inside of a function: `function Person() { var saysSomething = function() {}`
In order to expose the function to the rest of the application, you would define it on the prototype of the object or the object itself: `function Person() {}; Person.saysSomething = function() {}; `

###Naming conventions
Variables names should be descriptive. Better use long names such as `productDescription` than abbreviations `prDesc`. JavaScript code can be minified and concatenated for production, but should be readables by humans during development.
Variables that store a state should use the `is` prefix, e.g. `isActive`.