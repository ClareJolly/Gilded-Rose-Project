# Gilded Rose Project

This is a project and set of resources designed to help you learn good object
oriented design principles.

You will start with a given codebase for a shop inventory system. The codebase
is completely functional and tested. Your task is to explore a number of ways
to improve its design. In the process you have the opportunity to learn:

* What 'well-designed code' means
* Forwarding (often called Delegation)
* Polymorphism
* Mocking
* Dependency injection

## Exercises

Hi and welcome to team Gilded Rose. As you know, we are a small inn with a prime
location in a prominent city ran by a friendly innkeeper named Allison. We also
buy and sell only the finest goods. Unfortunately, our goods are constantly
degrading in quality as they approach their sell by date. We have a system in
place that updates our inventory for us. It was developed by a no-nonsense type
named Leeroy, who has moved on to new adventures. Your task is to add new
features to our system so that we can begin selling new categories of items.
First an introduction to our system:

* All items have a `sell_in` value which denotes the number of days we have to sell
  the item
* All items have a `quality` value which denotes how valuable the item is
* At the end of each day our system lowers both values for every item

Pretty simple, right? Well this is where it gets interesting:

* Once the sell by date has passed, `quality` degrades twice as fast
* The `quality` of an item is never negative
* "Aged Brie" actually increases in `quality` the older it gets
* The `quality` of an item is never more than 50
* "Sulfuras", being a legendary item, never has to be sold or decreases in
  `quality`
* "Backstage passes", like aged brie, increases in `quality` as its `sell_in` value
  approaches; `quality` increases by 2 when there are 10 days or less and by 3
  when there are 5 days or less but `quality` drops to 0 after the concert

Feel free to make any changes to the `#update_quality` method and add any new
code as long as everything still works correctly. However, do not alter the
`Item` class as it belongs to the goblin in the corner who will insta-rage and
one-shot you as he doesn't believe in shared code ownership.

Just for clarification, an item can never have its Quality increase above 50,
however "Sulfuras" is a legendary item and as such its Quality is 80 and it
never alters.

### Write the tests (optional)

If you would like to get more practice writing tests or an extra challenge, go
ahead and delete the contents of `spec/gilded_rose_spec.rb`. You can then write
your own tests. Note that this won't be good practice for test-driven
development as the code is already written, but you will still learn much about
testing legacy code in the process.

### Refactor the project

Right now, the project is very hard to change — not a good thing for software.
To make life easier for yourself, you should refactor it to make it easier to
change.

This will likely involve refactoring your tests too, but remember to preserve
your test coverage by test-driving your design changes.

Feel free to keep in mind the first change illustrated below to guide your
design changes.

### Add the first new feature

We have recently signed a supplier of conjured items. This requires an update to
our system:

* "Conjured" items degrade in `quality` twice as fast as normal items
