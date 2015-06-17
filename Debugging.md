Adding the following as the contents of `features/support/debugging.rb` can be helpful in debugging failing steps:
```ruby
# `LAUNCHY=1 cucumber` to open page on failure
After do |scenario|
  # rubocop:disable Lint/Debugger
  save_and_open_page if scenario.failed? && ENV['LAUNCHY']
  # rubocop:enable Lint/Debugger
end

# `FAST=1 cucumber` to stop on first failure
After do |scenario|
  Cucumber.wants_to_quit = ENV['FAST'] && scenario.failed?
end

# `DEBUG=1 cucumber` to drop into debugger
Before do |scenario|
  next unless ENV['DEBUG']
  # rubocop:disable Lint/Debugger
  puts "Debugging scenario: #{scenario.title}"
  binding.pry
  # rubocop:enable Lint/Debugger
end
```
By setting an environment variable, you can cause Cucumber to use various debugging tools.