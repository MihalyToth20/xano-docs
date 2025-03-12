---
hidden: true
---

# XanoScript Key Concepts

{% include "../.gitbook/includes/xs-beta-alpha-notice.md" %}

## Core Data Types

### Numbers

{% hint style="info" %}
## Integers

Whole numbers like 1, 2, 3, and -5

```
-5
```

```
3
```

```
2
```

```
1
```
{% endhint %}

{% hint style="info" %}
## Decimals

Numbers with fractional parts like 1.23, 0.5, -10.7

```
-10.7
```

```
0.5
```

```
1.23
```
{% endhint %}

### Text

{% hint style="info" %}
## Simple Text

Text must be wrapped in double or single quotes.

```
"Hello"
```

```
'Hello'
```
{% endhint %}

{% hint style="info" %}
## Escaping Quotes

Escape characters are required when using single or double quotes inside of a text string.

```
'This has a \'quoted\' word inside it'
```

```
"This has a \"quoted\" word inside it"
```
{% endhint %}

{% hint style="info" %}
## Complex Data Types (JSON)

XanoScript automatically chooses the most readable quote style for your text. It uses double quotes by default, but switches to single quotes when your text contains double quotes (like JSON data). This makes JSON strings much cleaner and easier to read in your code.

This is problematic and hard to read.

```
"{\"name\":\"John\",\"age\":30}"
```

This is how XanoScript handles it.

```
'{"name":"John","age":30}'
```
{% endhint %}

{% hint style="info" %}
## Multiline Text

For longer text that spans multiple lines, XanoScript provides the `<<` delimiter. These allow you to write text naturally without escape characters for line breaks. This is similiar to how multiline text is supported within YAML, where the common spacing to the left is removed from the end result. This allows you to keep the block of text in the relavent spot without having to indent everything to the far left of your file. Note that multiline text blocks cannot be used with filters or transformations.

```
value = << 
    This is a multiline text value
    that can span multiple lines
    without needing escape characters
    for line breaks.
```

Multiline is **not** supported when using filters. Instead, you should use escaped line break characters.

```
"Dear John,\nYour order will arrive by Friday.\nRegards,\nCustomer Service"|upper
```
{% endhint %}

### Boolean (true/false) Values

{% hint style="info" %}
## True / False

Booleans are special values that, while presented as text, do not require quotes.

```
false
```

```
true
```
{% endhint %}

### Date & Time

{% hint style="info" %}
## Standard Date & Time Format

XanoScript uses a standardized format for timestamps: `YYYY-MM-DD HH:MM:SS+ZZZZ`. This format includes the date, time, and timezone offset.

```
2024-12-09 17:37:42+0000
```

This represents December 09, 2024 at 5:37.42 PM in UTC time.

It's important to note that XanoScript does not plainly support the **Unix EPOCH** format that you might be used to when working in Xano. XanoScript can't tell the difference between a timestamp and a regular integer.&#x20;
{% endhint %}

### Complex Data Types

{% hint style="info" %}
## Objects

Objects can be written in XanoScript using `` ` `` characters.

```
`{"name":"John", "age":30, "car":null}`
```

Standard JavaScript syntax works perfectly.

```
{
  "name": "John",
  "age": 30,
  "city": "New York"
}
```

Commas are not required, but XanoScript also supports trailing commas.

```
{
  "name": "John",
  "age": 30,
  "city": "New York",
}
```
{% endhint %}

{% hint style="info" %}
## Arrays

Arrays can be written in XanoScript using \` characters.

```
`[1,2,3,4,5]`
```

Standard JavaScript syntax works perfectly.

```
["apple", "banana", "cherry"]
```

Commas are not required, and XanoScript also supports trailing commas.

```
[
  "apple",
  "banana",
  "cherry",
]
```
{% endhint %}

### Expressions

Xano's [Expression data type](../the-function-stack/data-types/expression.md) is fully supported in XanoScript. Expressions should be wrapped in `` ` `` characters.

```
`{a:1, b:2}`
```

```
`123|add:1`
```

## Type Casting

Type casting is the **optional** process of preceding a value with its intended type, such as one from the list below.

| Data Type  | Cast       |
| ---------- | ---------- |
| Number     | !int       |
| Text       | !text      |
| Boolean    | !boolean   |
| Decimal    | !decimal   |
| null       | !null      |
| Array      | !array     |
| Object     | !object    |
| Expression | !expr      |
| Timestamp  | !timestamp |

Because XanoScript can infer types from the data that exists, you typically will not have to work with type casting, but it can serve as an additional layer of certainty around data integrity.

Using type casting limits some of your available options for writing XanoScript.

* Casted values do not support multi-line text. You will want to use line break characters.
* All casted values only operate on text strings, so each value must be wrapped inside quotes.

{% hint style="success" %}
## Valid Type Casting

```
value = !int "123"
```
{% endhint %}

{% hint style="danger" %}
## Invalid Type Casting

```
value = !int 123
```
{% endhint %}

## Getting Started

Now that you understand the basic concepts of XanoScript, you can move forward to learning about the intricacies of using XanoScript in your function stacks or in the database.

<table data-card-size="large" data-view="cards"><thead><tr><th></th><th data-hidden data-card-target data-type="content-ref"></th></tr></thead><tbody><tr><td><strong>XanoScript for the Database</strong></td><td><a href="db/">db</a></td></tr><tr><td><strong>XanoScript for Function Stacks</strong></td><td><a href="fs/">fs</a></td></tr></tbody></table>

