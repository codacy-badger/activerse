# WIP: Activerse
[![Gem Version](https://badge.fury.io/rb/activerse.svg)](https://badge.fury.io/rb/activerse)
[![Codacy Badge](https://api.codacy.com/project/badge/Grade/fe0e9c2138d24d10a268e72491562fec)](https://www.codacy.com/manual/pietromoro/activerse?utm_source=github.com&amp;utm_medium=referral&amp;utm_content=pietromoro/activerse&amp;utm_campaign=Badge_Grade)

This gem is currently in the process of being made.

**DISCLAMER** All text is either temporary or not yet implemented. It is only a proposal of how the library could work

## Usage
Run `rails generate activerse:install` to create the configuration file and the setup structure file, as well as uncheking your `credentials.yml.enc` file from version control and adding it to the `.gitignore`. Then you can setup the structure file as you like, for example:

```yml
pages:
  - name: "APIS"
    fields:
      - google_api: text_field
      - aws_api: text_field
      - maps_api: text_field
  - name: "VARIABLES"
    fields:
      - my_var: select
        options:
          - true
          - false
          - "nothing"
      - my_var2: number_field
        options:
          step: 0.5
          data:
            attribute: false
  - devise
```
See the wiki for more informations.

In the `config/initializers/activese.rb` file you can specify some code to be run before the web ui gets loaded or after it is submitted.

```ruby
config.on_initialization do
  # some initialization code
end

config.after_submit do
  # do your stuff here
  # example: set up first user or first policies...
end
```

See the wiki or directly the initializer file for more configuration options.

## Installation
Add this line to your application's Gemfile:

```ruby
gem 'activerse'
```

And then execute:
```bash
$ bundle
```

Or install it yourself as:
```bash
$ gem install activerse
```

To create all necessary setup and files run:
```ruby
rails generate activerse:install
```

## Contributing
Contributions will be welome when first few iterations will be going out.

## License
The gem is available as open source under the terms of the [MIT License](https://opensource.org/licenses/MIT).
