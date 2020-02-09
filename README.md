# GreenDay
Automatically create workspace and tests for Atcoder contests

## Installation

Add this line to your application's Gemfile:

```ruby
gem 'green_day'
```

And then execute:

    $ bundle

Or install it yourself as:

    $ gem install green_day

## Usage
login(this command stores your cookie as `cookie-store` in current dir)

    $ bundle exec green_day login
    
And create directory and spec as below.
   
    $ bundle exec green_day new <contest-name>

For example 
   
    $ bundle exec green_day new abc150
   
   ```
    abc150
    ├── A.rb
    ├── B.rb
    ├── C.rb
    ├── D.rb
    ├── E.rb
    ├── F.rb
    └── spec
        ├── A_spec.rb
        ├── B_spec.rb
        ├── C_spec.rb
        ├── D_spec.rb
        ├── E_spec.rb
        └── F_spec.rb
   ```
   
   Example of output spec
   
   ```ruby
    require 'rspec'
    
    RSpec.describe 'test' do
      it 'test with "2 900\n"' do
        io = IO.popen("ruby abc150/A.rb", "w+")
        io.puts("2 900\n")
        expect(io.gets).to eq("Yes\n")
      end
    
      it 'test with "1 501\n"' do
        io = IO.popen("ruby abc150/A.rb", "w+")
        io.puts("1 501\n")
        expect(io.gets).to eq("No\n")
      end
    
      it 'test with "4 2000\n"' do
        io = IO.popen("ruby abc150/A.rb", "w+")
        io.puts("4 2000\n")
        expect(io.gets).to eq("Yes\n")
      end
    
    end
  ```

## Development

After checking out the repo, run `bin/setup` to install dependencies. Then, run `rake spec` to run the tests. You can also run `bin/console` for an interactive prompt that will allow you to experiment.

To install this gem onto your local machine, run `bundle exec rake install`. To release a new version, update the version number in `version.rb`, and then run `bundle exec rake release`, which will create a git tag for the version, push git commits and tags, and push the `.gem` file to [rubygems.org](https://rubygems.org).

## Contributing

Bug reports and pull requests are welcome on GitHub at https://github.com/QWYNG/green_day. This project is intended to be a safe, welcoming space for collaboration, and contributors are expected to adhere to the [Contributor Covenant](http://contributor-covenant.org) code of conduct.

## License

The gem is available as open source under the terms of the [MIT License](https://opensource.org/licenses/MIT).

## Code of Conduct

Everyone interacting in the GreenDay project’s codebases, issue trackers, chat rooms and mailing lists is expected to follow the [code of conduct](https://github.com/[USERNAME]/green_day/blob/master/CODE_OF_CONDUCT.md).
