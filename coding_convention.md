# Elixir Coding Convention

## Explicit Contract
- Good
```elixir
  @spec some_func(term, term)::{atom, binary}
  def some_func(parameter_1, parameter_2), do: blah, blah, blah
```
- Bad
```elixir
  def some_func(parameter_1, parameter_2), do: blah, blah, blah
```

## Type definition
- Good
```elixir
  @typedoc "My type is here"
  @type my_type::{atom, binary, atom, any}

  # later in code
  @spec some_fun(term)::my_type
```
- Bad
```elixir
  @spec some_fun(term)::{atom, binary, atom, any}
```

## Module Attribute Access
```elixir
  @module_attr 10
  def module_attr, do: @module_attr
```

## Return value
- Good
```elixir
  def some_func(term)::%SomeStructure{} | {atom, binary}
```
- Bad
```elixir
  def some_func(term)::map | tuple
```
