# Project Structuring & Modules

Bigger projects require structure and architectural considerations.

## For budget App, consider:

This is an example of how to think about a project's structure:

### Firstly, compile a list of tasks that must be completed, for exampe.

1. All functionality of app starts with click of **enter** button. Therefore an **event handler** must be used. - *UI*
2. The value entered must be retrieved.
3. The new value must be added to data structure.
4. The new item must then be added to the UI.
5. The budget must then be calculated.
6. And finally, the UI must be updated.

### The organise them into modules. 

Modules are units of code that are separated and organised, break up the code into logical parts that can then interact. 

They also facilitate data privacy where needed.

In this example, the application can be modulated as follows;

1. There should be a User Interface module. *( Get input values, add the values to the UI, update the UI, add item to UI)*
2. There should be a data structure module *( Add new item to data structure, Calculate budget  )*
3. Controller Module: *(Add event handler, add link between the two other modules)*.