---
title: into record
categories: |
  conversions
version: 0.84.0
conversions: |
  Convert value to record.
usage: |
  Convert value to record.
---

# <code>{{ $frontmatter.title }}</code> for conversions

<div class='command-title'>{{ $frontmatter.conversions }}</div>

## Signature

```> into record ```


## Input/output types:

| input     | output |
| --------- | ------ |
| datetime  | record |
| duration  | record |
| list\<any\> | record |
| range     | record |
| record    | record |
| table     | record |
## Examples

Convert from one row table to record
```shell
> [[value]; [false]] | into record
╭───────┬───────╮
│ value │ false │
╰───────┴───────╯
```

Convert from list to record
```shell
> [1 2 3] | into record
╭───┬───╮
│ 0 │ 1 │
│ 1 │ 2 │
│ 2 │ 3 │
╰───┴───╯
```

Convert from range to record
```shell
> 0..2 | into record
╭───┬───╮
│ 0 │ 0 │
│ 1 │ 1 │
│ 2 │ 2 │
╰───┴───╯
```

convert duration to record (weeks max)
```shell
> (-500day - 4hr - 5sec) | into record
╭────────┬────╮
│ week   │ 71 │
│ day    │ 3  │
│ hour   │ 4  │
│ second │ 5  │
│ sign   │ -  │
╰────────┴────╯
```

convert record to record
```shell
> {a: 1, b: 2} | into record
╭───┬───╮
│ a │ 1 │
│ b │ 2 │
╰───┴───╯
```

convert date to record
```shell
> 2020-04-12T22:10:57+02:00 | into record
╭──────────┬────────╮
│ year     │ 2020   │
│ month    │ 4      │
│ day      │ 12     │
│ hour     │ 22     │
│ minute   │ 10     │
│ second   │ 57     │
│ timezone │ +02:00 │
╰──────────┴────────╯
```
