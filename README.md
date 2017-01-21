# Cucumber Elixir Core

Cucumber Core is the [inner hexagon](http://alistair.cockburn.us/Hexagonal+architecture) for the Elixir flavour of Cucumber (currently in progress).

It contains the core domain logic to execute Cucumber features. It has no user interface, just a Ruby API. If you're interested in how Cucumber works, or in building other tools that work with Gherkin documents, you've come to the right place.

### An overview

The entry-point is a single function on the module [`Cucumber.Core`](Cucumber/Core.html) called `execute`. Here's what it does:

1. Parses the plain-text Gherkin documents into an **AST**
2. Compiles the AST down to **test cases**
3. Passes the test cases through any **filters**
4. Executes the test cases, emitting **events** as it goes


## Installation

If [available in Hex](https://hex.pm/docs/publish), the package can be installed as:

  1. Add `cucumber_elixir_core` to your list of dependencies in `mix.exs`:

    ```elixir
    def deps do
      [{:cucumber_elixir_core, "~> 0.1.0"}]
    end
    ```

  2. Ensure `cucumber_elixir_core` is started before your application:

    ```elixir
    def application do
      [applications: [:cucumber_elixir_core]]
    end
    ```

