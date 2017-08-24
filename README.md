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

## Section 3.2.1
1. Successfully generated Foo controller with `rails generate controller Foo bar baz`
2. Successfully destroyed Foo controller with `rails destroy controller Foo bar baz`

## Section 3.4.2
1. Tests run successfully. Replaced "Ruby on Rails Tutorial Sample App" in `test/controllers/static_pages_controller_test.rb` with an instance variable `@base_title` and used string interpolation to inject `@base_title` into the title of each page.

## Section 3.4.3
1. Contact Page added. Added `get "static_pages/contact"` route. Added `contact` action in StaticPages controller. Created new Contact Page view (/views/static_pages/contact.html.erb). Added content to Contact Page. All tests pass.

## Section 3.4.4
1. Test passes. Test looks similar to other tests written so far: 
```
test "should get root" do
  get root_url
  assert_response :success
end
```
2. Commenting out `root 'static_pages#home'` does cause tests to fail, and tests pass when uncommented.

## Section 4.2.2
1. `city = "Chicago"`, `state = "Illinois"`
2. `puts "#{city}, #{state}"` #=> `Chicago, Illinois`
3. `puts "#{city},\t#{state}"` #=> `Chicago,        Illinois`
4. `puts '#{city},\t#{state}'` #=> `Chicago,\tIllinois`

## Section 4.2.3
1. `"racecar".length` # => 7
2. `"racecar".reverse` # => "racecar"
3. `s == s.reverse` # => true
4. `prints "Its a palindrome!"`; returns nil and prints nothing

## Section 4.2.4
1. `s == s.reverse`
2. Confirmed.
3. Confirmed.

## Section 4.3.1
1. `a = ["A man", "a plan", "a canal", "Panama"]`
2. `s = "A mana plana canalPanama"`
3. 
```
s = s.split.join  #=> "AmanaplanacanalPanama"
s = s.downcase    #=> "amanaplanacanalpanama"
s == s.reverse    #=> true
```
4. `alpha[7]`           #=> 'h'   
   `alpha.reverse[7]`   #=> 's'

## Section 4.3.2
1. `(0..16).map { |e| puts 2**e }`
2.
```
def yeller(array = [])
  array = array.map { |elem| elem.upcase }
  return array.join
end
```
3. 
```
def random_subdomain
  return ('a'..'z').to_a.shuffle[0..7].join
end
```
4.
```
def string_shuffle(s)
  s.split('').shuffle.join
end
```

## Section 4.3.3
1.
```
spanish = { one: "uno", two: "dos", three: "tres" }
spanish.each do |key, value|
  puts "'#{key}' in Spanish is '#{value}'"
end
```
2. 
```
person1 = { first: "Matt", last: "Layton"}
person2 = { first: "Lucas", "last: "Van Duyne" }
person3 = { first: "Sir Frostington", last: "Kittypuss" }
params = { father: person1, mother: person2, child: person3 }
#=> {:father=>{:first=>"Lucas", :last=>"Van Duyne"}, :mother=>{:first=>"Matt", :last=>"Layton"}, :child=>{:first=>"Sir Frostington", :last=>"Kittypuss"}}
```
3.
```
# random password generator
def random_pw
  return ('a'..'z').to_a.shuffle[0..15].join
end

# user hash
user = { :name => "Matt Layton", :email => "layton.matt1986@gmail.com", :password_digest => random_pw }
#=> {:name=>"Matt Layton", :email=>"layton.matt1986@gmail.com", :password_digest=>"jxadqirmbklzwogt"}
```
4. `{ "a" => 100, "b" => 300 }`

## Section 4.4.1
1. `(1..10)`
2. `Range.new(1, 10)`
3. true

## Section 4.4.2
1. Range < Object < BasicObject
   Hash < Object < BasicObject
   Symbol < Object < BasicObject
2. `self == reverse` works just like `self = self.reverse`

## Section 4.4.3
1. racecar => true; onomatopoeia => false; Malayalam.downcase => true
2. 
```
class String
  def shuffle
    self.split('').shuffle.join
  end
end
"foobar".shuffle  #=> "rboofa"
```
3. It does work

## Section 4.4.4
1. & 2. (Removed toy_app files from c9)

## Section 4.4.5
1. Revised `example_user.rb` file:
```
class User
  attr_accessor :first_name, :last_name, :email
  
  def initialize(attributes = {})
    @first_name = attributes[:first_name]
    @last_name = attributes[:last_name]
    @email = attributes[:email]
  end
  
  def full_name()
    "#{@first_name} #{@last_name}"
  end
  
  def formatted_email
    "#{full_name} <#{@email}>"
  end
end
```
2. 
```
def alphabetical_name
  "#{@last_name}, #{@first_name}"
end
```
3. `user.full_name.split == user.alphabetical_name.split(', ').reverse` #=> true

## Section 5.1.1
1. `curl -OL cdn.learnenough.com/kitten.jpg`
2. `mv kitten.jpg app/assets/images/`
3. `<%= image_tag("kitten.jpg", alt: "Cute Kitten" %>`

## Section 5.1.2
1. `<%#= image_tag("kitten.jpg", alt: "Cute Kitten") %>`; kitten image does not show up at all in source code
2. Added
```
img {
  display: none;
}
```
The image no longer appears on the page, but the `<a><img ... /></a>` does still appear in source code

## Section 5.1.3
1. Done
2. Confirmed: tests are red.
3. After `_rails_default.html.erb` is created, all tests pass.

## Section 5.2.2
1. Done.

## Section 5.3.2
1. `get '/help', to: 'static_pages#help', as: 'helf'`
2. change test to `get helf_path`; tests pass
3. Done.

## Section 5.3.3
1. and 2. Done

## Section 5.3.4
1. Integration tests do fail if `about_path` is changed to `contact_path`
2. Both `application_helper_test`s pass successfully.

## Section 5.4.1
1. Modified test to `get signup_path`
2. The change in #1 does cause one test to fail.

## Section 5.4.2
1. Added `signup_path` in previous section.
2. Test does run red when commented out, green when not commented out.
3. Added test to navigate to sign up page and verify title is correct:
```
get signup_path
assert_select "title", full_title("Sign Up")
```

## Section 6.1.1
1. `schema.rb` does not contain `id` field, since its automatically generated by the db.
2. `schema.rb` contains no table data once rollback is performed.
3. Re-running migration adds the data back to `schema.db`

## Section 6.1.2
1. Confirmed: User < Application Record < ActiveRecord::Base

## Section 6.1.3
1. `user.name.class` and `user.email.class` both return `String` data type
2. ActiveSupport::TimeWithZone

## Section 6.1.4
1. `find_by_name` works
2. `User.all.class` returns User::ActiveRecord_Relation
3. `User.all.length` returns a length of 2

## Section 6.1.5
1. `user.name = "Matthew Layton"`
`user.save`
2. `user.update_attributes(email: "layton.matt1986@gmail.com")`
3. `user.created_at = 1.year.ago`
`user.save`

## Section 6.2.1
1. `user = User.new(name: "Matthew Layton", email: "mattlayton1986@gmail.com")`
   `user.valid?` #=> true
2. true

## Section 6.2.2
1. ["Name can't be blank", "Email can't be blank"]
2. `u.errors.messages` => {:name=>["can't be blank"], :email=>["can't be blank"]}
   `u.errors.messages[:email]`

## Section 6.2.3
1. `user.valid?` #=> false
2. `user.errors.full_messages` #=> ["Name is too long (maximum is 50 characters)", "Email is too long (maximum is 255 characters)"]

## Section 6.2.4
1. Confirmed: all valid addresses match, all invalid addresses do not
2. Added updated regex: tests pass now
3. Confirmed: all valid addresses (still) match, all invalid addresses (still) do not

## Section 6.2.5
1. Test added and passes
2. `email.downcase!` does still allow tests to pass

## Section 6.3.2
1. `user.valid?` #=> false
2. `user.errors.full_messages` #=> ["Password can't be blank"]

## Section 6.3.3
1. `user.valid?` #=> false
2. `user.errors.full_messages` #=> ["Password is too short (minimum is 6 characters)"]

## Section 6.3.4
1. `user.find_by(id: 1)`
2. Skip
3. Skip

## Section 7.1.1
1. controller: static_pages, action: about
2. 
```
---
id: 1
name: Matthew Layton
email: layton.matt1986@gmail.com
created_at: !ruby/object:ActiveSupport::TimeWithZone
  utc: &1 2017-08-15 02:17:22.207886000 Z
  zone: &2 !ruby/object:ActiveSupport::TimeZone
    name: Etc/UTC
  time: *1
updated_at: !ruby/object:ActiveSupport::TimeWithZone
  utc: &3 2017-08-15 02:17:22.207886000 Z
  zone: *2
  time: *3
password_digest: "$2a$10$IF/LaC3I0IC0IsNzTrmXOeJ0G4rRtpzlPR4UExsLAgtN8aGLR1fGm"
=> nil
```
`puts user.attributes.to_yaml` yields identical console output results as `y user.attributes`

## Section 7.1.2
1. Added with `<%= @user.created_at %>, <%= @user.updated_at %>`
2. Added with `<%= Time.now %>`; time updates each time browser is refreshed.

## Section 7.1.3
1. `puts params.to_yaml` #=>
```
--- !ruby/object:ActionController::Parameters
parameters: !ruby/hash:ActiveSupport::HashWithIndifferentAccess
  controller: users
  action: show
  id: '1'
permitted: false
nil
```
2. @user = nil

## Section 7.1.4
1. eaced42f18e456a5e142146facc83c99
2. This code does work as expected.
3. This does work. The `options` hash parameter allows for the possibility of passing multiple options into the helper; the keyword arguments form gives the helper _only_ the `size` option.

## Section 7.2.1
1. "Undefined method 'nome' for User..."
2. Replacing all occurrences of `f` with `foobar` does still work. It would still be a bad idea, though, because variable names should have some indication of what their function/reference is.
3. 
## Section 7.2.2
1. Forms are more complicated than typical HTML features and require more understanding of back-end processes for form submission, validation, and database storage than other markup features, so its MORE than enough to be dangerous with.

## Section 7.3.2
1. Admin parameter does show up in debug dump:
```
--- !ruby/object:ActionController::Parameters
parameters: !ruby/hash:ActiveSupport::HashWithIndifferentAccess
  admin: '1'
  controller: users
  action: new
permitted: false
```

## Section 7.3.3
1. Changing minimum length of password to 5 does update error message: "Password is too short (minimum is 5 characters)"
2. Both are routes for the `GET users#new` action. When clicking the Signup button on the home page, the `signup_path` is called, which is defined in the routes as `get '/signup', to: 'users#new'`. When submitting the Signup form, however, an invalid form submission reloads the /users url via the call to `render 'new'`, which route is defined in `resources :users`, thus allowing for two different paths to display the same page.

## Section 7.3.4
1. Implemented error message tests as follows:
```
assert_select 'div#error_explanation'
assert_select 'div.field_with_errors'
```
2. Making these changes does ensure the URL /signup shows for both unsubmitted and submitted-with-errors signup pages. All tests still pass, because the form does not POST/#create successfully, so `users#new` is rendered each time, which is what our test currently expects.
3. Tests are still green after `changing users_path` to `signup_path`.
4. Made appropriate changes to tests and all tests pass. New test added is: `assert_select 'form[action="/signup"]'`

## Section 7.4.1
1. User is created successfully: `User.count` is 2, and `User.find(2)` returns the newly-created user.
2. Both forms of the redirect work successfully and correctly.

## Section 7.4.2
1. `"#{:success}"` => Returns the raw string "success"
2. The flash iteration exercise uses symbol interpolation to convert the key and value of each message into a string before `puts`ing them to the console.

## Section 7.4.3
1. `User.find_by(email: "example@railstutorial.org")`
2. Done, and Gravatar correctly appears.

## Section 7.4.4
1. Per the hint given in the exercise: `assert_not flash.empty?` Added an additional test to make sure the correct key shows up for the flash: ` assert_select 'div[class$="success"]'`
2. Using `content_tag` to clean up the flash HTML still passes all tests.
3. Tests do fail with a "RuntimeError: not a redirect! 204 No Content" when the redirect command is commented out.
4. If `@user.save` is false, nothing will be written to the database, so the `User.count` will not be increased by one.

## Section 7.5.3
1. SSL lock and `https://` both appear in browser bar of Heroku app.
2. Profile successfully created and Gravatar appears correctly.

## Section 8.1.1
1. `GET login_path` retrieves the page that displays the login form. `POST login_path` transmits the login form data to the server for validation.
2. 
```
rails routes | grep users#
 ``signup GET    /signup(.:format)         users#new
          POST   /signup(.:format)         users#create
    users GET    /users(.:format)          users#index
          POST   /users(.:format)          users#create
 new_user GET    /users/new(.:format)      users#new
edit_user GET    /users/:id/edit(.:format) users#edit
     user GET    /users/:id(.:format)      users#show
          PATCH  /users/:id(.:format)      users#update
          PUT    /users/:id(.:format)      users#update
          DELETE /users/:id(.:format)      users#destroy
```
```
rails routes | grep sessions#
    login GET    /login(.:format)          sessions#new
          POST   /login(.:format)          sessions#create
   logout DELETE /logout(.:format)         sessions#destroy
```

## Section 8.1.2
1. Rails knows to submit the form to the Sessions controller's `create` action because we've defined the `form_for` url as `login_path` and the data will be `post`ed; `post login_path` is defined in our routes as using the `sessions#create` action of the controller.

## Section 8.1.3
1. Using Rails console, each of the values in Table 8.2 were confirmed to be correct.

## Section 8.1.5
1. Followed sequence in browser and flash properly disappears when a subsequent request is made.

## Section 8.2.1
1. bFFmZ2ExSjM4ZC9KT2piajdIVHN4NTVjTUxQbmhSU2xkNmh2TkZlbFMyeWY2OFRwV2I1M3RjVld4enA2S0p1R2s1bXc5MTlYUWpveUtGMlMweEZ1NHlsekNsRzdMMjRGeVpGLzZoclhSNGdLY3VJc2NrdEV1Z1Q5c0c5NE1KWE5JVUtQOXdKemlvNU50S3VVYTZiL3RRPT0tLTdTK2lqWUZ4RDE4ZHQ1YTdMcnp3VWc9PQ%3D%3D--e1285218a90b714974e8a1a3f8495f9583fe3265
2. At end of session

## Section 8.2.2
1. `User.find_by(id: 4)` returns nil (database currently only has 3 users in it.)
2. 
```
>> session = {}
>> session[:user_id] = nil
>> @current_user ||= User.find_by(id: session[:user_id])   #=> nil
>> session[:user_id] = User.first.id                       #=> 1
>> @current_user ||= User.find_by(id: session[:user_id])
#=> #<User id: 1, name: "Rails Tutorial", email: "example@railstutorial.org", created_at: "2017-08-19 20:57:18", updated_at: "2017-08-19 20:57:18", password_digest: "$2a$10$cYWVJ7BP7bm9u5OZJMEhIuShPStlMeFcsWASvtt4LHu...">
>> @current_user ||= User.find_by(id: session[:user_id])
#=> #<User id: 1, name: "Rails Tutorial", email: "example@railstutorial.org", created_at: "2017-08-19 20:57:18", updated_at: "2017-08-19 20:57:18", password_digest: "$2a$10$cYWVJ7BP7bm9u5OZJMEhIuShPStlMeFcsWASvtt4LHu...">
```

## Section 8.2.3
1. Removed session from browser cookies and layout _does_ revert to non-logged-in state.
2. Closing browser completely and opening application again does correctly switch between logged-in and logged-out states.

## Section 8.2.4
1. Removing the bang from the Sessions helper `logged_in?` method does cause the "login with valid information" test to fail. Reinserting the bang causes all tests to pass again.

## Section 8.2.5
1. The "valid signup information" test fails.
2. Confirmed. Commenting out triggers toggle action.

## Section 8.3
1. The "Log out" link does cause the correct changes to final site layout. It redirects to home page (root_path), and "Log in" link replaces the User's profile toggle menu.
2. Cookie for session data seems to persist after logging out, but disappears from cookie list when closing and re-opening browser. Site functionality seems to work properly, even if session data is persisting.

