# Conventions

- Use minitest/spec for tests: This means that you will be writing the tests using RSpec-style syntax: it ".." do, rather than the traditional test "…" do syntax, and some_variable.must_be_xxxxx rather than assert some_variable.is_xxxxxx?

- Don't bother writing tests for validations or associations: gems such as "Shoulda" provide easy ways to test validations and associations, but this is often unnecessary. A caveat here: if you are using a format validator or something beyond just presence and uniqueness, it might be worth testing.

- When writing validations, use the validates_presence_of and validates_uniqueness_of macros. See the gist here for more info: https://gist.github.com/a8bba69518f44a989a79

- Write integration tests instead of functional tests: controllers can be difficult to test directly, and you'll get more bang for your testing buck if you write integration tests instead. Capybara with headless webkit makes it a breeze.

- Use Draper "Decorator" classes instead of Presenters or helper methods: As mendicant community friend Steve Klabnik will attest to (http://blog.steveklabnik.com/posts/2011-09-06-the-secret-to-rails-oo-design, http://blog.steveklabnik.com/posts/2011-09-09-better-ruby-presenters), using some type of Presentation class is OO. Steve also is a contributor to Draper, a neat gem that provides a base Decorator class to save you the work of creating your own base Presenter class. The Railscasts episode on Draper is a good place to learn what you need to know: http://railscasts.com/episodes/286-draper

- Use the old hash syntax hashrocket instead of the newer "hashrocket-less" one. While the newer syntax is aesthetically pleasing, it's limitation to symbol keys make it difficult to stay consistent within files.