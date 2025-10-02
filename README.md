# Countries

Countries is a collection of all sorts of useful information for every country
in the [ISO 3166](https://en.wikipedia.org/wiki/ISO_3166) standard.
It is based on the data from the Ruby Gem [Countries](https://github.com/hexorx/countries).

## Forked

This is a fork of the original repo, which makes a minor change to the ordering
of the `:unoffical_names` list for the GB data; which adheres to DICE's
preference for 'United Kingdom' over 'The United Kingdom'.

Additionally, it has been updated to compile without warnings on Elixir 1.18
and the dependencies have been updated to the latest versions.

## Installation

```elixir
defp deps do
  [
    {:countries, "~> 1.6"}
  ]
end
```

After you are done, run ```mix deps.get``` in your shell to fetch and compile countries.

## Usage

Find country by attribute:

```elixir
country = Countries.filter_by(:alpha2, "DE")
# [%Countries.Country{alpha2: 'DE', alpha3: 'DEU', continent: 'Europe',
#  country_code: '49', currency: 'EUR', ...]

countries = Countries.filter_by(:region, "Europe")
Enum.count(countries)
# 51
```

Get all countries:

```elixir
countries = Countries.all
Enum.count(countries)
# 250
```

## Contributing

1. Fork it
2. Create your feature branch (`git checkout -b my-new-feature`)
3. Commit your changes (`git commit -am 'Add some feature'`)
4. Push to the branch (`git push origin my-new-feature`)
5. Create new Pull Request

## Copyright and License

Copyright (c) 2015 Sebastian Szturo

This software is licensed under [the MIT license](./LICENSE.md).
