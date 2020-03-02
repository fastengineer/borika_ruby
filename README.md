Borika Ruby Gem for Payments

## Getting started

Add the following line to your Gemfile:

```ruby
gem 'borika'
```

Here is a possible configuration for development `config/environments/development.rb`:

```ruby
Borika.configure  do |config|
  config.private_key = File.binread  "testPrivateKey.key"
  config.private_key_password = "Password"
  config.borika_terminal_id = "11111111" # Borika KEY 
  config.borika_url = "https://gatet.borica.bg/boreps/"
  config.request_type = "registerTransaction"
end
```
This parameters are default but you can change it while using on the fly.

Note: You must send the signed CSR file to Borica BANK, otherwise you will get, certificate error.

### Example Usage

Let's create a url

```ruby
order_id = rand(1..200000) # Give your uniq order_id
amaount = rand(100..50000) # Integer with cents
Borika::Request.new(order_id, amount).url
```

### Contributors
This repository originally inspired from
[Genadi Samokovarov's Borica Gem](https://github.com/gsamokovarov/borica)


## License

GPL Licence. Copyleft.
