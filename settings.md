# Settings

- [Languages](#languages)
- [Menu types](#menu-types)
- [Codelist](#codelist)
- [Plugins](#plugins)
- [Roles](#roles)
- [Permissions](#permissions)

<a name="languages"></a>
## Languages

Language management provides you with the possibility to have a multi-lingual website. You can add as many languages as
you want by clicking the **Add new** button. At least one language is required for the website to work.

#####Locale
Unique, usually 2-letter string, which represents the language abbreviation, eg. *en*.

#####Label
Representational language title, eg. *English*.

#####Order
The sort order, taken into account in administration and language selection on the website, expressed by the number,
eg. *10*.

#####Is default?
Default language in which the website opens on first visit. Only one language can be default and if you mark this
checkbox, any other language that was set as default will be un-selected.

#####Is hidden?
When checked, the language will be disabled and hidden on the websites' language selection.

<a name="menu-types"></a>
## Menu types

The system allows you to create different menu types (navigations) with appropriate elements (menu items) and place
them on the website. 

Let's say you want to have a main menu and a sidebar menu. For this occasion you must create a "Main menu" type and a
"Sidebar menu" type. Later on, you can assign a dedicated views (templates) for each of the menu types and style them
accordingly.

Each menu type must have a unique code, which is used in views with a custom Blade directive **@menu**.
Read more about the usage of it here. ***TODO: link to the @menu logic***

#####Code
Unique code that represents the single menu type, eg. *sidebar*.

#####Title
Representational menu type title, eg. *Main Menu*.

#####Order
The sort order, taken into account only in administration, expressed by the number, eg. *10*.

<a name="codelist"></a>
## Codelist

Codelist is a collection of grouped data items which are widely used across the administration. 

On the initial installation, there are three codelist groups present: Dictionary group, Page layout and Content 
position.

For example, Content position group defines all the positions that are available for positioning the content blocks
across the website. Each position is later on defined in the views.
Read more about the usage content positions here. ***TODO: link to the content positions logic***

####Codelist group

#####Code
Unique code that represents the single codelist group, eg. *content_position*.

#####Title
Representational codelist group title, eg. *Content Position*.

#####Order
The sort order, taken into account only in administration, expressed by the number, eg. *10*.

####Codelist item

#####Code
Unique code that represents the single codelist group item, eg. *center*.

#####Title
Representational codelist group item title, eg. *Center position*.

#####Order
The sort order, taken into account only in administration, expressed by the number, eg. *10*.

<a name="plugins"></a>
## Plugins

<a name="roles"></a>
## Roles

<a name="permissions"></a>
## Permissions