##What is a gem?
```
Rubygems provides two things for the Ruby community.

- A remote repository/packaging format and installer
- A runtime dependency manager
```

##Naming your gem
```
Naming your gem is important. 
Before you pick a name for your gem, do a quick search on RubyGems.org and GitHub to see if someone else has taken it. 
Every published gem must have a unique name. 
Be sure to read our naming recommendations when you’ve found a name you like.
```
[Rubygems naming conventions](http://guides.rubygems.org/patterns/#consistent-naming)


##Build your gem

1. After you've named your gem (using the conventions shown above), type in 
``` ruby
gem build placeholder.gemspec
=>   Successfully built RubyGem
  Name: placeholder
  Version: 0.0.0
  File: placeholder-0.0.0.gem
```

``` ruby
gem install ./placeholder-0.0.0

=> Successfully installed placeholder-0.0.0
Parsing documentation for placeholder-0.0.0
Installing ri documentation for placeholder-0.0.0
Done installing documentation for placeholder after 0 seconds
1 gem installed
```

``` ruby
irb >> require 'placeholder'
=> true

irb >>  Placeholder.hi

=> Hello
```

``` ruby
irb >> curl -u qrush https://rubygems.org/api/v1/api_key.yaml > ~/.gem/credentials; chmod 0600 ~/.gem/credentials

=> Enter host password for user 'byefelicia':
```

``` ruby
gem push placeholder-0.0.0.gem

# it will ask you for your credentials
=>Pushing gem to https://rubygems.org...
Successfully registered gem: placeholder (0.0.0)
```

``` ruby
# install your gem!
gem install placeholder

=> Parsing documentation for placeholder-0.0.0
Done installing documentation for placeholder after 0 seconds
1 gem installed
