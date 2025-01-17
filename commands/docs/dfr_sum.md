---
title: dfr sum
categories: |
  expression
version: 0.84.0
expression: |
  Creates a sum expression for an aggregation or aggregates columns to their sum value
usage: |
  Creates a sum expression for an aggregation or aggregates columns to their sum value
---

# <code>{{ $frontmatter.title }}</code> for expression

<div class='command-title'>{{ $frontmatter.expression }}</div>

## Signature

```> dfr sum ```


## Input/output types:

| input | output |
| ----- | ------ |
| any   | any    |

## Examples

Sums all columns in a dataframe
```shell
> [[a b]; [6 2] [1 4] [4 1]] | dfr into-df | dfr sum
╭───┬────┬───╮
│ # │ a  │ b │
├───┼────┼───┤
│ 0 │ 11 │ 7 │
╰───┴────┴───╯

```

Sum aggregation for a group-by
```shell
> [[a b]; [one 2] [one 4] [two 1]]
    | dfr into-df
    | dfr group-by a
    | dfr agg (dfr col b | dfr sum)
╭───┬─────┬───╮
│ # │  a  │ b │
├───┼─────┼───┤
│ 0 │ one │ 6 │
│ 1 │ two │ 1 │
╰───┴─────┴───╯

```


**Tips:** Dataframe commands were not shipped in the official binaries by default, you have to build it with `--features=dataframe` flag