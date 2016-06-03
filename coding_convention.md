# Elixir Coding Convention

## Explicit Contract
- Good
```elixir
  @spec some_func(term, term)::{atom, binary}
  @doc "Description of what this function does"
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

## Docs for function
- All public facing functions & Apis should be documented as below
```elixir
@doc """
This function does blah blah blah, given `parameter1::type`, `parameter2::type`

# Type can be ignored if can be inferred
Returns `:return_value`

## Examples

  # if doctest is possible
    iex> SomeModule.this_function
    :return_value

  # if doctest is not available
    SomeModule.this_function
    => :return_value

"""
```
