#Basic JavaScript rules

**Style**
* 2 spaces – for indentation
* Single quotes for strings – except to avoid escaping
* Use semicolons at the end of each statement
* Space after keywords if (condition) { ... }
* Space after function name function name (arg) { ... }
* Use PascalCase for classes, lowerCamelCase for variables and functions, SCREAMING_SNAKE_CASE for constants, _singleLeadingUnderscore for private variables and functions.

**Variables**
* Eliminate unused variables
* Name the context variable self – var self = this
* Accidental window.self usage is dissallowed (happens when var self = this is omitted)
* Always prefix browser globals with window – except document and navigator are okay

**Operators**
* Always use === instead of == – but obj == null is allowed to check null || undefined.

#Advanced rules
* Prefer ES6 classes over prototypes.
* Prefer arrow functions =>, over the function keyword except when defining classes or methods.
* Prefer template strings over string concatenation.
* Prefer promises over callbacks.
* Prefer array functions like map and forEach over for loops.
* Use const for declaring variables that will never be re-assigned, and let otherwise.
* Avoid var to declare variables.