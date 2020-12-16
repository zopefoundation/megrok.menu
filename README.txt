.. caution:: 

    This repository has been archived. If you want to work on it please open a ticket in https://github.com/zopefoundation/meta/issues requesting its unarchival.

This package allows you to register browser menus and menu items for
browser views in Grok.

A menu is easily registered by creating a subclass of ``megrok.menu.Menu``::

  import megrok.menu.Menu

  class Tabs(megrok.menu.Menu):
      grok.name('tabs')
      grok.title('Tabs')
      grok.description('')

A view can then placed on a menu with the ``menuitem`` directive::

  class Edit(grok.View):
      grok.title('Edit')
      grok.description("Change this object's data.")
      megrok.menu.menuitem('tabs')

      ...

The ``title`` and ``description`` directives used here specifie the
menu item's label and description.  The ``menuitem`` directive takes
at least one argument, the menu that the item is registered to be for.
This can either be an identifier string or the menu class
itself. Other optional parameters include ``icon``, ``filter``, ``order``
and ``extra``.

For more use cases and examples, take a look to tests/test_functional.py
