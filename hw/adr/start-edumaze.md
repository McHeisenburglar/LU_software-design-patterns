# Decision record template by Michael Nygard

# Command-line

## Status

Proposed.

## Context

Currently, the configuration of the maze happens within `main.py`. This includes
the values for the number of rows and columns, which are currently set to 12 and
16, respectively.

If a user wants to change the dimensions of the maze, they would have to change
the code themselves.

## Decision

The proposal is to allow the teacher to input the number of rows and columns
through the command-line, as user input prompts, as these are the only two
values that they might want to change at the moment.

If no value is given, the program will use predefined default values for each
(12 and 16).

```py
default_rows = 12
    default_rows = 12
    default_cols = 16

    num_rows = get_non_negative_int(f"Enter number of rows (default: {default_rows}): ") or default_rows
    num_cols = get_non_negative_int(f"Enter number of columns (default: {default_cols}): ") or default_cols
```

## Consequences

The `main()` function will now rely on command-line input for it to function.
This might not be the most flexible solution for the future.
