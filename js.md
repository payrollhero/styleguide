## Javascript & Coffeescript Styleguide

### Coding Style & Syntax
For raw coding style I will refer you to:
Javascript: https://github.com/airbnb/javascript
Coffeescript: https://github.com/polarmobile/coffeescript-style-guide

### Best practices

Use Coffeescript where possible.  It is easier to read and avoids many of the 'gotchas' when writing normal javascript.

### Coffeescript best practices

Always use classes where possible.  This will keep you from polluting the global namespaces.
Namespace your classes appropriately into the application, this will make your classes more reuseable.

### Private member functions and variables

Do NOT use the practice of using anonymous functions with closure variables to create private member functions for a class.  This is NOT recommended and is very difficult to read.  Instead use _ to start the name of your member function to indicate that it should be private.

### Utility functions

Place useful converion and utility functions by extending Underscore (_.extend ... ).
