Adding the following as the contents of `features/support/debugging.rb` can be helpful in debugging failing steps:
```ruby
# `LAUNCHY=1 cucumber` to open page on failure
After do |scenario|
  save_and_open_page if scenario.failed? && ENV['LAUNCHY']
end

# `FAST=1 cucumber` to stop on first failure
After do |scenario|
  Cucumber.wants_to_quit = ENV['FAST'] && scenario.failed?
end

# `DEBUG=1 cucumber` to drop into debugger
Before do |scenario|
  next unless ENV['DEBUG']
  puts "Debugging scenario: #{scenario.title}"
  if respond_to? :debugger
    debugger
  elsif binding.respond_to? :pry
    binding.pry
  else
    puts "Can't find debugger or pry to debug"
  end 
end
```
By setting an environment variable, you can cause Cucumber to use various debugging tools.