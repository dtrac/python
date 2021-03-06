## Using the format() method

```python
"base string with {} placeholders".format(variables)
```

- The format method returns a copy of the string where the {} placeholders have been replaced with the values of the variables. These variables are converted to strings if they weren't strings already. Empty placeholders are replaced by the variables passed to format in the same order.

```python
"{0} {1}".format(first, second)
```

- If the placeholders indicate a number, they’re replaced by the variable corresponding to that order (starting at zero).

```python
"{var1} {var2}".format(var1=value1, var2=value2)
```

- If the placeholders indicate a field name, they’re replaced by the variable corresponding to that field name. This means that parameters to format need to be passed indicating the field name.

```python
"{:exp1} {:exp2}".format(value1, value2)
```

- If the placeholders include a colon, what comes after the colon is a formatting expression. See below for the expression reference.

## Formatting expressions

| Expr	| Meaning	| Example |
|-------|---------|---------|
{:d}	| integer value	| '{:d}'.format(10.5) → '10'
{:.2f}	| floating point with that many decimals	| '{:.2f}'.format(0.5) → '0.50'
{:.2s}	| string with that many characters	| '{:.2s}'.format('Python') → 'Py'
{:<6s}	| string aligned to the left that many spaces	| '{:<6s}'.format('Py') → 'Py    '
{:>6s}	| string aligned to the right that many spaces	| '{:<6s}'.format('Py') → '    Py'
{:^6s}	| string centered in that many spaces	| '{:<6s}'.format('Py') → '  Py '

# Formatted string literals
This feature was added in Python 3.6.

A formatted string literal or f-string is a string that starts with 'f' or 'F' before the quotes. These strings might contain {} placeholders using expressions like the ones used for format method strings.

The important difference with the format method is that it takes the value of the variables from the current context, instead of taking the values from parameters.

Examples:

```python
>>> name = "Micah"

>>> print(f'Hello {name}')

Hello Micah

>>> item = "Purple Cup"

>>> amount = 5

>>> price = amount * 3.25

>>> print(f'Item: {item} - Amount: {amount} - Price: {price:.2f}')

Item: Purple Cup - Amount: 5 - Price: 16.25
```
