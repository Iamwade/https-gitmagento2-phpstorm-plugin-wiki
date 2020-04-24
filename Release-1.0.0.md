# WHAT’S NEW IN MAGENTO PHPSTORM 1.0.0

This major release includes MFTF support, Require JS mapping support, GraphQl support, Plugin declaration inspection,
code generation, and many more.

## Code generation

The code generation is one of the most wanted features by the Magento community. There are a bunch of existing open source solutions, however, generating code using the IDE seems to be the most convenient way to go. Therefore we created several actions that help with common Magento 2 customizations. This list will be extended in the future.
All templates used for generation can be found and edited in `Preferences/Settings | Editor | File and Code Templates`.

### Create a new module

You can create a new Magento 2 module from the context menu or by pressing Ctrl(⌘)+N. 

### Create a new module as a separate project

This should be useful for extension developers. When the project is created IDE suggests selecting the PHP version and suggests including the Magento source code to PHP include paths.

### Create a plugin for a class public method

The action creates a plugin class method along with a plugin declaration record in di.xml in the scope of the specified module and area. A plugin class and di.xml being created if needed.

### Override class by reference
 
The action creates a class along with a preference declaration record in di.xml in the scope of the specified module and area.

 
### Create an observer for an event

You can create a new observer from the context menu. Just right click on the event name and specify the module, area, and observer name.

#### Create a module file using a template (MVP).

We added several actions for creating module files from templates.

* Block:

* ViewModel:

* GraphQl Resolver:

### In editor generation of Plugin Methods

You can create a new plugin method from the context menu (generate...) or by pressing Ctrl(⌘)+N.

## Inspections

### Plugin inspection in the scope of PHP class

Inspection highlights the following cases:
* Plugin declared for a final class
* Plugin declared for a final method
* Plugin declared for a constructor
* Plugin declared for a not public method
* Plugin declared for a static method
* Incompatible parameter
* Redundant parameter

### Plugin duplication inspection in the scope of di.xml

This inspection highlights possible accidental plugin duplication.
Plugin names must be unique. In case overriding is wanted, the best practice is to disable the original plugin and give a unique name to the current plugin.

### Observer duplication inspection in the scope of events.xml

Inspection for observer declaration records, similar to plugin one.

### GraphQL resolver inspection in the scope of PHP class (Requires GraphqlJs plugin)

If a class is configured in `schema.graphqls` as a resolver, it should implement one of the resolver interfaces. 

### Cacheable false in the scope of the default layout

This inspection highlights the` cacheable` attribute which is set to be false in default.xml as that can make the whole site uncacheable.

## Reference and navigation

### Line markers from a Plugin class to a Target class

In the previous version of the plugin existed a possibility to navigate from the target class and method to the plugin class and method via line markers. Now we added line markers for the navigation in the opposite direction.

### MFTF support

We added support of the most commonly used MFTF XML directives.

* Page URL completion and reference

* Action group completion and reference

* Test extends attribute completion and reference

* Selector completion and reference

### RequireJs mapping support

The RequireJs configuration file `requirejs-config.js` is commonly used in the different areas of Magento 2. There is a possibility to make aliases for a component using it. We added support of this mapping to have an ability to easily navigate between JS files.

* Reference on injected argument

* Completion and reference in XML

### GraphQL support (Optional, Requires GraphqlJs plugin)

Sometimes you may need to quickly navigate from GraphQl resolver to schema and vice versa. We added line markers to make it possible. To use this functionality please install GraphqlJs plugin https://plugins.jetbrains.com/plugin/8097-js-graphql.

Thanks for our awesome contributors who make this release possible: 
Vasilii Burlacu, Roman Glushko, Vitaliy Boyko, Eduard Chitoraga, Max Mezhensky, Yaroslav Rogoza, Andrew Chornij
Shankar Konar
Alexander Shkurko
Bohdan Harniuk
Eugene Tulika
Igor Melnikov, Dan Mooney, Lena Orobei




