.. HuskyCrates - Last updated v1.7.2

Writing Your Own Config
===============================
.. image:: http://i.imgur.com/ZRN1RVN.png

************
Starting Out
************

We suggest using an app such as Sublime Text which has a HOCON module that can aid you in properly formatting your config files.

**Very important:** Please make sure you save your config in UTF-8 ecoding the *first* time you save! It will prevent a lot of potential problems for your config.
Please note that HOCON does sort everything within 

Your first line of every config is always going to be ``crates {``. This is necessasry to indicate that this is crates information
The next line is where your first crate is initiated this is your ``crate_id`` which you will use to call your crates in commands. Give it an easy to type name and type on the next line your ``<crate_id> {``.
You can have as many crates as you want but lets make your first crate.

*****
Items 
*****

The first and most important part of a crate is its items, items are an array which means it starts as shown::

    items=[
    {

The open brace marks your first reward that can be given in your crate. To add another reward, once you're done add a comma after the closing brace.

=====
Count
=====

``count=<int>``

Your count dictates how many of an item are given to the player. If your item is a command this should be set to 1.

==============
Format Version
==============

``formatversion=1``

Absolutely necessary in every item.

=================
Damage (Optional)
=================

``damage=<int>``

Optional for the damage value of your item given.

---------
Huskydata
---------

Huskydata is where all information in the scope of crate rewarding happens. Nothing in terms of inventory apperance is here yet.::

    huskydata {
        rewards=[

Note that rewards is an array like items is, this allows you to give more than one item or run multiple commands when the crate is opened.

**There are two ways you can do rewards**

+-----------------+-----------------+
| Item            | Command         |
+=================+=================+
|``type=item``    |``command=<>``   |
|                 +-----------------+
|                 |``type=command`` |
+-----------------+-----------------+
