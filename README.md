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
2. `puts "#{city}, #{state}"` => # `Chicago, Illinois`
3. `puts "#{city},\t#{state}"` => # `Chicago,        Illinois`
4. `puts '#{city},\t#{state}'` => # `Chicago,\tIllinois`

## Section 4.2.3
1. "racecar".length # => 7
2. "racecar".reverse # => "racecar"
3. s == s.reverse # => true
4. prints "Its a palindrome!"; returns nil and prints nothing

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