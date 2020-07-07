# Mod 2

## Week 1 Day 1

### ERB tags
 If you feel confused about ERB tags, here’s a very simplified cheat sheet that works 90% of the time:
https://medium.com/swlh/cheatsheet-which-erb-tag-should-i-use-4b3de261f15f

### Capybara announcement
@here  CAPYBARA ANNOUNCEMENT in case someone drifted away:
We thought we’d spare you despair and give you a heads-up on that the tests for this module are written in Capybara. They are slightly different - Capybara tests are SUPER specific. If your wording/spacing/capitalization/spelling is not exact and precise, the test will not pass. It is more precise than the tests for the previous labs. If you solve the problem, and you get the output that the read me asks, but the tests do not pass, that is okay. These labs are going to test you behavior-driven development skills, unlike the other labs which were using test-driven development.
Also, some tests require you to finish ALL the app (even if the error mentions a status code or routing) to turn green so you may wanna move onto the next error before losing patience.
Please don’t feel discouraged if you did what has been asked from you and yet the tests are not passing. The real test of whether your code is working is how it looks in the browser.
However, if you are a person who cares about having the learn.co all adorned with green marks :green_light:, you can either spend more time comparing your code vs the tests, change the tests or simply check the solution branch on GitHub and see where the difference is.
:bangbang: BUT PLEASE DO REMEMBER THAT CAPYBARAS ARE AWSOME IN REALITY :bangbang:
Here’s a meme about capybaras bringing folks together:
https://files.slack.com/files-pri/T02MD9XTF-F015A6LL347/capy.jpeg

## Week 1

### Labels in HTML
:railsrailsrails: :railsrailsrails: :railsrailsrails: Labels in HTML :railsrailsrails: :railsrailsrails: :railsrailsrails:
:arrow_right:  What is it for: the `<label>` tag enhances user experience,  making it easy to make sure what you are expected to type in the field but also increasing its accessibility for screen users.
:arrow_right: In plain HTML, do we need to include the `id` ?
- YES, if you write your labels above the input (and you need the attribute “for”)
```html
<label for = "city"> City </label>
 <input type="text" name="City" id="city">
```
- NO, if you wrap the label around the input — this should be used as a last resort, e.g. when you are using third-party code and can’t know what the id generated:
```html
<label> City
 <input type="text" name="City" id="city">
</label>
```
:arrow_right: Sometimes folks don’t want to use a label because they know how to style it to look okay or think that without a label their page looks better and the placeholder text in the inputs already makes it clear what you are supposed to type in. This approach makes your page inaccessible because navigation through a form without labels is a real nightmare if you’re using a screen reader + placeholders can do only so much even for the sighted users. However, if you decide to not have labels on the page, do it properly:
:sparkles: **Approach 1:** keep the label but visually hide it with css:
```html
<label for="search" class="visuallyhidden">Search: </label>
<input type="text" name="search" id="search">
<button type="submit">Search</button>
```
:sparkles: **Approach 2:** Use an `aria-label`:
<input type="text" name="search" aria-label="Search">
<button type="submit">Search</button>
```
@here

### Deleting dependents
Problem: ActiveRecord doesn't delete dependent objects by using force: :cascade!
Solution:
In the model with association add: dependent: :destroy
For example,
```ruby
class Owner < ActiveRecord::Base
    has_many :dogs, dependent: :destroy
end
```
A foreign key with cascade delete means that if a record in the parent table is deleted, then the corresponding records in the child table will automatically be deleted. This is called a cascade delete in SQL Server.
[Good explanation of cascade (ON DELETE/UPDATE) behavior](https://dba.stackexchange.com/questions/44956/good-explanation-of-cascade-on-delete-update-behavior)

### Closing zombie ports
Hey if any of you are having port issues with shotgun, check out Sylwia’s blog that shows you how to kill a running process you can’t initially see:
https://dev.to/sylwiavargas/how-to-properly-close-a-port-2p36

### REST API and request-response cycle
An article about REST APIs and the request-response cycle that I found helpful:
https://www.smashingmagazine.com/2018/01/understanding-using-rest-api/

### HTTP Codes with Rihanna
:sparkles: HTTP codes with Rihanna: https://www.httriri.com/ :sparkles:
It’s a work in progress — Monica Powell has launched it just recently and you all can contribute the gifs there to the codes that are missing :heart: contribute here: https://github.com/M0nica/httriri
@here

### Nice formatting of Rails
Problem: How to get nice formatting in the Rails console?
-------------------------------------------------------------------------
**Solution-1:** 
- add `gem "awesome_print"` to gem file
- In rails console: run commands starting with ap for example: `ap Dog.all`
-------------------------------------------------------------------------
**Solution-2:**
Add "awesome_print" gem by default with irb/rails/pry console:
`gem install awesome_print`
Add following lines to your `~/.irbrc`   file(usually find at `/Users/yourLaptopUsername/.irbrcat`):
```bash
require "awesome_print"
AwesomePrint.irb!
```

### Validations in Rails
@here Build your own custom validations in two ways:
https://dev.to/sylwiavargas/rails-custom-validations-58mo
For only changing error messages, :message  option can be used. Find more details here: https://guides.rubyonrails.org/active_record_validations.html#message

### Rails generators:
Rails generators syntax: https://medium.com/@kevinyckim33/rails-generators-cli-cheatsheet-711295e7a1ed

### Ruby on Rails Slack Community:
@here Here’s a Ruby on Rails slack community of ~15k devs who always are happy to help out and share awesome materials :heart:
https://www.rubyonrails.link/

### Rails project examples:
Additional examples with youtube videos:
https://github.com/anamsoomro/CaptionIt		https://youtu.be/qpiVlTYH9As
https://github.com/pahoffart25/project-2		https://www.youtube.com/watch?v=15LeO02_Ms0&feature=youtu.be
https://github.com/somaia-khalil/QuizMe1		https://www.youtube.com/watch?v=FTQ13u0bsoM&feature=youtu.be
https://github.com/SteRobWms/mod2-blackjack-project		https://youtu.be/A7KbyE3_uwA
https://github.com/timothyalton/flight-guru-app		

### For/in loop vs each
:ruby: :ruby: :ruby:  I heard a good question today: why is for/in loop a less optimal option than .each? :ruby: :ruby: :ruby:
So, `for/in loop` contains an elaborate `if/else` statement and also, syntactic sugar for each and as such:
- takes more computing time
- uses more memory because it has a wider lexical scope
- has a different return statement
- its variable (e.g. for element in array; the element is the variable) is returned
`.each` on the other hand works on a block of code, returns the same array and introduces new, temporary lexical scope and as such is just faster
Look here, element persists in the memory when using `for/in`:
```ruby
array = [1,2,3]
for element in array
     puts element
end
# => 1
# => 2
# => 3
# => [1, 2, 3] 
element
# => 3 
```
vs in `.each`:
```ruby
array = [1,2,3]
array.each{|el| puts el}
# => 1
# => 2
# => 3
# => [1, 2, 3] 
element
# => NameError (undefined local variable or method `el' for main:Object)
```
Read more: http://graysoftinc.com/early-steps/the-evils-of-the-for-loop

===
## Project Week 

### I wish I had known about CSS
Here’s something I wish I had known before doing my MOD2 (that I cover in the lecture and in the repo):
:bangbang: 4 RULES OF CSS :bangbang:
- **Cascade:** CSS is a cascade (a type of algorithm). At a very low level, it means that that the order of CSS rules matter; meaning, if you define a background color of a div in two places, the color that comes last will be applied;
- **Specificity:** however, more important than the cascading character of css is the rule of specificity; CSS will take more seriously the requsts that are more specific; here’s the hierarchy of specificity (from the most to the least): element selector -> class selector -> id selector note: inline CSS is more specific than external file, which is why it’s easy to overwrite external libraries;
PS: Specificity is set up with point system -- each declaration is evaluated in points, then compared and the winners take it all! For instance, if you declare styling inline, this declaration gets 1000 points from the get-go (for real), as opposed to 0 when declared in an outside stylesheet;
- **Inheritance:** now, some elements inherit styling from their parents while others don’t; for instance, color and font will be inherited by children but width and height will not! You can play with inheritance by using an inherit attribute!
- **!important:** now, you can override all rules using the value of !important; however, beware: you will enter the long-term css debugging hell if you invite this value without an absolute desperate necessity;

### Friendly CSS libraries:
:sparkles: :sparkles: :sparkles:  Friendly CSS libraries  :sparkles: :sparkles: :sparkles:
Semantic UI (my fav): https://semantic-ui.com/
setting up with Rails: https://stackoverflow.com/questions/37283642/how-do-i-set-up-a-rails-application-with-semantic-ui
Materialize: https://materializecss.com/
Setting up with Rails: https://rubyinrails.com/2015/09/17/how-to-integrate-material-ui-with-rails/
Bootstrap: https://getbootstrap.com/
Setting up with Rails: https://github.com/twbs/bootstrap-rubygem (edited) 

### Make your page accessible
LAST BUT NOT LEAST, PLEASE READ ABOUT HOW TO MAKE YOUR PAGE ACCESSIBLE:
https://dev.to/sylwiavargas/checklist-web-accessibility-3abl

### Polymorhpic / Self-referential 
@here if anyone is thinking about building a social media platform, please be mindful of that you need to have so-called self-referential/polymorphic associations. For instance, in a standard social media site, you’d have a functionality of users following each other. That would mean that a User has_many Users (followers) and/or has_many Users (and those who they follow) but also belongs_to User. That’s messy unless you build it with self-referentials. Other examples of this include e.g. comments, liked posts, etc.
Please read this before you venture onto this quest :slightly_smiling_face:
- https://medium.com/@TheDickWard/self-referential-relationships-aka-self-joins-in-rails-64f8f36ac311
- https://flatiron-school.slack.com/archives/G0167UWPN2W/p1593444569002500
And watch this lecture by one of our instructors, Eric Kim on fancy Active Record including self-referentials:
Code: https://github.com/learn-co-students/dumbo-web-060319/tree/master/22-advanced-activerecord
Video: https://youtu.be/LDKZvG8NHto

### On designing your Domain Model:
Also, so I don’t need to say it in DMs:
If you are planning on filtering/sorting feature in your app based on an attribute, in 99% of cases, that is a hint for you to make this attribute a separate model. What do I mean by that? Imagine I’m building a database of all after-school activities run by teachers:
```
Activity -< ActivityTeacher >- Teacher
price                          name
subject
location
```
In this case, `subject` and `location` will be strings and `price` would be an int. In that case, it is possible that somewhere along the way you’d end up not only with spellings but also two different versions of e.g. the same subject (“Math” and “Mathematics”). Instead of thinking of 10,000 safeguards, you can just…
```
subject   
   |
   ^
Activity -< ActivityTeacher >- Teacher
   |
   ^                          
location
```
In this case, you pre-populate all the possible subjects and when someone wants to create a new entry, they just choose an already-existing one. It also helps with querying because instead of querying 10,000 activities to find the three that are connected to “curling”, you’d just find the Curling subject and get all `Activities` connected to it.
Moreover, `location` can also be further split into several models, e.g.: `city`, `zipcode`, `street`, etc. to make it easier to query.
@here

### Uploading files
If anyone is looking to upload files/pictures to their rails app:
- https://medium.com/@gabalexa/using-active-storage-to-handle-image-uploads-in-ruby-on-rails-b8df32be7d79
- https://medium.com/better-programming/how-to-upload-files-in-a-react-and-rails-app-69c31a9cf9b7
@here 

### Bootstrap and Rails
@here For all of you working with Bootstrap, please remember that it is an opinionated library and it needs you to follow closely best practices in the framework/library of your choosing, which means that e.g. instead of using `<button>` , it prefers you use `<%= button_to %>`  . In the same manner, there’s also a gem specifically for forms:
https://github.com/bootstrap-ruby/bootstrap_form
And a gem specifically for nav bars (I never worked with this one):
https://github.com/bootstrap-ruby/rails-bootstrap-navbar
Here’s one project from my previous student (Stephanie Zou) who used Bootstrap with Rails and shed many tears. If something is not working in your code, please check how she implemented it for reference:
https://github.com/stephaniezou1/Acorn-Search-Engine

===
## Week 3 Day 5

### Before JS
@here if at any point today you fell done with the project and rails and want to have a pleasant read about JS, I’d recommend either of these two very friendly books:
- https://justjavascript.com/ - written by Dan Abramov (React core team, creator of Redux); it’s still free and comes in chapters to your email (so far only 8/10 mini-chapters are released)
- https://eloquentjavascript.net/ - a longer book that goes into details of how everything works in js; reading even one chapter can shed a lot of light on the language

### Sandi Metz's rules
Also, you could spend a second refactoring your project following Sandi Metz’s rules:
1. Classes can be no longer than one hundred lines of code.
2. Methods can be no longer than five lines of code.
3. Pass no more than four parameters into a method. Hash options are parameters.
4. Controllers can instantiate only one object. 
More on them here:
https://thoughtbot.com/blog/sandi-metz-rules-for-developers

### bye bye Rails
GREAT APPS, EVERYONE!! I really appreciate all the thought and work you put into the apps. You’ve worked very hard —and it shows. Congratulations! 🥳 🥳 🥳
A good way to close the Ruby chapter and enter JavaScript world is watching this video:
@here
https://files.slack.com/files-pri/T02MD9XTF-F01636RSAJ3/download/wat.mp4

### After project presentations
Resources I mentioned in the zoom chat:
 :star: Deploying Rails on Heroku:
https://medium.com/@kasiarosenb/deploying-your-rails-app-on-heroku-a2096dc40aac
:star: here’s a good starter for realtime messaging (without page refreshing):
 https://iridakos.com/programming/2019/04/04/creating-chat-application-rails-websockets
:star: here’s a good twilio walkthrough for sms messaging feature:
 https://www.twilio.com/blog/2017/12/send-sms-ruby-rails-5-coffee.html

 ### JS is powerful
 @here for all you Hamilton fans — an example of why JS is awesome and powerful:
https://pudding.cool/2017/03/hamilton/index.html

