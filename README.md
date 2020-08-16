> 📌 Unordered random list of transpiles for JavaScript and Elixir

<div style="text-align:center;">
    <img src="image.png" alt="JS TO ELIXIR" style="width: 50%;" />
</div>

## Table of contents

[Map](#map)

[Reduce](#reduce)

[Every](#every)

[Some](#some)

[Each](#each)

[Sort](#sort)

[Unique by](#unique-by)

[Size of list](#size-of-list)

[List concat](#list-concat)

[Split by regex](#split-by-regex)

[String interpolation](#string-interpolation)


### Map

```js
[1, 2, 3].map(x => x * 2) // -> [ 2, 4, 6 ]
```

```elixir
Enum.map([1, 2, 3], fn(x) -> x * 2 end)
```

### Reduce

```js
["A", "B", "C"].reduce((x, acc) => x + acc) // -> 'ABC'
```

```elixir
Enum.reduce(["A", "B", "C"], fn(x, acc) -> acc <> x end)
```

### Every

```js
[11, 13, 15].every(x => x > 10) // -> true
```

```elixir
Enum.all?([11, 13, 15], fn(x) -> x > 10 end)
```

### Some

```js
["Apple", "Microsoft"].some(x => x.length > 6) // -> true
```

```elixir
Enum.any?(["Apple", "Microsoft"], fn(x) -> String.length(x) > 6 end)
```

### Each

```js
["Fish", "Fisherman", "Phising"].forEach(x => console.log(x)) // -> Fish ...
```

```elixir
Enum.each(["Fish", "Fisherman", "Phising"], fn(x) -> IO.puts x end)
```

### Sort

```js
[2, 2, 4, 6].sort((a, b) => b - a) // -> [ 6, 4, 2, 2 ]
```

```elixir
Enum.sort([2, 2, 4, 6], fn(a, b) -> a > b end)

# Alternative
Enum.sort([2, 2, 4, 6], :desc)
```

### Unique by

```js
[...new Set([1, 1, 2, 2, 3])] // -> [ 1, 2, 3 ]
```

```elixir
Enum.uniq_by([1, 1, 2, 2, 3], fn(x) -> x end)
```

<details>
<summary>Advacned</summary>

In Elixir, `compare function` helps normalizing objects easliy.

```elixir
Enum.uniq_by([a: {:tea, 2}, b: {:tea, 2}, c: {:coffee, 1}], fn {_, y} -> y end)

# -> [a: {:tea, 2}, c: {:coffee, 1}]
```

Don't want to write this code in JavaScript :(

</details>

### Size of list

```js
[1, 2].length // -> 2
```

```elixir
Enum.count([1, 2])
```

### List concat

```js
[...[1, 2], ...[3, 4]] // -> [ 1, 2, 3, 4 ]
```

```elixir
[1, 2] ++ [3, 4]
```

### Split by regex

```js
"100_000_000".split(/_/) // -> [ '100', '000', '000' ]
```

```elixir
Regex.split(~r/_/, "100_000_000")
```

### String interpolation

```js
`It is ${1 + 2} of the clock` // -> 'It is 3 of the clock'
```

```elixir
"It is #{1 + 2} of the clock"
```
