# Clamxir [![Build Status](https://travis-ci.org/ramortegui/clamxir.svg?branch=master)](https://travis-ci.org/ramortegui/clamxir)

Database wrapper for clamav based on
[clamby](https://github.com/kobaltz/clamby)

This package depends of clamd.

## Installation

If [available in Hex](https://hex.pm/docs/publish), the package can be installed
by adding `clamxir` to your list of dependencies in `mix.exs`:

```elixir
def deps do
  [
    {:clamxir, "~> 0.1.3"}
  ]
end
```

## Usage

Clamxir receive the configs on each public method, and based on the configs,
will perform their task.

The config file by default is the struct `%Clamxir{}`.  The default values of
the structure are:

```elixir
%Clamxir{
  daemonize: false,
  stream: false,
  check: fase
}
```

Set daemonize to true, in order to use one instance of the clamav instead of
the creation of an instance each time that the scanner is invoke.

Check is a flag to check if the scanner is available.  Set to true in order to

```elixir
  iex> Clamxir.safe?(%Clamxir{}, "/path/file")
```

Stream true, will pass the argument --stream to clamdscan.

```elixir
  iex> Clamxir.safe?(%Clamxir{stream: true}, "/path/file")
```

check if the scanner exists, before try to use it.
`
```elixir
  iex> Clamxir.safe?(%Clamxir{check: true}, "/path/file")
```

## TODO

- Add sample of integration (mix app, and phoenix)


Documentation can be generated with [ExDoc](https://github.com/elixir-lang/ex_doc)
and published on [HexDocs](https://hexdocs.pm). Once published, the docs can
be found at [https://hexdocs.pm/clamxir](https://hexdocs.pm/clamxir).

