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
