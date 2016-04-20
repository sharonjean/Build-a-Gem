##What is a gem?
```
Rubygems provides two things for the Ruby community.

- A remote repository/packaging format and installer
- A runtime dependency manager
```

##Naming your gem
```
Naming your gem is important! 
Look up your desired gem name on RubyGems.org and GitHub to see if someone else has taken it (gem names must be unique). 
Feel free to read through gem naming conventions below.
```
[Rubygems naming conventions](http://guides.rubygems.org/patterns/#consistent-naming)


##Build your gem

1. After you've selected your gem name, create a 'lib' folder
2. Create a new rb file in your 'lib' folder, using the gem naming convention
``` ruby
% byefelicia    lib/placeholder.rb

class placeholder
  def self.bye
    puts "Bye, Felicia"
  end
end
```
3. Create a gemspec file with the optional parameters below
``` ruby
% byefelicia    placeholder.gemspec
Gem::Specification.new do |s|
  s.name        = 'placeholder'
  s.version     = '0.0.0'
  s.date        = '2010-04-28'
  s.summary     = "sure ok"
  s.description = "bye, felicia"
  s.authors     = ["Whatever Forever"]
  s.email       = 'sam@aol.com'
  s.files       = ["lib/placeholder.rb"]
  s.homepage    = 'http://rubygems.org/gems/placeholder'
  s.license     = 'MIT'
end
```
4. After you've set up your gemspec, you can build your gem
``` ruby
% byefelicia    gem build placeholder.gemspec
=>   Successfully built RubyGem
  Name: placeholder
  Version: 0.0.0
  File: placeholder-0.0.0.gem
```
5. Now you install and test your gem locally!
``` ruby
% byefelicia    gem install ./placeholder-0.0.0.gem

=> Successfully installed placeholder-0.0.0
Parsing documentation for placeholder-0.0.0
Installing ri documentation for placeholder-0.0.0
Done installing documentation for placeholder after 0 seconds
1 gem installed
```
6. Require your gem in irb
``` ruby
irb >> require 'placeholder'
=> true
# Then you can test out your gem 
irb >>  Placeholder.bye
=> Bye, Felicia
```
7. Share your gem! Setup and push your gem out to the community!
``` ruby
irb >> curl -u qrush https://rubygems.org/api/v1/api_key.yaml > ~/.gem/credentials; chmod 0600 ~/.gem/credentials

# it will ask you for your credentials
=> Enter host password for user 'byefelicia':

% byefelicia    gem push placeholder-0.0.0.gem
=>Pushing gem to https://rubygems.org...
Successfully registered gem: placeholder (0.0.0)
```
8. Your gem is now available for download! Try it, and share it!
``` ruby
% byefelicia    gem install placeholder

=> Parsing documentation for placeholder-0.0.0
Done installing documentation for placeholder after 0 seconds
1 gem installed
```
