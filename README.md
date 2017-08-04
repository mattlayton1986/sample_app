# Ruby on Rails Tutorial sample application

## sample_app

This is the sample application for
[*Ruby on Rails Tutorial:
Learn Web Development with Rails*](http://www.railstutorial.org/)
by [Michael Hartl](http://www.michaelhartl.com/).

## License

All source code in the [Ruby on Rails Tutorial](http://railstutorial.org/)
is available jointly under the MIT License and the Beerware License. See
[LICENSE.md](LICENSE.md) for details.

## Getting started

To get started with the app, clone the repo and then install the needed gems:

```
$ bundle install --without production
```

Next, migrate the database:

```
$ rails db:migrate
```

Finally, run the test suite to verify that everything is working correctly:

```
$ rails test
```

If the test suite passes, you'll be ready to run the app in a local server:

```
$ rails server
```

For more information, see the
[*Ruby on Rails Tutorial* book](http://www.railstutorial.org/book).

# My Solutions to Exercises

## Section 3.1
1. Confirmed. It does.
2. Verified. It works.

# Section 3.2.1
1. Successfully generated Foo controller with `rails generate controller Foo bar baz`
2. Successfully destroyed Foo controller with `rails destroy controller Foo bar baz`

# Section 3.4.2
1. Tests run successfully. Replaced "Ruby on Rails Tutorial Sample App" in `test/controllers/static_pages_controller_test.rb` with an instance variable `@base_title` and used string interpolation to inject `@base_title` into the title of each page.

# Section 3.4.3
1. Contact Page added. Added `get "static_pages/contact"` route. Added `contact` action in StaticPages controller. Created new Contact Page view (/views/static_pages/contact.html.erb). Added content to Contact Page. All tests pass.

# Section 3.4.4
1. Test passes. Test looks similar to other tests written so far: 
```
test "should get root" do
  get root_url
  assert_response :success
end
```
2. Commenting out `root 'static_pages#home'` does cause tests to fail, and tests pass when uncommented.

