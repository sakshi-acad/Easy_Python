# Python Chapter 3: Data Types

### The Complete Deep Dive

Every built-in data type of Python, taught step by step: what it is, a runnable example, the real output, then every method, variation and consequence, followed by graded questions with a verified answer key.

| Topics | Sections | Verified demos | Graded questions |
|---|---|---|---|
| 131 | 14 | 377 | 618 |

> Every output shown was produced by running the code on Python 3.12.3. Sizes and timings can differ on other versions; the concepts do not.

## Table of Contents

- [How to Use This Book](#how-to-use-this-book)
- [Section 3.1 Python's Type System](#section-31-pythons-type-system)
  - [3.1.1 What is a data type](#311-what-is-a-data-type)
  - [3.1.2 The built-in type map](#312-the-built-in-type-map)
  - [3.1.3 type(), isinstance() and issubclass()](#313-type-isinstance-and-issubclass)
  - [3.1.4 Mutable and immutable types](#314-mutable-and-immutable-types)
  - [3.1.5 Truthiness of every type](#315-truthiness-of-every-type)
  - [3.1.6 Literals of every type](#316-literals-of-every-type)
  - [3.1.7 Sequences, sets and mappings: the common protocols](#317-sequences-sets-and-mappings-the-common-protocols)
- [Section 3.2 int: Integers](#section-32-int-integers)
  - [3.2.1 Integer literals and bases](#321-integer-literals-and-bases)
  - [3.2.2 Arbitrary precision](#322-arbitrary-precision)
  - [3.2.3 Arithmetic operators](#323-arithmetic-operators)
  - [3.2.4 Floor division, modulo and negatives; divmod](#324-floor-division-modulo-and-negatives-divmod)
  - [3.2.5 Exponentiation and pow()](#325-exponentiation-and-pow)
  - [3.2.6 Bitwise operators](#326-bitwise-operators)
  - [3.2.7 The int() constructor](#327-the-int-constructor)
  - [3.2.8 Converting to other bases: bin, oct, hex, format](#328-converting-to-other-bases-bin-oct-hex-format)
  - [3.2.9 int methods and attributes](#329-int-methods-and-attributes)
  - [3.2.10 Built-in numeric functions: abs, round, divmod, pow, sum, min, max](#3210-built-in-numeric-functions-abs-round-divmod-pow-sum-min-max)
  - [3.2.11 math functions for integers](#3211-math-functions-for-integers)
  - [3.2.12 Comparing ints and other numbers; chained comparison](#3212-comparing-ints-and-other-numbers-chained-comparison)
  - [3.2.13 Small-int caching and the 4300-digit string limit](#3213-small-int-caching-and-the-4300-digit-string-limit)
  - [3.2.14 Common int pitfalls](#3214-common-int-pitfalls)
- [Section 3.3 float: Floating-Point Numbers](#section-33-float-floating-point-numbers)
  - [3.3.1 Float literals and scientific notation](#331-float-literals-and-scientific-notation)
  - [3.3.2 Binary representation and precision](#332-binary-representation-and-precision)
  - [3.3.3 The float() constructor, inf and nan](#333-the-float-constructor-inf-and-nan)
  - [3.3.4 inf and nan behaviour](#334-inf-and-nan-behaviour)
  - [3.3.5 Comparing floats safely: math.isclose](#335-comparing-floats-safely-mathisclose)
  - [3.3.6 Rounding: round, floor, ceil, trunc, int](#336-rounding-round-floor-ceil-trunc-int)
  - [3.3.7 float methods and attributes](#337-float-methods-and-attributes)
  - [3.3.8 Limits: sys.float_info, overflow and underflow](#338-limits-sysfloat_info-overflow-and-underflow)
  - [3.3.9 Formatting floats for display](#339-formatting-floats-for-display)
  - [3.3.10 The math module for floats](#3310-the-math-module-for-floats)
  - [3.3.11 The decimal module: exact decimal arithmetic](#3311-the-decimal-module-exact-decimal-arithmetic)
  - [3.3.12 The fractions module: exact rationals](#3312-the-fractions-module-exact-rationals)
  - [3.3.13 Common float pitfalls](#3313-common-float-pitfalls)
- [Section 3.4 complex: Complex Numbers](#section-34-complex-complex-numbers)
  - [3.4.1 Complex literals and attributes](#341-complex-literals-and-attributes)
  - [3.4.2 Complex arithmetic, no ordering, and cmath](#342-complex-arithmetic-no-ordering-and-cmath)
- [Section 3.5 bool: Booleans](#section-35-bool-booleans)
  - [3.5.1 bool is a subclass of int](#351-bool-is-a-subclass-of-int)
  - [3.5.2 Boolean operators: and, or, not](#352-boolean-operators-and-or-not)
  - [3.5.3 Bitwise operators on bool, comparisons and any/all](#353-bitwise-operators-on-bool-comparisons-and-anyall)
  - [3.5.4 bool pitfalls](#354-bool-pitfalls)
- [Section 3.6 NoneType and Special Singletons](#section-36-nonetype-and-special-singletons)
  - [3.6.1 None: the absence of a value](#361-none-the-absence-of-a-value)
  - [3.6.2 None as default and sentinel patterns](#362-none-as-default-and-sentinel-patterns)
  - [3.6.3 Ellipsis, NotImplemented and slice objects](#363-ellipsis-notimplemented-and-slice-objects)
- [Section 3.7 str: Strings](#section-37-str-strings)
  - [3.7.1 Creating strings: quotes, triple quotes, concatenation](#371-creating-strings-quotes-triple-quotes-concatenation)
  - [3.7.2 Escape sequences and raw strings](#372-escape-sequences-and-raw-strings)
  - [3.7.3 str versus repr, print and multi-line text](#373-str-versus-repr-print-and-multi-line-text)
  - [3.7.4 Immutability and identity of strings](#374-immutability-and-identity-of-strings)
  - [3.7.5 Indexing: positive and negative](#375-indexing-positive-and-negative)
  - [3.7.6 Slicing in every form](#376-slicing-in-every-form)
  - [3.7.7 Concatenation and repetition](#377-concatenation-and-repetition)
  - [3.7.8 len, in, comparison and ordering](#378-len-in-comparison-and-ordering)
  - [3.7.9 Iterating over strings](#379-iterating-over-strings)
  - [3.7.10 Case methods: upper, lower, capitalize, title, swapcase, casefold](#3710-case-methods-upper-lower-capitalize-title-swapcase-casefold)
  - [3.7.11 Searching: find, rfind, index, rindex, count, in](#3711-searching-find-rfind-index-rindex-count-in)
  - [3.7.12 startswith, endswith, removeprefix, removesuffix](#3712-startswith-endswith-removeprefix-removesuffix)
  - [3.7.13 strip, lstrip, rstrip](#3713-strip-lstrip-rstrip)
  - [3.7.14 split and rsplit](#3714-split-and-rsplit)
  - [3.7.15 splitlines, partition and rpartition](#3715-splitlines-partition-and-rpartition)
  - [3.7.16 join](#3716-join)
  - [3.7.17 replace](#3717-replace)
  - [3.7.18 translate and maketrans](#3718-translate-and-maketrans)
  - [3.7.19 Alignment and padding: center, ljust, rjust, zfill, expandtabs](#3719-alignment-and-padding-center-ljust-rjust-zfill-expandtabs)
  - [3.7.20 Testing methods: isalpha, isdigit, isdecimal, isnumeric, isalnum, isspace and more](#3720-testing-methods-isalpha-isdigit-isdecimal-isnumeric-isalnum-isspace-and-more)
  - [3.7.21 Old-style % formatting](#3721-old-style--formatting)
  - [3.7.22 str.format()](#3722-strformat)
  - [3.7.23 f-strings and the format-spec mini-language](#3723-f-strings-and-the-format-spec-mini-language)
  - [3.7.24 format_map, the string module and Template](#3724-format_map-the-string-module-and-template)
  - [3.7.25 Unicode, encode, decode, ord and chr](#3725-unicode-encode-decode-ord-and-chr)
  - [3.7.26 Unicode normalisation, grapheme caveats and unicodedata](#3726-unicode-normalisation-grapheme-caveats-and-unicodedata)
  - [3.7.27 Complete reference: all 47 str methods](#3727-complete-reference-all-47-str-methods)
  - [3.7.28 Classic string tasks and idioms](#3728-classic-string-tasks-and-idioms)
  - [3.7.29 Performance and memory of strings](#3729-performance-and-memory-of-strings)
  - [3.7.30 Common string pitfalls](#3730-common-string-pitfalls)
- [Section 3.8 bytes, bytearray and memoryview](#section-38-bytes-bytearray-and-memoryview)
  - [3.8.1 bytes: immutable sequences of integers 0-255](#381-bytes-immutable-sequences-of-integers-0-255)
  - [3.8.2 bytes methods and bytearray](#382-bytes-methods-and-bytearray)
  - [3.8.3 memoryview and the buffer protocol](#383-memoryview-and-the-buffer-protocol)
- [Section 3.9 list: Lists](#section-39-list-lists)
  - [3.9.1 Creating lists](#391-creating-lists)
  - [3.9.2 Indexing and slicing lists](#392-indexing-and-slicing-lists)
  - [3.9.3 append, extend, insert and the + / += operators](#393-append-extend-insert-and-the----operators)
  - [3.9.4 remove, pop, del and clear](#394-remove-pop-del-and-clear)
  - [3.9.5 index, count and membership](#395-index-count-and-membership)
  - [3.9.6 sort, sorted, reverse, reversed](#396-sort-sorted-reverse-reversed)
  - [3.9.7 copy: alias, shallow copy and deep copy](#397-copy-alias-shallow-copy-and-deep-copy)
  - [3.9.8 Operators: +, \*, in, comparison and unpacking](#398-operators---in-comparison-and-unpacking)
  - [3.9.9 List comprehensions](#399-list-comprehensions)
  - [3.9.10 Nested lists and matrices](#3910-nested-lists-and-matrices)
  - [3.9.11 Lists as stacks and queues; deque](#3911-lists-as-stacks-and-queues-deque)
  - [3.9.12 enumerate, zip, map, filter and unpacking with lists](#3912-enumerate-zip-map-filter-and-unpacking-with-lists)
  - [3.9.13 min, max, sum, len, any, all and statistics on lists](#3913-min-max-sum-len-any-all-and-statistics-on-lists)
  - [3.9.14 Mutation during iteration and other aliasing traps](#3914-mutation-during-iteration-and-other-aliasing-traps)
  - [3.9.15 Performance of list operations](#3915-performance-of-list-operations)
  - [3.9.16 Complete reference: all 11 list methods](#3916-complete-reference-all-11-list-methods)
  - [3.9.17 Common list pitfalls](#3917-common-list-pitfalls)
- [Section 3.10 tuple: Tuples](#section-310-tuple-tuples)
  - [3.10.1 Creating tuples](#3101-creating-tuples)
  - [3.10.2 Indexing, slicing, operators and methods](#3102-indexing-slicing-operators-and-methods)
  - [3.10.3 Immutability: what is and is not frozen](#3103-immutability-what-is-and-is-not-frozen)
  - [3.10.4 Tuple versus list: when to use which](#3104-tuple-versus-list-when-to-use-which)
  - [3.10.5 Unpacking, swapping and star expressions](#3105-unpacking-swapping-and-star-expressions)
  - [3.10.6 namedtuple and typing.NamedTuple](#3106-namedtuple-and-typingnamedtuple)
  - [3.10.7 Common tuple pitfalls](#3107-common-tuple-pitfalls)
- [Section 3.11 set and frozenset: Sets](#section-311-set-and-frozenset-sets)
  - [3.11.1 Creating sets](#3111-creating-sets)
  - [3.11.2 Adding and removing: add, update, remove, discard, pop, clear](#3112-adding-and-removing-add-update-remove-discard-pop-clear)
  - [3.11.3 Set algebra: union, intersection, difference, symmetric difference](#3113-set-algebra-union-intersection-difference-symmetric-difference)
  - [3.11.4 Subsets, supersets and isdisjoint](#3114-subsets-supersets-and-isdisjoint)
  - [3.11.5 Set comprehensions, deduplication and fast membership](#3115-set-comprehensions-deduplication-and-fast-membership)
  - [3.11.6 frozenset: the immutable set](#3116-frozenset-the-immutable-set)
  - [3.11.7 Hashing, ordering and equality of sets](#3117-hashing-ordering-and-equality-of-sets)
  - [3.11.8 Complete reference: all 17 set methods](#3118-complete-reference-all-17-set-methods)
  - [3.11.9 Common set pitfalls](#3119-common-set-pitfalls)
- [Section 3.12 dict: Dictionaries](#section-312-dict-dictionaries)
  - [3.12.1 Creating dictionaries](#3121-creating-dictionaries)
  - [3.12.2 Reading values: [], get, in and KeyError](#3122-reading-values--get-in-and-keyerror)
  - [3.12.3 Adding and updating: [], update, setdefault, | and |=](#3123-adding-and-updating--update-setdefault--and-)
  - [3.12.4 Removing: pop, popitem, del and clear](#3124-removing-pop-popitem-del-and-clear)
  - [3.12.5 Views: keys(), values(), items()](#3125-views-keys-values-items)
  - [3.12.6 Changing a dict while iterating](#3126-changing-a-dict-while-iterating)
  - [3.12.7 Dict comprehensions, fromkeys, zip and inversion](#3127-dict-comprehensions-fromkeys-zip-and-inversion)
  - [3.12.8 Nested dictionaries, copy and deepcopy](#3128-nested-dictionaries-copy-and-deepcopy)
  - [3.12.9 Ordering: insertion order, sorting and reversing](#3129-ordering-insertion-order-sorting-and-reversing)
  - [3.12.10 Key rules: hashability, equal keys and tuple keys](#31210-key-rules-hashability-equal-keys-and-tuple-keys)
  - [3.12.11 collections: defaultdict, Counter, OrderedDict, ChainMap](#31211-collections-defaultdict-counter-ordereddict-chainmap)
  - [3.12.12 Complete reference: all 11 dict methods](#31212-complete-reference-all-11-dict-methods)
  - [3.12.13 Common dict pitfalls](#31213-common-dict-pitfalls)
- [Section 3.13 range: Ranges](#section-313-range-ranges)
  - [3.13.1 range(start, stop, step)](#3131-rangestart-stop-step)
  - [3.13.2 Using range correctly: loops, indexes and off-by-one](#3132-using-range-correctly-loops-indexes-and-off-by-one)
- [Section 3.14 Type Conversion and Choosing a Type](#section-314-type-conversion-and-choosing-a-type)
  - [3.14.1 Implicit and explicit conversion](#3141-implicit-and-explicit-conversion)
  - [3.14.2 The conversion matrix](#3142-the-conversion-matrix)
  - [3.14.3 Text to values and back: literal_eval, json, eval](#3143-text-to-values-and-back-literal_eval-json-eval)
  - [3.14.4 Converting between containers](#3144-converting-between-containers)
  - [3.14.5 Safe conversion helpers](#3145-safe-conversion-helpers)
  - [3.14.6 Type checking: isinstance, duck typing and annotations](#3146-type-checking-isinstance-duck-typing-and-annotations)
  - [3.14.7 Choosing the right data type](#3147-choosing-the-right-data-type)
- [Chapter 3 Summary: The 42 Rules](#chapter-3-summary-the-42-rules)
  - [Error Message Decoder](#error-message-decoder)
- [Final Exam (60 mixed HARD and TRAP questions)](#final-exam-60-mixed-hard-and-trap-questions)
- [Answer Key (outputs from running the code)](#answer-key-outputs-from-running-the-code)
- [Final exam answers](#final-exam-answers)

---

## How to Use This Book

Each topic follows the same teaching order as your Chapter 2 book: what it is, then a runnable example, then the verified output, then every variation and consequence, then graded practice.

Green-edged boxes are code, blue-edged boxes are the exact output the code printed.

- Read the explanation, then try each example yourself before looking at the printed output.
- In the Practice list, cover the answer key at the end of the book, write your prediction, and only then run the question.
- Levels: BASIC (direct), MID (needs the model), HARD (combines ideas), TRAP (looks easy, hides a pitfall).
- Some TRAP questions end in an error on purpose; the answer key then shows the final error line Python printed.
- Method reference tables (str 47, list 11, dict 11, set 17, tuple 2) are checked against dir() so no method is missed.
- Set and dict-view results are shown sorted whenever order is not guaranteed, so your output will match.
- If an output surprises you, that is the point: stop and ask which object each name points to and what its type allows.

```text
Core idea of the whole chapter
 every object has ONE type; the type decides what you can do
 immutable: int float complex bool str bytes tuple frozenset range None
 mutable  : list dict set bytearray
 hashable (dict key / set member): the immutable ones, if their items are hashable
 sequences : str list tuple range bytes  (index, slice, len, in)
 sets      : set frozenset               (unique, unordered, fast in)
 mapping   : dict                        (key -> value, insertion ordered)
```

---

## Section 3.1 Python's Type System

### 3.1.1 What is a data type

A data type (a CLASS in Python) decides three things about an object: what values it can hold, which operations work on it, and how it behaves in memory (can it change, can it be a dict key). Every value you will ever meet is an object of exactly one type.

Python has a small set of BUILT-IN types that need no import: numbers (int, float, complex, bool), text (str), binary (bytes, bytearray), sequences (list, tuple, range), sets (set, frozenset), mapping (dict) and the single value None.

> **Key rule:** a type belongs to the OBJECT, never to the name; type(obj) tells you which class made it.

**Example 3.1.1.1: Asking the type of different values**

```python
print(type(42))
print(type(3.14))
print(type("hi"))
print(type(True))
print(type(None))
print(type([1, 2]), type((1, 2)), type({1, 2}), type({1: 2}))
```

*Output:*

```text
<class 'int'>
<class 'float'>
<class 'str'>
<class 'bool'>
<class 'NoneType'>
<class 'list'> <class 'tuple'> <class 'set'> <class 'dict'>
```

**Example 3.1.1.2: Every type is itself an object of class type**

```python
print(type(int))
print(type(type(int)))
print(int.__name__, str.__name__)
```

*Output:*

```text
<class 'type'>
<class 'type'>
int str
```

**Example 3.1.1.3: Types decide which operations are legal**

```python
print(3 + 4, "3" + "4", [3] + [4])
print((1, 2) * 2)
print({1, 2} | {2, 3})
```

*Output:*

```text
7 34 [3, 4]
(1, 2, 1, 2)
{1, 2, 3}
```

> ⚠️ **Watch out:** `type(x) == int` fails for subclasses such as bool. Prefer `isinstance` (topic 3.1.3).

#### Practice 3.1.1

**3.1.1-Q1** · `BASIC`

```python
print(type(7), type(7.0), type('7'))
```

**3.1.1-Q2** · `BASIC`

```python
print(type([]), type(()), type({}), type(set()))
```

**3.1.1-Q3** · `MID`

```python
print(type(None), type(print), type(len))
```

**3.1.1-Q4** · `HARD`

```python
print(type(type), type(type) is type)
```

**3.1.1-Q5** · `TRAP`

```python
print(type(1 + 1.0), type(True + True), type('a' * 2))
```

### 3.1.2 The built-in type map

Python groups its types into families. Knowing the family tells you which operations and methods to expect before you read any documentation.

> **Key rule:** every built-in type belongs to one family, and the family predicts the available operations.

**Built-in types at a glance**

| Family | Types | Literal example | Mutable? |
|---|---|---|---|
| Integer | `int`, `bool` | `42`, `True` | no |
| Floating point | `float` | `3.14`, `1e-3` | no |
| Complex | `complex` | `2+3j` | no |
| Text | `str` | `'hello'` | no |
| Binary | `bytes`, `bytearray`, `memoryview` | `b'hi'` | bytes no, bytearray yes |
| Sequence | `list`, `tuple`, `range` | `[1,2]`, `(1,2)`, `range(3)` | list yes; tuple, range no |
| Set | `set`, `frozenset` | `{1,2}` | set yes, frozenset no |
| Mapping | `dict` | `{'a': 1}` | yes |
| Null | `NoneType` | `None` | no |

**Example 3.1.2.1: Listing the type of each literal in one loop**

```python
values = [1, 1.5, 2j, True, "s", b"b", [1], (1,), {1}, {1: 1}, range(2), None]
for v in values:
    print(f"{v!r:10} -> {type(v).__name__}")
```

*Output:*

```text
1          -> int
1.5        -> float
2j         -> complex
True       -> bool
's'        -> str
b'b'       -> bytes
[1]        -> list
(1,)       -> tuple
{1}        -> set
{1: 1}     -> dict
range(0, 2) -> range
None       -> NoneType
```

**Example 3.1.2.2: The numeric tower with isinstance**

```python
import numbers
print(isinstance(1, numbers.Integral), isinstance(1.5, numbers.Real))
print(isinstance(2j, numbers.Complex), isinstance(2j, numbers.Real))
```

*Output:*

```text
True True
True False
```

#### Practice 3.1.2

**3.1.2-Q1** · `BASIC`

```python
print(type(range(3)).__name__, type(b'x').__name__)
```

**3.1.2-Q2** · `MID`

```python
print(isinstance(True, int), isinstance(1, bool))
```

**3.1.2-Q3** · `MID`

```python
print(isinstance(5, float), isinstance(5.0, float))
```

**3.1.2-Q4** · `HARD`

```python
import numbers; print(isinstance(1.5, numbers.Integral), isinstance(True, numbers.Integral))
```

**3.1.2-Q5** · `TRAP`

```python
print(type({}), type({1}), type({1: 1}.keys()).__name__)
```

### 3.1.3 type(), isinstance() and issubclass()

`type(x)` returns the exact class. `isinstance(x, C)` is True when x is an instance of C OR of any subclass of C, and it accepts a tuple of classes. `issubclass(A, B)` compares classes directly.

Because bool is a subclass of int, `isinstance(True, int)` is True while `type(True) is int` is False. This is why professional code almost always uses isinstance.

> **Key rule:** use isinstance(x, (A, B)) for checks; use type(x) is T only when subclasses must be rejected.

**Example 3.1.3.1: type versus isinstance**

```python
x = True
print(type(x) is int, type(x) is bool)
print(isinstance(x, int), isinstance(x, bool))
```

*Output:*

```text
False True
True True
```

**Example 3.1.3.2: Checking several types at once**

```python
def kind(v):
    if isinstance(v, (int, float)):
        return "number"
    if isinstance(v, (list, tuple)):
        return "sequence"
    return "other"
print(kind(3), kind(2.5), kind([1]), kind("s"))
```

*Output:*

```text
number number sequence other
```

**Example 3.1.3.3: issubclass and the class hierarchy**

```python
print(issubclass(bool, int), issubclass(int, object))
print(bool.__mro__)
print(issubclass(list, tuple))
```

*Output:*

```text
True True
(<class 'bool'>, <class 'int'>, <class 'object'>)
False
```

> ⚠️ **Watch out:** `isinstance(True, int)` is True, so a loop that counts 'integers' will also count booleans.

#### Practice 3.1.3

**3.1.3-Q1** · `BASIC`

```python
print(isinstance(3, int), isinstance(3, float))
```

**3.1.3-Q2** · `BASIC`

```python
print(isinstance('a', str), isinstance('a', (int, str)))
```

**3.1.3-Q3** · `MID`

```python
print(type(True) == int, isinstance(True, int))
```

**3.1.3-Q4** · `HARD`

```python
print(issubclass(bool, (str, int)), issubclass(str, object))
```

**3.1.3-Q5** · `TRAP`

```python
data = [1, True, 2.0, 'x', 3]
print(sum(1 for d in data if isinstance(d, int)))
```

### 3.1.4 Mutable and immutable types

An immutable object can never change after creation; every 'modification' builds a NEW object. A mutable object can change in place, so every name pointing at it sees the change. This single property decides copying behaviour, dictionary-key eligibility, and the famous default-argument trap.

> **Key rule:** immutable: operations return new objects. mutable: methods change the object in place.

**Mutability of the built-in types**

| Immutable | Mutable |
|---|---|
| `int`, `float`, `complex`, `bool` | `list` |
| `str`, `bytes` | `dict` |
| `tuple`, `frozenset`, `range` | `set`, `bytearray` |
| `NoneType` | user-defined class instances (by default) |

**Example 3.1.4.1: Immutable: the id changes after +=**

```python
s = "ab"
before = id(s)
s += "c"
print(s, id(s) == before)
```

*Output:*

```text
abc False
```

**Example 3.1.4.2: Mutable: the id stays the same after +=**

```python
lst = [1, 2]
before = id(lst)
lst += [3]
print(lst, id(lst) == before)
```

*Output:*

```text
[1, 2, 3] True
```

**Example 3.1.4.3: Item assignment: allowed on mutable, error on immutable**

```python
lst = [1, 2, 3]
lst[0] = 99
print(lst)
t = (1, 2, 3)
t[0] = 99
```

*Output:*

```text
[99, 2, 3]
TypeError: 'tuple' object does not support item assignment
```

#### Practice 3.1.4

**3.1.4-Q1** · `BASIC`

```python
s = 'abc'
try:
    s[0] = 'x'
except TypeError:
    print('immutable')
```

**3.1.4-Q2** · `BASIC`

```python
a = [1]
a.append(2)
print(a)
```

**3.1.4-Q3** · `MID`

```python
t = (1, [2])
t[1].append(3)
print(t)
```

**3.1.4-Q4** · `HARD`

```python
x = 5
i = id(x)
x += 0
print(id(x) == i)
```

**3.1.4-Q5** · `TRAP`

```python
a = (1, 2)
b = a
a += (3,)
print(a, b)
```

### 3.1.5 Truthiness of every type

Every object is either truthy or falsy. Falsy values are exactly: None, False, zero of any numeric type (0, 0.0, 0j), and every EMPTY container or string ('', [], (), {}, set(), range(0), b''). Everything else is truthy. User classes are truthy unless they define __bool__ or __len__.

> **Key rule:** falsy = None, False, zero, or empty. Everything else (including the string 'False' and nan) is truthy.

**The complete falsy list**

| Type | Falsy value | Truthy example |
|---|---|---|
| NoneType | `None` | - |
| bool | `False` | `True` |
| int | `0` | `-1`, `7` |
| float | `0.0`, `-0.0` | `0.1`, `nan` |
| complex | `0j` | `1j` |
| str | `''` | `' '`, `'0'`, `'False'` |
| list/tuple | `[]`, `()` | `[0]`, `(None,)` |
| dict/set | `{}`, `set()` | `{0: 0}`, `{0}` |
| range | `range(0)` | `range(1)` |
| bytes | `b''` | `b' '` |

**Example 3.1.5.1: bool() of many values**

```python
for v in [0, 1, -1, 0.0, "", " ", "0", [], [0], (), {}, {0: 0}, None, float("nan")]:
    print(f"{v!r:8} -> {bool(v)}")
```

*Output:*

```text
0        -> False
1        -> True
-1       -> True
0.0      -> False
''       -> False
' '      -> True
'0'      -> True
[]       -> False
[0]      -> True
()       -> False
{}       -> False
{0: 0}   -> True
None     -> False
nan      -> True
```

**Example 3.1.5.2: Using truthiness in conditions**

```python
items = []
if not items:
    print("empty list is falsy")
name = ""
print(name or "anonymous")
```

*Output:*

```text
empty list is falsy
anonymous
```

> ⚠️ **Watch out:** `if x:` also rejects 0, so `if count:` cannot tell 'no value' from 'zero'. Use `is None` when None means missing.

#### Practice 3.1.5

**3.1.5-Q1** · `BASIC`

```python
print(bool(0), bool(1), bool(''), bool('a'))
```

**3.1.5-Q2** · `BASIC`

```python
print(bool([]), bool([0]), bool(()), bool({}))
```

**3.1.5-Q3** · `MID`

```python
print(bool('False'), bool(0.0), bool(None), bool(' '))
```

**3.1.5-Q4** · `HARD`

```python
print(bool(float('nan')), bool(-0.0), bool(0j), bool(range(0)))
```

**3.1.5-Q5** · `TRAP`

```python
x = 0
print(x or 'default', x if x is not None else 'default')
```

### 3.1.6 Literals of every type

A literal is a value written directly in source code. Python lets you write numbers in several bases, strings with several quote styles, and containers with brackets. Knowing every literal form prevents syntax surprises.

> **Key rule:** `{}` is an empty DICT, `()` is an empty tuple, and `set()` is the only way to write an empty set.

**Literal forms**

| Type | Forms |
|---|---|
| int | `10`, `1_000`, `0b101`, `0o17`, `0xFF` |
| float | `1.5`, `.5`, `5.`, `1e3`, `2.5E-4`, `1_0.5` |
| complex | `3j`, `2+3j`, `1.5J` |
| str | `'a'`, `"a"`, `'''a'''`, `"""a"""`, `r'a\n'`, `f'{x}'` |
| bytes | `b'abc'`, `rb'a\n'` |
| list/tuple | `[]`, `[1,2]`, `()`, `(1,)`, `1,2` |
| set/dict | `{1,2}`, `set()`, `{}` (dict!), `{'a':1}` |
| None/bool | `None`, `True`, `False` |

**Example 3.1.6.1: Number literals in several bases**

```python
print(0b101, 0o17, 0xFF, 1_000_000)
print(1e3, .5, 5., 2.5E-4)
print(3j, 2 + 3j)
```

*Output:*

```text
5 15 255 1000000
1000.0 0.5 5.0 0.00025
3j (2+3j)
```

**Example 3.1.6.2: Container literals**

```python
print(type({}), type({1}), type(()), type((1,)), type((1)))
a, b = 1, 2
print(type((a, b)), type([a, b]), type({a, b}))
```

*Output:*

```text
<class 'dict'> <class 'set'> <class 'tuple'> <class 'tuple'> <class 'int'>
<class 'tuple'> <class 'list'> <class 'set'>
```

#### Practice 3.1.6

**3.1.6-Q1** · `BASIC`

```python
print(0xFF, 0b11, 0o10)
```

**3.1.6-Q2** · `BASIC`

```python
print(type({}), type(set()))
```

**3.1.6-Q3** · `MID`

```python
print(type((1)), type((1,)), type(()))
```

**3.1.6-Q4** · `HARD`

```python
x = 1,
print(x, type(x))
```

**3.1.6-Q5** · `TRAP`

```python
print(1_0 + 1_0, 0b1_1, 1e1_0)
```

### 3.1.7 Sequences, sets and mappings: the common protocols

Containers share small protocols. Anything with `len()`, `in`, and iteration is a container. SEQUENCES (str, list, tuple, range, bytes) add ordering, integer indexing and slicing. SETS add fast membership and set algebra. MAPPINGS (dict) look values up by key.

> **Key rule:** the same built-in functions (len, in, iteration, sorted, min, max, sum) work across most containers.

**Which operations each family supports**

| Operation | Sequence | Set | dict |
|---|---|---|---|
| `len(x)` | yes | yes | yes |
| `x in c` | yes (slow, O(n)) | yes (fast) | keys (fast) |
| `x[i]` integer index | yes | no | by key |
| slicing `x[a:b]` | yes | no | no |
| `+` concatenate | yes (not range) | no | no (use `\|`) |
| `*` repeat | yes (not range) | no | no |
| ordering guaranteed | yes | no | yes (insertion order) |

**Example 3.1.7.1: The shared functions**

```python
for c in ([3, 1, 2], (3, 1, 2), {3, 1, 2}, "312"):
    print(type(c).__name__, len(c), sorted(c), 3 in c if not isinstance(c, str) else "3" in c)
```

*Output:*

```text
list 3 [1, 2, 3] True
tuple 3 [1, 2, 3] True
set 3 [1, 2, 3] True
str 3 ['1', '2', '3'] True
```

**Example 3.1.7.2: Dict iteration goes over keys**

```python
d = {"a": 1, "b": 2}
print(len(d), "a" in d, 1 in d, list(d), sorted(d.values()))
```

*Output:*

```text
2 True False ['a', 'b'] [1, 2]
```

#### Practice 3.1.7

**3.1.7-Q1** · `BASIC`

```python
print(len([1,2]), len((1,)), len({1,2,3}), len('abcd'))
```

**3.1.7-Q2** · `MID`

```python
print(2 in {1:2}, 2 in {2:1}, 2 in [1,2], 2 in {1,2})
```

**3.1.7-Q3** · `HARD`

```python
print(sorted({3: 'c', 1: 'a'}), sorted({3: 'c', 1: 'a'}.values()))
```

**3.1.7-Q4** · `TRAP`

```python
print(len({}), len({'a': 1, 'a': 2}), len({1, 1.0, True}))
```

---

## Section 3.2 int: Integers

### 3.2.1 Integer literals and bases

An int is a whole number of any size. You can write it in four bases: decimal (default), binary `0b`, octal `0o` and hexadecimal `0x`. Underscores may separate digits for readability and are ignored. Prefixes are case-insensitive. Leading zeros on a nonzero decimal are a syntax error.

> **Key rule:** the base only changes how a number is WRITTEN; the stored value is the same int.

**Example 3.2.1.1: Four spellings of the same value**

```python
print(255, 0b11111111, 0o377, 0xFF)
print(255 == 0xFF == 0o377 == 0b11111111)
```

*Output:*

```text
255 255 255 255
True
```

**Example 3.2.1.2: Underscores for readability**

```python
population = 7_900_000_000
mask = 0b1111_0000
print(population, mask, 0xFF_FF)
```

*Output:*

```text
7900000000 240 65535
```

**Example 3.2.1.3: Invalid forms**

```python
print(010)
```

*Output:*

```text
SyntaxError: leading zeros in decimal integer literals are not permitted; use an 0o prefix for octal integers
```

> ⚠️ **Watch out:** `010` is a SyntaxError in Python 3. Write `0o10` for octal 8.

#### Practice 3.2.1

**3.2.1-Q1** · `BASIC`

```python
print(0b101, 0o17, 0x1F)
```

**3.2.1-Q2** · `BASIC`

```python
print(1_000 + 1_000)
```

**3.2.1-Q3** · `MID`

```python
print(0xff == 255, 0XFF == 0xff)
```

**3.2.1-Q4** · `HARD`

```python
print(0b1111 + 0o10 + 0x10)
```

**3.2.1-Q5** · `TRAP`

```python
print(int('010'), int('0b11', 0), int('0o10', 0))
```

### 3.2.2 Arbitrary precision

Python integers have no fixed size: they grow as needed, limited only by memory. There is no overflow and no separate long type. This is why factorials and big exponents just work, and why integer arithmetic is slower than in C.

> **Key rule:** int never overflows; results are exact no matter how large.

**Example 3.2.2.1: Huge exact values**

```python
print(2 ** 100)
print(2 ** 64 - 1)
print(len(str(2 ** 1000)))
```

*Output:*

```text
1267650600228229401496703205376
18446744073709551615
302
```

**Example 3.2.2.2: Factorial of 30**

```python
import math
print(math.factorial(30))
```

*Output:*

```text
265252859812191058636308480000000
```

**Example 3.2.2.3: Size grows with the value**

```python
import sys
print(sys.getsizeof(1), sys.getsizeof(2 ** 30), sys.getsizeof(2 ** 100), sys.getsizeof(2 ** 1000))
```

*Output:*

```text
28 32 40 160
```

#### Practice 3.2.2

**3.2.2-Q1** · `BASIC`

```python
print(2 ** 10, 10 ** 3)
```

**3.2.2-Q2** · `BASIC`

```python
print(2 ** 70)
```

**3.2.2-Q3** · `MID`

```python
print(len(str(3 ** 100)))
```

**3.2.2-Q4** · `HARD`

```python
import sys; print(sys.maxsize == 2 ** 63 - 1, sys.maxsize + 1)
```

**3.2.2-Q5** · `TRAP`

```python
print((2 ** 64) * (2 ** 64) == 2 ** 128)
```

### 3.2.3 Arithmetic operators

`+ - *` return an int for int operands. `/` ALWAYS returns a float, even when the division is exact. `//` is floor division and `%` is modulo. `**` is exponentiation. `-x` negates. Mixing an int with a float gives a float.

> **Key rule:** / gives a float; // and % give ints for int operands; ** with a negative exponent gives a float.

**The seven arithmetic operators**

| Operator | Name | Example | Result |
|---|---|---|---|
| `+` | add | `7 + 2` | 9 |
| `-` | subtract | `7 - 2` | 5 |
| `*` | multiply | `7 * 2` | 14 |
| `/` | true division | `7 / 2` | 3.5 |
| `//` | floor division | `7 // 2` | 3 |
| `%` | modulo | `7 % 2` | 1 |
| `**` | power | `7 ** 2` | 49 |

**Example 3.2.3.1: The operators side by side**

```python
a, b = 17, 5
print(a + b, a - b, a * b)
print(a / b, a // b, a % b, a ** 2)
```

*Output:*

```text
22 12 85
3.4 3 2 289
```

**Example 3.2.3.2: Exact division still gives a float**

```python
print(10 / 2, type(10 / 2))
print(10 // 2, type(10 // 2))
```

*Output:*

```text
5.0 <class 'float'>
5 <class 'int'>
```

**Example 3.2.3.3: Precedence: ** binds tighter than unary minus on its left**

```python
print(-2 ** 2, (-2) ** 2)
print(2 ** 3 ** 2, (2 ** 3) ** 2)
print(2 + 3 * 4, (2 + 3) * 4)
```

*Output:*

```text
-4 4
512 64
14 20
```

#### Practice 3.2.3

**3.2.3-Q1** · `BASIC`

```python
print(9 + 4, 9 - 4, 9 * 4)
```

**3.2.3-Q2** · `BASIC`

```python
print(9 / 4, 9 // 4, 9 % 4)
```

**3.2.3-Q3** · `MID`

```python
print(8 / 2, 2 ** -1, 2 ** 0.5 == 4 ** 0.25)
```

**3.2.3-Q4** · `HARD`

```python
print(-2 ** 2, 2 ** 3 ** 2, 10 - 2 - 3)
```

**3.2.3-Q5** · `TRAP`

```python
print(type(6 / 3), type(6 // 3), type(6.0 // 3), type(2 ** -1))
```

### 3.2.4 Floor division, modulo and negatives; divmod

`//` rounds toward MINUS INFINITY, not toward zero, and `%` takes the sign of the DIVISOR. Together they always satisfy `a == (a // b) * b + (a % b)`. `divmod(a, b)` returns both in one call, which is also faster than two separate operations.

> **Key rule:** a == (a // b) \* b + a % b always holds, and a % b has the sign of b.

**Example 3.2.4.1: Negative operands**

```python
print(7 // 2, -7 // 2, 7 // -2, -7 // -2)
print(7 % 3, -7 % 3, 7 % -3, -7 % -3)
```

*Output:*

```text
3 -4 -4 3
1 2 -2 -1
```

**Example 3.2.4.2: The identity always holds**

```python
for a, b in [(7, 3), (-7, 3), (7, -3), (-7, -3)]:
    print(a, b, a == (a // b) * b + a % b)
```

*Output:*

```text
7 3 True
-7 3 True
7 -3 True
-7 -3 True
```

**Example 3.2.4.3: divmod and clock arithmetic**

```python
print(divmod(17, 5), divmod(-17, 5))
minutes = 135
print(divmod(minutes, 60))
print((23 + 5) % 24)
```

*Output:*

```text
(3, 2) (-4, 3)
(2, 15)
4
```

> ⚠️ **Watch out:** Truncating languages (C, Java) give -7 // 2 == -3 and -7 % 3 == -1. Python gives -4 and 2.

#### Practice 3.2.4

**3.2.4-Q1** · `BASIC`

```python
print(17 // 5, 17 % 5, divmod(17, 5))
```

**3.2.4-Q2** · `MID`

```python
print(-17 // 5, -17 % 5)
```

**3.2.4-Q3** · `MID`

```python
print(17 // -5, 17 % -5)
```

**3.2.4-Q4** · `HARD`

```python
print(divmod(-7, -2), divmod(7, -2))
```

**3.2.4-Q5** · `TRAP`

```python
print(int(-7 / 2), -7 // 2, round(-3.5), -7 % 2)
```

### 3.2.5 Exponentiation and pow()

`a ** b` and `pow(a, b)` are equal. `pow(a, b, m)` computes `a ** b % m` using fast modular exponentiation, which stays quick even for huge exponents. With two arguments a negative exponent returns a float; with three arguments a negative exponent computes a modular inverse (Python 3.8+).

> **Key rule:** pow(a, b, m) is the right tool for modular exponentiation; never write (a ** b) % m for large b.

**Example 3.2.5.1: Equivalent forms**

```python
print(2 ** 10, pow(2, 10), 2 ** -2, pow(2, -2))
```

*Output:*

```text
1024 1024 0.25 0.25
```

**Example 3.2.5.2: Three-argument pow**

```python
print(pow(2, 10, 1000))
print(pow(3, 200, 13), (3 ** 200) % 13)
print(pow(7, -1, 13))
```

*Output:*

```text
24
9 9
2
```

**Example 3.2.5.3: Roots as fractional powers (floats)**

```python
print(9 ** 0.5, 27 ** (1 / 3))
print((-8) ** (1 / 3))
```

*Output:*

```text
3.0 3.0
(1.0000000000000002+1.7320508075688772j)
```

#### Practice 3.2.5

**3.2.5-Q1** · `BASIC`

```python
print(pow(3, 4), 3 ** 4)
```

**3.2.5-Q2** · `MID`

```python
print(pow(2, 5, 7), 2 ** 5 % 7)
```

**3.2.5-Q3** · `MID`

```python
print(0 ** 0, pow(0, 0), 5 ** 0)
```

**3.2.5-Q4** · `HARD`

```python
print(pow(3, -1, 7), 3 * pow(3, -1, 7) % 7)
```

**3.2.5-Q5** · `TRAP`

```python
print(27 ** (1 / 3), round(27 ** (1 / 3), 6))
```

### 3.2.6 Bitwise operators

Bitwise operators work on the binary form of an int. `&` AND, `|` OR, `^` XOR, `~` NOT (equals `-x - 1`), `<<` shift left (multiply by 2**n),** `>>` **shift right (floor divide by 2**n). Negative numbers behave as if they had infinitely many leading 1 bits (two's complement).

> **Key rule:** ~x == -x - 1; x << n == x \* 2n; x >> n == x // 2n.

**Bitwise operators**

| Op | Meaning | Example | Result |
|---|---|---|---|
| `&` | AND | `12 & 10` | 8 |
| `\|` | OR | `12 \| 10` | 14 |
| `^` | XOR | `12 ^ 10` | 6 |
| `~` | NOT | `~12` | -13 |
| `<<` | shift left | `3 << 2` | 12 |
| `>>` | shift right | `12 >> 2` | 3 |

**Example 3.2.6.1: Binary view of AND, OR, XOR**

```python
a, b = 12, 10
print(f"{a:04b} {b:04b}")
print(f"{a & b:04b} {a | b:04b} {a ^ b:04b}")
```

*Output:*

```text
1100 1010
1000 1110 0110
```

**Example 3.2.6.2: Shifts as multiplication and division**

```python
print(3 << 4, 3 * 2 ** 4)
print(100 >> 3, 100 // 2 ** 3, -100 >> 3)
```

*Output:*

```text
48 48
12 12 -13
```

**Example 3.2.6.3: Common bit tricks**

```python
n = 0b101100
print(n & 1, bool(n & 0b100), n & (n - 1), n & -n)
print(5 ^ 5, 5 ^ 0, 7 ^ 2 ^ 2)
```

*Output:*

```text
0 True 40 4
0 5 7
```

#### Practice 3.2.6

**3.2.6-Q1** · `BASIC`

```python
print(6 & 3, 6 | 3, 6 ^ 3)
```

**3.2.6-Q2** · `BASIC`

```python
print(1 << 5, 64 >> 3)
```

**3.2.6-Q3** · `MID`

```python
print(~0, ~5, ~-1)
```

**3.2.6-Q4** · `HARD`

```python
print(-9 >> 1, -9 // 2, -1 >> 10)
```

**3.2.6-Q5** · `TRAP`

```python
print(True & False, True | False, True ^ True, ~True)
```

### 3.2.7 The int() constructor

`int(x)` converts a number or string to an int. A float is TRUNCATED toward zero (use round, floor or ceil for other behaviour). A string must contain a valid integer literal; spaces and underscores between digits are allowed, a decimal point is not. `int(s, base)` parses in base 2 to 36, and base 0 means 'detect the prefix'.

> **Key rule:** int(3.99) == 3 and int(-3.99) == -3; int('3.5') raises ValueError.

**Example 3.2.7.1: From floats, strings and bools**

```python
print(int(3.99), int(-3.99), int("42"), int(" 42 "), int(True))
print(int("1_000"), int("+7"), int("-7"))
```

*Output:*

```text
3 -3 42 42 1
1000 7 -7
```

**Example 3.2.7.2: With a base**

```python
print(int("1010", 2), int("ff", 16), int("FF", 16), int("z", 36))
print(int("0xff", 16), int("0xff", 0), int("0b101", 0))
```

*Output:*

```text
10 255 255 35
255 255 5
```

**Example 3.2.7.3: The failures**

```python
for s in ["3.5", "", "12a", "1e3"]:
    try:
        int(s)
    except ValueError as e:
        print(repr(s), "->", e)
```

*Output:*

```text
'3.5' -> invalid literal for int() with base 10: '3.5'
'' -> invalid literal for int() with base 10: ''
'12a' -> invalid literal for int() with base 10: '12a'
'1e3' -> invalid literal for int() with base 10: '1e3'
```

> ⚠️ **Watch out:** `int('3.0')` also fails. Convert in two steps: `int(float('3.0'))`.

#### Practice 3.2.7

**3.2.7-Q1** · `BASIC`

```python
print(int(7.9), int('7'), int(-7.9))
```

**3.2.7-Q2** · `MID`

```python
print(int('101', 2), int('77', 8), int('ff', 16))
```

**3.2.7-Q3** · `MID`

```python
print(int(' 12 '), int('+5'), int('0012'))
```

**3.2.7-Q4** · `HARD`

```python
print(int(float('1e3')), int(1e3), int(2.5e0))
```

**3.2.7-Q5** · `TRAP`

```python
print(int('3.0'))
```

### 3.2.8 Converting to other bases: bin, oct, hex, format

`bin()`, `oct()` and `hex()` return STRINGS with a prefix. To get digits without a prefix, or with padding, use format specs: `f'{n:b}'`, `f'{n:o}'`, `f'{n:x}'`, `f'{n:X}'`, `f'{n:08b}'`. Round-trip with `int(text, base)`.

> **Key rule:** bin/oct/hex return str (with prefix); int(text, base) goes back.

**Example 3.2.8.1: Built-in converters**

```python
n = 255
print(bin(n), oct(n), hex(n))
print(bin(-5), hex(-255))
print(type(bin(5)))
```

*Output:*

```text
0b11111111 0o377 0xff
-0b101 -0xff
<class 'str'>
```

**Example 3.2.8.2: Format specs: no prefix, padding, alternate form**

```python
n = 10
print(f"{n:b} {n:o} {n:x} {n:X}")
print(f"{n:08b} {n:#b} {n:#x} {n:#o}")
print(format(n, "b"), format(255, ",d"), f"{1234567:,}")
```

*Output:*

```text
1010 12 a A
00001010 0b1010 0xa 0o12
1010 255 1,234,567
```

**Example 3.2.8.3: Round trip**

```python
s = bin(37)
print(s, int(s, 2), int(s, 0), int(s[2:], 2))
```

*Output:*

```text
0b100101 37 37 37
```

#### Practice 3.2.8

**3.2.8-Q1** · `BASIC`

```python
print(bin(5), oct(8), hex(255))
```

**3.2.8-Q2** · `BASIC`

```python
print(f'{5:b}', f'{255:x}', f'{255:X}')
```

**3.2.8-Q3** · `MID`

```python
print(f'{5:08b}', f'{5:#010b}')
```

**3.2.8-Q4** · `HARD`

```python
print(bin(-5), int(bin(-5), 2))
```

**3.2.8-Q5** · `TRAP`

```python
print(bin(5) + bin(3), int(bin(5), 2) + int(bin(3), 2))
```

### 3.2.9 int methods and attributes

Because ints are objects they have methods. The ones worth knowing: `bit_length()` (bits needed), `bit_count()` (number of 1 bits, 3.10+), `to_bytes()` / `int.from_bytes()` (binary serialisation), `as_integer_ratio()`, `is_integer()` (3.12+, always True), `conjugate()`, and the attributes `real`, `imag`, `numerator`, `denominator`.

> **Key rule:** write `5 .bit_length()` or `(5).bit_length()`; `5.bit_length()` is a syntax error.

**Every public int method and attribute**

| Name | Meaning | Example -> result |
|---|---|---|
| `bit_length()` | bits needed, excluding sign | `37 .bit_length()` -> 6 |
| `bit_count()` | number of 1 bits in abs value | `37 .bit_count()` -> 3 |
| `to_bytes(n, order)` | int to bytes | `258 .to_bytes(2, 'big')` -> b'\x01\x02' |
| `int.from_bytes(b, order)` | bytes to int | `int.from_bytes(b'\x01\x02','big')` -> 258 |
| `as_integer_ratio()` | (numerator, 1) | `6 .as_integer_ratio()` -> (6, 1) |
| `is_integer()` | always True (3.12+) | `5 .is_integer()` -> True |
| `conjugate()` | returns itself | `5 .conjugate()` -> 5 |
| `real`, `imag` | itself and 0 | `5 .real, 5 .imag` -> 5, 0 |
| `numerator`, `denominator` | itself and 1 | `5 .numerator` -> 5 |

**Example 3.2.9.1: Bits and sizes**

```python
n = 37
print(bin(n), n.bit_length(), n.bit_count())
print((0).bit_length(), (255).bit_length(), (256).bit_length(), (-5).bit_length())
```

*Output:*

```text
0b100101 6 3
0 8 9 3
```

**Example 3.2.9.2: Bytes round trip**

```python
b = (258).to_bytes(2, "big")
print(b, list(b), int.from_bytes(b, "big"))
print((258).to_bytes(2, "little"), (-2).to_bytes(1, "big", signed=True))
```

*Output:*

```text
b'\x01\x02' [1, 2] 258
b'\x02\x01' b'\xfe'
```

**Example 3.2.9.3: The numeric attributes**

```python
x = 7
print(x.real, x.imag, x.numerator, x.denominator, x.conjugate())
print(x.as_integer_ratio(), x.is_integer())
```

*Output:*

```text
7 0 7 1 7
(7, 1) True
```

> ⚠️ **Watch out:** `to_bytes` raises OverflowError when the value does not fit in the requested length.

#### Practice 3.2.9

**3.2.9-Q1** · `BASIC`

```python
print((8).bit_length(), (7).bit_length(), (0).bit_length())
```

**3.2.9-Q2** · `MID`

```python
print((255).bit_count(), (1023).bit_count(), (-7).bit_count())
```

**3.2.9-Q3** · `MID`

```python
print((1).to_bytes(2, 'big'), (1).to_bytes(2, 'little'))
```

**3.2.9-Q4** · `HARD`

```python
print(int.from_bytes(b'\xff\xff', 'big'), int.from_bytes(b'\xff\xff', 'big', signed=True))
```

**3.2.9-Q5** · `TRAP`

```python
print((256).to_bytes(1, 'big'))
```

### 3.2.10 Built-in numeric functions: abs, round, divmod, pow, sum, min, max

A small group of built-ins handles most integer work. `abs` removes the sign. `round(n)` on an int returns it unchanged and `round(n, -k)` rounds to tens, hundreds. `sum` adds an iterable (optional start value). `min` and `max` accept an iterable OR several arguments and a `key=` function. `sum(bools)` counts True values.

> **Key rule:** sum(iterable, start=0), min/max(iterable, key=, default=) are the workhorse reducers.

**Example 3.2.10.1: abs, round with negative digits**

```python
print(abs(-7), abs(7), abs(-0))
print(round(1234, -1), round(1250, -2), round(1350, -2), round(5))
```

*Output:*

```text
7 7 0
1230 1200 1400 5
```

**Example 3.2.10.2: sum, min, max**

```python
nums = [4, 9, 1, 7]
print(sum(nums), min(nums), max(nums), sum(nums, 100))
print(max(3, 9, 2), min("b", "a"))
print(max(nums, key=lambda n: -n), max([], default="empty"))
```

*Output:*

```text
21 1 9 121
9 a
1 empty
```

**Example 3.2.10.3: Counting with sum**

```python
data = [3, 8, 10, 15, 22]
print(sum(1 for d in data if d % 2 == 0))
print(sum(d % 2 == 0 for d in data))
print(sum([True, True, False]))
```

*Output:*

```text
3
3
2
```

> ⚠️ **Watch out:** `max([])` raises ValueError unless you pass `default=`.

#### Practice 3.2.10

**3.2.10-Q1** · `BASIC`

```python
print(abs(-3), min(4, 2, 8), max(4, 2, 8))
```

**3.2.10-Q2** · `BASIC`

```python
print(sum([1, 2, 3, 4]), sum([1, 2, 3, 4], 10))
```

**3.2.10-Q3** · `MID`

```python
print(round(1234, -2), round(1250, -2), round(1350, -2))
```

**3.2.10-Q4** · `HARD`

```python
print(max([3, -7, 5], key=abs), min([3, -7, 5], key=abs))
```

**3.2.10-Q5** · `TRAP`

```python
print(max([]))
```

### 3.2.11 math functions for integers

The `math` module adds exact integer tools: `gcd`, `lcm`, `isqrt` (exact integer square root), `factorial`, `comb` (n choose k), `perm`, and `prod`. All of them accept and return ints, so there is no floating-point error.

> **Key rule:** use isqrt, not int(n ** 0.5), for exact square roots of large integers.

**Integer-friendly math functions**

| Function | Returns | Example |
|---|---|---|
| `math.gcd(a, b, ...)` | greatest common divisor | `gcd(12, 18)` -> 6 |
| `math.lcm(a, b, ...)` | least common multiple (3.9+) | `lcm(4, 6)` -> 12 |
| `math.isqrt(n)` | floor of the square root | `isqrt(17)` -> 4 |
| `math.factorial(n)` | n! | `factorial(5)` -> 120 |
| `math.comb(n, k)` | n choose k | `comb(5, 2)` -> 10 |
| `math.perm(n, k)` | ordered arrangements | `perm(5, 2)` -> 20 |
| `math.prod(it)` | product of items | `prod([2,3,4])` -> 24 |

**Example 3.2.11.1: The family in action**

```python
import math
print(math.gcd(12, 18), math.lcm(4, 6), math.isqrt(17), math.factorial(5))
print(math.comb(5, 2), math.perm(5, 2), math.prod([2, 3, 4]))
print(math.gcd(12, 18, 30), math.gcd(0, 5), math.prod([]))
```

*Output:*

```text
6 12 4 120
10 20 24
6 5 1
```

**Example 3.2.11.2: isqrt is exact where ** 0.5 is not**

```python
import math
n = 10 ** 30 + 1
print(math.isqrt(n * n) == n, int((n * n) ** 0.5) == n)
```

*Output:*

```text
True False
```

#### Practice 3.2.11

**3.2.11-Q1** · `BASIC`

```python
import math; print(math.gcd(8, 12), math.factorial(4))
```

**3.2.11-Q2** · `MID`

```python
import math; print(math.lcm(6, 8), math.comb(6, 3))
```

**3.2.11-Q3** · `MID`

```python
import math; print(math.isqrt(99), math.isqrt(100), math.isqrt(101))
```

**3.2.11-Q4** · `HARD`

```python
import math; print(math.gcd(0, 0), math.factorial(0), math.comb(3, 5))
```

**3.2.11-Q5** · `TRAP`

```python
import math; print(math.factorial(-1))
```

### 3.2.12 Comparing ints and other numbers; chained comparison

Numeric types compare by VALUE across types: `1 == 1.0 == True` is True. Comparison operators (`< <= > >=` `== !=`) return bool and can be CHAINED: `1 < x < 10` means `1 < x and x < 10` with x evaluated once. Hash values agree for equal numbers, so 1, 1.0 and True collide as dict keys.

> **Key rule:** equal numbers of different types are equal and hash alike; chain comparisons instead of using `and`.

**Example 3.2.12.1: Cross-type equality**

```python
print(1 == 1.0, 1 == True, 1.0 == True, 2 == 2.0000000001)
print(hash(1) == hash(1.0) == hash(True))
print({1: "a", 1.0: "b", True: "c"})
```

*Output:*

```text
True True True False
True
{1: 'c'}
```

**Example 3.2.12.2: Chained comparisons**

```python
x = 5
print(1 < x < 10, 1 < x < 3, 10 > x >= 5, 1 < x > 3)
print(1 == 1.0 < 2)
```

*Output:*

```text
True False True True
True
```

**Example 3.2.12.3: Sorting a mixed numeric list**

```python
print(sorted([3, 1.5, True, 2, 0.5]))
print(max(1, 1.0), max(1.0, 1))
```

*Output:*

```text
[0.5, True, 1.5, 2, 3]
1 1.0
```

#### Practice 3.2.12

**3.2.12-Q1** · `BASIC`

```python
print(3 == 3.0, 3 != 4, 3 < 3.5)
```

**3.2.12-Q2** · `BASIC`

```python
x = 7; print(0 < x < 10, 0 < x < 5)
```

**3.2.12-Q3** · `MID`

```python
print(True + True, True == 1, False == 0, True + 0.5)
```

**3.2.12-Q4** · `HARD`

```python
d = {}
d[1] = 'int'
d[1.0] = 'float'
d[True] = 'bool'
print(d, len(d))
```

**3.2.12-Q5** · `TRAP`

```python
print(1 < 2 < 3, 1 < 3 < 2, 3 > 2 > 1, 1 == 1 != 2)
```

### 3.2.13 Small-int caching and the 4300-digit string limit

CPython pre-creates the ints from -5 to 256, so those values are the same object every time. Beyond that range, equal ints may or may not be the same object. NEVER use `is` to compare numbers. Separately, since Python 3.11 converting an int with more than 4300 digits to or from a decimal string raises ValueError, to stop denial-of-service attacks; `sys.set_int_max_str_digits` changes the limit.

> **Key rule:** compare numbers with ==, never `is`; the digit limit applies only to decimal-style string conversion.

**Example 3.2.13.1: Cached range**

```python
a = 256; b = 256
c = int("257"); d = int("257")
print(a is b, c is d, c == d)
```

*Output:*

```text
True False True
```

**Example 3.2.13.2: The digit limit**

```python
import sys
print(sys.get_int_max_str_digits())
big = 10 ** 5000
try:
    str(big)
except ValueError as e:
    print("ValueError")
print(len(hex(big)))
```

*Output:*

```text
4300
ValueError
4155
```

**Example 3.2.13.3: Raising the limit**

```python
import sys
sys.set_int_max_str_digits(0)
print(len(str(10 ** 5000)))
```

*Output:*

```text
5001
```

#### Practice 3.2.13

**3.2.13-Q1** · `BASIC`

```python
a = 100; b = 100; print(a == b, a is b)
```

**3.2.13-Q2** · `MID`

```python
print(int('1000') == int('1000'))
```

**3.2.13-Q3** · `HARD`

```python
print(len(str(2 ** 4000)))
```

**3.2.13-Q4** · `TRAP`

```python
print(len(str(2 ** 20000)))
```

### 3.2.14 Common int pitfalls

Most int bugs come from five habits: expecting `/` to return an int, converting user input without validation, using `is` for numbers, indexing with a float, and forgetting that bool is an int. This topic collects them in one place.

**Pitfall checklist**

| Mistake | What happens | Fix |
|---|---|---|
| `n / 2` used as an index | float, so IndexError/TypeError | use `n // 2` |
| `int(input())` on bad text | ValueError | wrap in try/except |
| `x is 1000` | unreliable True/False | use `==` |
| `l[2.0]` | TypeError: indices must be integers | `l[int(2.0)]` |
| `sum` over mixed bool/int | True counted as 1 | filter by `type(v) is int` |
| `round(2.5)` | 2 (banker's rounding) | see float chapter |

**Example 3.2.14.1: The index mistake**

```python
items = ["a", "b", "c", "d"]
mid = len(items) / 2
print(mid)
try:
    items[mid]
except TypeError as e:
    print(e)
print(items[len(items) // 2])
```

*Output:*

```text
2.0
list indices must be integers or slices, not float
c
```

**Example 3.2.14.2: Safe parsing**

```python
def to_int(text):
    try:
        return int(text)
    except ValueError:
        return None
print(to_int("12"), to_int("12.5"), to_int("abc"), to_int(""))
```

*Output:*

```text
12 None None None
```

#### Practice 3.2.14

**3.2.14-Q1** · `BASIC`

```python
print(7 / 2, 7 // 2)
```

**3.2.14-Q2** · `MID`

```python
print(round(0.5), round(1.5), round(2.5), round(3.5))
```

**3.2.14-Q3** · `MID`

```python
print([10, 20, 30][1])
```

**3.2.14-Q4** · `HARD`

```python
print(sum([True, 2, 3.5, False]))
```

**3.2.14-Q5** · `TRAP`

```python
print([10, 20, 30][4 / 2])
```

---

## Section 3.3 float: Floating-Point Numbers

### 3.3.1 Float literals and scientific notation

A float is a 64-bit IEEE 754 double: about 15 to 17 significant decimal digits, a range up to about 1.8e308. Write them with a decimal point (`3.14`, `.5`, `5.`), with an exponent (`1e3`, `2.5E-4`), or with underscores (`1_000.5`). `float` is the type of `/` results and of `math` functions.

> **Key rule:** a float is an approximation stored in binary; an int is exact.

**Example 3.3.1.1: Spellings of float literals**

```python
print(3.14, .5, 5., 1e3, 2.5E-4, 1_000.5)
print(type(5.), type(1e3), type(1e3) is float)
```

*Output:*

```text
3.14 0.5 5.0 1000.0 0.00025 1000.5
<class 'float'> <class 'float'> True
```

**Example 3.3.1.2: Display switches to scientific notation at the extremes**

```python
print(1e15, 1e16, 1e-4, 1e-5)
print(123456789012345678.0, 0.000123)
```

*Output:*

```text
1000000000000000.0 1e+16 0.0001 1e-05
1.2345678901234568e+17 0.000123
```

**Example 3.3.1.3: Mixing int and float always gives float**

```python
print(1 + 2.0, 3 * 1.0, 2 ** 2.0, 10 // 3.0, 10 % 3.0)
```

*Output:*

```text
3.0 3.0 4.0 3.0 1.0
```

#### Practice 3.3.1

**3.3.1-Q1** · `BASIC`

```python
print(1.5 + 2, 3 * 1.0, type(2 * 1.5))
```

**3.3.1-Q2** · `BASIC`

```python
print(1e2, 1e-2, 5e0)
```

**3.3.1-Q3** · `MID`

```python
print(1e16, 1e15, 1e-5)
```

**3.3.1-Q4** · `HARD`

```python
print(10 // 3.0, 10 % 3.0, -10 // 3.0, 2 ** 0.5 > 1.41)
```

**3.3.1-Q5** · `TRAP`

```python
print(type(10 / 2), type(2 ** 3), type(2 ** 3.0), type(-2 ** 0.5))
```

### 3.3.2 Binary representation and precision

Computers store floats in binary. Most decimal fractions (0.1, 0.2, 0.3) have NO finite binary form, exactly like 1/3 has no finite decimal form, so the stored value is the nearest representable number. This is not a Python bug; every language shows it.

> **Key rule:** never compare computed floats with ==; 0.1 + 0.2 != 0.3.

**Example 3.3.2.1: The classic**

```python
print(0.1 + 0.2)
print(0.1 + 0.2 == 0.3)
print(0.1 + 0.2 - 0.3)
```

*Output:*

```text
0.30000000000000004
False
5.551115123125783e-17
```

**Example 3.3.2.2: What is really stored**

```python
from decimal import Decimal
print(Decimal(0.1))
print(Decimal(0.5))
print(f"{0.1:.20f}")
```

*Output:*

```text
0.1000000000000000055511151231257827021181583404541015625
0.5
0.10000000000000000555
```

**Example 3.3.2.3: Errors accumulate**

```python
total = 0.0
for _ in range(10):
    total += 0.1
print(total, total == 1.0)
print(sum([0.1] * 10), round(total, 10) == 1.0)
```

*Output:*

```text
0.9999999999999999 False
1.0 True
```

> ⚠️ **Watch out:** Powers of two (0.5, 0.25, 0.125) ARE exact; 0.1, 0.2, 0.3 are not.

#### Practice 3.3.2

**3.3.2-Q1** · `BASIC`

```python
print(0.5 + 0.25, 0.5 + 0.25 == 0.75)
```

**3.3.2-Q2** · `BASIC`

```python
print(0.1 + 0.1 == 0.2, 0.1 + 0.2 == 0.3)
```

**3.3.2-Q3** · `MID`

```python
print(0.1 * 3, 0.1 * 3 == 0.3)
```

**3.3.2-Q4** · `HARD`

```python
print(sum([0.1] * 10) == 1.0, 1.1 + 2.2, 3.3 == 1.1 + 2.2)
```

**3.3.2-Q5** · `TRAP`

```python
print(1e16 + 1 == 1e16, 2 ** 53 + 1 == float(2 ** 53 + 1))
```

### 3.3.3 The float() constructor, inf and nan

`float(x)` accepts ints, numeric strings (with whitespace, exponent and sign), and the special strings 'inf', '-inf', 'infinity' and 'nan' in any letter case. Invalid text raises ValueError. Python has no float literal for infinity or nan; create them with `float('inf')`, `math.inf`, `math.nan`.

> **Key rule:** float('inf') and float('nan') are the only ways to build the special values from text.

**Example 3.3.3.1: Valid conversions**

```python
print(float(3), float("3.5"), float(" 2e3 "), float("-0"), float("1_0.5"))
print(float("inf"), float("-Infinity"), float("NaN"))
```

*Output:*

```text
3.0 3.5 2000.0 -0.0 10.5
inf -inf nan
```

**Example 3.3.3.2: Invalid text**

```python
for s in ["", "1,5", "ten", "1.2.3"]:
    try:
        float(s)
    except ValueError as e:
        print(repr(s), "->", e)
```

*Output:*

```text
'' -> could not convert string to float: ''
'1,5' -> could not convert string to float: '1,5'
'ten' -> could not convert string to float: 'ten'
'1.2.3' -> could not convert string to float: '1.2.3'
```

**Example 3.3.3.3: math constants**

```python
import math
print(math.inf, -math.inf, math.nan, math.pi, math.e, math.tau)
```

*Output:*

```text
inf -inf nan 3.141592653589793 2.718281828459045 6.283185307179586
```

#### Practice 3.3.3

**3.3.3-Q1** · `BASIC`

```python
print(float(7), float('2.5'), float('1e2'))
```

**3.3.3-Q2** · `MID`

```python
print(float('  3.5\n'), float('+1'), float('-.5'))
```

**3.3.3-Q3** · `MID`

```python
print(float('INF'), float('-inf'), float('nan'))
```

**3.3.3-Q4** · `HARD`

```python
print(float(10 ** 400))
```

**3.3.3-Q5** · `TRAP`

```python
print(float('1,5'))
```

### 3.3.4 inf and nan behaviour

Infinity behaves like a very large number: `inf + 1 == inf`, `inf > everything`. NaN means 'not a number' and is UNORDERED: it is not equal to anything, INCLUDING ITSELF, and every ordering comparison with it is False. Test with `math.isnan` / `math.isinf` / `math.isfinite`, never with ==.

> **Key rule:** nan != nan. Use math.isnan(x). inf - inf and 0 \* inf produce nan.

**Example 3.3.4.1: Infinity arithmetic**

```python
inf = float("inf")
print(inf + 1, inf * 2, -inf, inf > 10 ** 100)
print(inf - inf, 0 * inf, inf / inf, 1 / inf)
```

*Output:*

```text
inf inf -inf True
nan nan nan 0.0
```

**Example 3.3.4.2: NaN is not equal to itself**

```python
nan = float("nan")
print(nan == nan, nan != nan, nan < 1, nan > 1)
print(nan in [nan], any(x is nan for x in [nan]))
```

*Output:*

```text
False True False False
True True
```

**Example 3.3.4.3: The right tests**

```python
import math
vals = [1.0, float("inf"), float("nan")]
for v in vals:
    print(v, math.isfinite(v), math.isinf(v), math.isnan(v))
```

*Output:*

```text
1.0 True False False
inf False True False
nan False False True
```

**Example 3.3.4.4: Division by zero is an exception, not inf**

```python
try:
    1 / 0.0
except ZeroDivisionError as e:
    print(e)
print(1e308 * 10)
```

*Output:*

```text
float division by zero
inf
```

> ⚠️ **Watch out:** `x in [nan]` is True only because Python checks identity first. A different nan object is not found.

#### Practice 3.3.4

**3.3.4-Q1** · `BASIC`

```python
inf = float('inf'); print(inf > 1e308, -inf < 0)
```

**3.3.4-Q2** · `MID`

```python
nan = float('nan'); print(nan == nan, nan != nan)
```

**3.3.4-Q3** · `MID`

```python
inf = float('inf'); print(inf + inf, inf - inf)
```

**3.3.4-Q4** · `HARD`

```python
print(max(1, float('nan')), max(float('nan'), 1))
```

**3.3.4-Q5** · `TRAP`

```python
print(1 / 0.0)
```

### 3.3.5 Comparing floats safely: math.isclose

To test 'are these numbers equal for practical purposes' use `math.isclose(a, b, rel_tol=1e-09,` `abs_tol=0.0)`. The relative tolerance scales with the size of the numbers; the absolute tolerance is needed when comparing against 0. Another choice is `abs(a - b) < eps` with a tolerance you choose.

> **Key rule:** rel_tol handles large numbers; abs_tol is required when one value is 0.

**Example 3.3.5.1: isclose rescues 0.1 + 0.2**

```python
import math
print(0.1 + 0.2 == 0.3, math.isclose(0.1 + 0.2, 0.3))
```

*Output:*

```text
False True
```

**Example 3.3.5.2: Comparing with zero needs abs_tol**

```python
import math
tiny = 1e-12
print(math.isclose(tiny, 0), math.isclose(tiny, 0, abs_tol=1e-9))
```

*Output:*

```text
False True
```

**Example 3.3.5.3: Choosing tolerances**

```python
import math
print(math.isclose(1e10, 1e10 + 1))
print(math.isclose(1e10, 1e10 + 1, rel_tol=1e-12))
print(math.isclose(100.0, 101.0, rel_tol=0.02))
```

*Output:*

```text
True
False
True
```

#### Practice 3.3.5

**3.3.5-Q1** · `BASIC`

```python
import math; print(math.isclose(0.1 * 3, 0.3))
```

**3.3.5-Q2** · `MID`

```python
import math; print(math.isclose(1e-10, 0.0))
```

**3.3.5-Q3** · `MID`

```python
import math; print(math.isclose(1e-10, 0.0, abs_tol=1e-9))
```

**3.3.5-Q4** · `HARD`

```python
import math; print(math.isclose(100, 101, rel_tol=0.01), math.isclose(100, 101, rel_tol=0.011))
```

**3.3.5-Q5** · `TRAP`

```python
import math; nan = float('nan'); print(math.isclose(nan, nan), math.isclose(float('inf'), float('inf')))
```

### 3.3.6 Rounding: round, floor, ceil, trunc, int

Python offers several ways to turn a float into a whole number, and they disagree on negatives and halves. `round(x)` uses ROUND-HALF-TO-EVEN ('banker's rounding') and returns an int; `round(x, n)` keeps n decimals and returns a float. `math.floor` goes down, `math.ceil` goes up, `math.trunc` and `int()` cut toward zero.

> **Key rule:** round(2.5) == 2 and round(3.5) == 4; floor goes down, ceil goes up, trunc goes toward zero.

**The five tools on the same inputs**

| x | round(x) | floor | ceil | trunc / int |
|---|---|---|---|---|
| 2.5 | 2 | 2 | 3 | 2 |
| 3.5 | 4 | 3 | 4 | 3 |
| -2.5 | -2 | -3 | -2 | -2 |
| 2.7 | 3 | 2 | 3 | 2 |
| -2.7 | -3 | -3 | -2 | -2 |

**Example 3.3.6.1: All five on the table's inputs**

```python
import math
for x in (2.5, 3.5, -2.5, 2.7, -2.7):
    print(x, round(x), math.floor(x), math.ceil(x), math.trunc(x), int(x))
```

*Output:*

```text
2.5 2 2 3 2 2
3.5 4 3 4 3 3
-2.5 -2 -3 -2 -2 -2
2.7 3 2 3 2 2
-2.7 -3 -3 -2 -2 -2
```

**Example 3.3.6.2: round with digits works on the stored value**

```python
print(round(2.675, 2), round(1.005, 2), round(0.125, 2), round(0.375, 2))
print(round(1234.5678, -2), round(1234.5678, 1), type(round(1.5)), type(round(1.5, 0)))
```

*Output:*

```text
2.67 1.0 0.12 0.38
1200.0 1234.6 <class 'int'> <class 'float'>
```

**Example 3.3.6.3: Round half up when you need it**

```python
from decimal import Decimal, ROUND_HALF_UP
print(Decimal("2.675").quantize(Decimal("0.01"), rounding=ROUND_HALF_UP))
print(int(2.5 + 0.5), int(-2.5 - 0.5))
```

*Output:*

```text
2.68
3 -3
```

> ⚠️ **Watch out:** `round(2.675, 2)` gives 2.67 because the stored value is slightly below 2.675. This is not a rounding bug.

#### Practice 3.3.6

**3.3.6-Q1** · `BASIC`

```python
import math; print(round(4.6), math.floor(4.6), math.ceil(4.2))
```

**3.3.6-Q2** · `MID`

```python
print(round(0.5), round(1.5), round(2.5), round(-0.5))
```

**3.3.6-Q3** · `MID`

```python
import math; print(math.floor(-1.1), math.ceil(-1.9), math.trunc(-1.9))
```

**3.3.6-Q4** · `HARD`

```python
print(round(2.675, 2), round(2.665, 2), round(0.285, 2))
```

**3.3.6-Q5** · `TRAP`

```python
print(round(5.5), round(6.5), round(7.5), round(8.5))
```

### 3.3.7 float methods and attributes

A float has few methods, but each solves a real problem: `is_integer()` (does it have no fractional part), `as_integer_ratio()` (exact fraction), `hex()` and `float.fromhex()` (exact hexadecimal form), `conjugate()`, and `real` / `imag`.

**Every public float method and attribute**

| Name | Meaning | Example -> result |
|---|---|---|
| `is_integer()` | True if no fractional part | `2.0.is_integer()` -> True |
| `as_integer_ratio()` | exact (numerator, denominator) | `0.75.as_integer_ratio()` -> (3, 4) |
| `hex()` | exact hexadecimal string | `1.0.hex()` -> '0x1.0000000000000p+0' |
| `float.fromhex(s)` | inverse of hex() | `float.fromhex('0x1.8p+1')` -> 3.0 |
| `conjugate()` | returns itself | `2.5.conjugate()` -> 2.5 |
| `real`, `imag` | itself and 0.0 | `2.5.real, 2.5.imag` -> 2.5, 0.0 |

**Example 3.3.7.1: is_integer and as_integer_ratio**

```python
print((2.0).is_integer(), (2.5).is_integer(), (-0.0).is_integer())
print((0.75).as_integer_ratio(), (0.1).as_integer_ratio())
print((3.0).as_integer_ratio())
```

*Output:*

```text
True False True
(3, 4) (3602879701896397, 36028797018963968)
(3, 1)
```

**Example 3.3.7.2: hex and fromhex are exact**

```python
x = 0.1
h = x.hex()
print(h, float.fromhex(h) == x)
print((1.0).hex(), (255.5).hex())
```

*Output:*

```text
0x1.999999999999ap-4 True
0x1.0000000000000p+0 0x1.ff00000000000p+7
```

**Example 3.3.7.3: real, imag, conjugate**

```python
x = 2.5
print(x.real, x.imag, x.conjugate())
```

*Output:*

```text
2.5 0.0 2.5
```

#### Practice 3.3.7

**3.3.7-Q1** · `BASIC`

```python
print((4.0).is_integer(), (4.1).is_integer())
```

**3.3.7-Q2** · `MID`

```python
print((0.5).as_integer_ratio(), (0.125).as_integer_ratio())
```

**3.3.7-Q3** · `MID`

```python
print(float.fromhex('0x1.8p+1'), float.fromhex('0x1p-1'))
```

**3.3.7-Q4** · `HARD`

```python
x = 10 ** 16 + 1.0
print(x.is_integer(), x == 10 ** 16)
```

**3.3.7-Q5** · `TRAP`

```python
print((1e300 * 1e10).is_integer())
```

### 3.3.8 Limits: sys.float_info, overflow and underflow

`sys.float_info` reports the exact limits of this machine's float. The largest finite value is about 1.7976931348623157e308; anything bigger becomes `inf` in float arithmetic but raises OverflowError in some functions (`**`, `math.exp`). The smallest positive value is about 5e-324; smaller values underflow silently to 0.0.

> **Key rule:** float overflow gives inf (or OverflowError in ** and math.exp); underflow gives 0.0 silently.

**Example 3.3.8.1: The limits**

```python
import sys
fi = sys.float_info
print(fi.max)
print(fi.min)
print(fi.epsilon)
print(fi.dig, fi.mant_dig)
```

*Output:*

```text
1.7976931348623157e+308
2.2250738585072014e-308
2.220446049250313e-16
15 53
```

**Example 3.3.8.2: Overflow and underflow**

```python
print(1e308 * 10, -1e308 * 10)
print(5e-324, 5e-324 / 2, 1e-320)
try:
    10.0 ** 400
except OverflowError as e:
    print("OverflowError:", e)
```

*Output:*

```text
inf -inf
5e-324 0.0 1e-320
OverflowError: (34, 'Numerical result out of range')
```

**Example 3.3.8.3: Spacing between floats grows with size**

```python
import math
print(math.ulp(1.0), math.ulp(1e10), math.ulp(1e16))
print(math.nextafter(1.0, 2.0), math.nextafter(1.0, 0.0))
```

*Output:*

```text
2.220446049250313e-16 1.9073486328125e-06 2.0
1.0000000000000002 0.9999999999999999
```

#### Practice 3.3.8

**3.3.8-Q1** · `BASIC`

```python
import sys; print(sys.float_info.max > 1e308)
```

**3.3.8-Q2** · `MID`

```python
print(1e308 + 1e308, 1e-324)
```

**3.3.8-Q3** · `MID`

```python
import sys; print(1.0 + sys.float_info.epsilon == 1.0, 1.0 + sys.float_info.epsilon / 2 == 1.0)
```

**3.3.8-Q4** · `HARD`

```python
import math; print(math.exp(710))
```

**3.3.8-Q5** · `TRAP`

```python
print(2.0 ** 1024)
```

### 3.3.9 Formatting floats for display

Formatting changes only the TEXT, never the stored value. In f-strings: `:.2f` fixed decimals, `:.3e` scientific, `:.3g` significant digits, `:%` percentage, `:,.2f` thousands separator, `:10.2f` width 10, `:+.1f` always show sign. `repr(float)` gives the shortest string that round-trips to the same value.

**Float format specs**

| Spec | Meaning | f'{1234.5678:spec}' |
|---|---|---|
| `.2f` | 2 decimals | 1234.57 |
| `.0f` | no decimals | 1235 |
| `,.2f` | thousands separator | 1,234.57 |
| `10.1f` | width 10, 1 decimal | ' 1234.6' |
| `<10.1f` | left aligned | '1234.6 ' |
| `+.1f` | force sign | +1234.6 |
| `.3e` | scientific | 1.235e+03 |
| `.3g` | 3 significant | 1.23e+03 |
| `.1%` | percent | 123456.8% |

**Example 3.3.9.1: The common specs**

```python
x = 1234.5678
print(f"{x:.2f} {x:.0f} {x:,.2f} {x:.3e} {x:.3g} {x:+.1f}")
print(f"[{x:12.1f}] [{x:<12.1f}] [{x:^12.1f}] [{x:012.1f}]")
print(f"{0.256:.1%} {0.5:.0%}")
```

*Output:*

```text
1234.57 1235 1,234.57 1.235e+03 1.23e+03 +1234.6
[      1234.6] [1234.6      ] [   1234.6   ] [0000001234.6]
25.6% 50%
```

**Example 3.3.9.2: Formatting does not change the value**

```python
x = 0.1 + 0.2
print(x, f"{x:.2f}", x == 0.3, float(f"{x:.2f}") == 0.3)
print(repr(0.1), str(0.1), f"{0.1:.20f}")
```

*Output:*

```text
0.30000000000000004 0.30 False True
0.1 0.1 0.10000000000000000555
```

**Example 3.3.9.3: format() and % styles**

```python
x = 3.14159
print(format(x, ".3f"), "%.2f" % x, "%8.3f|" % x, "{:.1f}".format(x))
```

*Output:*

```text
3.142 3.14    3.142| 3.1
```

#### Practice 3.3.9

**3.3.9-Q1** · `BASIC`

```python
print(f'{3.14159:.2f}', f'{2:.1f}')
```

**3.3.9-Q2** · `MID`

```python
print(f'{1234567.891:,.1f}', f'{0.05:.0%}')
```

**3.3.9-Q3** · `MID`

```python
print(f'{5.5:6.2f}|', f'{5.5:<6.2f}|', f'{5.5:06.2f}')
```

**3.3.9-Q4** · `HARD`

```python
print(f'{1e-7}', f'{1e-7:f}', f'{123456789.0:e}')
```

**3.3.9-Q5** · `TRAP`

```python
print(f'{2.5:.0f}', f'{3.5:.0f}', f'{0.5:.0f}', f'{1.5:.0f}')
```

### 3.3.10 The math module for floats

`math` offers the standard functions: powers and roots (`sqrt`, `cbrt` 3.11+, `pow`, `exp`, `log`, `log2`, `log10`, `hypot`), trigonometry in RADIANS (`sin`, `cos`, `tan`, `asin`, `acos`, `atan`, `atan2`, `degrees`, `radians`), and summing (`fsum`, which avoids accumulated error).

**Most-used math functions**

| Function | Does | Example |
|---|---|---|
| `sqrt(x)` | square root (x >= 0) | `sqrt(16)` -> 4.0 |
| `hypot(a, b)` | sqrt(a*a + b*b) | `hypot(3, 4)` -> 5.0 |
| `exp(x)`, `log(x)` | e**x and natural log | `log(math.e)` -> 1.0 |
| `log2`, `log10` | base 2 and 10 | `log10(1000)` -> 3.0 |
| `radians`, `degrees` | convert angle units | `degrees(pi)` -> 180.0 |
| `sin`, `cos`, `tan` | radians in | `cos(0)` -> 1.0 |
| `fsum(it)` | exact float sum | `fsum([0.1]*10)` -> 1.0 |
| `copysign(a, b)` | abs(a) with sign of b | `copysign(3, -0.0)` -> -3.0 |

**Example 3.3.10.1: Everyday functions**

```python
import math
print(math.sqrt(16), math.hypot(3, 4), math.log10(1000), math.log2(8))
print(math.exp(0), math.log(math.e), math.degrees(math.pi), math.radians(180))
print(round(math.sin(math.pi / 2), 5), round(math.cos(math.pi), 5))
```

*Output:*

```text
4.0 5.0 3.0 3.0
1.0 1.0 180.0 3.141592653589793
1.0 -1.0
```

**Example 3.3.10.2: fsum versus sum**

```python
import math
vals = [0.1] * 10
print(sum(vals), math.fsum(vals))
```

*Output:*

```text
1.0 1.0
```

**Example 3.3.10.3: Domain errors**

```python
import math
for f, a in [(math.sqrt, -1), (math.log, 0), (math.acos, 2)]:
    try:
        f(a)
    except ValueError as e:
        print(f.__name__, "->", e)
```

*Output:*

```text
sqrt -> math domain error
log -> math domain error
acos -> math domain error
```

#### Practice 3.3.10

**3.3.10-Q1** · `BASIC`

```python
import math; print(math.sqrt(81), math.hypot(5, 12))
```

**3.3.10-Q2** · `MID`

```python
import math; print(math.log(1), math.log10(100), math.log(8, 2))
```

**3.3.10-Q3** · `MID`

```python
import math; print(round(math.sin(math.radians(30)), 6), math.degrees(math.atan2(1, 1)))
```

**3.3.10-Q4** · `HARD`

```python
import math; print(sum([0.1] * 10) == 1.0, math.fsum([0.1] * 10) == 1.0)
```

**3.3.10-Q5** · `TRAP`

```python
import math; print(math.sqrt(-4))
```

### 3.3.11 The decimal module: exact decimal arithmetic

`decimal.Decimal` stores numbers in base 10, so 0.1 really is 0.1. Use it for money and anything that must match hand arithmetic. ALWAYS build Decimals from STRINGS or ints, not from floats, or you copy the float error. Precision and rounding are controlled with the context (`getcontext().prec`) and `quantize`.

> **Key rule:** Decimal('0.1') + Decimal('0.2') == Decimal('0.3'); Decimal(0.1) copies the float's error.

**Example 3.3.11.1: Exact where float is not**

```python
from decimal import Decimal
print(0.1 + 0.2, Decimal("0.1") + Decimal("0.2"))
print(Decimal("0.1") + Decimal("0.2") == Decimal("0.3"))
print(Decimal(0.1))
```

*Output:*

```text
0.30000000000000004 0.3
True
0.1000000000000000055511151231257827021181583404541015625
```

**Example 3.3.11.2: Quantize and rounding modes**

```python
from decimal import Decimal, ROUND_HALF_UP, ROUND_HALF_EVEN, ROUND_DOWN
x = Decimal("2.675")
print(x.quantize(Decimal("0.01"), rounding=ROUND_HALF_UP))
print(x.quantize(Decimal("0.01"), rounding=ROUND_HALF_EVEN))
print(x.quantize(Decimal("0.01"), rounding=ROUND_DOWN))
```

*Output:*

```text
2.68
2.68
2.67
```

**Example 3.3.11.3: Context precision**

```python
from decimal import Decimal, getcontext
getcontext().prec = 6
print(Decimal(1) / Decimal(7))
getcontext().prec = 28
print(Decimal(1) / Decimal(7))
```

*Output:*

```text
0.142857
0.1428571428571428571428571429
```

**Example 3.3.11.4: Money total**

```python
from decimal import Decimal
prices = ["19.99", "5.01", "0.10"]
print(sum(Decimal(p) for p in prices), sum(float(p) for p in prices))
```

*Output:*

```text
25.10 25.099999999999998
```

> ⚠️ **Watch out:** Mixing Decimal with float in arithmetic raises TypeError; convert explicitly.

#### Practice 3.3.11

**3.3.11-Q1** · `BASIC`

```python
from decimal import Decimal; print(Decimal('1.1') + Decimal('2.2'))
```

**3.3.11-Q2** · `MID`

```python
from decimal import Decimal; print(Decimal('1.10') + Decimal('2.20'), Decimal('1.10') == Decimal('1.1'))
```

**3.3.11-Q3** · `MID`

```python
from decimal import Decimal; print(Decimal('10') / Decimal('4'), Decimal('10') // Decimal('4'))
```

**3.3.11-Q4** · `HARD`

```python
from decimal import Decimal; print(Decimal(0.5), Decimal(0.1) == Decimal('0.1'))
```

**3.3.11-Q5** · `TRAP`

```python
from decimal import Decimal; print(Decimal('1.5') + 1.5)
```

### 3.3.12 The fractions module: exact rationals

`fractions.Fraction` stores a numerator and a denominator as ints, always in lowest terms, so arithmetic is exact. Build from two ints, from a string like '3/4' or '0.75', or from a float (copying its error) / Decimal. `limit_denominator(n)` finds the closest simple fraction.

> **Key rule:** Fraction arithmetic never loses precision; Fraction(0.1) copies float error, Fraction('0.1') does not.

**Example 3.3.12.1: Exact arithmetic**

```python
from fractions import Fraction
a, b = Fraction(1, 3), Fraction(1, 6)
print(a + b, a * b, a / b, a - b, a ** 2)
print(Fraction(6, 8), Fraction("0.75"), Fraction(3))
```

*Output:*

```text
1/2 1/18 2 1/6 1/9
3/4 3/4 3
```

**Example 3.3.12.2: From floats**

```python
from fractions import Fraction
print(Fraction(0.1))
print(Fraction("0.1"))
print(Fraction(0.1).limit_denominator(100))
print(Fraction(3.14159).limit_denominator(100))
```

*Output:*

```text
3602879701896397/36028797018963968
1/10
1/10
311/99
```

**Example 3.3.12.3: Attributes and conversion**

```python
from fractions import Fraction
f = Fraction(7, 4)
print(f.numerator, f.denominator, float(f), int(f), f.as_integer_ratio())
print(f == 1.75, f < 2)
```

*Output:*

```text
7 4 1.75 1 (7, 4)
True True
```

#### Practice 3.3.12

**3.3.12-Q1** · `BASIC`

```python
from fractions import Fraction; print(Fraction(2, 4), Fraction(3, 1))
```

**3.3.12-Q2** · `MID`

```python
from fractions import Fraction; print(Fraction(1, 2) + Fraction(1, 3))
```

**3.3.12-Q3** · `MID`

```python
from fractions import Fraction; print(Fraction('1.25'), Fraction(1, 3) * 3)
```

**3.3.12-Q4** · `HARD`

```python
from fractions import Fraction; print(Fraction(1, 10) + Fraction(2, 10) == Fraction(3, 10))
```

**3.3.12-Q5** · `TRAP`

```python
from fractions import Fraction; print(Fraction(1, 0))
```

### 3.3.13 Common float pitfalls

Float trouble comes from a short list of causes: comparing with ==, adding numbers of very different size, subtracting nearly equal numbers (catastrophic cancellation), accumulating errors in loops, converting floats to int without thinking about truncation, and using float for money.

**Pitfall checklist**

| Pitfall | Example | Remedy |
|---|---|---|
| == on computed floats | `0.1+0.2 == 0.3` False | `math.isclose` |
| absorption | `1e16 + 1 == 1e16` | sum small first / `fsum` |
| cancellation | `(1 + 1e-16) - 1` is 0.0 | reformulate the formula |
| loop accumulation | adding 0.1 ten times | integer loop counter |
| float as loop counter | `while x != 1.0` | `while x < 1.0` or ints |
| money | `0.1 + 0.2` cents wrong | `Decimal` or integer cents |

**Example 3.3.13.1: A float loop that never hits the target**

```python
x = 0.0
steps = 0
while x != 1.0 and steps < 15:
    x += 0.1
    steps += 1
print(steps, x)
```

*Output:*

```text
15 1.5000000000000002
```

**Example 3.3.13.2: The same loop with an integer counter**

```python
vals = [i / 10 for i in range(11)]
print(vals[-1], vals[3], 3 / 10 == 0.3)
```

*Output:*

```text
1.0 0.3 True
```

**Example 3.3.13.3: Absorption and cancellation**

```python
print(1e16 + 1 - 1e16, 1 + 1e16 - 1e16)
print((1 + 1e-16) - 1, (1 + 2e-16) - 1)
```

*Output:*

```text
0.0 0.0
0.0 2.220446049250313e-16
```

#### Practice 3.3.13

**3.3.13-Q1** · `BASIC`

```python
print(0.1 + 0.7, 0.1 * 7)
```

**3.3.13-Q2** · `MID`

```python
print(1e16 + 1 - 1e16, 1e16 - 1e16 + 1)
```

**3.3.13-Q3** · `MID`

```python
print(round(0.1 + 0.2, 2) == 0.3)
```

**3.3.13-Q4** · `HARD`

```python
total = 0
for _ in range(3):
    total += 0.1
print(total, total == 0.3)
```

**3.3.13-Q5** · `TRAP`

```python
print(int(0.29 * 100), round(0.29 * 100), int(round(0.29 * 100)))
```

---

## Section 3.4 complex: Complex Numbers

### 3.4.1 Complex literals and attributes

A complex number has a real part and an imaginary part, both stored as floats. The imaginary unit is written `j` (not `i`) directly after a number: `3j`, `2+3j`. Build one with `complex(real, imag)`. The parts are `.real` and `.imag`; `.conjugate()` flips the sign of the imaginary part.

> **Key rule:** the suffix j makes an imaginary literal; `j` alone is just a name, so write `1j`.

**Example 3.4.1.1: Creating and inspecting**

```python
z = 2 + 3j
print(z, type(z), z.real, z.imag, z.conjugate())
print(complex(1, -1), complex("1+2j"), complex(5), 1j * 1j)
```

*Output:*

```text
(2+3j) <class 'complex'> 2.0 3.0 (2-3j)
(1-1j) (1+2j) (5+0j) (-1+0j)
```

**Example 3.4.1.2: abs is the magnitude**

```python
z = 3 + 4j
print(abs(z), z * z.conjugate(), (z * z.conjugate()).real == abs(z) ** 2)
```

*Output:*

```text
5.0 (25+0j) True
```

**Example 3.4.1.3: Parts are floats**

```python
z = 5j
print(z, z.real, z.imag, type(z.real))
print(complex("3+4j") == 3 + 4j)
```

*Output:*

```text
5j 0.0 5.0 <class 'float'>
True
```

> ⚠️ **Watch out:** `complex('1 + 2j')` with spaces inside raises ValueError; write '1+2j'.

#### Practice 3.4.1

**3.4.1-Q1** · `BASIC`

```python
z = 1 + 2j; print(z.real, z.imag)
```

**3.4.1-Q2** · `BASIC`

```python
print(abs(3 + 4j), (1 + 2j).conjugate())
```

**3.4.1-Q3** · `MID`

```python
print(1j ** 2, (1 + 1j) ** 2)
```

**3.4.1-Q4** · `HARD`

```python
print((1 + 2j) * (3 - 1j), (1 + 2j) / (1 - 1j))
```

**3.4.1-Q5** · `TRAP`

```python
print(complex('1 + 2j'))
```

### 3.4.2 Complex arithmetic, no ordering, and cmath

`+ - * / **` all work. Complex numbers have NO order: `<`, `>`, `<=`, `>=` raise TypeError, while `==` and `!=` work. `//` and `%` are not defined for complex. The `cmath` module provides `sqrt`, `exp`, `log`, `phase`, `polar`, `rect`, which handle negative inputs that `math` rejects.

> **Key rule:** complex supports == but not <; math.sqrt(-1) fails but cmath.sqrt(-1) returns 1j.

**Example 3.4.2.1: Arithmetic**

```python
a, b = 2 + 3j, 1 - 1j
print(a + b, a - b, a * b, a / b, a ** 2)
```

*Output:*

```text
(3+2j) (1+4j) (5+1j) (-0.5+2.5j) (-5+12j)
```

**Example 3.4.2.2: cmath handles negatives**

```python
import cmath
print(cmath.sqrt(-1), cmath.sqrt(-4), cmath.exp(1j * cmath.pi))
print(cmath.phase(1j), cmath.polar(1 + 1j), cmath.rect(1, cmath.pi / 2))
```

*Output:*

```text
1j 2j (-1+1.2246467991473532e-16j)
1.5707963267948966 (1.4142135623730951, 0.7853981633974483) (6.123233995736766e-17+1j)
```

**Example 3.4.2.3: Unsupported operations**

```python
z = 1 + 2j
for f in (lambda: z < 2, lambda: z // 2, lambda: z % 2):
    try:
        f()
    except TypeError as e:
        print(e)
print(z == 1 + 2j, z != 3)
```

*Output:*

```text
'<' not supported between instances of 'complex' and 'int'
unsupported operand type(s) for //: 'complex' and 'int'
unsupported operand type(s) for %: 'complex' and 'int'
True True
```

#### Practice 3.4.2

**3.4.2-Q1** · `BASIC`

```python
print((1 + 2j) + (3 + 4j), (1 + 2j) * 2)
```

**3.4.2-Q2** · `MID`

```python
import cmath; print(cmath.sqrt(-9), cmath.sqrt(9))
```

**3.4.2-Q3** · `MID`

```python
print((1 + 2j) == (1 + 2j), (1 + 0j) == 1)
```

**3.4.2-Q4** · `HARD`

```python
print((2j) ** 2, (2j) ** 0.5 == (2j) ** (1 / 2))
```

**3.4.2-Q5** · `TRAP`

```python
print(1 + 2j < 3 + 4j)
```

---

## Section 3.5 bool: Booleans

### 3.5.1 bool is a subclass of int

`bool` has exactly two instances, `True` and `False`, and it is a SUBCLASS of int: True behaves as 1 and False as 0 in arithmetic. They are singletons, created once. Comparison operators return bool.

> **Key rule:** True == 1, False == 0, and True + True == 2, but True is not 1.

**Example 3.5.1.1: Booleans are integers**

```python
print(True + True, True * 5, False - 1, True / 2)
print(isinstance(True, int), True == 1, int(True), int(False))
print(sum([True, False, True, True]))
```

*Output:*

```text
2 5 -1 0.5
True True 1 0
3
```

**Example 3.5.1.2: Indexing with a bool**

```python
names = ["off", "on"]
flag = True
print(names[flag], names[not flag], names[2 > 1])
```

*Output:*

```text
on off on
```

**Example 3.5.1.3: bool() and str()**

```python
print(bool(1), bool(0), str(True), repr(False), bool("False"))
print(True.__class__, bool.__bases__)
```

*Output:*

```text
True False True False True
<class 'bool'> (<class 'int'>,)
```

#### Practice 3.5.1

**3.5.1-Q1** · `BASIC`

```python
print(True + 1, False + 1, True * 3)
```

**3.5.1-Q2** · `BASIC`

```python
print(int(True), int(False), float(True))
```

**3.5.1-Q3** · `MID`

```python
print(sum([x > 2 for x in [1, 2, 3, 4, 5]]))
```

**3.5.1-Q4** · `HARD`

```python
print(True == 1, True is 1, isinstance(True, bool), type(True + 1))
```

**3.5.1-Q5** · `TRAP`

```python
print(['a', 'b'][True], {True: 'x', 1: 'y'}, str(True) + '!')
```

### 3.5.2 Boolean operators: and, or, not

`and`, `or` do NOT return booleans; they return one of their OPERANDS and SHORT-CIRCUIT. `x or y` returns x if x is truthy else y. `x and y` returns x if x is falsy else y. `not x` always returns a real bool. Precedence: `not` > `and` > `or`.

> **Key rule:** `a or b` = first truthy (or last); `a and b` = first falsy (or last); `not` always gives True/False.

**Example 3.5.2.1: Returning operands, not booleans**

```python
print(0 or 5, 3 or 5, "" or "default", [] or None)
print(0 and 5, 3 and 5, "x" and "y", None and 1)
print(not 0, not "a", not [], not not [1])
```

*Output:*

```text
5 3 default None
0 5 y None
True False True True
```

**Example 3.5.2.2: Short-circuit: the right side may never run**

```python
def noisy(tag):
    print("ran", tag)
    return tag
print(noisy(0) and noisy(1))
print(noisy(2) or noisy(3))
```

*Output:*

```text
ran 0
0
ran 2
2
```

**Example 3.5.2.3: Precedence**

```python
print(True or False and False)
print((True or False) and False)
print(not True or True, not (True or True))
```

*Output:*

```text
True
False
True False
```

#### Practice 3.5.2

**3.5.2-Q1** · `BASIC`

```python
print(True and False, True or False, not True)
```

**3.5.2-Q2** · `BASIC`

```python
print(0 or 'a', 1 and 'b', '' or 0)
```

**3.5.2-Q3** · `MID`

```python
print(1 or 1 / 0)
```

**3.5.2-Q4** · `HARD`

```python
print(not 1 == 2, not (1 == 2), 1 or 2 and 0, (1 or 2) and 0)
```

**3.5.2-Q5** · `TRAP`

```python
x = []
print(x and x[0], x or 'empty', len(x) > 0 and x[0])
```

### 3.5.3 Bitwise operators on bool, comparisons and any/all

`&`, `|`, `^` on two bools return a bool and do NOT short-circuit; `~True` is -2 (it is an int operation). Comparisons return bool. `any(iterable)` is True if at least one item is truthy; `all(iterable)` is True if every item is truthy. `all([])` is True and `any([])` is False.

> **Key rule:** use `not x`, never `~x`, to flip a bool; all([]) is True, any([]) is False.

**Example 3.5.3.1: Bitwise on bool**

```python
print(True & False, True | False, True ^ True, type(True & True))
print(~True, ~False, ~1 == -2)
```

*Output:*

```text
False True False <class 'bool'>
-2 -1 True
```

**Example 3.5.3.2: any and all**

```python
nums = [3, 5, 8]
print(any(n % 2 == 0 for n in nums), all(n % 2 == 1 for n in nums))
print(all([]), any([]), all([0]), any([0, "", None]))
```

*Output:*

```text
True False
True False False False
```

**Example 3.5.3.3: Chained comparison returns a single bool**

```python
x = 5
r = 1 < x < 10
print(r, type(r))
```

*Output:*

```text
True <class 'bool'>
```

#### Practice 3.5.3

**3.5.3-Q1** · `BASIC`

```python
print(any([0, 0, 1]), all([1, 1, 0]))
```

**3.5.3-Q2** · `MID`

```python
print(all([]), any([]), all([[]]), any([[]]))
```

**3.5.3-Q3** · `MID`

```python
print(True ^ True, True | False, True & 0)
```

**3.5.3-Q4** · `HARD`

```python
print(~True, ~False, not True)
```

**3.5.3-Q5** · `TRAP`

```python
print(all(x > 0 for x in []), any(x > 0 for x in []))
```

### 3.5.4 bool pitfalls

Four traps: testing with `== True` or `is True`, treating non-empty strings like 'False' as False, using `bool` as a counter by accident, and forgetting that `bool(x)` reads truthiness, not meaning. Prefer `if flag:` for real booleans and `is None` for missing values.

**Boolean pitfalls**

| Code | Problem | Better |
|---|---|---|
| `if x == True:` | False for x = 2 | `if x:` |
| `if x is True:` | False for x = 1 | `if x:` |
| `bool('False')` | True (non-empty string) | `s.lower() == 'true'` |
| `not x == y` | reads as `not (x == y)` | `x != y` |
| `if a == b or c:` | `c` is tested alone | `if a in (b, c):` |

**Example 3.5.4.1: == True is not the same as truthiness**

```python
for x in (1, 2, "yes", [0]):
    print(repr(x), bool(x), x == True)
```

*Output:*

```text
1 True True
2 True False
'yes' True False
[0] True False
```

**Example 3.5.4.2: Parsing a boolean from text**

```python
for text in ["True", "false", "0", "no", ""]:
    print(repr(text), bool(text), text.strip().lower() in ("true", "1", "yes"))
```

*Output:*

```text
'True' True True
'false' True False
'0' True False
'no' True False
'' False False
```

**Example 3.5.4.3: The or-trap**

```python
colour = "green"
print(colour == "red" or "blue")
print(colour in ("red", "blue"))
```

*Output:*

```text
blue
False
```

#### Practice 3.5.4

**3.5.4-Q1** · `BASIC`

```python
print(bool('0'), bool(0), bool('False'))
```

**3.5.4-Q2** · `MID`

```python
x = 2
print(x == True, bool(x))
```

**3.5.4-Q3** · `MID`

```python
c = 'green'
print(c == 'red' or 'blue')
```

**3.5.4-Q4** · `HARD`

```python
print(True == 1.0, True is 1.0, {True, 1, 1.0})
```

**3.5.4-Q5** · `TRAP`

```python
x = 'a'
print(x == 'a' or 'b' == x, x == ('a' or 'b'), x == ('b' or 'a'))
```

---

## Section 3.6 NoneType and Special Singletons

### 3.6.1 None: the absence of a value

`None` is the only instance of `NoneType`. It represents 'no value here'. Functions without a return statement return None. It is falsy, but it is NOT the same as 0, '' or False. There is exactly one None object, so test with `is None`.

> **Key rule:** test with `x is None` / `x is not None`; None is a singleton.

**Example 3.6.1.1: None everywhere**

```python
def nothing():
    pass
r = nothing()
print(r, type(r), r is None, bool(r))
print(print("x") is None)
```

*Output:*

```text
None <class 'NoneType'> True False
x
True
```

**Example 3.6.1.2: None is not zero, empty or False**

```python
print(None == 0, None == "", None == False, None is None)
print(None == None, not None, None is False)
```

*Output:*

```text
False False False True
True True False
```

**Example 3.6.1.3: Methods that return None**

```python
a = [3, 1, 2]
r = a.sort()
print(r, a)
b = a.append(9)
print(b, a)
```

*Output:*

```text
None [1, 2, 3]
None [1, 2, 3, 9]
```

> ⚠️ **Watch out:** `x = x.sort()` sets x to None. In-place methods return None by design.

#### Practice 3.6.1

**3.6.1-Q1** · `BASIC`

```python
print(None is None, None == 0, bool(None))
```

**3.6.1-Q2** · `MID`

```python
def f(x):
    if x > 0:
        return x
print(f(1), f(-1))
```

**3.6.1-Q3** · `MID`

```python
a = [2, 1]
b = a.reverse()
print(a, b)
```

**3.6.1-Q4** · `HARD`

```python
print(type(None), type(None)(), None is type(None)())
```

**3.6.1-Q5** · `TRAP`

```python
print(max(None, 1))
```

### 3.6.2 None as default and sentinel patterns

Use None to mean 'argument not supplied'. A mutable default (list, dict) is created ONCE at function definition and shared by every call; the cure is `def f(x=None): if x is None: x = []`. When None itself is a legal value, create a private sentinel with `object()`.

> **Key rule:** never write def f(x=[]); use None and create the list inside.

**Example 3.6.2.1: The shared-default bug**

```python
def add(x, bucket=[]):
    bucket.append(x)
    return bucket
print(add(1), add(2), add(3))
```

*Output:*

```text
[1, 2, 3] [1, 2, 3] [1, 2, 3]
```

**Example 3.6.2.2: The fix**

```python
def add(x, bucket=None):
    if bucket is None:
        bucket = []
    bucket.append(x)
    return bucket
print(add(1), add(2), add(3, [9]))
```

*Output:*

```text
[1] [2] [9, 3]
```

**Example 3.6.2.3: A sentinel when None is a valid value**

```python
MISSING = object()
def get(d, key, default=MISSING):
    if key in d:
        return d[key]
    if default is MISSING:
        raise KeyError(key)
    return default
d = {"a": None}
print(get(d, "a"), get(d, "b", None), get(d, "b", 0))
```

*Output:*

```text
None None 0
```

#### Practice 3.6.2

**3.6.2-Q1** · `BASIC`

```python
def f(x=None):
    return 'none' if x is None else x
print(f(), f(0), f(''))
```

**3.6.2-Q2** · `MID`

```python
def f(a, l=[]):
    l.append(a)
    return l
f(1); print(f(2))
```

**3.6.2-Q3** · `MID`

```python
def f(a, l=None):
    l = l or []
    l.append(a)
    return l
x = []
f(1, x); print(x)
```

**3.6.2-Q4** · `HARD`

```python
def f(x, t=[]):
    t = t + [x]
    return t
print(f(1), f(2))
```

**3.6.2-Q5** · `TRAP`

```python
def f(x=len([1, 2])):
    return x
print(f(), f(5))
```

### 3.6.3 Ellipsis, NotImplemented and slice objects

Three more built-in singletons and helpers appear in real code. `...` (Ellipsis) is a placeholder body and a multidimensional-slice marker. `NotImplemented` is returned (not raised) by operator methods to say 'I do not know how to do this with that type'. `slice(start, stop, step)` is the object behind `a[1:5:2]`.

**Special objects**

| Object | Type | Typical use |
|---|---|---|
| `None` | NoneType | no value, default argument |
| `...` / `Ellipsis` | ellipsis | placeholder body, NumPy slicing |
| `NotImplemented` | NotImplementedType | return from `__eq__`, `__add__` etc. |
| `slice(1, 5, 2)` | slice | reusable named slice |

**Example 3.6.3.1: Ellipsis**

```python
print(..., type(...), ... is Ellipsis, bool(...))
def todo():
    ...
print(todo())
```

*Output:*

```text
Ellipsis <class 'ellipsis'> True True
None
```

**Example 3.6.3.2: NotImplemented is returned, not raised**

```python
class Money:
    def __init__(self, v): self.v = v
    def __eq__(self, o):
        if not isinstance(o, Money):
            return NotImplemented
        return self.v == o.v
print(Money(1) == Money(1), Money(1) == 1, Money(1).__eq__(1))
```

*Output:*

```text
True False NotImplemented
```

**Example 3.6.3.3: slice objects**

```python
s = slice(1, 6, 2)
print(s, s.start, s.stop, s.step)
print("abcdefgh"[s], [0, 1, 2, 3, 4, 5, 6][s])
print(slice(None, 3).indices(10), slice(-3, None).indices(10))
```

*Output:*

```text
slice(1, 6, 2) 1 6 2
bdf [1, 3, 5]
(0, 3, 1) (7, 10, 1)
```

#### Practice 3.6.3

**3.6.3-Q1** · `BASIC`

```python
print(type(...).__name__, type(NotImplemented).__name__)
```

**3.6.3-Q2** · `MID`

```python
print('abcdef'[slice(0, 6, 2)], 'abcdef'[::2])
```

**3.6.3-Q3** · `MID`

```python
print(slice(None, None, -1), 'abc'[slice(None, None, -1)])
```

**3.6.3-Q4** · `HARD`

```python
print(slice(2, 100).indices(5), slice(-100, 2).indices(5))
```

**3.6.3-Q5** · `TRAP`

```python
print(bool(NotImplemented), 1 == NotImplemented)
```

---

## Section 3.7 str: Strings

### 3.7.1 Creating strings: quotes, triple quotes, concatenation

A str is an immutable sequence of Unicode characters. Create one with single quotes, double quotes, or triple quotes (which may span lines). The two single-line styles are identical; pick the one that avoids escaping. Adjacent literals are joined automatically, which helps split long text across lines. `str(x)` converts any object to its readable text.

> **Key rule:** 'a' and "a" are the same; triple quotes keep line breaks; there is no separate char type, a character is a str of length 1.

**Example 3.7.1.1: Quote styles**

```python
a = 'single'
b = "double"
c = "it's easy"
d = 'say "hi"'
print(a, b, c, d, sep=" | ")
print(type('x'), len('x'), 'x' == "x")
```

*Output:*

```text
single | double | it's easy | say "hi"
<class 'str'> 1 True
```

**Example 3.7.1.2: Triple-quoted and implicit joining**

```python
text = '''line one
line two'''
print(text)
print(len(text), text.count("\n"))
msg = ("part one, "
       "part two")
print(msg)
```

*Output:*

```text
line one
line two
17 1
part one, part two
```

**Example 3.7.1.3: str() on other types**

```python
print(str(42), str(3.5), str(True), str(None), str([1, 2]), str((1,)))
print(str(), len(str()), repr(str()))
```

*Output:*

```text
42 3.5 True None [1, 2] (1,)
 0 ''
```

#### Practice 3.7.1

**3.7.1-Q1** · `BASIC`

```python
print('a' 'b' 'c', 'ab' == "ab")
```

**3.7.1-Q2** · `BASIC`

```python
print(len('hello'), len(''), len(' '))
```

**3.7.1-Q3** · `MID`

```python
print(str(12) + str(3), str(1.0), str(-0.0))
```

**3.7.1-Q4** · `HARD`

```python
s = '''a
  b'''
print(len(s), s.split('\n'))
```

**3.7.1-Q5** · `TRAP`

```python
print('ab' 'cd' * 2, ('ab' 'cd') * 2, 'ab' + 'cd' * 2)
```

### 3.7.2 Escape sequences and raw strings

A backslash starts an escape sequence. `\n` newline, `\t` tab, `\\` backslash, `\'` and `\"` quotes, `\r` carriage return, `\0` NUL, `\xHH` hex byte-value character, `\uHHHH` and `\UHHHHHHHH` Unicode, `\N{NAME}` by name. A RAW string `r'...'` leaves backslashes untouched, which is ideal for Windows paths and regular expressions. A raw string cannot end with an odd number of backslashes.

> **Key rule:** r'...' keeps backslashes literally; use it for paths and regex patterns.

**Escape sequences**

| Escape | Meaning | Escape | Meaning |
|---|---|---|---|
| `\n` | newline | `\\` | backslash |
| `\t` | tab | `\' \"` | quotes |
| `\r` | carriage return | `\xe9` | char U+00E9 |
| `\b` | backspace | `\u20ac` | char U+20AC |
| `\0` | NUL char | `\N{BULLET}` | named char |

**Example 3.7.2.1: Common escapes**

```python
print("a\tb\nc")
print("quote: \" and \' and backslash: \\")
print(len("a\nb"), len("a\\nb"))
```

*Output:*

```text
a    b
c
quote: " and ' and backslash: \
3 4
```

**Example 3.7.2.2: Unicode escapes**

```python
print("\u00e9", "\xe9", "\N{GREEK SMALL LETTER ALPHA}", "\U0001F600")
print("\u00e9" == "é", len("\U0001F600"))
```

*Output:*

```text
é é α \x00
True 1
```

**Example 3.7.2.3: Raw strings**

```python
path = r"C:\new\table"
print("raw   :", path, len(path))
print("normal:", "C:\new\table")
print(r"\d+\.\d*", repr(r"a\nb"))
```

*Output:*

```text
raw   : C:\new\table 12
normal: C:
ew    able
\d+\.\d* 'a\\nb'
```

> ⚠️ **Watch out:** `r'C:\folder\'` is a SyntaxError (the last backslash escapes the quote). Write `r'C:\folder' +` `'\\'`.

#### Practice 3.7.2

**3.7.2-Q1** · `BASIC`

```python
print(len('a\nb'), len(r'a\nb'))
```

**3.7.2-Q2** · `MID`

```python
print('a\tb'.split('\t'), 'x\\y')
```

**3.7.2-Q3** · `MID`

```python
print(len('\u00e9'), len('e\u0301'), '\u00e9' == 'e\u0301')
```

**3.7.2-Q4** · `HARD`

```python
print(r'\n' == '\\n', repr('\n'), repr(r'\n'))
```

**3.7.2-Q5** · `TRAP`

```python
print(len(r'\\'), len('\\'), len(r'\''))
```

### 3.7.3 str versus repr, print and multi-line text

`str(x)` is the friendly text for people; `repr(x)` is the unambiguous text for programmers, usually valid code that rebuilds x. For strings, repr adds quotes and shows escapes. `print` uses str, the REPL and f-string `!r` use repr. `print(..., sep=, end=)` controls separators and the line ending.

> **Key rule:** print shows str(); the debugger and `!r` show repr(); in doubt, repr(x) reveals hidden spaces and newlines.

**Example 3.7.3.1: Same value, two views**

```python
s = "hi\n\tthere"
print(s)
print(repr(s), str(s) == s)
print(repr('it\'s'), repr("say \"x\""), repr('both \' and \"'))
```

*Output:*

```text
hi
    there
'hi\n\tthere' True
"it's" 'say "x"' 'both \' and "'
```

**Example 3.7.3.2: repr reveals the invisible**

```python
a = "yes"
b = "yes "
print(a == b, repr(a), repr(b))
print(f"{b!r} {b!s}|")
```

*Output:*

```text
False 'yes' 'yes '
'yes ' yes |
```

**Example 3.7.3.3: print options**

```python
print("a", "b", "c")
print("a", "b", "c", sep="-")
print("no newline", end="")
print(" ... continued")
print(1, 2, sep="\n")
```

*Output:*

```text
a b c
a-b-c
no newline ... continued
1
2
```

#### Practice 3.7.3

**3.7.3-Q1** · `BASIC`

```python
print(repr('a'), str('a'), repr(5), repr(5.0))
```

**3.7.3-Q2** · `MID`

```python
print(repr('a\tb'), len(repr('a\tb')))
```

**3.7.3-Q3** · `MID`

```python
print('x', 'y', sep='', end='!')
print()
```

**3.7.3-Q4** · `HARD`

```python
print(repr(repr('a')), str(str('a')))
```

**3.7.3-Q5** · `TRAP`

```python
print(str([1, 'a']), repr([1, 'a']), str(['a']) == repr(['a']))
```

### 3.7.4 Immutability and identity of strings

A string can never change in place. Every 'modifying' method (upper, replace, strip, +) returns a NEW string and leaves the original untouched, so you must assign the result. Assigning to an index or slice is a TypeError. CPython may reuse (intern) identical short literals, but you must not rely on `is` for strings.

> **Key rule:** s.upper() does nothing to s; write s = s.upper().

**Example 3.7.4.1: Methods return new strings**

```python
s = "python"
s.upper()
print(s)
t = s.upper()
print(s, t)
s = s.upper()
print(s)
```

*Output:*

```text
python
python PYTHON
PYTHON
```

**Example 3.7.4.2: Item assignment fails; rebuild instead**

```python
s = "cat"
try:
    s[0] = "b"
except TypeError as e:
    print(e)
s = "b" + s[1:]
print(s)
```

*Output:*

```text
'str' object does not support item assignment
bat
```

**Example 3.7.4.3: Equality versus identity**

```python
a = "".join(["he", "llo"])
b = "hello"
print(a == b, a is b)
print(id("x") == id("x"))
```

*Output:*

```text
True False
True
```

#### Practice 3.7.4

**3.7.4-Q1** · `BASIC`

```python
s = 'abc'
s.upper()
print(s)
```

**3.7.4-Q2** · `MID`

```python
s = 'abc'
t = s
s += 'd'
print(s, t)
```

**3.7.4-Q3** · `MID`

```python
s = 'abc'
print(s.replace('a', 'z'), s)
```

**3.7.4-Q4** · `HARD`

```python
s = 'abc'
s = s[:1] + 'X' + s[2:]
print(s)
```

**3.7.4-Q5** · `TRAP`

```python
s = 'abc'
del s[0]
```

### 3.7.5 Indexing: positive and negative

Characters are numbered from 0 on the left and from -1 on the right. `s[i]` returns a one-character string. An index outside `-len(s) .. len(s)-1` raises IndexError. There is no character type: `s[0]` is itself a str, so it supports all string methods.

> **Key rule:** s[0] is the first char, s[-1] the last; valid range is -len(s) to len(s) - 1.

**Index map for 'PYTHON'**

| char | P | Y | T | H | O | N |
|---|---|---|---|---|---|---|
| positive | 0 | 1 | 2 | 3 | 4 | 5 |
| negative | -6 | -5 | -4 | -3 | -2 | -1 |

**Example 3.7.5.1: Reading characters**

```python
s = "PYTHON"
print(s[0], s[3], s[-1], s[-3], s[len(s) - 1])
print(type(s[0]), s[0].lower())
```

*Output:*

```text
P H N H N
<class 'str'> p
```

**Example 3.7.5.2: Out of range**

```python
s = "abc"
for i in (3, -4, 0, -3):
    try:
        print(i, s[i])
    except IndexError as e:
        print(i, "->", e)
```

*Output:*

```text
3 -> string index out of range
-4 -> string index out of range
0 a
-3 a
```

**Example 3.7.5.3: First and last safely on empty strings**

```python
s = ""
print(s[:1], s[-1:], repr(s[:1]))
print(s[0] if s else "empty")
```

*Output:*

```text
  ''
empty
```

#### Practice 3.7.5

**3.7.5-Q1** · `BASIC`

```python
s = 'hello'
print(s[0], s[4], s[-1], s[-5])
```

**3.7.5-Q2** · `BASIC`

```python
print('abc'[1], 'abc'[-2])
```

**3.7.5-Q3** · `MID`

```python
s = 'abc'
print(s[len(s) // 2], s[-len(s)])
```

**3.7.5-Q4** · `HARD`

```python
s = ''
print(repr(s[:1]), repr(s[-1:]))
```

**3.7.5-Q5** · `TRAP`

```python
print('abc'[3])
```

### 3.7.6 Slicing in every form

`s[start:stop:step]` returns a new string. `start` is included, `stop` is EXCLUDED, `step` defaults to 1. Omitted start/stop mean 'from the beginning' / 'to the end' (reversed for negative step). Slices NEVER raise IndexError: out-of-range bounds are clipped. A negative step walks backwards, so `s[::-1]` reverses.

> **Key rule:** slices are half-open [start, stop) and never raise IndexError; s[::-1] reverses.

**Slice recipes (s = 'abcdefgh')**

| Expression | Result | Meaning |
|---|---|---|
| `s[2:5]` | 'cde' | index 2 up to 4 |
| `s[:3]` | 'abc' | first 3 |
| `s[3:]` | 'defgh' | from index 3 |
| `s[-3:]` | 'fgh' | last 3 |
| `s[:-3]` | 'abcde' | all but last 3 |
| `s[::2]` | 'aceg' | every 2nd |
| `s[1::2]` | 'bdfh' | odd positions |
| `s[::-1]` | 'hgfedcba' | reversed |
| `s[6:2:-1]` | 'gfed' | backwards |
| `s[:]` | 'abcdefgh' | full copy |
| `s[10:20]` | '' | clipped, no error |

**Example 3.7.6.1: All the recipes**

```python
s = "abcdefgh"
print(s[2:5], s[:3], s[3:], s[-3:], s[:-3])
print(s[::2], s[1::2], s[::-1], s[6:2:-1], s[:], s[10:20] == "")
```

*Output:*

```text
cde abc defgh fgh abcde
aceg bdfh hgfedcba gfed abcdefgh True
```

**Example 3.7.6.2: Negative step and bounds**

```python
s = "abcdefgh"
print(s[-1:-4:-1], s[5::-1], s[:2:-1], s[::-3])
print(s[2:2], s[5:2], repr(s[5:2]))
```

*Output:*

```text
hgf fedcba hgfed heb
  ''
```

**Example 3.7.6.3: Slice assignment idiom: rebuild with concatenation**

```python
s = "hello world"
print(s[:5] + "!" + s[5:])
print(s[:-5] + "there")
print(s[::-1].split()[::-1], " ".join(s.split()[::-1]))
```

*Output:*

```text
hello! world
hello there
['olleh', 'dlrow'] world hello
```

#### Practice 3.7.6

**3.7.6-Q1** · `BASIC`

```python
s = 'abcdef'
print(s[1:4], s[:2], s[4:])
```

**3.7.6-Q2** · `BASIC`

```python
s = 'abcdef'
print(s[-2:], s[::-1])
```

**3.7.6-Q3** · `MID`

```python
s = 'abcdef'
print(s[::2], s[1::2], s[::-2])
```

**3.7.6-Q4** · `HARD`

```python
s = 'abcdef'
print(s[4:1:-1], s[1:4:-1], s[-1:-4:-1], s[2:100])
```

**3.7.6-Q5** · `TRAP`

```python
s = 'abcdef'
print(s[:2] + s[2:] == s, s[-2:2], s[0:0] == s[5:5], s[::-1][::-1] == s)
```

### 3.7.7 Concatenation and repetition

`+` joins two strings (both must be str; mixing with int is a TypeError). `*` repeats a string n times (n <= 0 gives ''). `+=` rebinds the name to a new string. For many pieces prefer `''.join(parts)`, which builds the result once. `str.join` and f-strings convert and combine more safely than `+`.

> **Key rule:** str + int is a TypeError; convert with str() or use an f-string.

**Example 3.7.7.1: Plus and times**

```python
print("ab" + "cd", "ab" * 3, 3 * "ab", "ab" * 0, "ab" * -2 == "")
print("-" * 20)
print("=" * 5 + " title " + "=" * 5)
```

*Output:*

```text
abcd ababab ababab  True
--------------------
===== title =====
```

**Example 3.7.7.2: Mixing with numbers**

```python
age = 30
try:
    print("age: " + age)
except TypeError as e:
    print(e)
print("age: " + str(age), f"age: {age}", "age:", age)
```

*Output:*

```text
can only concatenate str (not "int") to str
age: 30 age: 30 age: 30
```

**Example 3.7.7.3: Building in a loop**

```python
parts = []
for i in range(5):
    parts.append(str(i))
print("".join(parts), ",".join(parts))
```

*Output:*

```text
01234 0,1,2,3,4
```

#### Practice 3.7.7

**3.7.7-Q1** · `BASIC`

```python
print('a' + 'b', 'a' * 3, 2 * 'ab')
```

**3.7.7-Q2** · `MID`

```python
print('ab' * 0 == '', 'ab' * -1 == '', len('x' * 10))
```

**3.7.7-Q3** · `MID`

```python
x = 'a'
y = x
x += 'b'
print(x, y)
```

**3.7.7-Q4** · `HARD`

```python
print('1' + '2', 1 + 2, '1' * 2, int('1') * 2)
```

**3.7.7-Q5** · `TRAP`

```python
print('Total: ' + 5)
```

### 3.7.8 len, in, comparison and ordering

`len(s)` counts characters (code points). `sub in s` tests for a SUBSTRING (not just one character). Strings compare lexicographically by Unicode code point, so uppercase letters sort BEFORE lowercase ('Z' < 'a') and '10' < '9' as text. Use `key=str.lower` or `key=str.casefold` for case-insensitive sorts and `key=int` for numeric ones.

> **Key rule:** strings compare by code point: 'Z' < 'a' and '10' < '9'. Provide key= to sort the way humans expect.

**Example 3.7.8.1: len and in**

```python
s = "hello world"
print(len(s), "lo w" in s, "x" in s, "" in s, "hello" not in s)
```

*Output:*

```text
11 True False True False
```

**Example 3.7.8.2: Lexicographic order**

```python
print("apple" < "banana", "Z" < "a", "10" < "9", "abc" < "abd", "ab" < "abc")
print(ord("A"), ord("Z"), ord("a"), ord("0"), ord(" "))
```

*Output:*

```text
True True True True True
65 90 97 48 32
```

**Example 3.7.8.3: Sorting with keys**

```python
words = ["banana", "Apple", "cherry", "apple"]
print(sorted(words))
print(sorted(words, key=str.lower))
print(sorted(["10", "9", "100"]), sorted(["10", "9", "100"], key=int))
print(sorted(words, key=len), max(words), max(words, key=len))
```

*Output:*

```text
['Apple', 'apple', 'banana', 'cherry']
['Apple', 'apple', 'banana', 'cherry']
['10', '100', '9'] ['9', '10', '100']
['Apple', 'apple', 'banana', 'cherry'] cherry banana
```

#### Practice 3.7.8

**3.7.8-Q1** · `BASIC`

```python
print('a' < 'b', 'a' < 'B', 'a' == 'A')
```

**3.7.8-Q2** · `MID`

```python
print('abc' in 'xabcx', 'ac' in 'abc', '' in 'abc')
```

**3.7.8-Q3** · `MID`

```python
print(sorted(['b', 'A', 'a', 'B']))
```

**3.7.8-Q4** · `HARD`

```python
print(sorted(['b', 'A', 'a', 'B'], key=str.lower))
```

**3.7.8-Q5** · `TRAP`

```python
print('10' < '9', 10 < 9, '10' < '2', sorted(['10', '9', '2']))
```

### 3.7.9 Iterating over strings

A string is iterable: `for ch in s` yields one-character strings. Use `enumerate(s)` for index and character, `zip(a, b)` to walk two strings together, `reversed(s)` to walk backwards, and `list(s)` to get a list of characters (the way to 'modify' a string, then `''.join` it back).

> **Key rule:** to edit a string: list(s), change the list, ''.join(list) back.

**Example 3.7.9.1: Loops**

```python
for ch in "abc":
    print(ch, end=" ")
print()
for i, ch in enumerate("abc", start=1):
    print(i, ch, end="; ")
print()
for a, b in zip("abc", "xyz"):
    print(a + b, end=" ")
print()
```

*Output:*

```text
a b c
1 a; 2 b; 3 c;
ax by cz
```

**Example 3.7.9.2: Converting**

```python
s = "hello"
print(list(s), tuple(s), sorted(s), set(s) == set("olleh"))
print("".join(reversed(s)), [c.upper() for c in s])
```

*Output:*

```text
['h', 'e', 'l', 'l', 'o'] ('h', 'e', 'l', 'l', 'o') ['e', 'h', 'l', 'l', 'o'] True
olleh ['H', 'E', 'L', 'L', 'O']
```

**Example 3.7.9.3: Editing through a list**

```python
s = "cat"
chars = list(s)
chars[0] = "b"
print("".join(chars))
print("".join(c for c in "a1b2c3" if c.isalpha()))
```

*Output:*

```text
bat
abc
```

#### Practice 3.7.9

**3.7.9-Q1** · `BASIC`

```python
print([c for c in 'abc'])
```

**3.7.9-Q2** · `MID`

```python
print(list(enumerate('ab')), list(zip('ab', 'xyz')))
```

**3.7.9-Q3** · `MID`

```python
print(''.join(reversed('abc')), sorted('banana'))
```

**3.7.9-Q4** · `HARD`

```python
print(len(set('mississippi')), ''.join(sorted(set('mississippi'))))
```

**3.7.9-Q5** · `TRAP`

```python
print(list('ab' 'cd'), list(['ab', 'cd']), list('ab, cd'))
```

### 3.7.10 Case methods: upper, lower, capitalize, title, swapcase, casefold

These return a new string with the case changed. `upper` / `lower` change every cased character. `capitalize` makes the FIRST character upper and the REST lower. `title` capitalises every word but treats apostrophes as word breaks, so `\"they're\".title()` is wrong. `swapcase` flips each letter. `casefold` is a stronger lower() meant for case-insensitive comparison ('ß' becomes 'ss').

> **Key rule:** compare text case-insensitively with casefold(); title() mishandles apostrophes.

**Example 3.7.10.1: The six methods**

```python
s = "hello WORLD of Python"
print(s.upper()); print(s.lower()); print(s.capitalize())
print(s.title()); print(s.swapcase()); print(s.casefold())
```

*Output:*

```text
HELLO WORLD OF PYTHON
hello world of python
Hello world of python
Hello World Of Python
HELLO world OF pYTHON
hello world of python
```

**Example 3.7.10.2: title() and apostrophes**

```python
print("they're bill's friends".title())
import string
print(string.capwords("they're bill's friends"))
```

*Output:*

```text
They'Re Bill'S Friends
They're Bill's Friends
```

**Example 3.7.10.3: casefold versus lower**

```python
a, b = "Straße", "STRASSE"
print(a.lower() == b.lower(), a.casefold() == b.casefold())
print("ß".lower(), "ß".casefold(), "ß".upper())
```

*Output:*

```text
False True
ß ss SS
```

> ⚠️ **Watch out:** `'ß'.upper()` is 'SS', so upper() can change the length of a string.

#### Practice 3.7.10

**3.7.10-Q1** · `BASIC`

```python
print('Hello'.upper(), 'Hello'.lower(), 'hello'.capitalize())
```

**3.7.10-Q2** · `MID`

```python
print('hELLO wORLD'.capitalize(), 'hELLO wORLD'.title())
```

**3.7.10-Q3** · `MID`

```python
print('aBc'.swapcase(), 'ab1c'.upper(), '123'.upper())
```

**3.7.10-Q4** · `HARD`

```python
print('ß'.upper(), len('ß'.upper()), 'ß'.casefold())
```

**3.7.10-Q5** · `TRAP`

```python
print('3rd place'.title(), 'o\'neil'.title(), 'ab-cd'.title())
```

### 3.7.11 Searching: find, rfind, index, rindex, count, in

`find(sub[, start[, end]])` returns the LOWEST index where sub begins, or -1. `rfind` returns the HIGHEST index. `index` and `rindex` do the same but raise ValueError when absent. `count` returns NON-OVERLAPPING occurrences. Use `in` when you only need a yes/no answer, because `if s.find(x):` is a classic bug (0 is falsy, -1 is truthy).

> **Key rule:** find returns -1 when missing, index raises; never test `if s.find(x):`, test `if x in s:`.

**Example 3.7.11.1: find, rfind, index, rindex**

```python
s = "banana"
print(s.find("an"), s.rfind("an"), s.find("x"), s.rfind("x"))
print(s.index("an"), s.rindex("an"))
try:
    s.index("x")
except ValueError as e:
    print(e)
```

*Output:*

```text
1 3 -1 -1
1 3
substring not found
```

**Example 3.7.11.2: start and end arguments**

```python
s = "banana"
print(s.find("a", 2), s.find("a", 2, 3), s.find("an", 2), s.count("a", 2))
print(s.find(""), s.rfind(""), s.find("", 10))
```

*Output:*

```text
3 -1 3 2
0 6 -1
```

**Example 3.7.11.3: count is non-overlapping**

```python
print("banana".count("a"), "banana".count("an"), "aaaa".count("aa"), "abc".count(""))
print("aaaa".count("a", 1, 3), "banana".count("A"))
```

*Output:*

```text
3 2 2 4
2 0
```

**Example 3.7.11.4: The find truthiness bug**

```python
s = "apple"
print(s.find("a"), bool(s.find("a")))
print(s.find("z"), bool(s.find("z")))
print("a" in s, "z" in s)
```

*Output:*

```text
0 False
-1 True
True False
```

#### Practice 3.7.11

**3.7.11-Q1** · `BASIC`

```python
s = 'hello'
print(s.find('l'), s.rfind('l'), s.find('z'))
```

**3.7.11-Q2** · `BASIC`

```python
print('banana'.count('a'), 'banana'.count('na'))
```

**3.7.11-Q3** · `MID`

```python
print('aaaa'.count('aa'), 'abcabc'.find('c', 3), 'abcabc'.index('b', 2))
```

**3.7.11-Q4** · `HARD`

```python
s = 'hello'
print(s.find('h'), bool(s.find('h')), s.find('o', -2), s.find('', 5))
```

**3.7.11-Q5** · `TRAP`

```python
print('abc'.index('d'))
```

### 3.7.12 startswith, endswith, removeprefix, removesuffix

`startswith` and `endswith` return bool, accept a TUPLE of alternatives, and accept optional start/end positions. `removeprefix` and `removesuffix` (3.9+) delete one exact prefix/suffix if present and otherwise return the string unchanged. They are the safe replacement for `strip(chars)`, which removes any SET of characters, not a word.

> **Key rule:** strip('abc') removes characters, not the word 'abc'; use removeprefix/removesuffix for words.

**Example 3.7.12.1: Starts and ends**

```python
f = "report_2026.pdf"
print(f.startswith("report"), f.endswith(".pdf"), f.endswith((".png", ".jpg", ".pdf")))
print(f.startswith("port", 2), f.startswith(("a", "b")))
```

*Output:*

```text
True True True
True False
```

**Example 3.7.12.2: removeprefix / removesuffix**

```python
f = "report_2026.pdf"
print(f.removeprefix("report_"), f.removesuffix(".pdf"), f.removeprefix("xyz"))
print("test_test_a".removeprefix("test_"))
```

*Output:*

```text
2026.pdf report_2026 report_2026.pdf
test_a
```

**Example 3.7.12.3: Why not strip**

```python
f = "tests.pytest"
print(f.removesuffix("test"), f.rstrip("test"))
print("www.example.com".lstrip("w."), "www.example.com".removeprefix("www."))
```

*Output:*

```text
tests.py tests.py
example.com example.com
```

#### Practice 3.7.12

**3.7.12-Q1** · `BASIC`

```python
print('hello'.startswith('he'), 'hello'.endswith('lo'), 'hello'.startswith('lo'))
```

**3.7.12-Q2** · `MID`

```python
print('a.py'.endswith(('.py', '.txt')), 'a.py'.startswith(()))
```

**3.7.12-Q3** · `MID`

```python
print('hello'.removeprefix('he'), 'hello'.removesuffix('xx'))
```

**3.7.12-Q4** · `HARD`

```python
print('banana'.removesuffix('na'), 'banana'.rstrip('na'))
```

**3.7.12-Q5** · `TRAP`

```python
print('hello'.startswith(['he', 'xx']))
```

### 3.7.13 strip, lstrip, rstrip

`strip()` removes leading AND trailing whitespace (spaces, tabs, newlines). `lstrip()` only the left, `rstrip()` only the right. With an argument, the argument is a SET of characters to remove from the ends, in any order, until a non-member is met. Whitespace in the MIDDLE is never touched.

> **Key rule:** strip(chars) treats chars as a set and only touches the ends.

**Example 3.7.13.1: Whitespace stripping**

```python
s = "  \t hello world \n"
print(repr(s.strip()), repr(s.lstrip()), repr(s.rstrip()))
print(repr("a  b".strip()))
```

*Output:*

```text
'hello world' 'hello world \n' '  \t hello world'
'a  b'
```

**Example 3.7.13.2: Stripping a character set**

```python
print("xxhixx".strip("x"), "xyxhixyx".strip("xy"), "[tag]".strip("[]"))
print("3.1400".rstrip("0"), "3.000".rstrip("0").rstrip("."), "007".lstrip("0"))
```

*Output:*

```text
hi hi tag
3.14 3 7
```

**Example 3.7.13.3: Cleaning input**

```python
raw = "  Alice ,  Bob,Carol  "
print([p.strip() for p in raw.split(",")])
print(repr("".strip()), repr("   ".strip()))
```

*Output:*

```text
['Alice', 'Bob', 'Carol']
'' ''
```

#### Practice 3.7.13

**3.7.13-Q1** · `BASIC`

```python
print(repr('  hi  '.strip()), repr('  hi  '.lstrip()), repr('  hi  '.rstrip()))
```

**3.7.13-Q2** · `MID`

```python
print('--a--'.strip('-'), '-a-b-'.strip('-'), 'abcba'.strip('ab'))
```

**3.7.13-Q3** · `MID`

```python
print('1.500'.rstrip('0'), '100'.rstrip('0'), '0.0'.rstrip('0'))
```

**3.7.13-Q4** · `HARD`

```python
print(repr(' \t\n'.strip()), 'xxhixx'.lstrip('x'), 'hello'.strip('hel'))
```

**3.7.13-Q5** · `TRAP`

```python
print('www.site.org'.strip('w.org'))
```

### 3.7.14 split and rsplit

`split(sep=None, maxsplit=-1)` returns a LIST. With no separator it splits on RUNS of whitespace and drops empty strings from the ends. With an explicit separator every separator splits, so consecutive separators create empty strings. `maxsplit` limits the number of splits; `rsplit` counts from the right. An empty separator is a ValueError.

> **Key rule:** split() with no argument collapses whitespace; split(' ') does not.

**Example 3.7.14.1: Default versus explicit separator**

```python
s = "  a   b  c  "
print(s.split())
print(s.split(" "))
print("a,b,,c".split(","), "a,b,,c".split(",") == ["a", "b", "", "c"])
```

*Output:*

```text
['a', 'b', 'c']
['', '', 'a', '', '', 'b', '', 'c', '', '']
['a', 'b', '', 'c'] True
```

**Example 3.7.14.2: maxsplit and rsplit**

```python
s = "a b c d"
print(s.split(None, 1), s.split(" ", 2), s.rsplit(None, 1), s.rsplit(" ", 2))
print("path/to/file.txt".rsplit("/", 1), "file.tar.gz".rsplit(".", 1))
```

*Output:*

```text
['a', 'b c d'] ['a', 'b', 'c d'] ['a b c', 'd'] ['a b', 'c', 'd']
['path/to', 'file.txt'] ['file.tar', 'gz']
```

**Example 3.7.14.3: Edge cases and parsing**

```python
print("".split(), "".split(","), ",".split(","), "abc".split("x"))
line = "name=Ann;age=30"
print(dict(p.split("=") for p in line.split(";")))
print([int(x) for x in "1 2 3".split()])
```

*Output:*

```text
[] [''] ['', ''] ['abc']
{'name': 'Ann', 'age': '30'}
[1, 2, 3]
```

**Example 3.7.14.4: An empty separator is an error**

```python
try:
    "abc".split("")
except ValueError as e:
    print(e)
```

*Output:*

```text
empty separator
```

#### Practice 3.7.14

**3.7.14-Q1** · `BASIC`

```python
print('a b c'.split(), 'a,b,c'.split(','))
```

**3.7.14-Q2** · `MID`

```python
print(' a  b '.split(), ' a  b '.split(' '))
```

**3.7.14-Q3** · `MID`

```python
print('a-b-c-d'.split('-', 2), 'a-b-c-d'.rsplit('-', 2))
```

**3.7.14-Q4** · `HARD`

```python
print(''.split(), ''.split(','), ','.split(','), 'a,'.split(','))
```

**3.7.14-Q5** · `TRAP`

```python
print('1,2,3'.split(',') == [1, 2, 3], sum(map(int, '1,2,3'.split(','))))
```

### 3.7.15 splitlines, partition and rpartition

`splitlines(keepends=False)` splits on every line boundary (\n, \r\n, \r and some Unicode ones) and does NOT return a trailing empty string for a final newline. `partition(sep)` splits at the FIRST sep into exactly three parts `(before, sep, after)`; if sep is missing you get `(s, '', '')`. `rpartition` splits at the LAST sep and returns `('', '', s)` when missing. They never raise.

> **Key rule:** partition always returns a 3-tuple, so it unpacks safely where split would not.

**Example 3.7.15.1: splitlines versus split('\n')**

```python
text = "one\ntwo\r\nthree\n"
print(text.splitlines())
print(text.split("\n"))
print(text.splitlines(keepends=True))
```

*Output:*

```text
['one', 'two', 'three']
['one', 'two\r', 'three', '']
['one\n', 'two\r\n', 'three\n']
```

**Example 3.7.15.2: partition and rpartition**

```python
s = "key=value=more"
print(s.partition("="))
print(s.rpartition("="))
print("novalue".partition("="), "novalue".rpartition("="))
```

*Output:*

```text
('key', '=', 'value=more')
('key=value', '=', 'more')
('novalue', '', '') ('', '', 'novalue')
```

**Example 3.7.15.3: Typical use**

```python
email = "user@example.com"
name, at, domain = email.partition("@")
print(name, domain)
base, dot, ext = "archive.tar.gz".rpartition(".")
print(base, ext)
```

*Output:*

```text
user example.com
archive.tar gz
```

#### Practice 3.7.15

**3.7.15-Q1** · `BASIC`

```python
print('a\nb\nc'.splitlines(), 'a=b'.partition('='))
```

**3.7.15-Q2** · `MID`

```python
print('a=b=c'.partition('='), 'a=b=c'.rpartition('='))
```

**3.7.15-Q3** · `MID`

```python
print('abc'.partition('x'), 'abc'.rpartition('x'))
```

**3.7.15-Q4** · `HARD`

```python
print('a\n'.splitlines(), 'a\n'.split('\n'), ''.splitlines(), '\n'.splitlines())
```

**3.7.15-Q5** · `TRAP`

```python
print('a  b'.partition(' '), 'a b c'.partition(' ')[2])
```

### 3.7.16 join

`sep.join(iterable)` glues the items with `sep` between them. Every item MUST be a str (convert numbers first). It is called on the SEPARATOR, not on the list, and it is the fastest way to build a string from many parts. A string is itself iterable, so `'-'.join('abc')` works.

> **Key rule:** 'sep'.join(list_of_strings); items must be str; the separator can be empty.

**Example 3.7.16.1: Basic joins**

```python
words = ["a", "b", "c"]
print(",".join(words), " ".join(words), "".join(words), "\n".join(words))
print("-".join("abc"), "+".join([]), repr(",".join(["only"])))
```

*Output:*

```text
a,b,c a b c abc a
b
c
a-b-c  'only'
```

**Example 3.7.16.2: Numbers must be converted**

```python
nums = [1, 2, 3]
try:
    ",".join(nums)
except TypeError as e:
    print(e)
print(",".join(str(n) for n in nums), ",".join(map(str, nums)))
```

*Output:*

```text
sequence item 0: expected str instance, int found
1,2,3 1,2,3
```

**Example 3.7.16.3: join and split are inverses**

```python
parts = "2026-11-01".split("-")
print(parts, "/".join(parts))
print(" ".join("the  quick   fox".split()))
print(", ".join(f"{k}={v}" for k, v in {"a": 1, "b": 2}.items()))
```

*Output:*

```text
['2026', '11', '01'] 2026/11/01
the quick fox
a=1, b=2
```

#### Practice 3.7.16

**3.7.16-Q1** · `BASIC`

```python
print('-'.join(['a', 'b', 'c']), ''.join(['a', 'b']))
```

**3.7.16-Q2** · `MID`

```python
print(','.join('abc'), ' '.join(['x']), '-'.join([]) == '')
```

**3.7.16-Q3** · `MID`

```python
print(','.join(str(i) for i in range(4)))
```

**3.7.16-Q4** · `HARD`

```python
print('ab'.join('123'), ''.join(['a', 'b']) * 2)
```

**3.7.16-Q5** · `TRAP`

```python
print(','.join([1, 2, 3]))
```

### 3.7.17 replace

`replace(old, new, count=-1)` returns a copy with EVERY occurrence of `old` replaced by `new` (or only the first `count`). Matches are non-overlapping and found left to right. Replacing with '' deletes. `replace('', x)` inserts x between all characters. It is case-sensitive and never raises when old is missing.

> **Key rule:** replace is literal, case-sensitive and returns a new string; chain calls for several substitutions.

**Example 3.7.17.1: Basics**

```python
s = "banana"
print(s.replace("a", "o"), s.replace("a", "o", 2), s.replace("na", ""), s.replace("x", "y"))
print(s.replace("A", "o"), s)
```

*Output:*

```text
bonono bonona ba banana
banana banana
```

**Example 3.7.17.2: Edge behaviour**

```python
print("aaa".replace("aa", "b"), "abc".replace("", "-"), "abc".replace("b", "bb"))
print("a.b.c".replace(".", ""), "Hello".replace("l", "L", 1))
```

*Output:*

```text
ba -a-b-c- abbc
abc HeLlo
```

**Example 3.7.17.3: Chained and cleaning**

```python
s = "  Hello,   World!  "
print(" ".join(s.split()).replace(",", "").replace("!", ""))
swap = "cat dog".replace("cat", "@").replace("dog", "cat").replace("@", "dog")
print(swap)
```

*Output:*

```text
Hello World
dog cat
```

#### Practice 3.7.17

**3.7.17-Q1** · `BASIC`

```python
print('hello'.replace('l', 'L'), 'hello'.replace('l', 'L', 1))
```

**3.7.17-Q2** · `MID`

```python
print('aaaa'.replace('aa', 'b'), 'abab'.replace('ab', 'ba'))
```

**3.7.17-Q3** · `MID`

```python
print('abc'.replace('', '-'), 'abc'.replace('abc', ''))
```

**3.7.17-Q4** · `HARD`

```python
print('a b'.replace(' ', '  ').replace('  ', ' '))
```

**3.7.17-Q5** · `TRAP`

```python
s = 'hello'
s.replace('h', 'j')
print(s)
```

### 3.7.18 translate and maketrans

`str.maketrans` builds a character-mapping table; `s.translate(table)` applies it in ONE pass, which is far faster than chained replace for single characters. Forms: `maketrans('abc', 'xyz')` maps one-to-one (equal lengths), a third argument lists characters to DELETE, and a dict maps code points (or characters) to strings, None (delete) or longer strings.

> **Key rule:** translate maps single characters in one pass: one-to-one, delete, or expand.

**Example 3.7.18.1: One-to-one and delete**

```python
t = str.maketrans("abc", "xyz")
print("aabbcc dd".translate(t))
t2 = str.maketrans("", "", "aeiou")
print("education".translate(t2))
t3 = str.maketrans("ab", "12", "z")
print("abzz".translate(t3))
```

*Output:*

```text
xxyyzz dd
dctn
12
```

**Example 3.7.18.2: Dictionary form**

```python
t = str.maketrans({"<": "&lt;", ">": "&gt;", "&": "&amp;"})
print("<a & b>".translate(t))
print(str.maketrans("ab", "xy"))
```

*Output:*

```text
&lt;a &amp; b&gt;
{97: 120, 98: 121}
```

**Example 3.7.18.3: Typical tasks**

```python
import string
print("Hello, World!".translate(str.maketrans("", "", string.punctuation)))
rot13 = str.maketrans("abcdefghijklmnopqrstuvwxyz", "nopqrstuvwxyzabcdefghijklm")
print("hello".translate(rot13), "uryyb".translate(rot13))
```

*Output:*

```text
Hello World
uryyb hello
```

#### Practice 3.7.18

**3.7.18-Q1** · `BASIC`

```python
print('abc'.translate(str.maketrans('a', 'z')))
```

**3.7.18-Q2** · `MID`

```python
print('hello'.translate(str.maketrans('', '', 'l')))
```

**3.7.18-Q3** · `MID`

```python
print('a-b'.translate({ord('-'): ' '}))
```

**3.7.18-Q4** · `HARD`

```python
print('ab'.translate({ord('a'): 'xyz', ord('b'): None}))
```

**3.7.18-Q5** · `TRAP`

```python
print(str.maketrans('ab', 'x'))
```

### 3.7.19 Alignment and padding: center, ljust, rjust, zfill, expandtabs

`ljust(width, fill=' ')` pads on the RIGHT (text stays left), `rjust` pads on the LEFT, `center` pads both sides. If the string is already at least `width` long it is returned unchanged. `zfill(width)` pads with zeros on the left AFTER a leading sign. `expandtabs(tabsize=8)` replaces each tab with spaces up to the next tab stop. F-strings (`f'{s:>10}'`) do the same jobs.

> **Key rule:** ljust/rjust/center never truncate; zfill keeps a leading +/-.

**Example 3.7.19.1: The four aligners**

```python
s = "ab"
print(repr(s.ljust(6)), repr(s.rjust(6)), repr(s.center(6)), repr(s.center(7, "*")))
print(s.ljust(6, "."), s.rjust(6, "."), "toolong".ljust(3))
```

*Output:*

```text
'ab    ' '    ab' '  ab  ' '***ab**'
ab.... ....ab toolong
```

**Example 3.7.19.2: zfill**

```python
print("42".zfill(5), "-42".zfill(5), "+42".zfill(5), "abc".zfill(5), "123456".zfill(3))
print(str(7).zfill(2) + ":" + str(5).zfill(2))
```

*Output:*

```text
00042 -0042 +0042 00abc 123456
07:05
```

**Example 3.7.19.3: expandtabs and f-string equivalents**

```python
print(repr("a\tb\tc".expandtabs(4)), repr("abcde\tf".expandtabs(4)))
s = "ab"
print(f"[{s:<6}] [{s:>6}] [{s:^6}] [{s:*^7}] [{5:05d}]")
```

*Output:*

```text
'a   b   c' 'abcde   f'
[ab    ] [    ab] [  ab  ] [**ab***] [00005]
```

**Example 3.7.19.4: A text table**

```python
rows = [("apple", 3), ("kiwi", 12)]
for name, qty in rows:
    print(name.ljust(8) + str(qty).rjust(4))
```

*Output:*

```text
apple      3
kiwi      12
```

#### Practice 3.7.19

**3.7.19-Q1** · `BASIC`

```python
print('7'.zfill(3), 'hi'.center(6, '-'), 'hi'.ljust(4, '.'))
```

**3.7.19-Q2** · `MID`

```python
print(repr('abc'.center(4)), repr('abc'.center(5)), repr('ab'.center(5)))
```

**3.7.19-Q3** · `MID`

```python
print('-5'.zfill(4), '+5'.zfill(4), '5'.zfill(0))
```

**3.7.19-Q4** · `HARD`

```python
print(repr('a\tb'.expandtabs()), len('a\tb'.expandtabs()), len('a\tb'.expandtabs(1)))
```

**3.7.19-Q5** · `TRAP`

```python
print(5.zfill(3))
```

### 3.7.20 Testing methods: isalpha, isdigit, isdecimal, isnumeric, isalnum, isspace and more

All the `is...()` methods return a bool, and (except isascii and isprintable) they are False for the EMPTY string. `isalpha` letters only; `isdecimal` strictly 0-9 style digits; `isdigit` also superscript digits; `isnumeric` also fractions and numerals in other scripts; `isalnum` letters or digits; `isspace` whitespace only; `isupper` / `islower` need at least one CASED character and no opposite case; `istitle`; `isidentifier`; `isprintable`; `isascii`.

> **Key rule:** the is-methods are False for '', and isdigit() is False for '-5' and '3.5'; validate numbers with try/int().

**Test results for sample strings**

| s | alpha | decimal | digit | numeric | alnum | space |
|---|---|---|---|---|---|---|
| `'abc'` | T | F | F | F | T | F |
| `'123'` | F | T | T | T | T | F |
| `'²'` | F | F | T | T | T | F |
| `'½'` | F | F | F | T | T | F |
| `'a1'` | F | F | F | F | T | F |
| `' '` | F | F | F | F | F | T |
| `''` | F | F | F | F | F | F |
| `'3.5'` | F | F | F | F | F | F |
| `'-5'` | F | F | F | F | F | F |

**Example 3.7.20.1: The table, computed**

```python
for s in ["abc", "123", "²", "½", "a1", " ", "", "3.5", "-5"]:
    print(repr(s).ljust(6), s.isalpha(), s.isdecimal(), s.isdigit(), s.isnumeric(), s.isalnum(), s.isspace())
```

*Output:*

```text
'abc'  True False False False True False
'123'  False True True True True False
'²'    False False True True True False
'½'    False False False True True False
'a1'   False False False False True False
' '    False False False False False True
''     False False False False False False
'3.5'  False False False False False False
'-5'   False False False False False False
```

**Example 3.7.20.2: Case and shape tests**

```python
print("ABC".isupper(), "abc".islower(), "A1".isupper(), "123".isupper(), "".isupper())
print("Hello World".istitle(), "Hello world".istitle(), "HELLO".istitle())
print("my_var".isidentifier(), "1var".isidentifier(), "class".isidentifier())
```

*Output:*

```text
True True True False False
True False False
True False True
```

**Example 3.7.20.3: isprintable and isascii**

```python
print("abc".isprintable(), "a\nb".isprintable(), "".isprintable(), "é".isascii(), "".isascii())
```

*Output:*

```text
True False True False True
```

**Example 3.7.20.4: Validating a number correctly**

```python
def is_int(s):
    try:
        int(s)
        return True
    except ValueError:
        return False
print([is_int(x) for x in ["12", "-5", "+3", "3.5", "x", " 7 ", "²"]])
print(["-5".isdigit(), "²".isdigit(), "²".isdecimal()])
```

*Output:*

```text
[True, True, True, False, False, True, False]
[False, True, False]
```

> ⚠️ **Watch out:** `'²'.isdigit()` is True but `int('²')` raises ValueError. Use isdecimal when you plan to call int().

#### Practice 3.7.20

**3.7.20-Q1** · `BASIC`

```python
print('abc'.isalpha(), 'abc1'.isalpha(), '123'.isdigit(), ''.isalpha())
```

**3.7.20-Q2** · `MID`

```python
print('a b'.isalpha(), 'a b'.replace(' ', '').isalpha(), ' '.isspace(), ''.isspace())
```

**3.7.20-Q3** · `MID`

```python
print('ABC'.isupper(), 'ABc'.isupper(), '123'.isupper(), 'A1'.isupper())
```

**3.7.20-Q4** · `HARD`

```python
print('Hello World'.istitle(), 'Hello world'.istitle(), 'HELLO'.istitle(), ''.istitle())
```

**3.7.20-Q5** · `TRAP`

```python
print('-5'.isdigit(), '5.0'.isdigit(), '٣'.isdigit(), int('٣'))
```

### 3.7.21 Old-style % formatting

The printf-style operator `fmt % values` is older than f-strings but is still common in logging and legacy code. `%s` (str), `%r` (repr), `%d`/`%i` (int), `%f` (float), `%x`/`%X`/`%o` (bases), `%e`, `%g`, `%c` (character), `%%` (literal percent). Flags and widths: `%5d`, `%-5d`, `%05d`, `%+d`, `%.2f`, `%8.3f`. Several values need a TUPLE; a named style uses a dict.

> **Key rule:** one value: fmt % x; several: fmt % (x, y); named: fmt % {'k': v}. Use %% for a literal percent.

**Example 3.7.21.1: Common codes**

```python
print("%s is %d years and %.1f m tall" % ("Ann", 30, 1.7))
print("%5d|%-5d|%05d|%+d" % (42, 42, 42, 42))
print("%x %X %o %e %g %c %%" % (255, 255, 8, 12345.678, 0.0001, 65))
```

*Output:*

```text
Ann is 30 years and 1.7 m tall
   42|42   |00042|+42
ff FF 10 1.234568e+04 0.0001 A %
```

**Example 3.7.21.2: A tuple versus a single value**

```python
print("%s" % "one", "%s" % (1,), "%s-%s" % (1, 2))
print("%s" % [1, 2], "%r" % "txt", "%s" % None)
```

*Output:*

```text
one 1 1-2
[1, 2] 'txt' None
```

**Example 3.7.21.3: Named placeholders and width from arguments**

```python
print("%(name)s owes %(amt).2f" % {"name": "Bo", "amt": 5})
print("%*d|%-*d|" % (6, 42, 6, 42), "%.3s" % "abcdef", "%10.3s|" % "abcdef")
```

*Output:*

```text
Bo owes 5.00
    42|42    | abc        abc|
```

> ⚠️ **Watch out:** `'%s' % some_tuple` unpacks the tuple. Wrap it: `'%s' % (some_tuple,)`.

#### Practice 3.7.21

**3.7.21-Q1** · `BASIC`

```python
print('%d + %d = %d' % (2, 3, 5))
```

**3.7.21-Q2** · `MID`

```python
print('%5.2f|%-6s|%06.1f' % (3.14159, 'ab', 2.5))
```

**3.7.21-Q3** · `MID`

```python
print('100%% sure', '%s' % 5, '%r' % 'a')
```

**3.7.21-Q4** · `HARD`

```python
print('%s' % (1, 2))
```

**3.7.21-Q5** · `TRAP`

```python
print('%d' % 3.9, '%d' % '3')
```

### 3.7.22 str.format()

`'{}'.format(...)` replaces braces with arguments: automatic order `{}`, positional `{0}`, named `{name}`, attribute `{obj.attr}`, item `{d[key]}` and `{lst[0]}`. After a colon comes the same format spec as f-strings. Literal braces are doubled `{{ }}`. A conversion flag `!r`, `!s`, `!a` goes before the colon.

> **Key rule:** {} auto-numbers, {0} picks by position, {name} by keyword; double the braces for literal ones.

**Example 3.7.22.1: Fields**

```python
print("{} {}".format("a", "b"), "{1} {0} {1}".format("a", "b"), "{x}-{y}".format(x=1, y=2))
print("{0.real} {0.imag}".format(3 + 4j), "{d[k]} {l[1]}".format(d={"k": "v"}, l=[7, 8]))
```

*Output:*

```text
a b b a b 1-2
3.0 4.0 v 8
```

**Example 3.7.22.2: Specs, conversions and literal braces**

```python
print("{:>8.2f}|{:<5}|{:^7}|{:08.3f}".format(3.14159, "ab", "mid", 3.14159))
print("{!r} {!s}".format("txt", "txt"), "{{literal}} {}".format(1))
print("{:,} {:b} {:#x} {:.1%}".format(1234567, 10, 255, 0.256))
```

*Output:*

```text
    3.14|ab   |  mid  |0003.142
'txt' txt {literal} 1
1,234,567 1010 0xff 25.6%
```

**Example 3.7.22.3: Reusing a template and unpacking**

```python
t = "{name} is {age}"
print(t.format(name="Ann", age=30))
person = {"name": "Bo", "age": 25}
print(t.format(**person))
print("{} {}".format(*"ab"))
```

*Output:*

```text
Ann is 30
Bo is 25
a b
```

**Example 3.7.22.4: Mixing automatic and manual numbering fails**

```python
try:
    print("{} {1}".format("a", "b"))
except ValueError as e:
    print(e)
```

*Output:*

```text
cannot switch from automatic field numbering to manual field specification
```

#### Practice 3.7.22

**3.7.22-Q1** · `BASIC`

```python
print('{} and {}'.format('x', 'y'), '{1}{0}'.format('a', 'b'))
```

**3.7.22-Q2** · `MID`

```python
print('{:05d} {:.3f} {:>4}'.format(42, 2.0, 'a'))
```

**3.7.22-Q3** · `MID`

```python
print('{0} {0} {1}'.format('a', 'b'), '{a}{b}'.format(a=1, b=2))
```

**3.7.22-Q4** · `HARD`

```python
print('{{}}'.format(), '{{{}}}'.format(5), '{:{}}|'.format('a', 4))
```

**3.7.22-Q5** · `TRAP`

```python
print('{} {}'.format('only one'))
```

### 3.7.23 f-strings and the format-spec mini-language

An f-string (`f'...'`) evaluates expressions inside `{}` at runtime. After the expression you may add `!r` / `!s` / `!a` and a `:spec`. The spec grammar is `[[fill]align][sign][#][0][width][,|_][.precision][type]`. Align `<` `>` `^` `=`; sign `+` `-` ; types `s d b o x X c e f g %`. `{x=}` prints the expression AND its value (debugging). Python 3.12 allows reusing the same quote type and backslashes inside the braces.

> **Key rule:** f'{value!r:>10.2f}' reads: expression, conversion, then spec. Put `=` after the name for debug output.

**Format spec quick reference**

| Spec | Applied to | Result |
|---|---|---|
| `>8` | 'ab' | ' ab' |
| `<8` | 'ab' | 'ab ' |
| `^8` | 'ab' | ' ab ' |
| `*^8` | 'ab' | `'***ab***'` |
| `05d` | 42 | 00042 |
| `+d` | 42 | +42 |
| `,d` | 1234567 | 1,234,567 |
| `_d` | 1234567 | 1_234_567 |
| `.3f` | 3.14159 | 3.142 |
| `.2%` | 0.256 | 25.60% |
| `#x` | 255 | 0xff |
| `08.2f` | 3.14159 | 00003.14 |
| `.3s` | 'abcdef' | abc |
| `c` | 65 | A |

**Example 3.7.23.1: Expressions, conversions, specs**

```python
name, price, qty = "tea", 2.5, 4
print(f"{name.upper()} costs {price * qty:.2f} for {qty}")
print(f"{name!r} {name!s} {name:>6} {name:<6}| {name:^7}| {name:*^9}")
print(f"{'nested ' + name} {[i * 2 for i in range(3)]} {price > 2}")
```

*Output:*

```text
TEA costs 10.00 for 4
'tea' tea    tea tea   |   tea  | ***tea***
nested tea [0, 2, 4] True
```

**Example 3.7.23.2: Debugging with =**

```python
x = 10
y = 3
print(f"{x=} {y=} {x / y=:.3f} {x + y = }")
print(f"{x * 2=} {x*2=} {x > y=}")
```

*Output:*

```text
x=10 y=3 x / y=3.333 x + y = 13
x * 2=20 x*2=20 x > y=True
```

**Example 3.7.23.3: Dynamic width, precision and date-like values**

```python
width, prec = 10, 3
val = 3.14159265
print(f"[{val:{width}.{prec}f}] [{val:<{width}.{prec}f}] [{val:^{width}}]")
import datetime
d = datetime.date(2026, 11, 1)
print(f"{d:%d/%m/%Y} {d:%A %B}")
```

*Output:*

```text
[     3.142] [3.142     ] [3.14159265]
01/11/2026 Sunday November
```

**Example 3.7.23.4: Escapes and quotes**

```python
print(f"{{braces}} {1 + 1}")
d = {"k": "v"}
print(f"{d['k']} {d["k"]}")
print(f"line1{'\n'}line2")
```

*Output:*

```text
{braces} 2
v v
line1
line2
```

#### Practice 3.7.23

**3.7.23-Q1** · `BASIC`

```python
x = 5
print(f'{x} {x * 2} {x:03d}')
```

**3.7.23-Q2** · `MID`

```python
s = 'ab'
print(f'[{s:>5}] [{s:<5}] [{s:^5}] [{s:-^6}]')
```

**3.7.23-Q3** · `MID`

```python
n = 1234567.891
print(f'{n:,.1f} {n:.2e} {n:_.0f}')
```

**3.7.23-Q4** · `HARD`

```python
a = 7
print(f'{a=}', f'{a=:>4}', f'{a!r:>4}', f'{a + 1 = }')
```

**3.7.23-Q5** · `TRAP`

```python
w = 6
print(f'{3.14159:{w}.2f}|{"x":{w}}|{{w}}')
```

### 3.7.24 format_map, the string module and Template

`format_map(mapping)` is `format(**mapping)` without copying, so a mapping subclass with `__missing__` can supply defaults. The `string` module provides ready constants: `ascii_lowercase`, `ascii_uppercase`, `ascii_letters`, `digits`, `hexdigits`, `octdigits`, `punctuation`, `whitespace`, `printable`, plus `capwords()` and `Template` (safe `$name` substitution for user-supplied templates).

**string module constants**

| Name | Content |
|---|---|
| `ascii_lowercase` | abcdefghijklmnopqrstuvwxyz |
| `ascii_uppercase` | ABCDEFGHIJKLMNOPQRSTUVWXYZ |
| `digits` | 0123456789 |
| `hexdigits` | 0123456789abcdefABCDEF |
| `octdigits` | 01234567 |
| `punctuation` | !"#$%&'()*+,-./:;<=>?@[\]^_`{\|}~ |

**Example 3.7.24.1: format_map with defaults**

```python
class Defaults(dict):
    def __missing__(self, key):
        return "<" + key + ">"
print("{a} and {b}".format_map(Defaults(a=1)))
print("{x}".format_map({"x": "plain"}))
```

*Output:*

```text
1 and <b>
plain
```

**Example 3.7.24.2: The constants**

```python
import string
print(string.ascii_lowercase)
print(string.digits, string.hexdigits, string.octdigits)
print(string.ascii_letters[:5], string.ascii_letters[-3:], len(string.printable), len(string.punctuation))
print(repr(string.whitespace))
```

*Output:*

```text
abcdefghijklmnopqrstuvwxyz
0123456789 0123456789abcdefABCDEF 01234567
abcde XYZ 100 32
' \t\n\r\x0b\x0c'
```

**Example 3.7.24.3: Template and capwords**

```python
from string import Template, capwords
t = Template("Hello $name, you owe $$${amount}")
print(t.substitute(name="Ann", amount=5))
print(t.safe_substitute(name="Bo"))
print(capwords("hELLO   wORLD"), capwords("a-b c", "-"))
try:
    t.substitute(name="x")
except KeyError as e:
    print("KeyError", e)
```

*Output:*

```text
Hello Ann, you owe $5
Hello Bo, you owe $${amount}
Hello World A-B c
KeyError 'amount'
```

#### Practice 3.7.24

**3.7.24-Q1** · `BASIC`

```python
import string; print(string.digits, len(string.ascii_letters))
```

**3.7.24-Q2** · `MID`

```python
import string; print(string.ascii_lowercase[:3], 'a' in string.ascii_uppercase)
```

**3.7.24-Q3** · `MID`

```python
from string import Template; print(Template('$a-$b').substitute(a=1, b=2))
```

**3.7.24-Q4** · `HARD`

```python
from string import Template; print(Template('$a $b').safe_substitute(a='x'))
```

**3.7.24-Q5** · `TRAP`

```python
from string import Template; print(Template('$a').substitute())
```

### 3.7.25 Unicode, encode, decode, ord and chr

A str holds Unicode CODE POINTS; bytes hold raw bytes. `s.encode(encoding='utf-8', errors='strict')` turns text into bytes; `b.decode(...)` turns bytes back. UTF-8 uses 1 to 4 bytes per character, so `len(s)` and `len(s.encode())` differ for non-ASCII text. `ord(c)` gives the code point, `chr(n)` the character. The `errors` argument chooses 'strict', 'ignore', 'replace', 'backslashreplace', 'xmlcharrefreplace'.

> **Key rule:** str = characters, bytes = encoded data. Decode when reading, encode when writing, and always name the encoding.

**Example 3.7.25.1: Encoding and decoding**

```python
s = "café €"
b = s.encode("utf-8")
print(b, len(s), len(b))
print(b.decode("utf-8"), s.encode("utf-16-le")[:4], s.encode("latin-1", errors="replace"))
```

*Output:*

```text
b'caf\xc3\xa9 \xe2\x82\xac' 6 9
café € b'c\x00a\x00' b'caf\xe9 ?'
```

**Example 3.7.25.2: Errors and error handlers**

```python
s = "naïve €"
for h in ("ignore", "replace", "backslashreplace", "xmlcharrefreplace"):
    print(h.ljust(18), s.encode("ascii", errors=h))
try:
    s.encode("ascii")
except UnicodeEncodeError as e:
    print("UnicodeEncodeError")
try:
    b"\xff".decode("utf-8")
except UnicodeDecodeError as e:
    print("UnicodeDecodeError")
```

*Output:*

```text
ignore             b'nave '
replace            b'na?ve ?'
backslashreplace   b'na\\xefve \\u20ac'
xmlcharrefreplace  b'na&#239;ve &#8364;'
UnicodeEncodeError
UnicodeDecodeError
```

**Example 3.7.25.3: ord and chr**

```python
print(ord("A"), ord("€"), chr(97), chr(8364), chr(0x1F600))
print([ord(c) for c in "abc"], "".join(chr(c) for c in (72, 105)))
print(chr(ord("a") + 1), ord("z") - ord("a"), hex(ord("é")))
print(len("\x00"), len("\x00".encode()), "\x00".encode("utf-16-le"))
```

*Output:*

```text
65 8364 a € \x00
[97, 98, 99] Hi
b 25 0xe9
1 4 b'=\xd8\x00\xde'
```

#### Practice 3.7.25

**3.7.25-Q1** · `BASIC`

```python
print(ord('a'), chr(65), ord('0'))
```

**3.7.25-Q2** · `MID`

```python
print(len('é'), len('é'.encode()), len('abc'.encode()))
```

**3.7.25-Q3** · `MID`

```python
print('hi'.encode(), b'hi'.decode(), type('hi'.encode()))
```

**3.7.25-Q4** · `HARD`

```python
print('é'.encode('latin-1'), 'é'.encode('utf-8'), 'é'.encode('latin-1').decode('utf-8', errors='replace'))
```

**3.7.25-Q5** · `TRAP`

```python
print('é'.encode('ascii'))
```

### 3.7.26 Unicode normalisation, grapheme caveats and unicodedata

The same visible text can be stored in several ways: 'é' is one code point (U+00E9) OR 'e' plus a combining accent (U+0065 U+0301). They look equal but compare unequal and have different lengths. `unicodedata.normalize('NFC', s)` (compose) or `'NFD'` (decompose) makes them comparable; `casefold` plus normalisation is the correct way to compare user text. Emoji with modifiers can also span several code points, so `len` is not 'what the user sees'.

> **Key rule:** normalise (NFC) before comparing or hashing text from different sources.

**Example 3.7.26.1: Two spellings of é**

```python
import unicodedata as ud
a, b = "\u00e9", "e\u0301"
print(a, b, a == b, len(a), len(b))
print(ud.normalize("NFC", b) == a, ud.normalize("NFD", a) == b, len(ud.normalize("NFD", a)))
```

*Output:*

```text
é é False 1 2
True True 2
```

**Example 3.7.26.2: unicodedata helpers**

```python
import unicodedata as ud
for ch in ("A", "é", "5", "€", " "):
    print(repr(ch), ud.name(ch), ud.category(ch))
print(ud.numeric("½"), ud.decimal("٣"), ud.lookup("GREEK SMALL LETTER ALPHA"))
```

*Output:*

```text
'A' LATIN CAPITAL LETTER A Lu
'é' LATIN SMALL LETTER E WITH ACUTE Ll
'5' DIGIT FIVE Nd
'€' EURO SIGN Sc
' ' SPACE Zs
0.5 3 α
```

**Example 3.7.26.3: Stripping accents and comparing safely**

```python
import unicodedata as ud
def base(s):
    d = ud.normalize("NFD", s)
    return "".join(c for c in d if not ud.combining(c))
print(base("café résumé"), base("naïve") == "naive")
def same(x, y):
    n = lambda t: ud.normalize("NFC", t).casefold()
    return n(x) == n(y)
print(same("\u00c9", "e\u0301"))
```

*Output:*

```text
cafe resume True
True
```

#### Practice 3.7.26

**3.7.26-Q1** · `BASIC`

```python
print(len('\u00e9'), len('e\u0301'))
```

**3.7.26-Q2** · `MID`

```python
import unicodedata as u; print(u.normalize('NFC', 'e\u0301') == '\u00e9')
```

**3.7.26-Q3** · `MID`

```python
import unicodedata as u; print(u.name('a'), u.category('1'))
```

**3.7.26-Q4** · `HARD`

```python
print(len('\x00\x00\x00\x00\x00'), len('\x00\x00'))
```

**3.7.26-Q5** · `TRAP`

```python
print('\u00e9' == 'e\u0301', '\u00e9'.upper() == 'E\u0301'.upper())
```

### 3.7.27 Complete reference: all 47 str methods

Every public method of `str` in Python 3.12, with the topic that teaches it. The table is checked against `dir(str)` so nothing is missing. The last example confirms it by listing the methods directly from Python.

**All str methods**

| Method | Purpose | Example -> result | Topic |
|---|---|---|---|
| `capitalize()` | first char upper, rest lower | `'hELLO'.capitalize()` -> 'Hello' | 3.7.10 |
| `casefold()` | aggressive lowercase for comparing | `'Straße'.casefold()` -> 'strasse' | 3.7.10 |
| `center(w, fill)` | centre in width w | `'ab'.center(6, '*')` -> `'**ab**'` | 3.7.19 |
| `count(sub, s, e)` | non-overlapping occurrences | `'banana'.count('an')` -> 2 | 3.7.11 |
| `encode(enc, errors)` | str to bytes | `'é'.encode()` -> b'\xc3\xa9' | 3.7.25 |
| `endswith(suf, s, e)` | ends with (tuple allowed) | `'a.py'.endswith('.py')` -> True | 3.7.12 |
| `expandtabs(n)` | tabs to spaces | `'a\tb'.expandtabs(4)` -> 'a b' | 3.7.19 |
| `find(sub, s, e)` | lowest index or -1 | `'hello'.find('l')` -> 2 | 3.7.11 |
| `format(*a, **k)` | brace formatting | `'{}-{}'.format(1, 2)` -> '1-2' | 3.7.22 |
| `format_map(d)` | format from a mapping | `'{a}'.format_map({'a': 1})` -> '1' | 3.7.24 |
| `index(sub, s, e)` | like find, raises ValueError | `'hello'.index('l')` -> 2 | 3.7.11 |
| `isalnum()` | letters or digits only | `'ab1'.isalnum()` -> True | 3.7.20 |
| `isalpha()` | letters only | `'ab'.isalpha()` -> True | 3.7.20 |
| `isascii()` | all chars < 128 | `'abc'.isascii()` -> True | 3.7.20 |
| `isdecimal()` | decimal digits 0-9 style | `'12'.isdecimal()` -> True | 3.7.20 |
| `isdigit()` | digits incl. superscripts | `'²'.isdigit()` -> True | 3.7.20 |
| `isidentifier()` | valid Python name | `'x_1'.isidentifier()` -> True | 3.7.20 |
| `islower()` | has cased chars, all lower | `'abc'.islower()` -> True | 3.7.20 |
| `isnumeric()` | numeric incl. fractions, CJK | `'½'.isnumeric()` -> True | 3.7.20 |
| `isprintable()` | no control chars | `'a\n'.isprintable()` -> False | 3.7.20 |
| `isspace()` | only whitespace, non-empty | `' \t'.isspace()` -> True | 3.7.20 |
| `istitle()` | title-cased words | `'Ab Cd'.istitle()` -> True | 3.7.20 |
| `isupper()` | has cased chars, all upper | `'ABC'.isupper()` -> True | 3.7.20 |
| `join(iterable)` | glue strings with separator | `'-'.join('abc')` -> 'a-b-c' | 3.7.16 |
| `ljust(w, fill)` | left-align, pad right | `'a'.ljust(3, '.')` -> 'a..' | 3.7.19 |
| `lower()` | all lowercase | `'AbC'.lower()` -> 'abc' | 3.7.10 |
| `lstrip(chars)` | strip from the left | `' a'.lstrip()` -> 'a' | 3.7.13 |
| `maketrans(...)` | build a translate table | `str.maketrans('ab', 'xy')` | 3.7.18 |
| `partition(sep)` | split at first sep into 3 | `'a=b=c'.partition('=')` -> ('a','=','b=c') | 3.7.15 |
| `removeprefix(p)` | drop prefix if present (3.9+) | `'test_x'.removeprefix('test_')` -> 'x' | 3.7.12 |
| `removesuffix(s)` | drop suffix if present (3.9+) | `'a.py'.removesuffix('.py')` -> 'a' | 3.7.12 |
| `replace(old, new, n)` | substitute substrings | `'aaa'.replace('a','b',2)` -> 'bba' | 3.7.17 |
| `rfind(sub, s, e)` | highest index or -1 | `'hello'.rfind('l')` -> 3 | 3.7.11 |
| `rindex(sub, s, e)` | like rfind, raises ValueError | `'hello'.rindex('l')` -> 3 | 3.7.11 |
| `rjust(w, fill)` | right-align, pad left | `'a'.rjust(3, '.')` -> '..a' | 3.7.19 |
| `rpartition(sep)` | split at last sep into 3 | `'a=b=c'.rpartition('=')` -> ('a=b','=','c') | 3.7.15 |
| `rsplit(sep, n)` | split from the right | `'a b c'.rsplit(None, 1)` -> ['a b','c'] | 3.7.14 |
| `rstrip(chars)` | strip from the right | `'a '.rstrip()` -> 'a' | 3.7.13 |
| `split(sep, n)` | split into a list | `'a,b'.split(',')` -> ['a','b'] | 3.7.14 |
| `splitlines(keepends)` | split on line boundaries | `'a\nb'.splitlines()` -> ['a','b'] | 3.7.15 |
| `startswith(pre, s, e)` | starts with (tuple allowed) | `'abc'.startswith('ab')` -> True | 3.7.12 |
| `strip(chars)` | strip both ends | `'xxaxx'.strip('x')` -> 'a' | 3.7.13 |
| `swapcase()` | swap upper and lower | `'aB'.swapcase()` -> 'Ab' | 3.7.10 |
| `title()` | capitalise each word | `'ab cd'.title()` -> 'Ab Cd' | 3.7.10 |
| `translate(table)` | map/delete characters | `'abc'.translate({97: 'X'})` -> 'Xbc' | 3.7.18 |
| `upper()` | all uppercase | `'abc'.upper()` -> 'ABC' | 3.7.10 |
| `zfill(w)` | pad with zeros on the left | `'42'.zfill(5)` -> '00042' | 3.7.19 |

**Example 3.7.27.1: The live list from Python**

```python
names = [n for n in dir(str) if not n.startswith("_")]
print(len(names))
print(names)
```

*Output:*

```text
47
['capitalize', 'casefold', 'center', 'count', 'encode', 'endswith', 'expandtabs', 'find', 'format', 'format_map', 'index', 'isalnum', 'isalpha', 'isascii', 'isdecimal', 'isdigit', 'isidentifier', 'islower', 'isnumeric', 'isprintable', 'isspace', 'istitle', 'isupper', 'join', 'ljust', 'lower', 'lstrip', 'maketrans', 'partition', 'removeprefix', 'removesuffix', 'replace', 'rfind', 'rindex', 'rjust', 'rpartition', 'rsplit', 'rstrip', 'split', 'splitlines', 'startswith', 'strip', 'swapcase', 'title', 'translate', 'upper', 'zfill']
```

**Example 3.7.27.2: Grouped by job**

```python
groups = {
    "case": ["upper", "lower", "capitalize", "title", "swapcase", "casefold"],
    "search": ["find", "rfind", "index", "rindex", "count", "startswith", "endswith"],
    "strip": ["strip", "lstrip", "rstrip", "removeprefix", "removesuffix"],
    "split/join": ["split", "rsplit", "splitlines", "partition", "rpartition", "join"],
    "change": ["replace", "translate", "maketrans", "expandtabs"],
    "align": ["center", "ljust", "rjust", "zfill"],
    "format": ["format", "format_map", "encode"],
}
tests = [n for n in dir(str) if n.startswith("is")]
print(sum(len(v) for v in groups.values()) + len(tests))
print(tests)
```

*Output:*

```text
47
['isalnum', 'isalpha', 'isascii', 'isdecimal', 'isdigit', 'isidentifier', 'islower', 'isnumeric', 'isprintable', 'isspace', 'istitle', 'isupper']
```

#### Practice 3.7.27

**3.7.27-Q1** · `BASIC`

```python
print(hasattr('', 'upper'), hasattr('', 'append'))
```

**3.7.27-Q2** · `MID`

```python
print('upper' in dir(str), callable(str.lower))
```

**3.7.27-Q3** · `MID`

```python
print(str.upper('abc'), 'abc'.upper(), str.join('-', 'ab'))
```

**3.7.27-Q4** · `HARD`

```python
print(len([n for n in dir(str) if n.startswith('is') and not n.startswith('__')]))
```

**3.7.27-Q5** · `TRAP`

```python
print('abc'.reverse())
```

### 3.7.28 Classic string tasks and idioms

A handful of patterns appear in almost every program: reversing, palindromes, counting characters and words, anagram checks, removing duplicates while keeping order, vowel counting and simple ciphers. Each is a short combination of the tools above.

**Example 3.7.28.1: Reverse, palindrome, anagram**

```python
s = "A man a plan a canal Panama"
clean = "".join(c.lower() for c in s if c.isalnum())
print(clean == clean[::-1])
print("listen"[::-1], sorted("listen") == sorted("silent"))
```

*Output:*

```text
True
netsil True
```

**Example 3.7.28.2: Counting**

```python
from collections import Counter
text = "the cat and the hat and the bat"
words = text.split()
print(len(words), Counter(words).most_common(2))
print(Counter("mississippi").most_common(2), sum(c in "aeiou" for c in "education"))
```

*Output:*

```text
8 [('the', 3), ('and', 2)]
[('i', 4), ('s', 4)] 5
```

**Example 3.7.28.3: Unique characters keeping order; title-case words; Caesar shift**

```python
s = "banana"
print("".join(dict.fromkeys(s)))
print(" ".join(w.capitalize() for w in "the quick brown fox".split()))
shift = lambda t, k: "".join(chr((ord(c) - 97 + k) % 26 + 97) if c.islower() else c for c in t)
print(shift("hello, world", 3), shift(shift("hello", 3), -3))
```

*Output:*

```text
ban
The Quick Brown Fox
khoor, zruog hello
```

#### Practice 3.7.28

**3.7.28-Q1** · `BASIC`

```python
s = 'level'
print(s == s[::-1])
```

**3.7.28-Q2** · `MID`

```python
print(''.join(sorted('hello')), ''.join(dict.fromkeys('hello')))
```

**3.7.28-Q3** · `MID`

```python
print(sum(1 for c in 'Hello World' if c.isupper()), 'Hello World'.swapcase())
```

**3.7.28-Q4** · `HARD`

```python
w = 'the rain in spain'
print(max(w.split(), key=len), ' '.join(x[::-1] for x in w.split()))
```

**3.7.28-Q5** · `TRAP`

```python
from collections import Counter
print(Counter('aabb') == Counter('bbaa'), sorted('aabb') == list('aabb'))
```

### 3.7.29 Performance and memory of strings

Because strings are immutable, `s += piece` in a loop may copy the string every time (CPython sometimes optimises the case but you cannot depend on it). Build a list and `''.join` once. Substring tests with `in` are implemented in C and are very fast. Memory: a str stores 1, 2 or 4 bytes per character depending on the widest character it contains.

> **Key rule:** build large strings with ''.join(parts); `in`, startswith and split are C-speed built-ins.

**Example 3.7.29.1: Memory per character**

```python
import sys
print(sys.getsizeof(""), sys.getsizeof("a"), sys.getsizeof("a" * 10))
for ch in ("a", "é", "€", "\x00"):
    per_char = (sys.getsizeof(ch * 200) - sys.getsizeof(ch * 100)) / 100
    print(ch, ord(ch), "bytes per char:", per_char)
```

*Output:*

```text
41 42 51
a 97 bytes per char: 1.0
é 233 bytes per char: 1.0
€ 8364 bytes per char: 2.0
\x00 128512 bytes per char: 4.0
```

**Example 3.7.29.2: Same result, two ways**

```python
parts = [str(i) for i in range(1000)]
slow = ""
for p in parts:
    slow += p
fast = "".join(parts)
print(slow == fast, len(fast))
```

*Output:*

```text
True 2890
```

**Example 3.7.29.3: Interning is an optimisation, not a promise**

```python
import sys
a = "hello_world"
b = "hello_world"
c = "".join(["hello", "_", "world"])
print(a is b, a == c, sys.intern(c) is a)
```

*Output:*

```text
True True True
```

#### Practice 3.7.29

**3.7.29-Q1** · `BASIC`

```python
print(len(''.join(['ab'] * 3)), 'ab' * 3 == ''.join(['ab'] * 3))
```

**3.7.29-Q2** · `MID`

```python
import sys; print(sys.getsizeof('a' * 100) - sys.getsizeof('a' * 99))
```

**3.7.29-Q3** · `HARD`

```python
s = ''
for i in range(3):
    s += str(i)
print(s, type(s))
```

**3.7.29-Q4** · `TRAP`

```python
import sys
a = 'x y'
b = 'x' + ' y'
print(a == b, sys.intern(a) is sys.intern(b))
```

### 3.7.30 Common string pitfalls

A final checklist of the mistakes beginners make most often. Each row names the mistake, shows what really happens, and gives the fix.

**Pitfall checklist**

| Mistake | What happens | Fix |
|---|---|---|
| `s.upper()` without assignment | s unchanged | `s = s.upper()` |
| `'a' + 1` | TypeError | `'a' + str(1)` or f-string |
| `s[0] = 'x'` | TypeError, immutable | rebuild with slicing |
| `if s.find('x'):` | 0 is falsy, -1 is truthy | `if 'x' in s:` |
| `s.strip('abc')` | removes chars, not a word | `removeprefix` / `removesuffix` |
| `'1,2'.split(',')` then sum | items are strings | `map(int, ...)` |
| `'-5'.isdigit()` | False | try/except around `int()` |
| `'a,b'.split(', ')` | no split (separator is two chars) | split(',') then strip |
| `input()` returned value | always str | `int(input())` |
| comparing text case-sensitively | 'Yes' != 'yes' | `casefold()` both sides |

**Example 3.7.30.1: Four bugs in one program, fixed**

```python
s = "Hello, World"
s = s.upper()                      # assign the result
count = "3" + str(4)               # convert before joining
ok = "x" in s                      # 'in', not find()
total = sum(int(x) for x in "1,2,3".split(","))
print(s, count, ok, total)
```

*Output:*

```text
HELLO, WORLD 34 False 6
```

**Example 3.7.30.2: input() is always a string**

```python
raw = "42"            # what input() would return
print(raw * 2, int(raw) * 2, raw.isdigit(), raw + "1", int(raw) + 1)
```

*Output:*

```text
4242 84 True 421 43
```

#### Practice 3.7.30

**3.7.30-Q1** · `BASIC`

```python
s = 'abc'
s.title()
print(s)
```

**3.7.30-Q2** · `MID`

```python
print('1' + '1', int('1') + int('1'), '1' * 3)
```

**3.7.30-Q3** · `MID`

```python
print('a, b'.split(','), 'a, b'.split(', '), [x.strip() for x in 'a, b'.split(',')])
```

**3.7.30-Q4** · `HARD`

```python
print('5' > '10', 5 > 10, '5' > '1', max('5', '10'), max(5, 10))
```

**3.7.30-Q5** · `TRAP`

```python
s = 'abc'
if s.find('a'):
    print('found a')
else:
    print('not found')
if s.find('c'):
    print('found c')
```

---

## Section 3.8 bytes, bytearray and memoryview

### 3.8.1 bytes: immutable sequences of integers 0-255

A `bytes` object is an immutable sequence of integers in the range 0..255, written `b'...'` (ASCII characters only in the literal; use `\xHH` for others). Indexing gives an INT (not a one-byte bytes), slicing gives bytes. Create from a list of ints with `bytes([72, 105])`, zero-filled with `bytes(5)`, from text with `s.encode()`, or from hex with `bytes.fromhex`.

> **Key rule:** b'abc'[0] is the int 97, but b'abc'[0:1] is b'a'. bytes is for data, str is for text.

**Example 3.8.1.1: Creating bytes**

```python
print(b"hello", bytes([72, 105]), bytes(3), "hi".encode(), bytes.fromhex("48 69 ff"))
print(type(b""), len(b"abc"), b"ab" + b"cd", b"ab" * 2, b"a" in b"abc", 97 in b"abc")
```

*Output:*

```text
b'hello' b'Hi' b'\x00\x00\x00' b'hi' b'Hi\xff'
<class 'bytes'> 3 b'abcd' b'abab' True True
```

**Example 3.8.1.2: Indexing versus slicing**

```python
b = b"abc"
print(b[0], b[-1], b[0:1], b[::-1], list(b), type(b[0]))
for x in b"AB":
    print(x, chr(x))
```

*Output:*

```text
97 99 b'a' b'cba' [97, 98, 99] <class 'int'>
65 A
66 B
```

**Example 3.8.1.3: Conversions**

```python
data = b"\x00\x01\xfe\xff"
print(data.hex(), data.hex("-"), bytes.fromhex("00 01"), int.from_bytes(data, "big"))
print(b"caf\xc3\xa9".decode("utf-8"), str(b"hi"), repr(b"hi\n"))
```

*Output:*

```text
0001feff 00-01-fe-ff b'\x00\x01' 130815
café b'hi' b'hi\n'
```

**Example 3.8.1.4: bytes versus str**

```python
try:
    b"a" + "a"
except TypeError as e:
    print(e)
print(b"a" == "a", "a".encode() == b"a")
```

*Output:*

```text
can't concat str to bytes
False True
```

> ⚠️ **Watch out:** `str(b'hi')` gives "b'hi'", NOT 'hi'. Use `b.decode()`.

#### Practice 3.8.1

**3.8.1-Q1** · `BASIC`

```python
print(b'abc'[0], b'abc'[1:], len(b'abc'))
```

**3.8.1-Q2** · `MID`

```python
print(bytes([65, 66]), bytes(2), list(b'AB'))
```

**3.8.1-Q3** · `MID`

```python
print(b'a' + b'b', b'ab'.hex(), bytes.fromhex('6162'))
```

**3.8.1-Q4** · `HARD`

```python
print(str(b'hi'), b'hi'.decode(), b'hi' == 'hi')
```

**3.8.1-Q5** · `TRAP`

```python
print(bytes([256]))
```

### 3.8.2 bytes methods and bytearray

`bytes` has most `str` methods (find, count, replace, split, join, strip, startswith, upper, lower, isalpha...), working on bytes arguments. `bytearray` is the MUTABLE version: item assignment, `append`, `extend`, `insert`, `pop`, `remove`, `reverse`, `clear`, slicing assignment. Use it to build binary data in place.

> **Key rule:** bytes = immutable, bytearray = mutable; both hold ints 0-255 and share the str-like methods.

**Example 3.8.2.1: str-like methods on bytes**

```python
b = b"Hello, World"
print(b.upper(), b.lower(), b.find(b"o"), b.count(b"l"), b.replace(b"l", b"L"))
print(b.split(b", "), b.startswith(b"He"), b"-".join([b"a", b"b"]), b.strip(b"Hd"))
```

*Output:*

```text
b'HELLO, WORLD' b'hello, world' 4 3 b'HeLLo, WorLd'
[b'Hello', b'World'] True b'a-b' b'ello, Worl'
```

**Example 3.8.2.2: bytearray is mutable**

```python
ba = bytearray(b"abc")
ba[0] = 65
ba.append(100)
ba.extend(b"ef")
ba.insert(1, 66)
print(ba, len(ba))
print(ba.pop(), ba.pop(0), ba)
ba[1:3] = b"XYZ"
print(ba, bytes(ba), type(ba))
```

*Output:*

```text
bytearray(b'ABbcdef') 7
102 65 bytearray(b'Bbcde')
bytearray(b'BXYZde') b'BXYZde' <class 'bytearray'>
```

**Example 3.8.2.3: Bounds are enforced**

```python
ba = bytearray(2)
try:
    ba[0] = 300
except ValueError as e:
    print(e)
print(bytearray([1, 2, 3]).reverse(), bytearray(b"ab") == b"ab")
```

*Output:*

```text
byte must be in range(0, 256)
None True
```

#### Practice 3.8.2

**3.8.2-Q1** · `BASIC`

```python
ba = bytearray(b'ab'); ba.append(99); print(ba)
```

**3.8.2-Q2** · `MID`

```python
ba = bytearray(3); ba[1] = 7; print(list(ba))
```

**3.8.2-Q3** · `MID`

```python
print(b'a,b'.split(b','), b'ab'.upper(), b'  x '.strip())
```

**3.8.2-Q4** · `HARD`

```python
ba = bytearray(b'hello'); ba[0:1] = b'J'; print(ba.decode(), bytes(ba) == b'Jello')
```

**3.8.2-Q5** · `TRAP`

```python
b = b'abc'
b[0] = 65
```

### 3.8.3 memoryview and the buffer protocol

A `memoryview` is a window onto another object's bytes WITHOUT copying. Slicing a memoryview creates a new view of the same memory, so you can hand big binary buffers around cheaply or edit a bytearray through a slice. It needs a bytes-like object (bytes, bytearray, array.array). Release with `release()` or a `with` block.

> **Key rule:** slicing bytes copies; slicing a memoryview shares memory.

**Example 3.8.3.1: A view shares memory**

```python
ba = bytearray(b"abcdef")
mv = memoryview(ba)
mv[0] = ord("X")
sub = mv[2:4]
sub[0] = ord("Z")
print(ba, bytes(sub), sub.tolist(), len(mv), mv.nbytes)
```

*Output:*

```text
bytearray(b'XbZdef') b'Zd' [90, 100] 6 6
```

**Example 3.8.3.2: Copy versus view**

```python
data = bytearray(b"0123456789")
copy = data[2:5]
view = memoryview(data)[2:5]
data[2] = ord("A")
print(bytes(copy), bytes(view))
```

*Output:*

```text
b'234' b'A34'
```

**Example 3.8.3.3: Read-only views and formats**

```python
mv = memoryview(b"abc")
print(mv.readonly, mv.format, mv.itemsize, mv[1])
try:
    mv[0] = 1
except TypeError as e:
    print(e)
import array
a = array.array("i", [1, 2, 3])
print(memoryview(a).tolist(), memoryview(a).itemsize)
```

*Output:*

```text
True B 1 98
cannot modify read-only memory
[1, 2, 3] 4
```

#### Practice 3.8.3

**3.8.3-Q1** · `BASIC`

```python
mv = memoryview(b'ab'); print(mv[0], mv.readonly)
```

**3.8.3-Q2** · `MID`

```python
ba = bytearray(b'abc'); mv = memoryview(ba); mv[1] = 66; print(ba)
```

**3.8.3-Q3** · `HARD`

```python
ba = bytearray(b'abc'); s = ba[:2]; v = memoryview(ba)[:2]; ba[0] = 90; print(s, bytes(v))
```

**3.8.3-Q4** · `TRAP`

```python
ba = bytearray(b'ab'); mv = memoryview(ba); ba.append(99)
```

---

## Section 3.9 list: Lists

### 3.9.1 Creating lists

A list is an ORDERED, MUTABLE sequence that can hold items of any type, including other lists. Create one with brackets `[1, 2, 3]`, with `list(iterable)`, with a comprehension, or by repetition `[0] * n`. `list('abc')` splits a string into characters; `list()` is empty.

> **Key rule:** [] literal, list(iterable), comprehension, or [x] \* n; lists may mix types and nest.

**Example 3.9.1.1: Ways to build a list**

```python
print([1, 2, 3], list("abc"), list(range(4)), list((1, 2)), list({"a": 1}), list())
print([0] * 3, [i * i for i in range(5)], [1, "two", 3.0, None, [5]])
```

*Output:*

```text
[1, 2, 3] ['a', 'b', 'c'] [0, 1, 2, 3] [1, 2] ['a'] []
[0, 0, 0] [0, 1, 4, 9, 16] [1, 'two', 3.0, None, [5]]
```

**Example 3.9.1.2: A list is ordered and allows duplicates**

```python
a = [3, 1, 3]
print(a, len(a), a == [1, 3, 3], a == [3, 1, 3])
```

*Output:*

```text
[3, 1, 3] 3 False True
```

**Example 3.9.1.3: Nested lists**

```python
grid = [[1, 2, 3], [4, 5, 6]]
print(grid[1][2], len(grid), len(grid[0]), grid[0] + grid[1])
```

*Output:*

```text
6 2 3 [1, 2, 3, 4, 5, 6]
```

#### Practice 3.9.1

**3.9.1-Q1** · `BASIC`

```python
print(len([1, [2, 3]]), [1, 2] == [2, 1])
```

**3.9.1-Q2** · `BASIC`

```python
print(list('hi'), list(range(1, 4)), [0] * 2)
```

**3.9.1-Q3** · `MID`

```python
print(list((3,)), [[]], len([[]]), [] == [[]])
```

**3.9.1-Q4** · `HARD`

```python
print(list({'b': 1, 'a': 2}), list({3, 1, 2}), list(map(str, [1, 2])))
```

**3.9.1-Q5** · `TRAP`

```python
print(list(5))
```

### 3.9.2 Indexing and slicing lists

Lists use the same index rules as strings: 0-based from the left, negative from the right, out of range raises IndexError. Slices `a[start:stop:step]` return a NEW list (a shallow copy of the selected part) and never raise. Unlike strings, you can ASSIGN to an index or slice and `del` them.

> **Key rule:** a[i] assigns in place; a[i:j] = iterable can change the length; slicing always returns a new list.

**Example 3.9.2.1: Reading**

```python
a = [10, 20, 30, 40, 50]
print(a[0], a[-1], a[1:3], a[:2], a[-2:], a[::2], a[::-1], a[10:], a[2:2])
```

*Output:*

```text
10 50 [20, 30] [10, 20] [40, 50] [10, 30, 50] [50, 40, 30, 20, 10] [] []
```

**Example 3.9.2.2: Writing: items and slices**

```python
a = [10, 20, 30, 40, 50]
a[0] = 11
a[1:3] = [21, 31, 41]
print(a)
a[::2] = [0, 0, 0]
print(a)
a[1:1] = ["ins"]
print(a)
a[:] = []
print(a)
```

*Output:*

```text
[11, 21, 31, 41, 40, 50]
[0, 21, 0, 41, 0, 50]
[0, 'ins', 21, 0, 41, 0, 50]
[]
```

**Example 3.9.2.3: Slice assignment needs the right size for extended slices**

```python
a = [1, 2, 3, 4]
try:
    a[::2] = [9]
except ValueError as e:
    print(e)
b = a[:]
b.append(5)
print(a, b, a is b, a == b[:4])
```

*Output:*

```text
attempt to assign sequence of size 1 to extended slice of size 2
[1, 2, 3, 4] [1, 2, 3, 4, 5] False True
```

#### Practice 3.9.2

**3.9.2-Q1** · `BASIC`

```python
a = [1, 2, 3, 4]
print(a[1], a[-1], a[1:3])
```

**3.9.2-Q2** · `MID`

```python
a = [1, 2, 3, 4, 5]
print(a[::2], a[::-1], a[1::2], a[-3:-1])
```

**3.9.2-Q3** · `MID`

```python
a = [1, 2, 3]
a[1:2] = [7, 8, 9]
print(a)
```

**3.9.2-Q4** · `HARD`

```python
a = [1, 2, 3, 4]
a[1:3] = []
print(a)
a[1:1] = [5, 6]
print(a)
```

**3.9.2-Q5** · `TRAP`

```python
a = [1, 2, 3]
print(a[3])
```

### 3.9.3 append, extend, insert and the + / += operators

`append(x)` adds ONE item at the end (even if x is a list). `extend(iterable)` adds EACH item. `insert(i, x)` puts x before index i (O(n); i beyond the end appends). `a + b` builds a new list; `a += b` is the same as `a.extend(b)` and mutates in place; `a * n` repeats. All the mutating methods return None.

> **Key rule:** append adds one object, extend adds many; a += b mutates, a = a + b rebinds.

**Example 3.9.3.1: append versus extend**

```python
a = [1, 2]
a.append([3, 4])
print(a, len(a))
b = [1, 2]
b.extend([3, 4])
b.extend("ab")
b.extend(range(2))
print(b)
```

*Output:*

```text
[1, 2, [3, 4]] 3
[1, 2, 3, 4, 'a', 'b', 0, 1]
```

**Example 3.9.3.2: insert**

```python
a = [1, 2, 3]
a.insert(0, "first")
a.insert(2, "mid")
a.insert(100, "end")
a.insert(-1, "before last")
print(a)
```

*Output:*

```text
['first', 1, 'mid', 2, 3, 'before last', 'end']
```

**Example 3.9.3.3: +, += and ***

```python
a = [1, 2]
b = a
a += [3]
print(a, b, a is b)
a = a + [4]
print(a, b, a is b)
print([0] * 3, [1, 2] * 2, [[0]] * 2)
```

*Output:*

```text
[1, 2, 3] [1, 2, 3] True
[1, 2, 3, 4] [1, 2, 3] False
[0, 0, 0] [1, 2, 1, 2] [[0], [0]]
```

**Example 3.9.3.4: Mutating methods return None**

```python
a = [3, 1]
r = a.append(5)
print(r, a)
```

*Output:*

```text
None [3, 1, 5]
```

> ⚠️ **Watch out:** `a = a.append(x)` sets a to None. Never assign the result of a mutating method.

#### Practice 3.9.3

**3.9.3-Q1** · `BASIC`

```python
a = [1]; a.append(2); a.extend([3, 4]); print(a)
```

**3.9.3-Q2** · `MID`

```python
a = [1]; a.append([2, 3]); print(a, len(a))
```

**3.9.3-Q3** · `MID`

```python
a = [1, 2, 3]; a.insert(1, 'x'); a.insert(-1, 'y'); print(a)
```

**3.9.3-Q4** · `HARD`

```python
a = [1]; b = a; a += [2]; a = a + [3]; print(a, b)
```

**3.9.3-Q5** · `TRAP`

```python
a = [1, 2]
a = a.append(3)
print(a)
```

### 3.9.4 remove, pop, del and clear

`remove(x)` deletes the FIRST item equal to x (ValueError if absent). `pop(i=-1)` deletes AND RETURNS the item at index i (IndexError if empty or out of range). `del a[i]` and `del a[i:j]` delete by position; `clear()` empties the list in place (same as `del a[:]`). Deleting while looping forward skips items.

> **Key rule:** remove works by VALUE, pop/del by POSITION; never remove from a list you are iterating over.

**Choosing a deletion tool**

| Want to remove | Use | Returns |
|---|---|---|
| a value (first match) | `a.remove(x)` | None |
| last item | `a.pop()` | the item |
| item at index i | `a.pop(i)` | the item |
| by index, no value needed | `del a[i]` | - |
| a range | `del a[i:j]` | - |
| everything | `a.clear()` | None |

**Example 3.9.4.1: The four tools**

```python
a = [5, 6, 7, 6, 8]
a.remove(6)
print(a)
x = a.pop()
y = a.pop(0)
print(x, y, a)
del a[0]
print(a)
b = [1, 2, 3, 4, 5, 6]
del b[1:3]
del b[::2]
print(b)
b.clear()
print(b)
```

*Output:*

```text
[5, 7, 6, 8]
8 5 [7, 6]
[6]
[4, 6]
[]
```

**Example 3.9.4.2: The errors**

```python
for f in (lambda: [1].remove(9), lambda: [].pop(), lambda: [1, 2].pop(5)):
    try:
        f()
    except (ValueError, IndexError) as e:
        print(type(e).__name__, "-", e)
```

*Output:*

```text
ValueError - list.remove(x): x not in list
IndexError - pop from empty list
IndexError - pop index out of range
```

**Example 3.9.4.3: Deleting while iterating skips items**

```python
a = [1, 2, 2, 3, 2]
for x in a:
    if x == 2:
        a.remove(x)
print(a)
b = [1, 2, 2, 3, 2]
print([x for x in b if x != 2])
c = [1, 2, 2, 3, 2]
c[:] = [x for x in c if x != 2]
print(c)
```

*Output:*

```text
[1, 3, 2]
[1, 3]
[1, 3]
```

#### Practice 3.9.4

**3.9.4-Q1** · `BASIC`

```python
a = [1, 2, 3]; a.remove(2); print(a)
```

**3.9.4-Q2** · `MID`

```python
a = [1, 2, 3, 4]; print(a.pop(), a.pop(0), a)
```

**3.9.4-Q3** · `MID`

```python
a = [1, 2, 1, 2]; a.remove(2); print(a)
```

**3.9.4-Q4** · `HARD`

```python
a = [1, 2, 3, 4, 5, 6]
del a[::2]
print(a)
```

**3.9.4-Q5** · `TRAP`

```python
a = [1, 1, 2, 2]
for x in a:
    if x == 1:
        a.remove(x)
print(a)
```

### 3.9.5 index, count and membership

`index(x[, start[, end]])` returns the position of the FIRST x and raises ValueError if absent. `count(x)` returns how many items equal x. `x in a` tests membership by scanning (O(n)); equality decides, so `1 in` `[True]` and `1 in [1.0]` are True. For many lookups convert to a set first.

> **Key rule:** index raises when missing; use `in` first or catch ValueError; `in` on a list is a linear scan.

**Example 3.9.5.1: Searching**

```python
a = [4, 2, 7, 2, 9]
print(a.index(2), a.index(2, 2), a.count(2), a.count(99), 7 in a, 8 not in a)
try:
    a.index(99)
except ValueError as e:
    print(e)
```

*Output:*

```text
1 3 2 0 True True
99 is not in list
```

**Example 3.9.5.2: Equality decides, identity is only a shortcut**

```python
print(1 in [1.0], True in [1], 0 in [False], "1" in [1])
nan = float("nan")
print(nan in [nan], float("nan") in [nan])
print([1, 2] in [[1, 2], [3]], (1, 2) in [[1, 2]])
```

*Output:*

```text
True True True False
True False
True False
```

**Example 3.9.5.3: Finding all positions**

```python
a = ["x", "y", "x", "z", "x"]
print([i for i, v in enumerate(a) if v == "x"])
big = list(range(100000))
fast = set(big)
print(99999 in big, 99999 in fast)
```

*Output:*

```text
[0, 2, 4]
True True
```

#### Practice 3.9.5

**3.9.5-Q1** · `BASIC`

```python
a = ['a', 'b', 'c', 'b']
print(a.index('b'), a.count('b'), 'z' in a)
```

**3.9.5-Q2** · `MID`

```python
a = [1, 2, 3, 2, 1]
print(a.index(1, 1), a.count(1))
```

**3.9.5-Q3** · `MID`

```python
print(1 in [1.0], 2 in ['2'], [1] in [[1]])
```

**3.9.5-Q4** · `HARD`

```python
a = [[1, 2], [3]]
print(a.count([1, 2]), a.index([3]), 3 in a)
```

**3.9.5-Q5** · `TRAP`

```python
print([1, 2].index(3))
```

### 3.9.6 sort, sorted, reverse, reversed

`a.sort()` sorts IN PLACE and returns None; `sorted(iterable)` returns a NEW sorted list from any iterable. Both accept `key=` (a function giving the sort value) and `reverse=True`. The sort is STABLE: equal items keep their original order, which allows multi-pass sorting. `a.reverse()` flips in place; `reversed(a)` returns an iterator. Items must be comparable: mixing str and int raises TypeError.

> **Key rule:** sort() mutates and returns None; sorted() returns a new list; stable sort lets you sort by several keys in passes.

**Example 3.9.6.1: sort versus sorted**

```python
a = [3, 1, 2]
print(sorted(a), a)
r = a.sort()
print(r, a)
a.sort(reverse=True)
print(a, sorted("banana"), sorted({3: "c", 1: "a"}))
```

*Output:*

```text
[1, 2, 3] [3, 1, 2]
None [1, 2, 3]
[3, 2, 1] ['a', 'a', 'a', 'b', 'n', 'n'] [1, 3]
```

**Example 3.9.6.2: key functions**

```python
words = ["pear", "fig", "banana", "kiwi"]
print(sorted(words, key=len))
print(sorted(words, key=lambda w: (len(w), w)))
print(sorted(words, key=lambda w: w[-1], reverse=True))
pairs = [("b", 2), ("a", 2), ("c", 1)]
print(sorted(pairs, key=lambda p: p[1]), sorted(pairs, key=lambda p: (-p[1], p[0])))
```

*Output:*

```text
['fig', 'pear', 'kiwi', 'banana']
['fig', 'kiwi', 'pear', 'banana']
['pear', 'kiwi', 'fig', 'banana']
[('c', 1), ('b', 2), ('a', 2)] [('a', 2), ('b', 2), ('c', 1)]
```

**Example 3.9.6.3: Stability: two-pass sort**

```python
people = [("Ann", 30), ("Bo", 25), ("Cy", 30), ("Di", 25)]
people.sort(key=lambda p: p[0], reverse=True)
people.sort(key=lambda p: p[1])
print(people)
```

*Output:*

```text
[('Di', 25), ('Bo', 25), ('Cy', 30), ('Ann', 30)]
```

**Example 3.9.6.4: reverse and reversed**

```python
a = [1, 2, 3]
print(list(reversed(a)), a[::-1], a)
a.reverse()
print(a)
try:
    sorted([3, "a"])
except TypeError as e:
    print(e)
```

*Output:*

```text
[3, 2, 1] [3, 2, 1] [1, 2, 3]
[3, 2, 1]
'<' not supported between instances of 'str' and 'int'
```

#### Practice 3.9.6

**3.9.6-Q1** · `BASIC`

```python
a = [3, 1, 2]; a.sort(); print(a)
```

**3.9.6-Q2** · `BASIC`

```python
a = [3, 1, 2]; print(sorted(a, reverse=True), a)
```

**3.9.6-Q3** · `MID`

```python
print(sorted(['b', 'A', 'a', 'B']), sorted(['b', 'A', 'a', 'B'], key=str.lower))
```

**3.9.6-Q4** · `HARD`

```python
print(sorted([3, -1, 2, -5], key=abs), sorted([3, -1, 2, -5], key=lambda x: -x))
```

**3.9.6-Q5** · `TRAP`

```python
a = [2, 1]
b = a.sort()
print(b is None, a)
print(sorted([1, 'a']))
```

### 3.9.7 copy: alias, shallow copy and deep copy

`b = a` creates a second NAME for the same list. `a.copy()`, `a[:]` and `list(a)` create a NEW outer list that shares the same inner objects (shallow copy). For nested mutable items use `copy.deepcopy(a)`. The repetition `[[0]] * 3` creates three references to ONE inner list, which is the commonest list bug.

> **Key rule:** shallow copy duplicates the container only; nested lists need deepcopy, and [[0]] \* n shares one row.

**Which copy do I get?**

| Code | New outer list? | Inner objects shared? |
|---|---|---|
| `b = a` | no (alias) | - |
| `b = a.copy()` | yes | yes |
| `b = a[:]` | yes | yes |
| `b = list(a)` | yes | yes |
| `b = copy.deepcopy(a)` | yes | no |

**Example 3.9.7.1: Alias versus copy**

```python
a = [1, 2, 3]
alias = a
copy1 = a.copy()
alias.append(4)
print(a, alias, copy1, a is alias, a is copy1)
```

*Output:*

```text
[1, 2, 3, 4] [1, 2, 3, 4] [1, 2, 3] True False
```

**Example 3.9.7.2: Shallow copies share inner lists**

```python
import copy
a = [[1, 2], [3]]
shallow = a.copy()
deep = copy.deepcopy(a)
a[0].append(99)
print(a, shallow, deep)
```

*Output:*

```text
[[1, 2, 99], [3]] [[1, 2, 99], [3]] [[1, 2], [3]]
```

**Example 3.9.7.3: The repeated-row bug**

```python
grid = [[0] * 3] * 2
grid[0][0] = 1
print(grid, grid[0] is grid[1])
good = [[0] * 3 for _ in range(2)]
good[0][0] = 1
print(good, good[0] is good[1])
```

*Output:*

```text
[[1, 0, 0], [1, 0, 0]] True
[[1, 0, 0], [0, 0, 0]] False
```

#### Practice 3.9.7

**3.9.7-Q1** · `BASIC`

```python
a = [1]; b = a; b.append(2); print(a)
```

**3.9.7-Q2** · `MID`

```python
a = [1]; b = a[:]; b.append(2); print(a, b)
```

**3.9.7-Q3** · `MID`

```python
a = [[1], [2]]; b = a.copy(); b[0].append(9); print(a)
```

**3.9.7-Q4** · `HARD`

```python
import copy
a = [[1], [2]]
b = copy.deepcopy(a)
b[0].append(9)
print(a, b)
```

**3.9.7-Q5** · `TRAP`

```python
g = [[0] * 2] * 2
g[1][1] = 5
print(g)
```

### 3.9.8 Operators: +, \*, in, comparison and unpacking

`+` concatenates two lists (both must be lists), `*` repeats, `==` compares element by element, and `<`, `>` compare lexicographically (first differing item decides, a prefix is smaller). `min`, `max`, `sum`, `len`, `any`, `all` work on lists. Unpacking `a, b, *rest = lst` spreads items into names; `*` in a literal splices another iterable.

> **Key rule:** lists compare lexicographically like strings; star-unpacking always gives a list.

**Example 3.9.8.1: Comparison**

```python
print([1, 2] == [1, 2], [1, 2] < [1, 3], [1, 2] < [1, 2, 0], [2] > [1, 99], [] < [0])
print([1, "a"] == [1, "a"], [1, 2] != [2, 1])
```

*Output:*

```text
True True True True True
True True
```

**Example 3.9.8.2: Reducers**

```python
a = [4, 9, 2]
print(len(a), min(a), max(a), sum(a), sorted(a), any(a), all(a), sum(a) / len(a))
```

*Output:*

```text
3 2 9 15 [2, 4, 9] True True 5.0
```

**Example 3.9.8.3: Unpacking**

```python
a, b, c = [1, 2, 3]
first, *rest = [1, 2, 3, 4]
*init, last = [1, 2, 3, 4]
head, *mid, tail = [1, 2, 3, 4, 5]
print(a, b, c, first, rest, init, last, head, mid, tail)
x, *y = [1]
print(x, y, [*[1, 2], *"ab", *range(2)])
try:
    p, q = [1, 2, 3]
except ValueError as e:
    print(e)
```

*Output:*

```text
1 2 3 1 [2, 3, 4] [1, 2, 3] 4 1 [2, 3, 4] 5
1 [] [1, 2, 'a', 'b', 0, 1]
too many values to unpack (expected 2)
```

#### Practice 3.9.8

**3.9.8-Q1** · `BASIC`

```python
print([1, 2] + [3], [0] * 3, [1, 2] == [1, 2])
```

**3.9.8-Q2** · `MID`

```python
print([1, 2, 3] < [1, 2, 4], [1, 2] < [1, 2, 0], [3] > [2, 9, 9])
```

**3.9.8-Q3** · `MID`

```python
a, *b = [1, 2, 3]
print(a, b)
```

**3.9.8-Q4** · `HARD`

```python
a, *b, c = [1, 2]
print(a, b, c)
```

**3.9.8-Q5** · `TRAP`

```python
print([1, 2] + (3,))
```

### 3.9.9 List comprehensions

`[expr for x in iterable if cond]` builds a list in one expression. Read it as: for each x, keep it if cond, and collect expr. Multiple `for` clauses nest left to right. A conditional expression `a if c else b` goes BEFORE the for; a filter `if` goes AFTER it. The loop variable stays local to the comprehension (it does not leak in Python 3).

> **Key rule:** [value for x in src if keep] filters; [a if c else b for x in src] transforms. Filter-if goes last, ternary goes first.

**Example 3.9.9.1: Map and filter**

```python
nums = range(10)
print([n * n for n in nums], [n for n in nums if n % 3 == 0], [n * n for n in nums if n % 2])
print(["even" if n % 2 == 0 else "odd" for n in range(4)])
```

*Output:*

```text
[0, 1, 4, 9, 16, 25, 36, 49, 64, 81] [0, 3, 6, 9] [1, 9, 25, 49, 81]
['even', 'odd', 'even', 'odd']
```

**Example 3.9.9.2: Nested loops and flattening**

```python
pairs = [(x, y) for x in "ab" for y in (1, 2)]
print(pairs)
grid = [[1, 2], [3, 4], [5]]
print([v for row in grid for v in row], [[v * 2 for v in row] for row in grid])
print([[r * c for c in range(1, 4)] for r in range(1, 4)])
```

*Output:*

```text
[('a', 1), ('a', 2), ('b', 1), ('b', 2)]
[1, 2, 3, 4, 5] [[2, 4], [6, 8], [10]]
[[1, 2, 3], [2, 4, 6], [3, 6, 9]]
```

**Example 3.9.9.3: Scope and comparison with a loop**

```python
x = "outer"
squares = [x * x for x in range(3)]
print(x, squares)
out = []
for n in range(3):
    out.append(n * n)
print(out == squares, [c for c in "Hello World" if c.isupper()])
```

*Output:*

```text
outer [0, 1, 4]
True ['H', 'W']
```

#### Practice 3.9.9

**3.9.9-Q1** · `BASIC`

```python
print([i * 2 for i in range(4)])
```

**3.9.9-Q2** · `MID`

```python
print([c for c in 'a1b2' if c.isdigit()], [int(c) for c in '123'])
```

**3.9.9-Q3** · `MID`

```python
print([x if x > 0 else 0 for x in [-1, 2, -3]])
```

**3.9.9-Q4** · `HARD`

```python
print([(i, j) for i in range(3) for j in range(i)])
```

**3.9.9-Q5** · `TRAP`

```python
print([x for x in range(5) if x % 2 else -x])
```

### 3.9.10 Nested lists and matrices

A list of lists models a table. `m[r][c]` reads row r, column c. Build rows with a comprehension so each is a separate list. Transpose with `zip(*m)`. Flatten with a nested comprehension or `itertools.chain`. Iterate rows with `for row in m` and cells with a second loop.

> **Key rule:** build grids with [[0] \* cols for _ in range(rows)]; transpose with list(zip(\*m)).

**Example 3.9.10.1: Create, read, write**

```python
rows, cols = 2, 3
m = [[0] * cols for _ in range(rows)]
m[0][1] = 5
m[1][2] = 7
print(m, m[1][2], len(m), len(m[0]))
```

*Output:*

```text
[[0, 5, 0], [0, 0, 7]] 7 2 3
```

**Example 3.9.10.2: Transpose, sums, flatten**

```python
m = [[1, 2, 3], [4, 5, 6]]
t = [list(r) for r in zip(*m)]
print(t)
print([sum(r) for r in m], [sum(c) for c in zip(*m)], sum(sum(r) for r in m))
import itertools
print(list(itertools.chain.from_iterable(m)), [v for r in m for v in r])
```

*Output:*

```text
[[1, 4], [2, 5], [3, 6]]
[6, 15] [5, 7, 9] 21
[1, 2, 3, 4, 5, 6] [1, 2, 3, 4, 5, 6]
```

**Example 3.9.10.3: Printing a grid**

```python
m = [[1, 20, 3], [400, 5, 6]]
for r in m:
    print(" ".join(f"{v:>4}" for v in r))
```

*Output:*

```text
   1   20    3
 400    5    6
```

#### Practice 3.9.10

**3.9.10-Q1** · `BASIC`

```python
m = [[1, 2], [3, 4]]
print(m[0][1], m[1][0], len(m))
```

**3.9.10-Q2** · `MID`

```python
m = [[1, 2], [3, 4]]
print(list(zip(*m)), [r[::-1] for r in m])
```

**3.9.10-Q3** · `HARD`

```python
m = [[1, 2, 3], [4, 5, 6]]
print([[r[i] for r in m] for i in range(3)])
```

**3.9.10-Q4** · `TRAP`

```python
m = [[0] * 2] * 2
m[0][0] = 1
print(m)
```

### 3.9.11 Lists as stacks and queues; deque

A STACK (last in, first out) uses `append` and `pop()`: both are O(1) at the end. A QUEUE (first in, first out) built with `pop(0)` is O(n) because every item shifts; use `collections.deque` with `append` and `popleft` for O(1) at both ends. `deque(maxlen=n)` keeps only the last n items.

> **Key rule:** stack: list.append / list.pop; queue: deque.append / deque.popleft.

**Example 3.9.11.1: Stack**

```python
stack = []
for x in [1, 2, 3]:
    stack.append(x)
print(stack, stack.pop(), stack.pop(), stack)
print(stack[-1] if stack else "empty")
```

*Output:*

```text
[1] 3 2 [1]
1
```

**Example 3.9.11.2: Queue with deque**

```python
from collections import deque
q = deque([1, 2, 3])
q.append(4)
print(q.popleft(), q.popleft(), q, len(q))
q.appendleft(0)
q.rotate(1)
print(q, list(q))
```

*Output:*

```text
1 2 deque([3, 4]) 2
deque([4, 0, 3]) [4, 0, 3]
```

**Example 3.9.11.3: Bounded history and a bracket matcher**

```python
from collections import deque
last3 = deque(maxlen=3)
for i in range(6):
    last3.append(i)
print(last3)
def balanced(s):
    st = []
    pair = {")": "(", "]": "[", "}": "{"}
    for ch in s:
        if ch in "([{":
            st.append(ch)
        elif ch in pair:
            if not st or st.pop() != pair[ch]:
                return False
    return not st
print(balanced("{[()]}"), balanced("([)]"), balanced("(("))
```

*Output:*

```text
deque([3, 4, 5], maxlen=3)
True False False
```

#### Practice 3.9.11

**3.9.11-Q1** · `BASIC`

```python
s = [1, 2]; s.append(3); print(s.pop(), s)
```

**3.9.11-Q2** · `MID`

```python
from collections import deque
q = deque([1, 2, 3]); q.append(4); print(q.popleft(), list(q))
```

**3.9.11-Q3** · `MID`

```python
from collections import deque
d = deque(maxlen=2)
for i in range(5): d.append(i)
print(list(d))
```

**3.9.11-Q4** · `HARD`

```python
from collections import deque
d = deque([1, 2, 3, 4]); d.rotate(1); print(list(d)); d.rotate(-2); print(list(d))
```

**3.9.11-Q5** · `TRAP`

```python
s = []
s.pop()
```

### 3.9.12 enumerate, zip, map, filter and unpacking with lists

`enumerate(a, start=0)` gives (index, item) pairs. `zip(a, b)` pairs items and STOPS at the shortest (use `zip(..., strict=True)` to raise on a length mismatch, 3.10+, or `itertools.zip_longest`). `map(f, a)` and `filter(f, a)` are LAZY iterators; wrap in `list()` to see them. `zip(*pairs)` unzips.

> **Key rule:** zip stops at the shortest input; map and filter are lazy and one-shot.

**Example 3.9.12.1: enumerate and zip**

```python
names = ["Ann", "Bo", "Cy"]
ages = [30, 25]
print(list(enumerate(names, 1)))
print(list(zip(names, ages)))
print(dict(zip(names, ages)))
import itertools
print(list(itertools.zip_longest(names, ages, fillvalue="?")))
try:
    list(zip(names, ages, strict=True))
except ValueError as e:
    print(e)
```

*Output:*

```text
[(1, 'Ann'), (2, 'Bo'), (3, 'Cy')]
[('Ann', 30), ('Bo', 25)]
{'Ann': 30, 'Bo': 25}
[('Ann', 30), ('Bo', 25), ('Cy', '?')]
zip() argument 2 is shorter than argument 1
```

**Example 3.9.12.2: map, filter, unzip**

```python
a = [1, 2, 3, 4]
print(list(map(lambda x: x * x, a)), list(filter(lambda x: x % 2, a)), list(map(str, a)))
pairs = [(1, "a"), (2, "b")]
nums, letters = zip(*pairs)
print(nums, letters)
m = map(str, a)
print(list(m), list(m))
```

*Output:*

```text
[1, 4, 9, 16] [1, 3] ['1', '2', '3', '4']
(1, 2) ('a', 'b')
['1', '2', '3', '4'] []
```

#### Practice 3.9.12

**3.9.12-Q1** · `BASIC`

```python
print(list(enumerate('ab')), list(zip([1, 2], 'ab')))
```

**3.9.12-Q2** · `MID`

```python
print(list(zip([1, 2, 3], 'ab')), list(map(len, ['a', 'bb'])))
```

**3.9.12-Q3** · `MID`

```python
print(list(filter(None, [0, 1, '', 'a', None])))
```

**3.9.12-Q4** · `HARD`

```python
m = map(int, ['1', '2'])
print(list(m), list(m))
```

**3.9.12-Q5** · `TRAP`

```python
print(list(zip([1, 2], 'abc', strict=True)))
```

### 3.9.13 min, max, sum, len, any, all and statistics on lists

The built-ins `len`, `min`, `max`, `sum`, `any`, `all`, `sorted` cover most list analysis. `min` / `max` accept `key=` and `default=`. The `statistics` module adds `mean`, `median`, `mode`, `stdev`, `variance`. For exact float totals use `math.fsum`.

**Example 3.9.13.1: Built-ins**

```python
a = [4, 8, 15, 16, 23, 42]
print(len(a), min(a), max(a), sum(a), sum(a) / len(a), max(a) - min(a))
print(max(a, key=lambda x: x % 10), min([], default=None), sorted(a)[len(a) // 2])
```

*Output:*

```text
6 4 42 108 18.0 38
8 None 16
```

**Example 3.9.13.2: statistics module**

```python
import statistics as st
data = [2, 4, 4, 4, 5, 5, 7, 9]
print(st.mean(data), st.median(data), st.mode(data), st.pstdev(data), st.variance(data))
print(st.median([1, 3, 5, 7]), st.median_low([1, 3, 5, 7]), st.multimode([1, 1, 2, 2]))
```

*Output:*

```text
5 4.5 4 2.0 4.571428571428571
4.0 3 [1, 2]
```

#### Practice 3.9.13

**3.9.13-Q1** · `BASIC`

```python
a = [3, 9, 6]
print(sum(a), min(a), max(a), len(a))
```

**3.9.13-Q2** · `MID`

```python
import statistics as s; print(s.mean([1, 2, 3, 4]), s.median([5, 1, 3]))
```

**3.9.13-Q3** · `HARD`

```python
import statistics as s; print(s.median([1, 2, 3, 4]), s.mode(['a', 'b', 'a']))
```

**3.9.13-Q4** · `TRAP`

```python
import statistics as s; print(s.mean([]))
```

### 3.9.14 Mutation during iteration and other aliasing traps

Never change the SIZE of a list while a `for` loop walks it: the loop index keeps moving, so items are skipped. Iterate over a COPY (`for x in a[:]`) or build a new list. Also remember: a function receives a reference, so `def f(l): l.append(1)` changes the caller's list; and mutable default arguments persist between calls.

> **Key rule:** iterate over a copy or build a new list; mutating methods on a parameter change the caller's list.

**Example 3.9.14.1: Skipped items**

```python
a = [1, 2, 3, 4, 5, 6]
for x in a:
    if x % 2 == 0:
        a.remove(x)
print(a)
b = [1, 2, 3, 4, 5, 6]
for x in b[:]:
    if x % 2 == 0:
        b.remove(x)
print(b)
```

*Output:*

```text
[1, 3, 5]
[1, 3, 5]
```

**Example 3.9.14.2: Appending while iterating never ends**

```python
a = [1, 2]
n = 0
for x in a:
    a.append(x)
    n += 1
    if n >= 5:
        break
print(a, n)
```

*Output:*

```text
[1, 2, 1, 2, 1, 2, 1] 5
```

**Example 3.9.14.3: Functions share your list**

```python
def add_one(l):
    l.append(1)
def add_one_safe(l):
    l = l + [1]
    return l
a = []
add_one(a); add_one(a)
print(a)
b = []
add_one_safe(b); print(b)
```

*Output:*

```text
[1, 1]
[]
```

#### Practice 3.9.14

**3.9.14-Q1** · `BASIC`

```python
a = [1, 2]; b = a; b.append(3); print(a)
```

**3.9.14-Q2** · `MID`

```python
a = [1, 2, 3, 4]
for x in a[:]:
    if x > 2: a.remove(x)
print(a)
```

**3.9.14-Q3** · `HARD`

```python
a = [0, 1, 2, 3]
for i, x in enumerate(a):
    if x == 1: a.pop(i)
print(a)
```

**3.9.14-Q4** · `TRAP`

```python
a = [1, 2, 3]
for x in a:
    a.remove(x)
print(a)
```

### 3.9.15 Performance of list operations

Lists are dynamic arrays. Index, `append`, `pop()` from the end are O(1); `insert(0, x)`, `pop(0)`, `remove`, `index`, `in`, `count` are O(n); `sort` is O(n log n); slicing is O(k). Use a `set` for fast membership, a `deque` for queues, `bisect` for sorted lists, and `array` or NumPy for huge numeric data.

**Big-O of list operations**

| Operation | Cost | Operation | Cost |
|---|---|---|---|
| `a[i]`, `a[i] = x` | O(1) | `x in a`, `a.index(x)` | O(n) |
| `a.append(x)` | O(1) amortised | `a.insert(i, x)` | O(n) |
| `a.pop()` | O(1) | `a.pop(0)`, `a.remove(x)` | O(n) |
| `len(a)` | O(1) | `a.sort()` | O(n log n) |
| `a[i:j]` | O(j - i) | `a + b`, `a.copy()` | O(n) |

**Example 3.9.15.1: bisect on a sorted list**

```python
import bisect
a = [10, 20, 30, 40]
print(bisect.bisect_left(a, 25), bisect.bisect_right(a, 30), bisect.bisect_left(a, 30))
bisect.insort(a, 25)
print(a)
```

*Output:*

```text
2 3 2
[10, 20, 25, 30, 40]
```

**Example 3.9.15.2: Over-allocation**

```python
import sys
a = []
sizes = []
for i in range(10):
    a.append(i)
    sizes.append(sys.getsizeof(a))
print(sorted(set(sizes)))
print(sys.getsizeof([]), sys.getsizeof([0] * 10))
```

*Output:*

```text
[88, 120, 184]
56 136
```

#### Practice 3.9.15

**3.9.15-Q1** · `BASIC`

```python
import bisect; print(bisect.bisect_left([1, 3, 5], 4))
```

**3.9.15-Q2** · `MID`

```python
import bisect; a = [1, 3, 5]; bisect.insort(a, 4); print(a)
```

**3.9.15-Q3** · `HARD`

```python
import bisect; print(bisect.bisect_left([1, 2, 2, 3], 2), bisect.bisect_right([1, 2, 2, 3], 2))
```

### 3.9.16 Complete reference: all 11 list methods

A list has exactly eleven public methods. Every one is covered above; this table is the one-page summary, checked against `dir(list)`.

**All list methods**

| Method | Does | Returns | Topic |
|---|---|---|---|
| `append(x)` | add x at the end | None | 3.9.3 |
| `clear()` | remove all items | None | 3.9.4 |
| `copy()` | shallow copy | new list | 3.9.7 |
| `count(x)` | number of items equal to x | int | 3.9.5 |
| `extend(it)` | add each item of it | None | 3.9.3 |
| `index(x, s, e)` | position of first x | int or ValueError | 3.9.5 |
| `insert(i, x)` | insert x before index i | None | 3.9.3 |
| `pop(i=-1)` | remove and return item i | the item | 3.9.4 |
| `remove(x)` | remove first x | None or ValueError | 3.9.4 |
| `reverse()` | reverse in place | None | 3.9.6 |
| `sort(key, reverse)` | sort in place | None | 3.9.6 |

**Example 3.9.16.1: Confirm the list from Python**

```python
names = [n for n in dir(list) if not n.startswith("_")]
print(len(names))
print(names)
```

*Output:*

```text
11
['append', 'clear', 'copy', 'count', 'extend', 'index', 'insert', 'pop', 'remove', 'reverse', 'sort']
```

#### Practice 3.9.16

**3.9.16-Q1** · `BASIC`

```python
print(len([n for n in dir(list) if not n.startswith('_')]))
```

**3.9.16-Q2** · `MID`

```python
a = [3, 1, 2]
print(a.copy() == a, a.copy() is a, a.sort(), a)
```

**3.9.16-Q3** · `HARD`

```python
a = [1, 2]
print(a.append(3), a.extend([4]), a.insert(0, 0), a.pop(), a)
```

**3.9.16-Q4** · `TRAP`

```python
a = [1, 2, 3]
print(a.remove(2) or a)
```

### 3.9.17 Common list pitfalls

A last checklist for lists: aliasing, shared rows, mutating while iterating, assigning the None result of a mutating method, shallow copies, mutable defaults, and confusing `append` with `extend`.

**Pitfall checklist**

| Mistake | Result | Fix |
|---|---|---|
| `b = a` | same list | `b = a.copy()` |
| `[[0]] * n` | n references to one row | comprehension |
| `a = a.sort()` | a is None | `a.sort()` or `a = sorted(a)` |
| `a.append(1, 2)` | TypeError | `extend` or `append((1, 2))` |
| `for x in a: a.remove(x)` | items skipped | iterate a copy |
| `def f(l=[])` | list shared across calls | `l=None` |
| `a[len(a)]` | IndexError | `a[-1]`, check `if a` |
| `a + 5` | TypeError | `a + [5]` |

**Example 3.9.17.1: Three bugs fixed**

```python
a = [3, 1, 2]
b = sorted(a)
rows = [[0] * 2 for _ in range(2)]
rows[0][0] = 1
clean = [x for x in a if x != 1]
print(a, b, rows, clean)
```

*Output:*

```text
[3, 1, 2] [1, 2, 3] [[1, 0], [0, 0]] [3, 2]
```

#### Practice 3.9.17

**3.9.17-Q1** · `BASIC`

```python
a = [1, 2]; a.append([3]); print(len(a))
```

**3.9.17-Q2** · `MID`

```python
a = [1, 2]; a.extend('34'); print(a)
```

**3.9.17-Q3** · `HARD`

```python
a = [1, 2, 3]
b = a
a = a + [4]
b += [5]
print(a, b)
```

**3.9.17-Q4** · `TRAP`

```python
a = [1, 2]
a.append(3, 4)
```

---

## Section 3.10 tuple: Tuples

### 3.10.1 Creating tuples

A tuple is an ORDERED, IMMUTABLE sequence. It is created by COMMAS, not parentheses: `1, 2` is a tuple. The parentheses are only grouping. A one-item tuple needs a trailing comma `(1,)`; `(1)` is just the number 1. `()` is the empty tuple, and `tuple(iterable)` converts any iterable.

> **Key rule:** the comma makes the tuple; (1) is an int, (1,) is a tuple.

**Example 3.10.1.1: Forms**

```python
a = 1, 2, 3
b = (1, 2, 3)
c = (1,)
d = 1,
e = ()
print(a == b, c == d, e, tuple("ab"), tuple([1, 2]), tuple(range(3)), tuple())
print(type(c), type((1)), type(e), len(e))
```

*Output:*

```text
True True () ('a', 'b') (1, 2) (0, 1, 2) ()
<class 'tuple'> <class 'int'> <class 'tuple'> 0
```

**Example 3.10.1.2: Mixed and nested**

```python
t = (1, "two", 3.0, [4, 5], (6, 7))
print(len(t), t[3], t[4][1], t[-1])
```

*Output:*

```text
5 [4, 5] 7 (6, 7)
```

**Example 3.10.1.3: Packing and unpacking**

```python
pt = 3, 4
x, y = pt
print(pt, x, y)
a, (b, c), d = 1, (2, 3), 4
print(a, b, c, d)
first, *rest = (1, 2, 3)
print(first, rest, type(rest))
```

*Output:*

```text
(3, 4) 3 4
1 2 3 4
1 [2, 3] <class 'list'>
```

#### Practice 3.10.1

**3.10.1-Q1** · `BASIC`

```python
print(type((1, 2)), type((1,)), type((1)))
```

**3.10.1-Q2** · `BASIC`

```python
t = 5, 6, 7
print(t, len(t), t[0])
```

**3.10.1-Q3** · `MID`

```python
print(tuple('abc'), tuple([1, [2]]), tuple({'a': 1}))
```

**3.10.1-Q4** · `HARD`

```python
a, *b = (1, 2, 3)
print(a, b, type(b))
```

**3.10.1-Q5** · `TRAP`

```python
x = 1,
y = (1)
z = (1,)
print(x == z, x == y, type(y))
```

### 3.10.2 Indexing, slicing, operators and methods

Tuples support everything a list does that does NOT modify: indexing, slicing (returns a tuple), `+`, `*`, `in`, `len`, `min`, `max`, `sum`, `sorted` (returns a LIST), comparison. A tuple has exactly TWO methods: `count` and `index`.

> **Key rule:** a tuple has only count and index; sorted(tuple) returns a list.

**The two tuple methods**

| Method | Does | Example |
|---|---|---|
| `t.count(x)` | occurrences of x | `(1, 2, 1).count(1)` -> 2 |
| `t.index(x, s, e)` | position of first x, else ValueError | `(5, 6).index(6)` -> 1 |

**Example 3.10.2.1: Everything read-only works**

```python
t = (10, 20, 30, 40, 50)
print(t[0], t[-1], t[1:3], t[::2], t[::-1], t + (60,), t * 2 == t + t)
print(20 in t, len(t), min(t), max(t), sum(t), t.count(20), t.index(30))
print(sorted((3, 1, 2)), tuple(sorted((3, 1, 2))), (1, 2) < (1, 3), (1, 2) < (1, 2, 0))
```

*Output:*

```text
10 50 (20, 30) (10, 30, 50) (50, 40, 30, 20, 10) (10, 20, 30, 40, 50, 60) True
True 5 10 50 150 1 2
[1, 2, 3] (1, 2, 3) True True
```

**Example 3.10.2.2: The methods**

```python
t = (1, 2, 1, 3)
print(t.count(1), t.index(3), t.index(1, 1))
try:
    t.index(9)
except ValueError as e:
    print(e)
print(sorted(dir(tuple))[-2:], [n for n in dir(tuple) if not n.startswith("_")])
```

*Output:*

```text
2 3 2
tuple.index(x): x not in tuple
['count', 'index'] ['count', 'index']
```

#### Practice 3.10.2

**3.10.2-Q1** · `BASIC`

```python
t = (1, 2, 3, 4)
print(t[1], t[-1], t[1:3], t.count(2))
```

**3.10.2-Q2** · `MID`

```python
print((1, 2) + (3,), (1, 2) * 2, (1, 2) < (1, 3))
```

**3.10.2-Q3** · `MID`

```python
print(sorted((3, 1, 2)), type(sorted((3, 1, 2))), max((1, 5, 2)))
```

**3.10.2-Q4** · `HARD`

```python
print((1, 'a') < (1, 'b'), (2,) > (1, 99, 99), () < (0,))
```

**3.10.2-Q5** · `TRAP`

```python
print((1, 2) + [3])
```

### 3.10.3 Immutability: what is and is not frozen

You cannot rebind an item (`t[0] = x`), delete one, or append. But immutability is SHALLOW: a tuple holds REFERENCES, so a mutable object inside (a list) can still change. A tuple is hashable only if every item is hashable.

> **Key rule:** tuple immutability protects the references, not the objects they point to.

**Example 3.10.3.1: Item assignment fails**

```python
t = (1, 2, 3)
for f in (lambda: t.__setitem__(0, 9), lambda: t.append(4)):
    try:
        f()
    except (TypeError, AttributeError) as e:
        print(type(e).__name__, "-", e)
```

*Output:*

```text
AttributeError - 'tuple' object has no attribute '__setitem__'
AttributeError - 'tuple' object has no attribute 'append'
```

**Example 3.10.3.2: A mutable item still mutates**

```python
t = (1, [2, 3])
t[1].append(4)
print(t)
try:
    t[1] += [5]
except TypeError as e:
    print(e)
print(t)
```

*Output:*

```text
(1, [2, 3, 4])
'tuple' object does not support item assignment
(1, [2, 3, 4, 5])
```

**Example 3.10.3.3: Hashability**

```python
print(hash((1, 2)) == hash((1, 2)))
try:
    hash((1, [2]))
except TypeError as e:
    print(e)
d = {(0, 0): "origin", (1, 2): "pt"}
print(d[(0, 0)], d[1, 2])
```

*Output:*

```text
True
unhashable type: 'list'
origin pt
```

> ⚠️ **Watch out:** `t[1] += [5]` BOTH extends the inner list and then fails on the assignment; the list changed anyway.

#### Practice 3.10.3

**3.10.3-Q1** · `BASIC`

```python
t = (1, 2)
t[0] = 5
```

**3.10.3-Q2** · `MID`

```python
t = ([1], 2)
t[0].append(9)
print(t)
```

**3.10.3-Q3** · `HARD`

```python
t = ([1], 2)
try:
    t[0] += [2]
except TypeError:
    pass
print(t)
```

**3.10.3-Q4** · `TRAP`

```python
print(hash((1, 2)) == hash((1, 2)), {(1, [2])})
```

### 3.10.4 Tuple versus list: when to use which

Use a TUPLE for a fixed record of different things (a point, an RGB colour, a database row, a function's multiple return values) and for dict keys and set members. Use a LIST for a growing collection of similar things. Tuples are slightly smaller and faster to create, and signal 'do not change this'.

**Tuple or list?**

| Question | Tuple | List |
|---|---|---|
| can change size / items? | no | yes |
| can be dict key / set member? | yes if items are hashable | no |
| typical content | heterogeneous record | homogeneous collection |
| methods | 2 (count, index) | 11 |
| memory | smaller | larger |
| literal | `(1, 2)` | `[1, 2]` |

**Example 3.10.4.1: Returning several values**

```python
def stats(nums):
    return min(nums), max(nums), sum(nums) / len(nums)
lo, hi, avg = stats([4, 8, 6])
print(lo, hi, avg, stats([1, 2]))
```

*Output:*

```text
4 8 6.0 (1, 2, 1.5)
```

**Example 3.10.4.2: Size and speed**

```python
import sys
print(sys.getsizeof(()), sys.getsizeof(()) < sys.getsizeof([]))
print(sys.getsizeof((1, 2, 3)), sys.getsizeof([1, 2, 3]))
```

*Output:*

```text
40 True
64 88
```

**Example 3.10.4.3: Tuples as dictionary keys**

```python
grid = {}
grid[(0, 1)] = "wall"
grid[(2, 3)] = "door"
print(grid.get((0, 1)), grid.get((9, 9), "empty"), sorted(grid))
```

*Output:*

```text
wall empty [(0, 1), (2, 3)]
```

#### Practice 3.10.4

**3.10.4-Q1** · `BASIC`

```python
def f(): return 1, 2
print(f(), type(f()))
```

**3.10.4-Q2** · `MID`

```python
d = {(1, 2): 'a'}
print(d[(1, 2)], (1, 2) in d, (2, 1) in d)
```

**3.10.4-Q3** · `HARD`

```python
import sys; print(sys.getsizeof((1, 2)) < sys.getsizeof([1, 2]))
```

**3.10.4-Q4** · `TRAP`

```python
d = {[1, 2]: 'a'}
```

### 3.10.5 Unpacking, swapping and star expressions

Unpacking assigns tuple (or any iterable) items to names. Counts must match unless ONE starred name collects the rest as a LIST. The swap `a, b = b, a` builds the right-hand tuple first. Unpacking also works in `for` loops, function calls (`f(*args)`) and literals.

**Example 3.10.5.1: Unpacking and swap**

```python
a, b = 1, 2
a, b = b, a
print(a, b)
x, y, z = "abc"
print(x, y, z)
(p, q), r = (1, 2), 3
print(p, q, r)
for i, (name, score) in enumerate([("a", 1), ("b", 2)]):
    print(i, name, score)
```

*Output:*

```text
2 1
a b c
1 2 3
0 a 1
1 b 2
```

**Example 3.10.5.2: Star targets**

```python
first, *middle, last = range(6)
print(first, middle, last)
head, *tail = "xyz"
print(head, tail)
*a, b = (1,)
print(a, b)
```

*Output:*

```text
0 [1, 2, 3, 4] 5
x ['y', 'z']
[] 1
```

**Example 3.10.5.3: Errors and in calls**

```python
try:
    a, b = (1, 2, 3)
except ValueError as e:
    print(e)
try:
    a, b, c = (1, 2)
except ValueError as e:
    print(e)
def add(x, y, z): return x + y + z
print(add(*(1, 2, 3)), add(*[1, 2], 3), (*(1, 2), 3))
```

*Output:*

```text
too many values to unpack (expected 2)
not enough values to unpack (expected 3, got 2)
6 6 (1, 2, 3)
```

#### Practice 3.10.5

**3.10.5-Q1** · `BASIC`

```python
a, b = (3, 4)
print(a + b)
```

**3.10.5-Q2** · `MID`

```python
a, b = 1, 2
a, b = b, a + b
print(a, b)
```

**3.10.5-Q3** · `MID`

```python
a, *b = 'xyz'
print(a, b)
```

**3.10.5-Q4** · `HARD`

```python
a, (b, *c), d = 1, (2, 3, 4), 5
print(a, b, c, d)
```

**3.10.5-Q5** · `TRAP`

```python
a, b = 1, 2, 3
```

### 3.10.6 namedtuple and typing.NamedTuple

`collections.namedtuple('Name', 'field1 field2')` creates a tuple subclass whose items are also reachable by NAME. It is still immutable and unpackable. Helper methods: `_asdict()`, `_replace(**kw)`, `_fields`, `_make(iterable)`. `typing.NamedTuple` is the class-syntax version with type hints and defaults.

> **Key rule:** namedtuple = tuple + field names: p.x and p[0] are the same item; use _replace to 'modify'.

**Example 3.10.6.1: Definition and use**

```python
from collections import namedtuple
Point = namedtuple("Point", ["x", "y"])
p = Point(3, 4)
print(p, p.x, p[1], p == (3, 4), len(p), isinstance(p, tuple))
x, y = p
print(x + y, Point(y=1, x=2), Point._fields)
```

*Output:*

```text
Point(x=3, y=4) 3 4 True 2 True
7 Point(x=2, y=1) ('x', 'y')
```

**Example 3.10.6.2: Helper methods**

```python
from collections import namedtuple
Point = namedtuple("Point", "x y")
p = Point(3, 4)
print(p._asdict(), p._replace(x=10), Point._make([5, 6]), p)
try:
    p.x = 9
except AttributeError as e:
    print(e)
```

*Output:*

```text
{'x': 3, 'y': 4} Point(x=10, y=4) Point(x=5, y=6) Point(x=3, y=4)
can't set attribute
```

**Example 3.10.6.3: typing.NamedTuple with defaults**

```python
from typing import NamedTuple
class Employee(NamedTuple):
    name: str
    dept: str = "ops"
    age: int = 0
e = Employee("Ann")
print(e, e.dept, e._replace(age=41), Employee("Bo", "dev", 30))
```

*Output:*

```text
Employee(name='Ann', dept='ops', age=0) ops Employee(name='Ann', dept='ops', age=41) Employee(name='Bo', dept='dev', age=30)
```

#### Practice 3.10.6

**3.10.6-Q1** · `BASIC`

```python
from collections import namedtuple
P = namedtuple('P', 'a b')
print(P(1, 2), P(1, 2).a)
```

**3.10.6-Q2** · `MID`

```python
from collections import namedtuple
P = namedtuple('P', 'a b')
p = P(1, 2)
print(p._replace(a=9), p)
```

**3.10.6-Q3** · `HARD`

```python
from collections import namedtuple
P = namedtuple('P', 'a b')
print(P(1, 2) == (1, 2), P(1, 2) == namedtuple('Q', 'a b')(1, 2))
```

**3.10.6-Q4** · `TRAP`

```python
from collections import namedtuple
P = namedtuple('P', 'a b')
p = P(1, 2)
p.a = 5
```

### 3.10.7 Common tuple pitfalls

Tuple bugs are few: forgetting the comma, expecting immutability to freeze inner lists, mixing up tuple and list methods, a stray trailing comma making a tuple by accident, and `+=` on tuples building a NEW tuple each time.

**Pitfall checklist**

| Mistake | Result | Fix |
|---|---|---|
| `t = (1)` | int, not tuple | `t = (1,)` |
| `x = 5,` | tuple `(5,)` by accident | remove the comma |
| `t.append(3)` | AttributeError | `t + (3,)` or use a list |
| `t[0] = 9` | TypeError | build a new tuple |
| `(1, [2])` as dict key | unhashable | use all-immutable items |
| `t += (x,)` in a loop | O(n) copy each time | collect in a list, then `tuple(...)` |

**Example 3.10.7.1: The accidental tuple**

```python
price = 9.99,
print(price, type(price))
total = (price[0] * 2,)
print(total)
```

*Output:*

```text
(9.99,) <class 'tuple'>
(19.98,)
```

**Example 3.10.7.2: Building a tuple efficiently**

```python
items = []
for i in range(4):
    items.append(i * i)
t = tuple(items)
print(t, t + (99,), t[:2] + (7,) + t[3:])
```

*Output:*

```text
(0, 1, 4, 9) (0, 1, 4, 9, 99) (0, 1, 7, 9)
```

#### Practice 3.10.7

**3.10.7-Q1** · `BASIC`

```python
x = 4,
print(x, type(x))
```

**3.10.7-Q2** · `MID`

```python
t = (1, 2)
t += (3,)
print(t)
```

**3.10.7-Q3** · `HARD`

```python
a = (1, 2)
b = a
a += (3,)
print(a, b, a is b)
```

**3.10.7-Q4** · `TRAP`

```python
t = (1, 2, 3)
t.append(4)
```

---

## Section 3.11 set and frozenset: Sets

### 3.11.1 Creating sets

A set is an UNORDERED collection of UNIQUE, HASHABLE items. Duplicates vanish, order is not guaranteed, and there is no indexing. Build one with braces `{1, 2, 3}`, with `set(iterable)`, or with a comprehension. The empty set is `set()`, because `{}` is an empty dict. Items must be hashable: ints, strings, tuples of hashables are fine; lists, dicts and sets are not.

> **Key rule:** {} is a dict; the empty set is set(). Items must be hashable and are stored without order.

**Example 3.11.1.1: Ways to build a set**

```python
print({3, 1, 2, 3, 1}, set([1, 2, 2]), set("hello") == {"h", "e", "l", "o"}, set(), type({}), type(set()))
print(len({1, 2, 2, 3}), {1, 1.0, True}, {(1, 2), (1, 2)})
```

*Output:*

```text
{1, 2, 3} {1, 2} True set() <class 'dict'> <class 'set'>
3 {1} {(1, 2)}
```

**Example 3.11.1.2: Only hashable items**

```python
for bad in ([1], {1: 2}, {1}):
    try:
        {bad}
    except TypeError as e:
        print(e)
print({1, "a", (2, 3), None, 4.5} == {4.5, None, (2, 3), "a", 1})
```

*Output:*

```text
unhashable type: 'list'
unhashable type: 'dict'
unhashable type: 'set'
True
```

**Example 3.11.1.3: No indexing, no order promise**

```python
s = {10, 20, 30}
try:
    s[0]
except TypeError as e:
    print(e)
print(sorted(s), list(s) == sorted(s), 20 in s)
```

*Output:*

```text
'set' object is not subscriptable
[10, 20, 30] True True
```

#### Practice 3.11.1

**3.11.1-Q1** · `BASIC`

```python
print(len({1, 2, 2, 3}), type({}), type(set()))
```

**3.11.1-Q2** · `BASIC`

```python
print(sorted(set('banana')), len(set('banana')))
```

**3.11.1-Q3** · `MID`

```python
print({1, 1.0, True, 'a'} == {1, 'a'}, len({1, 1.0, True}))
```

**3.11.1-Q4** · `HARD`

```python
print(len({(1, 2), (2, 1), (1, 2)}), {x % 3 for x in range(10)})
```

**3.11.1-Q5** · `TRAP`

```python
print({[1, 2], [3]})
```

### 3.11.2 Adding and removing: add, update, remove, discard, pop, clear

`add(x)` inserts one item (no error if present). `update(*iterables)` adds every item of each iterable. `remove(x)` raises KeyError when absent; `discard(x)` never raises. `pop()` removes and returns an ARBITRARY item (KeyError when empty). `clear()` empties the set. All return None.

> **Key rule:** remove raises KeyError, discard does not; pop removes an arbitrary element.

**Example 3.11.2.1: Adding**

```python
s = {1, 2}
s.add(3); s.add(3)
s.update([4, 5], {6}, "7")
print(sorted(s, key=str), len(s))
```

*Output:*

```text
[1, 2, 3, 4, 5, 6, '7'] 7
```

**Example 3.11.2.2: Removing**

```python
s = {1, 2, 3, 4}
s.remove(1)
s.discard(2)
s.discard(99)
print(s)
print(s.pop() in {3, 4}, len(s))
try:
    s.remove(99)
except KeyError as e:
    print("KeyError", e)
s.clear()
print(s, len(s))
```

*Output:*

```text
{3, 4}
True 1
KeyError 99
set() 0
```

**Example 3.11.2.3: pop on empty**

```python
try:
    set().pop()
except KeyError as e:
    print(e)
```

*Output:*

```text
'pop from an empty set'
```

#### Practice 3.11.2

**3.11.2-Q1** · `BASIC`

```python
s = {1}; s.add(2); s.add(2); print(sorted(s))
```

**3.11.2-Q2** · `MID`

```python
s = {1, 2, 3}; s.discard(5); s.remove(1); print(s)
```

**3.11.2-Q3** · `MID`

```python
s = {1}; s.update([2, 3], (4,)); print(sorted(s))
```

**3.11.2-Q4** · `HARD`

```python
s = {1, 2}
print(s.add(3), s.discard(1), s.update([9]), sorted(s))
```

**3.11.2-Q5** · `TRAP`

```python
s = {1, 2}
s.remove(3)
```

### 3.11.3 Set algebra: union, intersection, difference, symmetric difference

Operators and named methods give the same results. `a | b` (union) all items; `a & b` (intersection) common items; `a - b` (difference) in a not b; `a ^ b` (symmetric difference) in exactly one. The METHODS (`union`, `intersection`, ...) accept ANY iterable; the OPERATORS need both sides to be sets. In-place versions: `|=` / `update`, `&=` / `intersection_update`, `-=` / `difference_update`, `^=` / `symmetric_difference_update`.

> **Key rule:** operators need sets on both sides; methods accept any iterable. The in-place forms mutate and return None.

**Set algebra (a = {1,2,3}, b = {2,3,4})**

| Operation | Operator | Method | Result |
|---|---|---|---|
| union | `a \| b` | `a.union(b)` | {1, 2, 3, 4} |
| intersection | `a & b` | `a.intersection(b)` | {2, 3} |
| difference | `a - b` | `a.difference(b)` | {1} |
| symmetric difference | `a ^ b` | `a.symmetric_difference(b)` | {1, 4} |

**Example 3.11.3.1: All four**

```python
a, b = {1, 2, 3}, {2, 3, 4}
print(a | b, a & b, a - b, b - a, a ^ b)
print(a.union(b), a.intersection(b), a.difference(b), a.symmetric_difference(b))
```

*Output:*

```text
{1, 2, 3, 4} {2, 3} {1} {4} {1, 4}
{1, 2, 3, 4} {2, 3} {1} {1, 4}
```

**Example 3.11.3.2: Methods take any iterable, operators do not**

```python
a = {1, 2, 3}
print(a.union([3, 4]), a.intersection("123"), a.difference((1,)), a.union(range(5, 7)))
try:
    a | [3, 4]
except TypeError as e:
    print(e)
```

*Output:*

```text
{1, 2, 3, 4} set() {2, 3} {1, 2, 3, 5, 6}
unsupported operand type(s) for |: 'set' and 'list'
```

**Example 3.11.3.3: In-place and multiple arguments**

```python
a = {1, 2, 3, 4, 5}
a &= {2, 3, 4, 9}
a -= {4}
a |= {7}
a ^= {2, 8}
print(sorted(a))
print({1, 2}.union({3}, {4}), {1, 2, 3}.intersection({2, 3}, {3}), {1, 2, 3}.difference({1}, {2}))
```

*Output:*

```text
[3, 7, 8]
{1, 2, 3, 4} {3} {3}
```

**Example 3.11.3.4: Practical use**

```python
old, new = {"a", "b", "c"}, {"b", "c", "d"}
print(sorted(new - old), sorted(old - new), sorted(old & new), sorted(old ^ new))
```

*Output:*

```text
['d'] ['a'] ['b', 'c'] ['a', 'd']
```

#### Practice 3.11.3

**3.11.3-Q1** · `BASIC`

```python
print({1, 2} | {2, 3}, {1, 2} & {2, 3})
```

**3.11.3-Q2** · `BASIC`

```python
print({1, 2, 3} - {2}, {1, 2} ^ {2, 3})
```

**3.11.3-Q3** · `MID`

```python
a = {1, 2, 3}
print(a.union([5]), a.intersection([1, 9]), a)
```

**3.11.3-Q4** · `HARD`

```python
a = {1, 2, 3}
a ^= {3, 4}
a &= {1, 4, 9}
print(a)
```

**3.11.3-Q5** · `TRAP`

```python
print({1, 2} | [3])
```

### 3.11.4 Subsets, supersets and isdisjoint

`a <= b` / `a.issubset(b)`: every item of a is in b. `a < b`: proper subset (also a != b). `a >= b` / `a.issuperset(b)`. `a.isdisjoint(b)`: no common items. Note that `<` on sets is a PARTIAL order: two different sets can be neither `<` nor `>`, so `sorted` on sets does not give a meaningful order. The empty set is a subset of everything.

> **Key rule:** a <= b is subset, a < b is proper subset; isdisjoint means 'no overlap'.

**Example 3.11.4.1: Relationships**

```python
a, b = {1, 2}, {1, 2, 3}
print(a <= b, a < b, b >= a, b > a, a <= a, a < a)
print(a.issubset(b), b.issuperset(a), a.isdisjoint({5}), a.isdisjoint({2, 9}), set() <= a)
```

*Output:*

```text
True True True True True False
True True True False True
```

**Example 3.11.4.2: Partial order**

```python
a, b = {1, 2}, {2, 3}
print(a < b, a > b, a == b, a <= b or a >= b)
print(a.issubset([1, 2, 3]), a.isdisjoint([7, 8]))
```

*Output:*

```text
False False False False
True True
```

**Example 3.11.4.3: Checking requirements**

```python
required = {"name", "email"}
given = {"name": "Ann", "email": "a@x", "age": 3}
print(required <= given.keys(), required <= {"name"}, (required - {"name"}))
```

*Output:*

```text
True False {'email'}
```

#### Practice 3.11.4

**3.11.4-Q1** · `BASIC`

```python
print({1} <= {1, 2}, {1, 2} <= {1}, {1} < {1})
```

**3.11.4-Q2** · `MID`

```python
print({1, 2}.isdisjoint({3}), {1, 2}.isdisjoint({2}), set().isdisjoint(set()))
```

**3.11.4-Q3** · `HARD`

```python
a, b = {1, 2}, {2, 3}
print(a < b, a > b, a == b)
```

**3.11.4-Q4** · `TRAP`

```python
print(set() < {1}, set() < set(), set() <= set(), {1} == {1.0})
```

### 3.11.5 Set comprehensions, deduplication and fast membership

`{expr for x in src if cond}` builds a set. Passing a list through `set()` removes duplicates but LOSES ORDER; to keep first-seen order use `dict.fromkeys(items)`. Membership `x in s` is O(1) on average versus O(n) for a list, which makes sets the right tool for 'seen before?' checks.

> **Key rule:** dedupe with set() (unordered) or dict.fromkeys() (keeps order); use a set for repeated membership tests.

**Example 3.11.5.1: Comprehension and dedupe**

```python
print({x * x for x in range(-3, 4)}, {c for c in "mississippi" if c != "s"} == {"m", "i", "p"})
data = [3, 1, 3, 2, 1]
print(sorted(set(data)), list(dict.fromkeys(data)))
```

*Output:*

```text
{0, 9, 4, 1} True
[1, 2, 3] [3, 1, 2]
```

**Example 3.11.5.2: Seen-before pattern**

```python
seen = set()
dups = []
for x in [1, 2, 1, 3, 2, 1]:
    if x in seen:
        dups.append(x)
    seen.add(x)
print(dups, sorted(seen))
```

*Output:*

```text
[1, 2, 1] [1, 2, 3]
```

**Example 3.11.5.3: Speed of membership**

```python
import time
big_list = list(range(20000))
big_set = set(big_list)
t0 = time.perf_counter(); [19999 in big_list for _ in range(200)]; t1 = time.perf_counter()
[19999 in big_set for _ in range(200)]; t2 = time.perf_counter()
print((t1 - t0) > (t2 - t1) * 20)
```

*Output:*

```text
True
```

**Example 3.11.5.4: Common set tasks**

```python
a, b = [1, 2, 3, 4], [3, 4, 5]
print(sorted(set(a) & set(b)), len(set(a) | set(b)), len(a) != len(set(a)), "".join(sorted(set("hello"))))
```

*Output:*

```text
[3, 4] 5 False ehlo
```

#### Practice 3.11.5

**3.11.5-Q1** · `BASIC`

```python
print(sorted({x % 3 for x in range(10)}))
```

**3.11.5-Q2** · `MID`

```python
print(list(dict.fromkeys([3, 1, 3, 2])), sorted(set([3, 1, 3, 2])))
```

**3.11.5-Q3** · `HARD`

```python
print(len(set('abc') & set('cde')), set('abc') ^ set('cde') == set('abde'))
```

**3.11.5-Q4** · `TRAP`

```python
print(set([[1], [2]]))
```

### 3.11.6 frozenset: the immutable set

`frozenset(iterable)` is a set that cannot change after creation. Because it is hashable it can be a dict key or a member of another set, which a plain set cannot. All read-only operations (union, intersection, difference, subset tests, `in`, `len`) work and return a frozenset (type of the LEFT operand). It has no add, remove or update.

> **Key rule:** frozenset = immutable, hashable set; use it for dict keys and sets of sets.

**Example 3.11.6.1: Creating and using**

```python
f = frozenset([1, 2, 3, 2])
print(f, len(f), 2 in f, f | {9}, type(f | {9}).__name__, {9} | f)
print(f & {2, 3, 4}, f <= {1, 2, 3, 4}, f == {1, 2, 3}, frozenset() == set())
```

*Output:*

```text
frozenset({1, 2, 3}) 3 True frozenset({1, 2, 3, 9}) frozenset {9, 2, 3, 1}
frozenset({2, 3}) True True True
```

**Example 3.11.6.2: Hashable, so usable as a key**

```python
groups = {frozenset({"a", "b"}): "pair", frozenset({"c"}): "single"}
print(groups[frozenset({"b", "a"})], {frozenset({1}), frozenset({1})})
try:
    {{1}: "x"}
except TypeError as e:
    print(e)
```

*Output:*

```text
pair {frozenset({1})}
unhashable type: 'set'
```

**Example 3.11.6.3: No mutation**

```python
f = frozenset({1})
print(hasattr(f, "add"), hasattr(f, "union"), sorted(n for n in dir(set) if n not in dir(frozenset) and not n.startswith("_")))
```

*Output:*

```text
False True ['add', 'clear', 'difference_update', 'discard', 'intersection_update', 'pop', 'remove', 'symmetric_difference_update', 'update']
```

#### Practice 3.11.6

**3.11.6-Q1** · `BASIC`

```python
f = frozenset({1, 2}); print(len(f), 1 in f)
```

**3.11.6-Q2** · `MID`

```python
print(frozenset({1}) | {2}, type({2} | frozenset({1})).__name__)
```

**3.11.6-Q3** · `HARD`

```python
print(frozenset({1, 2}) == {1, 2}, hash(frozenset({1, 2})) == hash(frozenset({2, 1})))
```

**3.11.6-Q4** · `TRAP`

```python
f = frozenset({1})
f.add(2)
```

### 3.11.7 Hashing, ordering and equality of sets

Sets are built on hash tables: an item's hash decides where it is stored, so iteration order depends on hash values and insertion history. Small ints usually look sorted, strings do NOT (string hashes are randomised per process), so NEVER rely on set order. Two sets are equal when they hold equal items, regardless of order. Items that are equal must hash equally (1 == 1.0 == True).

> **Key rule:** never depend on set iteration order; sort when you need a predictable order.

**Example 3.11.7.1: Equality ignores order**

```python
print({1, 2, 3} == {3, 2, 1}, {1, 2} == {1, 2, 3}, {1} == [1], {} == set())
```

*Output:*

```text
True False False False
```

**Example 3.11.7.2: Equal hashes collapse items**

```python
s = {1, 1.0, True, 2, 2.0}
print(s, len(s))
print(hash(1) == hash(1.0) == hash(True), hash("a") == hash("a"), hash((1, 2)) == hash((1, 2)))
```

*Output:*

```text
{1, 2} 2
True True True
```

**Example 3.11.7.3: Deterministic output needs sorted**

```python
s = set("python")
print(sorted(s))
print("".join(sorted(s)), len(s))
```

*Output:*

```text
['h', 'n', 'o', 'p', 't', 'y']
hnopty 6
```

#### Practice 3.11.7

**3.11.7-Q1** · `BASIC`

```python
print({1, 2} == {2, 1}, {1, 2} == [1, 2])
```

**3.11.7-Q2** · `MID`

```python
print(len({1, 1.0, '1', True}))
```

**3.11.7-Q3** · `HARD`

```python
print(sorted({3, 1, 2}), list({5}), {1, 2, 3} - {1, 2, 3} == set())
```

**3.11.7-Q4** · `TRAP`

```python
print({} == set(), type({}) == type(set()), bool({}), bool({0}))
```

### 3.11.8 Complete reference: all 17 set methods

A set has seventeen public methods. The table lists each with its operator twin, checked against `dir(set)`.

**All set methods**

| Method | Operator | Mutates? | Returns |
|---|---|---|---|
| `add(x)` | - | yes | None |
| `clear()` | - | yes | None |
| `copy()` | - | no | new set |
| `difference(*its)` | `a - b` | no | new set |
| `difference_update(*its)` | `a -= b` | yes | None |
| `discard(x)` | - | yes | None |
| `intersection(*its)` | `a & b` | no | new set |
| `intersection_update(*its)` | `a &= b` | yes | None |
| `isdisjoint(it)` | - | no | bool |
| `issubset(it)` | `a <= b` | no | bool |
| `issuperset(it)` | `a >= b` | no | bool |
| `pop()` | - | yes | arbitrary item |
| `remove(x)` | - | yes | None or KeyError |
| `symmetric_difference(it)` | `a ^ b` | no | new set |
| `symmetric_difference_update(it)` | `a ^= b` | yes | None |
| `union(*its)` | `a \| b` | no | new set |
| `update(*its)` | `a \|= b` | yes | None |

**Example 3.11.8.1: Live count**

```python
names = [n for n in dir(set) if not n.startswith("_")]
print(len(names))
print(names)
print(len([n for n in dir(frozenset) if not n.startswith("_")]))
```

*Output:*

```text
17
['add', 'clear', 'copy', 'difference', 'difference_update', 'discard', 'intersection', 'intersection_update', 'isdisjoint', 'issubset', 'issuperset', 'pop', 'remove', 'symmetric_difference', 'symmetric_difference_update', 'union', 'update']
8
```

#### Practice 3.11.8

**3.11.8-Q1** · `BASIC`

```python
print(len([n for n in dir(set) if not n.startswith('_')]))
```

**3.11.8-Q2** · `MID`

```python
print(len([n for n in dir(frozenset) if not n.startswith('_')]))
```

**3.11.8-Q3** · `HARD`

```python
s = {1, 2}
print(s.union([3]), s, s.update([3]), s)
```

**3.11.8-Q4** · `TRAP`

```python
s = {1, 2}
t = s.copy()
t.add(3)
print(s, t, s is t)
```

### 3.11.9 Common set pitfalls

Set bugs come from `{}` meaning dict, relying on order, putting unhashable items in, mutating a set while looping, forgetting that `remove` raises, and expecting set operations to keep duplicates.

**Pitfall checklist**

| Mistake | Result | Fix |
|---|---|---|
| `s = {}` | empty dict | `s = set()` |
| `list(set(x))` to dedupe | order lost | `list(dict.fromkeys(x))` |
| `{[1, 2]}` | TypeError unhashable | `{(1, 2)}` |
| `s.remove(x)` when absent | KeyError | `discard` |
| `for x in s: s.add(...)` | RuntimeError: size changed | iterate over `list(s)` |
| `s[0]` | TypeError not subscriptable | `next(iter(s))` or `sorted(s)[0]` |
| `{1, 2} + {3}` | TypeError | `\|` |

**Example 3.11.9.1: Size change during iteration**

```python
s = {1, 2, 3}
try:
    for x in s:
        s.add(x + 10)
except RuntimeError as e:
    print(e)
s2 = {1, 2, 3}
for x in list(s2):
    s2.add(x + 10)
print(sorted(s2))
```

*Output:*

```text
Set changed size during iteration
[1, 2, 3, 11, 12, 13]
```

**Example 3.11.9.2: Getting 'the' element**

```python
s = {42}
print(next(iter(s)), min(s), sorted(s)[0], list(s)[0])
(only,) = s
print(only)
```

*Output:*

```text
42 42 42 42
42
```

#### Practice 3.11.9

**3.11.9-Q1** · `BASIC`

```python
print(type({}), type({1}), type(set()))
```

**3.11.9-Q2** · `MID`

```python
print(sorted(set([3, 1, 3]) | {5}), {1, 2} - {2})
```

**3.11.9-Q3** · `TRAP`

```python
print({1, 2} + {3})
```

---

## Section 3.12 dict: Dictionaries

### 3.12.1 Creating dictionaries

A dict maps unique, hashable KEYS to arbitrary VALUES. Since Python 3.7 it remembers INSERTION ORDER. Build one with braces `{'a': 1}`, with `dict(a=1, b=2)` (keys must be valid names), with `dict(pairs)`, with `dict(zip(keys, values))`, with a comprehension, or with `dict.fromkeys(keys, default)`. `{}` is an empty dict.

> **Key rule:** keys must be hashable and unique; a later duplicate key overwrites the earlier one.

**Example 3.12.1.1: Ways to create**

```python
print({"a": 1, "b": 2}, dict(a=1, b=2), dict([("a", 1), ("b", 2)]), dict(zip("ab", [1, 2])))
print({k: k * 2 for k in "ab"}, dict.fromkeys("ab", 0), dict.fromkeys([1, 2]), {}, dict())
```

*Output:*

```text
{'a': 1, 'b': 2} {'a': 1, 'b': 2} {'a': 1, 'b': 2} {'a': 1, 'b': 2}
{'a': 'aa', 'b': 'bb'} {'a': 0, 'b': 0} {1: None, 2: None} {} {}
```

**Example 3.12.1.2: Duplicate keys overwrite**

```python
d = {"a": 1, "a": 2, "b": 3}
print(d, len(d))
print({1: "int", 1.0: "float", True: "bool"})
```

*Output:*

```text
{'a': 2, 'b': 3} 2
{1: 'bool'}
```

**Example 3.12.1.3: Different key types, mixed values**

```python
d = {1: "one", "two": 2, (3, 4): [5], None: "nothing", 5.5: {"nested": True}}
print(d[1], d["two"], d[(3, 4)], d[None], d[5.5]["nested"], len(d))
```

*Output:*

```text
one 2 [5] nothing True 5
```

#### Practice 3.12.1

**3.12.1-Q1** · `BASIC`

```python
d = {'a': 1, 'b': 2}
print(len(d), d['a'], list(d))
```

**3.12.1-Q2** · `MID`

```python
print(dict(a=1), dict([(1, 2)]), dict(zip('xy', (1, 2))))
```

**3.12.1-Q3** · `MID`

```python
print({1: 'a', 1.0: 'b', True: 'c'})
```

**3.12.1-Q4** · `HARD`

```python
print(dict.fromkeys('aab', []), len(dict.fromkeys('aab')))
```

**3.12.1-Q5** · `TRAP`

```python
print({[1]: 'a'})
```

### 3.12.2 Reading values: [], get, in and KeyError

`d[key]` returns the value or raises KeyError. `d.get(key, default=None)` returns the default instead of raising, and never inserts. `key in d` tests KEYS (not values). Test values with `v in d.values()`. `len(d)` counts items. Iterating a dict yields its keys.

> **Key rule:** d[k] raises KeyError for a missing key; d.get(k, default) does not and does not insert.

**Example 3.12.2.1: Reading**

```python
d = {"a": 1, "b": 2}
print(d["a"], d.get("a"), d.get("z"), d.get("z", 0), "a" in d, "z" in d, 2 in d, 2 in d.values())
try:
    d["z"]
except KeyError as e:
    print("KeyError", e)
```

*Output:*

```text
1 1 None 0 True False False True
KeyError 'z'
```

**Example 3.12.2.2: get does not insert**

```python
d = {}
print(d.get("k"), d)
d.setdefault("k", []).append(1)
print(d)
```

*Output:*

```text
None {}
{'k': [1]}
```

**Example 3.12.2.3: get with falsy values**

```python
d = {"zero": 0, "none": None}
print(d.get("zero") or "fallback", d.get("zero", "fallback"), d.get("none", "fallback"), d.get("none") is None)
```

*Output:*

```text
fallback 0 None True
```

#### Practice 3.12.2

**3.12.2-Q1** · `BASIC`

```python
d = {'a': 1}
print(d['a'], d.get('b'), d.get('b', 9), 'a' in d)
```

**3.12.2-Q2** · `MID`

```python
d = {'a': 1}
print(1 in d, 1 in d.values(), len(d))
```

**3.12.2-Q3** · `HARD`

```python
d = {'a': None}
print(d.get('a', 'x'), d.get('b', 'x'), d.get('a') or 'x')
```

**3.12.2-Q4** · `TRAP`

```python
d = {'a': 1}
print(d['b'])
```

### 3.12.3 Adding and updating: [], update, setdefault, | and |=

`d[k] = v` inserts or overwrites. `update(other)` merges another mapping or pairs (existing keys are overwritten). `setdefault(k, default)` returns d[k], inserting default first if k is missing. `d1 | d2` (3.9+) returns a NEW merged dict, `d1 |= d2` merges in place; the right side wins on clashes. `{**a, **b}` is the older unpacking spelling.

> **Key rule:** update/| : right side wins; setdefault inserts only when the key is missing and returns the value.

**Example 3.12.3.1: Set and update**

```python
d = {"a": 1}
d["b"] = 2
d["a"] = 10
d.update({"c": 3, "b": 20})
d.update(x=7, y=8)
d.update([("z", 26)])
print(d)
```

*Output:*

```text
{'a': 10, 'b': 20, 'c': 3, 'x': 7, 'y': 8, 'z': 26}
```

**Example 3.12.3.2: setdefault and grouping**

```python
d = {}
for word in ["apple", "avocado", "banana", "blueberry", "cherry"]:
    d.setdefault(word[0], []).append(word)
print(d)
print({"a": 1}.setdefault("a", 99), {}.setdefault("k"))
```

*Output:*

```text
{'a': ['apple', 'avocado'], 'b': ['banana', 'blueberry'], 'c': ['cherry']}
1 None
```

**Example 3.12.3.3: Merging**

```python
a, b = {"x": 1, "y": 2}, {"y": 20, "z": 30}
print(a | b, b | a, {**a, **b}, a)
a |= b
print(a)
c = {"k": 1}
c |= [("m", 2)]
print(c)
```

*Output:*

```text
{'x': 1, 'y': 20, 'z': 30} {'y': 2, 'z': 30, 'x': 1} {'x': 1, 'y': 20, 'z': 30} {'x': 1, 'y': 2}
{'x': 1, 'y': 20, 'z': 30}
{'k': 1, 'm': 2}
```

#### Practice 3.12.3

**3.12.3-Q1** · `BASIC`

```python
d = {'a': 1}; d['b'] = 2; d['a'] = 5; print(d)
```

**3.12.3-Q2** · `MID`

```python
d = {'a': 1}; d.update({'a': 2, 'b': 3}); print(d)
```

**3.12.3-Q3** · `MID`

```python
d = {}; print(d.setdefault('k', 5), d.setdefault('k', 9), d)
```

**3.12.3-Q4** · `HARD`

```python
a = {'x': 1}; b = {'x': 2, 'y': 3}
print(a | b, b | a, a)
```

**3.12.3-Q5** · `TRAP`

```python
d = {}
d.setdefault('list', []).append(1)
d.setdefault('list', []).append(2)
print(d)
```

### 3.12.4 Removing: pop, popitem, del and clear

`pop(k[, default])` removes k and returns its value (KeyError without a default). `popitem()` removes and returns the LAST inserted (key, value) pair (LIFO since 3.7; KeyError when empty). `del d[k]` removes a key (KeyError if absent). `clear()` empties the dict.

> **Key rule:** pop(k, default) is the safe delete; popitem removes the most recently added pair.

**Example 3.12.4.1: The four tools**

```python
d = {"a": 1, "b": 2, "c": 3, "d": 4}
print(d.pop("a"), d.pop("zz", "none"), d)
print(d.popitem(), d)
del d["b"]
print(d)
d.clear()
print(d, len(d))
```

*Output:*

```text
1 none {'b': 2, 'c': 3, 'd': 4}
('d', 4) {'b': 2, 'c': 3}
{'c': 3}
{} 0
```

**Example 3.12.4.2: Errors**

```python
for f in (lambda: {}.pop("k"), lambda: {}.popitem(), lambda: {"a": 1}.__delitem__("b")):
    try:
        f()
    except KeyError as e:
        print("KeyError", e)
```

*Output:*

```text
KeyError 'k'
KeyError 'popitem(): dictionary is empty'
KeyError 'b'
```

**Example 3.12.4.3: Filtering a dict**

```python
d = {"a": 1, "b": 0, "c": 2, "d": 0}
print({k: v for k, v in d.items() if v})
for k in [k for k, v in d.items() if v == 0]:
    del d[k]
print(d)
```

*Output:*

```text
{'a': 1, 'c': 2}
{'a': 1, 'c': 2}
```

#### Practice 3.12.4

**3.12.4-Q1** · `BASIC`

```python
d = {'a': 1, 'b': 2}; print(d.pop('a'), d)
```

**3.12.4-Q2** · `MID`

```python
d = {'a': 1, 'b': 2, 'c': 3}; print(d.popitem(), d)
```

**3.12.4-Q3** · `MID`

```python
d = {'a': 1}; print(d.pop('x', None), d.pop('a'), d)
```

**3.12.4-Q4** · `HARD`

```python
d = {'a': 1, 'b': 2}
d['a'] = 9
print(d.popitem())
```

**3.12.4-Q5** · `TRAP`

```python
d = {'a': 1}
del d['b']
```

### 3.12.5 Views: keys(), values(), items()

`keys()`, `values()`, `items()` return VIEW objects that reflect later changes to the dict. `keys()` and `items()` behave like sets (you can use `&`, `|`, `-`, `^` and `in`). `values()` is not set-like. Convert to a list for a snapshot. Iterating `items()` with tuple unpacking is the standard way to loop over both.

> **Key rule:** views are live; keys() and items() support set operations; list(...) takes a snapshot.

**Example 3.12.5.1: Views are live**

```python
d = {"a": 1, "b": 2}
k, v, i = d.keys(), d.values(), d.items()
d["c"] = 3
print(k, v, i)
print(list(k), len(v), type(k).__name__)
```

*Output:*

```text
dict_keys(['a', 'b', 'c']) dict_values([1, 2, 3]) dict_items([('a', 1), ('b', 2), ('c', 3)])
['a', 'b', 'c'] 3 dict_keys
```

**Example 3.12.5.2: Set operations on keys and items**

```python
a, b = {"x": 1, "y": 2}, {"y": 2, "z": 3}
print(sorted(a.keys() & b.keys()), sorted(a.keys() - b.keys()), a.items() & b.items(), sorted(a.keys() | b.keys()))
print("x" in a.keys(), ("x", 1) in a.items(), 2 in a.values())
```

*Output:*

```text
['y'] ['x'] {('y', 2)} ['x', 'y', 'z']
True True True
```

**Example 3.12.5.3: Looping**

```python
d = {"a": 1, "b": 2, "c": 3}
for k in d: print(k, end=" ")
print()
for k, v in d.items(): print(f"{k}={v}", end=" ")
print()
print(sum(d.values()), max(d, key=d.get), [k for k, v in d.items() if v > 1], list(reversed(d)))
```

*Output:*

```text
a b c
a=1 b=2 c=3
6 c ['b', 'c'] ['c', 'b', 'a']
```

#### Practice 3.12.5

**3.12.5-Q1** · `BASIC`

```python
d = {'a': 1, 'b': 2}
print(list(d), list(d.values()), list(d.items()))
```

**3.12.5-Q2** · `MID`

```python
d = {'a': 1}
k = d.keys()
d['b'] = 2
print(list(k))
```

**3.12.5-Q3** · `MID`

```python
a = {'x': 1, 'y': 2}
print(sorted(a.keys() & {'y', 'z'}), 'x' in a.keys())
```

**3.12.5-Q4** · `HARD`

```python
d = {'a': 1, 'b': 2}
print(max(d, key=d.get), sorted(d, key=d.get, reverse=True))
```

**3.12.5-Q5** · `TRAP`

```python
d = {'a': 1, 'b': 2}
print(d.keys()[0])
```

### 3.12.6 Changing a dict while iterating

Adding or deleting keys while iterating over a dict raises `RuntimeError: dictionary changed size during` `iteration`. Changing the VALUE of an existing key is allowed. Safe patterns: iterate over `list(d)` (or `list(d.items())`), or build a new dict with a comprehension.

> **Key rule:** iterate over list(d) when you must add or delete keys.

**Example 3.12.6.1: The error and the cure**

```python
d = {"a": 1, "b": 2, "c": 3}
try:
    for k in d:
        if d[k] == 2:
            del d[k]
except RuntimeError as e:
    print(e)
d = {"a": 1, "b": 2, "c": 3}
for k in list(d):
    if d[k] == 2:
        del d[k]
print(d)
```

*Output:*

```text
dictionary changed size during iteration
{'a': 1, 'c': 3}
```

**Example 3.12.6.2: Changing values is fine**

```python
d = {"a": 1, "b": 2}
for k in d:
    d[k] *= 10
print(d)
d = {k: v + 1 for k, v in d.items()}
print(d)
```

*Output:*

```text
{'a': 10, 'b': 20}
{'a': 11, 'b': 21}
```

#### Practice 3.12.6

**3.12.6-Q1** · `BASIC`

```python
d = {'a': 1}
for k in d:
    d[k] = 5
print(d)
```

**3.12.6-Q2** · `MID`

```python
d = {'a': 1, 'b': 2}
for k in list(d):
    d[k + k] = 0
print(sorted(d))
```

**3.12.6-Q3** · `TRAP`

```python
d = {'a': 1, 'b': 2}
for k in d:
    d['c'] = 3
```

### 3.12.7 Dict comprehensions, fromkeys, zip and inversion

`{k: v for ... if ...}` builds a dict from any iterable. `dict(zip(keys, values))` pairs two lists. `dict.fromkeys(keys, value)` shares ONE value object for all keys, so do not pass a mutable default. Invert a dict with `{v: k for k, v in d.items()}` (values must be unique and hashable). `collections.Counter` is a dict subclass for counting.

> **Key rule:** fromkeys(keys, []) gives every key the SAME list; build per-key lists with a comprehension.

**Example 3.12.7.1: Comprehensions**

```python
words = ["apple", "kiwi", "banana"]
print({w: len(w) for w in words}, {w: len(w) for w in words if len(w) > 4}, {i: i * i for i in range(4)})
d = {"a": 1, "b": 2}
print({v: k for k, v in d.items()}, {k.upper(): v for k, v in d.items()})
```

*Output:*

```text
{'apple': 5, 'kiwi': 4, 'banana': 6} {'apple': 5, 'banana': 6} {0: 0, 1: 1, 2: 4, 3: 9}
{1: 'a', 2: 'b'} {'A': 1, 'B': 2}
```

**Example 3.12.7.2: Pitfall: fromkeys with a list**

```python
bad = dict.fromkeys("ab", [])
bad["a"].append(1)
print(bad, bad["a"] is bad["b"])
good = {k: [] for k in "ab"}
good["a"].append(1)
print(good)
```

*Output:*

```text
{'a': [1], 'b': [1]} True
{'a': [1], 'b': []}
```

**Example 3.12.7.3: Counting and grouping**

```python
text = "mississippi"
counts = {}
for ch in text:
    counts[ch] = counts.get(ch, 0) + 1
print(counts)
from collections import Counter
print(Counter(text), dict(Counter(text).most_common(2)))
print(dict(sorted(counts.items(), key=lambda kv: (-kv[1], kv[0]))))
```

*Output:*

```text
{'m': 1, 'i': 4, 's': 4, 'p': 2}
Counter({'i': 4, 's': 4, 'p': 2, 'm': 1}) {'i': 4, 's': 4}
{'i': 4, 's': 4, 'p': 2, 'm': 1}
```

#### Practice 3.12.7

**3.12.7-Q1** · `BASIC`

```python
print({x: x * 2 for x in range(3)})
```

**3.12.7-Q2** · `MID`

```python
print({v: k for k, v in {'a': 1, 'b': 2}.items()})
```

**3.12.7-Q3** · `HARD`

```python
print({v: k for k, v in {'a': 1, 'b': 1}.items()})
```

**3.12.7-Q4** · `TRAP`

```python
d = dict.fromkeys(['a', 'b'], [])
d['a'].append(1)
print(d)
```

### 3.12.8 Nested dictionaries, copy and deepcopy

Dict values can be anything, including dicts and lists, so JSON-like structures nest naturally. Read with chained keys `d['a']['b']` (KeyError if any level is missing) or with `.get()` chains. `d.copy()` and `dict(d)` are SHALLOW: inner objects are shared. Use `copy.deepcopy` for independent nested data.

> **Key rule:** d.copy() copies one level; nested mutable values are shared unless you deepcopy.

**Example 3.12.8.1: Reading nested data**

```python
cfg = {"db": {"host": "x", "ports": [1, 2]}, "debug": True}
print(cfg["db"]["host"], cfg["db"]["ports"][1], cfg.get("cache", {}).get("size", 0))
cfg["db"]["user"] = "root"
print(cfg)
```

*Output:*

```text
x 2 0
{'db': {'host': 'x', 'ports': [1, 2], 'user': 'root'}, 'debug': True}
```

**Example 3.12.8.2: Shallow versus deep**

```python
import copy
a = {"k": [1, 2]}
shallow = a.copy()
deep = copy.deepcopy(a)
a["k"].append(3)
print(a, shallow, deep)
shallow["new"] = 1
print(a, shallow)
```

*Output:*

```text
{'k': [1, 2, 3]} {'k': [1, 2, 3]} {'k': [1, 2]}
{'k': [1, 2, 3]} {'k': [1, 2, 3], 'new': 1}
```

**Example 3.12.8.3: Building nested dicts safely**

```python
from collections import defaultdict
tree = defaultdict(lambda: defaultdict(int))
tree["a"]["x"] += 1
tree["a"]["y"] += 2
tree["b"]["x"] += 5
print({k: dict(v) for k, v in tree.items()})
```

*Output:*

```text
{'a': {'x': 1, 'y': 2}, 'b': {'x': 5}}
```

#### Practice 3.12.8

**3.12.8-Q1** · `BASIC`

```python
d = {'a': {'b': 1}}
print(d['a']['b'], d['a'].get('c'))
```

**3.12.8-Q2** · `MID`

```python
d = {'a': [1]}
e = d.copy()
e['a'].append(2)
print(d)
```

**3.12.8-Q3** · `HARD`

```python
import copy
d = {'a': [1]}
e = copy.deepcopy(d)
e['a'].append(2)
print(d, e)
```

**3.12.8-Q4** · `TRAP`

```python
d = {'a': {}}
print(d['b']['c'])
```

### 3.12.9 Ordering: insertion order, sorting and reversing

Dicts preserve INSERTION order. Overwriting a key keeps its ORIGINAL position; deleting and re-adding moves it to the end. Equality ignores order (`{'a':1,'b':2} == {'b':2,'a':1}`). A dict cannot be sorted in place; build a sorted list of pairs or a new dict with `dict(sorted(d.items(), key=...))`. `reversed(d)` works since 3.8.

> **Key rule:** dict order = insertion order; sorting returns a new dict or list.

**Example 3.12.9.1: Order rules**

```python
d = {"b": 1, "a": 2}
d["c"] = 3
d["b"] = 10
print(d)
del d["a"]
d["a"] = 2
print(d, list(reversed(d)))
print({"a": 1, "b": 2} == {"b": 2, "a": 1}, list({"a": 1, "b": 2}) == list({"b": 2, "a": 1}))
```

*Output:*

```text
{'b': 10, 'a': 2, 'c': 3}
{'b': 10, 'c': 3, 'a': 2} ['a', 'c', 'b']
True False
```

**Example 3.12.9.2: Sorting a dict**

```python
d = {"pear": 3, "apple": 5, "fig": 1}
print(sorted(d), sorted(d.values()), sorted(d.items()))
print(dict(sorted(d.items())), dict(sorted(d.items(), key=lambda kv: kv[1], reverse=True)))
print(max(d, key=d.get), min(d.items(), key=lambda kv: kv[1]))
```

*Output:*

```text
['apple', 'fig', 'pear'] [1, 3, 5] [('apple', 5), ('fig', 1), ('pear', 3)]
{'apple': 5, 'fig': 1, 'pear': 3} {'apple': 5, 'pear': 3, 'fig': 1}
apple ('fig', 1)
```

#### Practice 3.12.9

**3.12.9-Q1** · `BASIC`

```python
d = {'b': 1, 'a': 2}
print(list(d), sorted(d))
```

**3.12.9-Q2** · `MID`

```python
d = {'a': 1, 'b': 2}
d['a'] = 9
print(list(d.items()))
```

**3.12.9-Q3** · `HARD`

```python
d = {'a': 1, 'b': 2}
del d['a']
d['a'] = 3
print(list(d))
```

**3.12.9-Q4** · `TRAP`

```python
print({'a': 1, 'b': 2} == {'b': 2, 'a': 1}, [1, 2] == [2, 1])
```

### 3.12.10 Key rules: hashability, equal keys and tuple keys

A key must be HASHABLE: immutable built-ins (int, float, str, bytes, bool, None, frozenset, tuples of hashables) qualify; list, dict and set do not. Keys that are EQUAL and hash equally are the SAME key, so 1, 1.0 and True collide and the first inserted key object is kept. Tuples are the standard way to key by coordinates or composite ids.

> **Key rule:** equal hashable keys are one key (1 == 1.0 == True); use tuples for composite keys.

**Example 3.12.10.1: Collisions of equal keys**

```python
d = {}
d[1] = "int"
d[1.0] = "float"
d[True] = "bool"
print(d, type(list(d)[0]).__name__)
print({0: "a", False: "b", 0.0: "c"}, {"1": "str", 1: "int"})
```

*Output:*

```text
{1: 'bool'} int
{0: 'c'} {'1': 'str', 1: 'int'}
```

**Example 3.12.10.2: Unhashable keys**

```python
for bad in ([1], {1}, {1: 2}):
    try:
        {bad: 0}
    except TypeError as e:
        print(e)
print({(1, 2): "ok", frozenset({1}): "ok2"})
```

*Output:*

```text
unhashable type: 'list'
unhashable type: 'set'
unhashable type: 'dict'
{(1, 2): 'ok', frozenset({1}): 'ok2'}
```

**Example 3.12.10.3: Composite keys and tuple-keyed grids**

```python
grid = {(r, c): r * c for r in range(2) for c in range(3)}
print(grid[(1, 2)], grid.get((5, 5), -1), sorted(grid)[:3])
print({("a", 1): "x"}[("a", 1)])
```

*Output:*

```text
2 -1 [(0, 0), (0, 1), (0, 2)]
x
```

#### Practice 3.12.10

**3.12.10-Q1** · `BASIC`

```python
d = {1: 'a'}
d[1.0] = 'b'
print(d)
```

**3.12.10-Q2** · `MID`

```python
print(len({1, 1.0, True, '1'}), len({1: 0, 1.0: 0, True: 0, '1': 0}))
```

**3.12.10-Q3** · `HARD`

```python
d = {}
d[(1, 2)] = 'a'
d[(2, 1)] = 'b'
print(len(d), d[1, 2])
```

**3.12.10-Q4** · `TRAP`

```python
d = {}
d[[1, 2]] = 'a'
```

### 3.12.11 collections: defaultdict, Counter, OrderedDict, ChainMap

The `collections` module has four dict-like tools. `defaultdict(factory)` creates missing values on first access. `Counter` counts hashable items and has `most_common`, arithmetic, `elements`, `update`, `subtract`. `OrderedDict` keeps order and adds `move_to_end` and order-sensitive equality. `ChainMap` searches several dicts as one.

**collections dict family**

| Class | Best for | Key feature |
|---|---|---|
| `defaultdict(list)` | grouping | missing key creates `list()` |
| `Counter` | frequencies | `most_common(n)`, `+`, `-` |
| `OrderedDict` | LRU caches, order-aware equality | `move_to_end`, `popitem(last=False)` |
| `ChainMap` | layered settings | lookup falls through maps |

**Example 3.12.11.1: defaultdict**

```python
from collections import defaultdict
groups = defaultdict(list)
for w in ["ant", "bee", "ape", "bat"]:
    groups[w[0]].append(w)
print(dict(groups), groups["zzz"], len(groups))
counts = defaultdict(int)
for ch in "aab":
    counts[ch] += 1
print(dict(counts))
```

*Output:*

```text
{'a': ['ant', 'ape'], 'b': ['bee', 'bat']} [] 3
{'a': 2, 'b': 1}
```

**Example 3.12.11.2: Counter**

```python
from collections import Counter
c = Counter("abracadabra")
print(c, c.most_common(2), c["a"], c["zzz"], sorted(c.elements())[:4])
c.update("aa"); c.subtract("b")
print(c["a"], c["b"], Counter("aab") + Counter("bcc"), Counter("aab") - Counter("a"))
print(Counter(a=3) & Counter(a=1, b=5), sum(c.values()), c.total())
```

*Output:*

```text
Counter({'a': 5, 'b': 2, 'r': 2, 'c': 1, 'd': 1}) [('a', 5), ('b', 2)] 5 0 ['a', 'a', 'a', 'a']
7 1 Counter({'a': 2, 'b': 2, 'c': 2}) Counter({'a': 1, 'b': 1})
Counter({'a': 1}) 12 12
```

**Example 3.12.11.3: OrderedDict and ChainMap**

```python
from collections import OrderedDict, ChainMap
od = OrderedDict(a=1, b=2, c=3)
od.move_to_end("a")
print(list(od), od.popitem(last=False), OrderedDict(x=1, y=2) == OrderedDict(y=2, x=1))
defaults, user = {"theme": "dark", "size": 10}, {"size": 14}
cm = ChainMap(user, defaults)
print(cm["size"], cm["theme"], dict(cm), list(cm.maps[1]))
```

*Output:*

```text
['b', 'c', 'a'] ('b', 2) False
14 dark {'theme': 'dark', 'size': 14} ['theme', 'size']
```

#### Practice 3.12.11

**3.12.11-Q1** · `BASIC`

```python
from collections import Counter
print(Counter('aab'), Counter('aab').most_common(1))
```

**3.12.11-Q2** · `MID`

```python
from collections import defaultdict
d = defaultdict(int)
d['x'] += 2
print(d['x'], d['y'], dict(d))
```

**3.12.11-Q3** · `MID`

```python
from collections import Counter
print(Counter('aab') + Counter('b'), Counter('aab') - Counter('aaa'))
```

**3.12.11-Q4** · `HARD`

```python
from collections import ChainMap
c = ChainMap({'a': 1}, {'a': 2, 'b': 3})
c['c'] = 9
print(c['a'], c['b'], list(c.maps[0]))
```

**3.12.11-Q5** · `TRAP`

```python
from collections import defaultdict
d = defaultdict(list)
print(d.get('k'), 'k' in d, d['k'], 'k' in d)
```

### 3.12.12 Complete reference: all 11 dict methods

A dict has exactly eleven public methods; all are covered above. This table is checked against `dir(dict)`.

**All dict methods**

| Method | Does | Returns | Topic |
|---|---|---|---|
| `clear()` | remove all items | None | 3.12.4 |
| `copy()` | shallow copy | new dict | 3.12.8 |
| `fromkeys(keys, v)` | class method: dict with one value | new dict | 3.12.7 |
| `get(k, d)` | value or default, no insert | value / default | 3.12.2 |
| `items()` | live (key, value) view | view | 3.12.5 |
| `keys()` | live key view | view | 3.12.5 |
| `pop(k, d)` | remove key, return value | value / default | 3.12.4 |
| `popitem()` | remove last (key, value) | tuple | 3.12.4 |
| `setdefault(k, d)` | get, inserting default if missing | value | 3.12.3 |
| `update(...)` | merge mapping or pairs | None | 3.12.3 |
| `values()` | live value view | view | 3.12.5 |

**Example 3.12.12.1: Live count**

```python
names = [n for n in dir(dict) if not n.startswith("_")]
print(len(names))
print(names)
```

*Output:*

```text
11
['clear', 'copy', 'fromkeys', 'get', 'items', 'keys', 'pop', 'popitem', 'setdefault', 'update', 'values']
```

#### Practice 3.12.12

**3.12.12-Q1** · `BASIC`

```python
print(len([n for n in dir(dict) if not n.startswith('_')]))
```

**3.12.12-Q2** · `MID`

```python
d = {'a': 1}
print(d.update({'b': 2}), d.clear(), d)
```

**3.12.12-Q3** · `HARD`

```python
d = {'a': 1}
print(d.setdefault('a', 2), d.setdefault('b', 3), d.pop('a'), d)
```

**3.12.12-Q4** · `TRAP`

```python
print({}.get('a', 1) + {}.get('a', 1), dict.fromkeys('ab', 1)['a'])
```

### 3.12.13 Common dict pitfalls

Frequent dict bugs: KeyError on direct access, `fromkeys` with a mutable value, changing size while iterating, using unhashable keys, assuming `.keys()` is a list, relying on value equality for keys (1 vs 1.0), and shallow copies.

**Pitfall checklist**

| Mistake | Result | Fix |
|---|---|---|
| `d['missing']` | KeyError | `d.get(k)` / `in` |
| `dict.fromkeys(k, [])` | one shared list | comprehension |
| delete while looping | RuntimeError | `for k in list(d)` |
| `d.keys()[0]` | TypeError | `next(iter(d))` |
| `{[1]: 2}` | TypeError | tuple key |
| `b = a` for dicts | alias | `b = a.copy()` |
| `d.get(k) or default` | wrong for 0, '' | `d.get(k, default)` |
| `for k, v in d:` | unpack error | `d.items()` |

**Example 3.12.13.1: Two classic mistakes**

```python
d = {"a": 1}
try:
    for k, v in d:
        pass
except ValueError as e:
    print(e)
print(next(iter(d)), list(d)[0], list(d.items())[0])
inv = {"x": 0}
print(inv.get("x") or "default", inv.get("x", "default"))
```

*Output:*

```text
not enough values to unpack (expected 2, got 1)
a a ('a', 1)
default 0
```

#### Practice 3.12.13

**3.12.13-Q1** · `BASIC`

```python
d = {'a': 1}
print(d.get('b', 0) + 1)
```

**3.12.13-Q2** · `MID`

```python
a = {'x': 1}
b = a
b['y'] = 2
print(a)
```

**3.12.13-Q3** · `HARD`

```python
d = {'a': 0}
print(d.get('a') or 5, d.get('a', 5), d.get('b') or 5)
```

**3.12.13-Q4** · `TRAP`

```python
d = {'a': 1, 'b': 2}
for k, v in d:
    print(k)
```

---

## Section 3.13 range: Ranges

### 3.13.1 range(start, stop, step)

`range` is an immutable sequence of integers computed LAZILY: `range(1_000_000)` takes the same tiny memory as `range(3)`. `range(stop)` runs 0..stop-1; `range(start, stop)`; `range(start, stop, step)` with a negative step counts down. The stop is EXCLUDED. A range supports `len`, indexing, slicing (returns a range), `in` (O(1)), `index`, `count`, `reversed`. It takes only INTS.

> **Key rule:** stop is excluded; range stores only start, stop, step; floats are not allowed.

**Example 3.13.1.1: Forms**

```python
print(list(range(5)), list(range(2, 6)), list(range(0, 10, 3)), list(range(5, 0, -1)), list(range(5, 0)), list(range(0)))
print(range(5), len(range(2, 11, 3)), range(3) == range(0, 3), type(range(3)))
```

*Output:*

```text
[0, 1, 2, 3, 4] [2, 3, 4, 5] [0, 3, 6, 9] [5, 4, 3, 2, 1] [] []
range(0, 5) 3 True <class 'range'>
```

**Example 3.13.1.2: It behaves like a sequence**

```python
r = range(10, 20, 2)
print(r[0], r[-1], r[1:3], list(r[::-1]), 14 in r, 15 in r, r.index(14), r.count(12), r.start, r.stop, r.step)
print(sum(r), max(r), list(reversed(r)))
```

*Output:*

```text
10 18 range(12, 16, 2) [18, 16, 14, 12, 10] True False 2 1 10 20 2
70 18 [18, 16, 14, 12, 10]
```

**Example 3.13.1.3: Lazy and huge**

```python
import sys
print(sys.getsizeof(range(3)) == sys.getsizeof(range(10 ** 12)), 10 ** 11 in range(10 ** 12), len(range(10 ** 12)))
for bad in (lambda: range(1.5), lambda: range(0, 5, 0)):
    try:
        bad()
    except (TypeError, ValueError) as e:
        print(type(e).__name__, e)
```

*Output:*

```text
True True 1000000000000
TypeError 'float' object cannot be interpreted as an integer
ValueError range() arg 3 must not be zero
```

#### Practice 3.13.1

**3.13.1-Q1** · `BASIC`

```python
print(list(range(4)), list(range(1, 4)), list(range(0, 10, 4)))
```

**3.13.1-Q2** · `MID`

```python
print(list(range(10, 0, -3)), len(range(5, 5)), len(range(0, 10, 3)))
```

**3.13.1-Q3** · `MID`

```python
r = range(5)
print(r[2], r[-1], r[1:4], 3 in r, 7 in r)
```

**3.13.1-Q4** · `HARD`

```python
print(list(range(5, 1)), list(range(1, 5, -1)), list(range(-3, 3, 2)))
```

**3.13.1-Q5** · `TRAP`

```python
print(range(0, 1, 0.1))
```

### 3.13.2 Using range correctly: loops, indexes and off-by-one

Use `for i in range(n)` to repeat n times, `range(len(a))` only when you truly need indexes (prefer `enumerate`), and `range(a, b + 1)` to include b. For floats build values from ints: `[i / 10 for i in range(11)]` or `numpy.arange`. `range` is not a list: convert with `list()` to print or mutate. Equality compares the SEQUENCE of numbers.

> **Key rule:** range(a, b + 1) to include b; prefer enumerate over range(len()); ranges are equal when they generate equal sequences.

**Example 3.13.2.1: Loops**

```python
for i in range(3):
    print("tick", i, end="; ")
print()
a = ["x", "y", "z"]
for i in range(len(a)):
    print(i, a[i], end="; ")
print()
for i, v in enumerate(a):
    print(i, v, end="; ")
print()
print(sum(range(1, 101)), list(range(1, 6)), list(range(1, 5 + 1)))
```

*Output:*

```text
tick 0; tick 1; tick 2;
0 x; 1 y; 2 z;
0 x; 1 y; 2 z;
5050 [1, 2, 3, 4, 5] [1, 2, 3, 4, 5]
```

**Example 3.13.2.2: Counting down and stepping**

```python
print(list(range(10, 0, -2)), list(range(len("abc") - 1, -1, -1)), "abc"[::-1])
print([i / 10 for i in range(0, 4)], [round(0.5 * i, 1) for i in range(4)])
```

*Output:*

```text
[10, 8, 6, 4, 2] [2, 1, 0] cba
[0.0, 0.1, 0.2, 0.3] [0.0, 0.5, 1.0, 1.5]
```

**Example 3.13.2.3: Equality and a range is not a list**

```python
print(range(0, 5, 2) == range(0, 6, 2), range(0) == range(5, 5), list(range(3)) == range(3))
r = range(3)
try:
    r[0] = 9
except TypeError as e:
    print(e)
print(r, list(r), r is r)
```

*Output:*

```text
True True False
'range' object does not support item assignment
range(0, 3) [0, 1, 2] True
```

#### Practice 3.13.2

**3.13.2-Q1** · `BASIC`

```python
print(sum(range(5)), list(range(2, 5)))
```

**3.13.2-Q2** · `MID`

```python
print(list(range(1, 4 + 1)), [x for x in range(10) if x % 4 == 0])
```

**3.13.2-Q3** · `HARD`

```python
print(range(0, 5, 2) == range(0, 6, 2), range(0) == range(5, 5), range(3) == [0, 1, 2])
```

**3.13.2-Q4** · `TRAP`

```python
r = range(3)
print(r)
print(list(r))
print(r.append(3))
```

---

## Section 3.14 Type Conversion and Choosing a Type

### 3.14.1 Implicit and explicit conversion

Python performs IMPLICIT conversion only between NUMBERS, upgrading toward the wider type: bool -> int -> float -> complex. It never mixes str with numbers silently. EXPLICIT conversion uses the type as a function: `int(x)`, `float(x)`, `str(x)`, `bool(x)`, `list(x)`, `tuple(x)`, `set(x)`, `dict(x)`, `complex(x)`. A failed conversion raises ValueError (bad value) or TypeError (impossible type).

> **Key rule:** numbers upgrade implicitly (bool -> int -> float -> complex); everything else needs an explicit constructor call.

**Example 3.14.1.1: Numeric promotion**

```python
print(True + 1, type(True + 1), 1 + 1.5, type(1 + 1.5), 1.5 + 2j, type(1.5 + 2j))
print(type(3 * 1.0), type(2 ** 2), type(2 ** -1), type(4 / 2))
```

*Output:*

```text
2 <class 'int'> 2.5 <class 'float'> (1.5+2j) <class 'complex'>
<class 'float'> <class 'int'> <class 'float'> <class 'float'>
```

**Example 3.14.1.2: Explicit constructors**

```python
print(int("12"), int(3.9), float("2.5"), float(3), str(5), bool(""), complex(1, 2))
print(list("ab"), tuple([1, 2]), set([1, 1]), dict([(1, 2)]))
```

*Output:*

```text
12 3 2.5 3.0 5 False (1+2j)
['a', 'b'] (1, 2) {1} {1: 2}
```

**Example 3.14.1.3: No silent str/number mixing**

```python
for f in (lambda: "5" + 5, lambda: 5 + "5", lambda: "5" * "5", lambda: int("5.5"), lambda: int(None)):
    try:
        f()
    except (TypeError, ValueError) as e:
        print(type(e).__name__, "-", e)
print("5" * 3, "5" + str(5), int("5") + 5)
```

*Output:*

```text
TypeError - can only concatenate str (not "int") to str
TypeError - unsupported operand type(s) for +: 'int' and 'str'
TypeError - can't multiply sequence by non-int of type 'str'
ValueError - invalid literal for int() with base 10: '5.5'
TypeError - int() argument must be a string, a bytes-like object or a real number, not 'NoneType'
555 55 10
```

#### Practice 3.14.1

**3.14.1-Q1** · `BASIC`

```python
print(type(1 + 2.0), type(True + True), type(1 / 1))
```

**3.14.1-Q2** · `MID`

```python
print(int('7') + 1, '7' + str(1), '7' * 2)
```

**3.14.1-Q3** · `MID`

```python
print(float('3'), int(float('3.9')), str(1.0), str(10 ** 3))
```

**3.14.1-Q4** · `HARD`

```python
print(1 + True + 1.0, type(1 + True + 1.0), 3 + 0j == 3)
```

**3.14.1-Q5** · `TRAP`

```python
print('2' + 3)
```

### 3.14.2 The conversion matrix

This table shows what each constructor does to each input type. Cells marked ERROR raise an exception; the examples after it run every cell.

**What int(), float(), str(), bool(), list(), set() do**

| Input | int | float | str | bool | list |
|---|---|---|---|---|---|
| `3` | 3 | 3.0 | '3' | True | ERROR |
| `3.7` | 3 | 3.7 | '3.7' | True | ERROR |
| `'12'` | 12 | 12.0 | '12' | True | ['1','2'] |
| `'1.5'` | ERROR | 1.5 | '1.5' | True | ['1','.','5'] |
| `''` | ERROR | ERROR | '' | False | [] |
| `True` | 1 | 1.0 | 'True' | True | ERROR |
| `None` | ERROR | ERROR | 'None' | False | ERROR |
| `[1, 2]` | ERROR | ERROR | '[1, 2]' | True | [1, 2] |
| `(1, 2)` | ERROR | ERROR | '(1, 2)' | True | [1, 2] |
| `{'a': 1}` | ERROR | ERROR | "{'a': 1}" | True | ['a'] |

**Example 3.14.2.1: The matrix, computed**

```python
inputs = [3, 3.7, "12", "1.5", "", True, None, [1, 2], (1, 2), {"a": 1}]
def attempt(f, x):
    try:
        return repr(f(x))
    except Exception:
        return "ERROR"
for x in inputs:
    print(repr(x).ljust(10), *(attempt(f, x).ljust(14) for f in (int, float, str, bool, list)))
```

*Output:*

```text
3          3              3.0            '3'            True           ERROR
3.7        3              3.7            '3.7'          True           ERROR
'12'       12             12.0           '12'           True           ['1', '2']
'1.5'      ERROR          1.5            '1.5'          True           ['1', '.', '5']
''         ERROR          ERROR          ''             False          []
True       1              1.0            'True'         True           ERROR
None       ERROR          ERROR          'None'         False          ERROR
[1, 2]     ERROR          ERROR          '[1, 2]'       True           [1, 2]
(1, 2)     ERROR          ERROR          '(1, 2)'       True           [1, 2]
{'a': 1}   ERROR          ERROR          "{'a': 1}"     True           ['a']
```

#### Practice 3.14.2

**3.14.2-Q1** · `BASIC`

```python
print(int(3.7), float(3), str(3.7), bool(3.7))
```

**3.14.2-Q2** · `MID`

```python
print(list('12'), list((1, 2)), list({'a': 1}), list(range(2)))
```

**3.14.2-Q3** · `HARD`

```python
print(int(True), float(False), str(None), bool(None), bool('None'))
```

**3.14.2-Q4** · `TRAP`

```python
print(float(''))
```

### 3.14.3 Text to values and back: literal_eval, json, eval

To turn TEXT that looks like Python data into real objects use `ast.literal_eval` (safe: only literals). NEVER feed untrusted text to `eval`, which can run any code. For data exchange use `json.dumps` / `json.loads` (JSON has true/false/null, double quotes, no tuples or sets). `repr` and `str` go the other way.

> **Key rule:** parse untrusted text with ast.literal_eval or json.loads, never with eval.

**Example 3.14.3.1: literal_eval**

```python
import ast
print(ast.literal_eval("[1, 2, {'a': (3, 4)}]"), ast.literal_eval("3.5"), ast.literal_eval("'hi'"), ast.literal_eval("None"))
for bad in ("__import__('os').getcwd()", "1 + 2", "len"):
    try:
        ast.literal_eval(bad)
    except (ValueError, SyntaxError) as e:
        print(type(e).__name__)
```

*Output:*

```text
[1, 2, {'a': (3, 4)}] 3.5 hi None
ValueError
ValueError
ValueError
```

**Example 3.14.3.2: json round trip**

```python
import json
data = {"name": "Ann", "tags": ["a", "b"], "ok": True, "none": None, "n": 1.5, "t": (1, 2)}
text = json.dumps(data)
print(text)
back = json.loads(text)
print(back, back == data, type(back["t"]).__name__)
print(json.dumps(data, indent=2, sort_keys=True)[:40].replace("\n", "|"))
```

*Output:*

```text
{"name": "Ann", "tags": ["a", "b"], "ok": true, "none": null, "n": 1.5, "t": [1, 2]}
{'name': 'Ann', 'tags': ['a', 'b'], 'ok': True, 'none': None, 'n': 1.5, 't': [1, 2]} False list
{|  "n": 1.5,|  "name": "Ann",|  "none":
```

**Example 3.14.3.3: What JSON cannot hold**

```python
import json
for bad in ({1, 2}, {(1, 2): 3}, float("nan")):
    try:
        print(json.dumps(bad))
    except TypeError as e:
        print("TypeError", e)
```

*Output:*

```text
TypeError Object of type set is not JSON serializable
TypeError keys must be str, int, float, bool or None, not tuple
NaN
```

> ⚠️ **Watch out:** `eval('__import__("os")...')` executes arbitrary code. Treat eval as a security hole.

#### Practice 3.14.3

**3.14.3-Q1** · `BASIC`

```python
import ast; print(ast.literal_eval('[1, 2]'), type(ast.literal_eval('(1, 2)')))
```

**3.14.3-Q2** · `MID`

```python
import json; print(json.dumps([1, 'a', None, True]), json.loads('[1, null, false]'))
```

**3.14.3-Q3** · `HARD`

```python
import json; print(json.loads(json.dumps({1: 'a'})))
```

**3.14.3-Q4** · `TRAP`

```python
import json; print(json.loads("{'a': 1}"))
```

### 3.14.4 Converting between containers

Any iterable can feed `list()`, `tuple()`, `set()`, `sorted()`, `dict()` (needs pairs). Conversions have side effects: set() removes duplicates and order, dict() from a list of pairs keeps the LAST value of a repeated key, str to list splits into characters, `''.join` goes back. `dict` to `list` gives the keys.

**Container conversion cheat sheet**

| From -> To | Code | Notes |
|---|---|---|
| str -> list of chars | `list('abc')` | `''.join(lst)` reverses |
| list -> tuple | `tuple(lst)` | immutable copy |
| list -> set | `set(lst)` | unique, unordered |
| list -> dict | `dict(pairs)` | needs 2-item items |
| dict -> list of keys | `list(d)` | also `list(d.keys())` |
| dict -> list of pairs | `list(d.items())` | list of tuples |
| two lists -> dict | `dict(zip(k, v))` | stops at shorter |
| any -> sorted list | `sorted(x)` | new list |

**Example 3.14.4.1: A round-trip tour**

```python
s = "banana"
l = list(s)
print(l, tuple(l)[:2], set(l) == {"b", "a", "n"}, "".join(l), "".join(sorted(set(l))))
d = dict(zip("abc", [1, 2, 3]))
print(d, list(d), list(d.values()), list(d.items()))
print(dict([("a", 1), ("a", 2)]), dict(list(d.items())[:2]))
```

*Output:*

```text
['b', 'a', 'n', 'a', 'n', 'a'] ('b', 'a') True banana abn
{'a': 1, 'b': 2, 'c': 3} ['a', 'b', 'c'] [1, 2, 3] [('a', 1), ('b', 2), ('c', 3)]
{'a': 2} {'a': 1, 'b': 2}
```

**Example 3.14.4.2: Errors when shapes do not fit**

```python
for f in (lambda: dict([1, 2]), lambda: dict(["ab", "c"]), lambda: dict([(1, 2, 3)])):
    try:
        print(f())
    except (TypeError, ValueError) as e:
        print(type(e).__name__, "-", e)
```

*Output:*

```text
TypeError - cannot convert dictionary update sequence element #0 to a sequence
ValueError - dictionary update sequence element #1 has length 1; 2 is required
ValueError - dictionary update sequence element #0 has length 3; 2 is required
```

**Example 3.14.4.3: Copy semantics**

```python
a = [1, [2, 3]]
b = list(a)
t = tuple(a)
b[1].append(4)
print(a, t, b is a, t[1] is a[1])
```

*Output:*

```text
[1, [2, 3, 4]] (1, [2, 3, 4]) False True
```

#### Practice 3.14.4

**3.14.4-Q1** · `BASIC`

```python
print(list('ab'), tuple([1, 2]), set((1, 1, 2)) == {1, 2})
```

**3.14.4-Q2** · `MID`

```python
print(dict([('a', 1), ('a', 2)]), list({'x': 1, 'y': 2}))
```

**3.14.4-Q3** · `MID`

```python
print(dict(zip([1, 2, 3], 'ab')))
```

**3.14.4-Q4** · `HARD`

```python
print(dict(['ab', 'cd']), list(dict(['ab']).items()))
```

**3.14.4-Q5** · `TRAP`

```python
print(dict([1, 2]))
```

### 3.14.5 Safe conversion helpers

Real programs receive messy text. Wrap each conversion in a function that catches `ValueError` / `TypeError` and returns a default or None. Strip spaces, normalise decimal commas and handle empty strings before converting. Check ranges AFTER converting, because 'valid int' is not 'valid age'.

**Example 3.14.5.1: A small toolbox**

```python
def to_int(x, default=None):
    try:
        return int(str(x).strip())
    except (ValueError, TypeError):
        return default
def to_float(x, default=None):
    try:
        return float(str(x).strip().replace(",", "."))
    except (ValueError, TypeError):
        return default
def to_bool(x):
    return str(x).strip().lower() in ("1", "true", "yes", "y", "on")
print(to_int(" 42 "), to_int("4.2"), to_int(None, -1), to_float("3,5"), to_float("abc"), to_bool("Yes"), to_bool("off"))
```

*Output:*

```text
42 None -1 3.5 None True False
```

**Example 3.14.5.2: Validate after converting**

```python
def to_int(x):
    try:
        return int(x)
    except ValueError:
        return None
def parse_age(text):
    n = to_int(text)
    if n is None or not 0 <= n <= 150:
        raise ValueError(f"bad age: {text!r}")
    return n
for t in ["30", "-4", "abc", "200"]:
    try:
        print(parse_age(t))
    except ValueError as e:
        print(e)
```

*Output:*

```text
30
bad age: '-4'
bad age: 'abc'
bad age: '200'
```

**Example 3.14.5.3: Parsing a line of mixed data**

```python
line = "Ann, 30, 5.5, yes"
name, age, height, flag = [p.strip() for p in line.split(",")]
row = (name, int(age), float(height), flag.lower() == "yes")
print(row, [type(v).__name__ for v in row])
```

*Output:*

```text
('Ann', 30, 5.5, True) ['str', 'int', 'float', 'bool']
```

#### Practice 3.14.5

**3.14.5-Q1** · `BASIC`

```python
print(int(' 5 '), float(' 2.5 '), float('1e2'))
```

**3.14.5-Q2** · `MID`

```python
print('Yes'.lower() in ('yes', 'y'), bool('no'), 'no' in ('yes', 'y'))
```

**3.14.5-Q3** · `HARD`

```python
def f(x):
    try:
        return int(x)
    except (TypeError, ValueError):
        return -1
print(f('3'), f('x'), f(None), f(3.9), f([1]))
```

**3.14.5-Q4** · `TRAP`

```python
print(int('1,000'))
```

### 3.14.6 Type checking: isinstance, duck typing and annotations

Python favours DUCK TYPING: use an object if it supports the operations you need (EAFP: 'easier to ask forgiveness than permission', try it and catch the error). Use `isinstance` when you must branch on type, preferring abstract classes from `collections.abc` (`Sequence`, `Mapping`, `Iterable`, `Callable`) over concrete ones. Type ANNOTATIONS (`def f(x: int) -> str`) document intent and feed tools like mypy, but are NOT enforced at run time.

> **Key rule:** annotations are hints, not rules; check types yourself with isinstance when you need to.

**Example 3.14.6.1: Abstract base classes**

```python
from collections.abc import Sequence, Mapping, Iterable
for v in ([1], (1,), "s", {1: 2}, {1}, range(2), 5):
    print(repr(v).ljust(8), isinstance(v, Sequence), isinstance(v, Mapping), isinstance(v, Iterable))
```

*Output:*

```text
[1]      True False True
(1,)     True False True
's'      True False True
{1: 2}   False True True
{1}      False False True
range(0, 2) True False True
5        False False False
```

**Example 3.14.6.2: Duck typing versus type tests**

```python
def total_len(items):
    try:
        return sum(len(x) for x in items)
    except TypeError:
        return "needs sized items"
print(total_len(["ab", [1, 2, 3], (4,)]), total_len([1, 2]))
def describe(x):
    if isinstance(x, bool): return "bool"
    if isinstance(x, (int, float)): return "number"
    if isinstance(x, str): return "text"
    return type(x).__name__
print([describe(v) for v in (True, 3, 2.5, "a", [1])])
```

*Output:*

```text
6 needs sized items
['bool', 'number', 'number', 'text', 'list']
```

**Example 3.14.6.3: Annotations are not enforced**

```python
def double(x: int) -> int:
    return x * 2
print(double(4), double("ab"), double.__annotations__)
from typing import Optional, Union
def f(a: Optional[int] = None, b: Union[int, str] = 0, c: list[int] | None = None) -> None:
    pass
print(f.__annotations__["a"], f.__annotations__["c"])
```

*Output:*

```text
8 abab {'x': <class 'int'>, 'return': <class 'int'>}
typing.Optional[int] list[int] | None
```

#### Practice 3.14.6

**3.14.6-Q1** · `BASIC`

```python
from collections.abc import Sequence
print(isinstance([1], Sequence), isinstance({1}, Sequence))
```

**3.14.6-Q2** · `MID`

```python
def f(x: int): return x
print(f('hi'), f.__annotations__)
```

**3.14.6-Q3** · `HARD`

```python
from collections.abc import Iterable, Mapping
print(isinstance('a', Iterable), isinstance({}, Mapping), isinstance(5, Iterable))
```

**3.14.6-Q4** · `TRAP`

```python
from collections.abc import Sequence
print(isinstance('abc', Sequence), isinstance(b'a', Sequence), isinstance({'a': 1}, Sequence), isinstance(range(1), Sequence))
```

### 3.14.7 Choosing the right data type

Pick the type from the job. If order and duplicates matter and the data changes, use a list; if it is a fixed record, a tuple. If you need fast membership and uniqueness, a set. If you look things up by a key, a dict. For money use Decimal or integer cents; for exact ratios Fraction; for flags bool; for 'no value' None; for binary data bytes/bytearray; for text str.

**Decision table**

| I need to... | Use | Why |
|---|---|---|
| store a changing sequence | `list` | append, pop, sort in place |
| return several values / fixed record | `tuple` / `namedtuple` | immutable, unpackable |
| remove duplicates, test membership | `set` | O(1) membership |
| look up by name or id | `dict` | O(1) key lookup |
| use a collection as a dict key | `tuple` / `frozenset` | hashable |
| count things | `Counter` | built-in frequency tools |
| loop N times | `range` | lazy, tiny memory |
| exact money | `Decimal` | decimal arithmetic |
| read and write binary data | `bytes` / `bytearray` | raw 0-255 values |
| queue | `collections.deque` | O(1) both ends |
| sorted data with fast insert | `bisect` + list | binary search |
| 'no value' | `None` | singleton, test with `is` |

**Example 3.14.7.1: The same task in four types**

```python
words = ["to", "be", "or", "not", "to", "be"]
print(len(words), len(set(words)), sorted(set(words)))
from collections import Counter
print(Counter(words).most_common(2), {w: words.count(w) for w in sorted(set(words))})
seen = {}
for i, w in enumerate(words):
    seen.setdefault(w, []).append(i)
print(seen)
```

*Output:*

```text
6 4 ['be', 'not', 'or', 'to']
[('to', 2), ('be', 2)] {'be': 2, 'not': 1, 'or': 1, 'to': 2}
{'to': [0, 4], 'be': [1, 5], 'or': [2], 'not': [3]}
```

**Example 3.14.7.2: Cost of the wrong choice**

```python
import time
items = list(range(5000))
lookups = list(range(5000, 7000))
as_set = set(items)
t0 = time.perf_counter(); [x in items for x in lookups]; t1 = time.perf_counter()
[x in as_set for x in lookups]; t2 = time.perf_counter()
print("set is much faster:", (t1 - t0) > (t2 - t1) * 50)
```

*Output:*

```text
set is much faster: True
```

#### Practice 3.14.7

**3.14.7-Q1** · `BASIC`

```python
print(len(set([1, 2, 2, 3])), len([1, 2, 2, 3]))
```

**3.14.7-Q2** · `MID`

```python
from collections import Counter
print(Counter([1, 2, 2, 3, 3, 3]).most_common(1)[0])
```

**3.14.7-Q3** · `HARD`

```python
d = {}
for i, c in enumerate('abca'):
    d.setdefault(c, []).append(i)
print(d)
```

**3.14.7-Q4** · `TRAP`

```python
pts = {[0, 0]: 'origin'}
```

---

## Chapter 3 Summary: The 42 Rules

1. A data type belongs to the object, never to the name; type(x) shows it.
2. Use isinstance(x, (A, B)) for checks; bool is a subclass of int, so isinstance(True, int) is True.
3. Falsy means None, False, zero, or empty. The string 'False', nan and [0] are truthy.
4. {} is an empty dict; the empty set is set(); (1) is an int and (1,) is a tuple.
5. int has unlimited size and never overflows; / always returns a float, // and % floor toward minus infinity.
6. a == (a // b) \* b + a % b always holds, and a % b takes the sign of b.
7. int(3.9) truncates to 3; int('3.5') is a ValueError. Convert in two steps for float text.
8. Compare numbers with ==, never is; small-int caching is an implementation detail.
9. float is binary: 0.1 + 0.2 != 0.3. Compare with math.isclose, never ==.
10. nan != nan. Test with math.isnan; inf - inf and 0 \* inf give nan.
11. round() uses banker's rounding (round(2.5) == 2); floor goes down, ceil up, trunc toward zero.
12. Use Decimal('0.1') (from strings) for money and Fraction for exact ratios; never Decimal(0.1).
13. complex has == but no ordering; use cmath for square roots of negatives.
14. bool arithmetic works (True + True == 2); and/or return operands, not booleans, and short-circuit.
15. Test None with is None; methods that mutate in place return None (a = a.sort() sets a to None).
16. Never use a mutable default argument; use None and create the object inside.
17. Strings are immutable: every method returns a new string, so assign the result.
18. s[i] is a str of length 1; slices never raise IndexError; s[::-1] reverses.
19. find returns -1, index raises; test membership with 'x' in s, never `if s.find(x):`.
20. strip(chars) removes a SET of characters from the ends; use removeprefix/removesuffix for words.
21. split() collapses whitespace; split(' ') does not; join is called on the separator and needs str items.
22. isdigit is True for superscripts and False for '-5'; validate numbers with try/int().
23. Build big strings with ''.join(parts); use f-strings for formatting and !r to see hidden characters.
24. str holds characters, bytes holds data; always name the encoding when you encode or decode.
25. Normalise (NFC) and casefold before comparing text from different sources.
26. Lists are mutable: b = a aliases; copy() is shallow; use copy.deepcopy for nested data.
27. [[0] \* n] \* m repeats one row m times; build grids with a comprehension.
28. append adds one object, extend adds each item; a += b mutates, a = a + b rebinds.
29. Never change a list's size while looping over it; iterate over a copy or build a new list.
30. sort() mutates and returns None, sorted() returns a new list, and both are stable.
31. Use deque for queues; list.pop(0) and insert(0, x) are O(n).
32. A tuple's immutability is shallow: a list inside a tuple can still change.
33. Sets are unordered and unique, with O(1) membership; never rely on set order.
34. remove raises KeyError, discard does not; operators need sets, methods accept any iterable.
35. Dict keys must be hashable; 1, 1.0 and True are the same key.
36. d[k] raises KeyError; get(k, default) does not insert; setdefault inserts if missing.
37. Do not add or delete dict keys while iterating; iterate over list(d).
38. dict.fromkeys(keys, []) shares one list for every key.
39. range is lazy, stop is excluded, and it accepts only ints.
40. Numbers upgrade implicitly (bool, int, float, complex); everything else needs an explicit constructor.
41. Parse untrusted text with ast.literal_eval or json.loads, never eval.
42. Annotations are hints and are not enforced at run time; use isinstance when you must check.

### Error Message Decoder

| Message | Usual cause | Fix |
|---|---|---|
| TypeError: can only concatenate str (not "int") to str | Mixed str and int with + | str(n) or an f-string |
| TypeError: 'str' object does not support item assignment | Tried to change a character | Rebuild the string with slicing |
| TypeError: 'tuple' object does not support item assignment | Tried to change a tuple item | Use a list, or build a new tuple |
| TypeError: unhashable type: 'list' | list/dict/set used as dict key or set member | Use a tuple or frozenset |
| TypeError: list indices must be integers or slices, not float | Used / where // was needed | Use // or int() |
| TypeError: 'int' object is not iterable | list(5), for x in 5 | Wrap in range() or a list |
| TypeError: sequence item 0: expected str instance, int found | join on non-strings | map(str, items) |
| TypeError: '<' not supported between instances of 'str' and 'int' | Sorting or comparing mixed types | Convert first or use key= |
| TypeError: unsupported operand type(s) for \|: 'set' and 'list' | Set operator with a non-set | Use the method (union) or set(x) |
| TypeError: 'dict_keys' object is not subscriptable | Indexed a dict view | list(d)[0] or next(iter(d)) |
| ValueError: invalid literal for int() with base 10 | Text is not a whole number | try/except; float() first for '3.0' |
| ValueError: could not convert string to float | Bad float text | Strip, replace ',' with '.', or catch |
| ValueError: substring not found | str.index / list.index missed | Use in or find, or catch ValueError |
| ValueError: too many values to unpack | Target count differs from length | Match counts or use a starred target |
| ValueError: math domain error | sqrt/log of an invalid number | Check the input; cmath for negatives |
| ValueError: empty separator | split('') or similar | Use list(s) to split characters |
| IndexError: list index out of range | Index >= len or empty list | Check len, or use slicing / [-1] with a guard |
| IndexError: string index out of range | Same for str | Slice instead: s[:1] |
| IndexError: pop from empty list | pop() on [] | if a: a.pop() |
| KeyError: 'name' | Missing dict key | d.get(k), `in`, or defaultdict |
| KeyError (set.remove) | remove of absent item | Use discard |
| AttributeError: 'tuple' object has no attribute 'append' | Mutating method on an immutable | Convert to list or concatenate |
| AttributeError: 'NoneType' object has no attribute ... | Used the None returned by sort/append | Do not assign mutating results |
| RuntimeError: dictionary changed size during iteration | Added/deleted keys in a loop | Loop over list(d) |
| RuntimeError: Set changed size during iteration | Same for sets | Loop over list(s) |
| ZeroDivisionError: division by zero | x / 0, x // 0, x % 0 | Check the divisor |
| OverflowError: (34, 'Numerical result out of range') | float ** too large | Use ints, Decimal or logs |
| UnicodeEncodeError / UnicodeDecodeError | Wrong encoding | Name the encoding; errors='replace' |
| SyntaxError: leading zeros in decimal integer literals | Wrote 010 | Use 10 or 0o10 |
| BufferError: Existing exports of data | Resized a bytearray with a live memoryview | release() the view first |

---

## Final Exam (60 mixed HARD and TRAP questions)

One question taken from each of 60 topics. Predict all outputs on paper, then check against the answer key. Score: 53+ mastery, 42-52 solid, below 42 revisit the earlier sections.

**E1 (from 3.1.1)**

```python
print(type(1 + 1.0), type(True + True), type('a' * 2))
```

**E2 (from 3.1.3)**

```python
data = [1, True, 2.0, 'x', 3]
print(sum(1 for d in data if isinstance(d, int)))
```

**E3 (from 3.1.5)**

```python
x = 0
print(x or 'default', x if x is not None else 'default')
```

**E4 (from 3.1.7)**

```python
print(len({}), len({'a': 1, 'a': 2}), len({1, 1.0, True}))
```

**E5 (from 3.2.2)**

```python
print((2 ** 64) * (2 ** 64) == 2 ** 128)
```

**E6 (from 3.2.4)**

```python
print(int(-7 / 2), -7 // 2, round(-3.5), -7 % 2)
```

**E7 (from 3.2.7)**

```python
print(int(float('1e3')), int(1e3), int(2.5e0))
```

**E8 (from 3.2.9)**

```python
print(int.from_bytes(b'\xff\xff', 'big'), int.from_bytes(b'\xff\xff', 'big', signed=True))
```

**E9 (from 3.2.11)**

```python
import math; print(math.gcd(0, 0), math.factorial(0), math.comb(3, 5))
```

**E10 (from 3.2.13)**

```python
print(len(str(2 ** 4000)))
```

**E11 (from 3.3.1)**

```python
print(type(10 / 2), type(2 ** 3), type(2 ** 3.0), type(-2 ** 0.5))
```

**E12 (from 3.3.4)**

```python
print(max(1, float('nan')), max(float('nan'), 1))
```

**E13 (from 3.3.6)**

```python
print(round(5.5), round(6.5), round(7.5), round(8.5))
```

**E14 (from 3.3.8)**

```python
import sys; print(1.0 + sys.float_info.epsilon == 1.0, 1.0 + sys.float_info.epsilon / 2 == 1.0)
```

**E15 (from 3.3.10)**

```python
import math; print(sum([0.1] * 10) == 1.0, math.fsum([0.1] * 10) == 1.0)
```

**E16 (from 3.3.12)**

```python
from fractions import Fraction; print(Fraction(1, 10) + Fraction(2, 10) == Fraction(3, 10))
```

**E17 (from 3.4.1)**

```python
print((1 + 2j) * (3 - 1j), (1 + 2j) / (1 - 1j))
```

**E18 (from 3.5.2)**

```python
x = []
print(x and x[0], x or 'empty', len(x) > 0 and x[0])
```

**E19 (from 3.5.4)**

```python
x = 'a'
print(x == 'a' or 'b' == x, x == ('a' or 'b'), x == ('b' or 'a'))
```

**E20 (from 3.6.2)**

```python
def f(x=len([1, 2])):
    return x
print(f(), f(5))
```

**E21 (from 3.7.1)**

```python
print('ab' 'cd' * 2, ('ab' 'cd') * 2, 'ab' + 'cd' * 2)
```

**E22 (from 3.7.3)**

```python
print(str([1, 'a']), repr([1, 'a']), str(['a']) == repr(['a']))
```

**E23 (from 3.7.6)**

```python
s = 'abcdef'
print(s[:2] + s[2:] == s, s[-2:2], s[0:0] == s[5:5], s[::-1][::-1] == s)
```

**E24 (from 3.7.8)**

```python
print('10' < '9', 10 < 9, '10' < '2', sorted(['10', '9', '2']))
```

**E25 (from 3.7.10)**

```python
print('3rd place'.title(), 'o\'neil'.title(), 'ab-cd'.title())
```

**E26 (from 3.7.12)**

```python
print('banana'.removesuffix('na'), 'banana'.rstrip('na'))
```

**E27 (from 3.7.14)**

```python
print('1,2,3'.split(',') == [1, 2, 3], sum(map(int, '1,2,3'.split(','))))
```

**E28 (from 3.7.16)**

```python
print('ab'.join('123'), ''.join(['a', 'b']) * 2)
```

**E29 (from 3.7.19)**

```python
print(repr('a\tb'.expandtabs()), len('a\tb'.expandtabs()), len('a\tb'.expandtabs(1)))
```

**E30 (from 3.7.21)**

```python
print('100%% sure', '%s' % 5, '%r' % 'a')
```

**E31 (from 3.7.23)**

```python
w = 6
print(f'{3.14159:{w}.2f}|{"x":{w}}|{{w}}')
```

**E32 (from 3.7.25)**

```python
print('é'.encode('latin-1'), 'é'.encode('utf-8'), 'é'.encode('latin-1').decode('utf-8', errors='replace'))
```

**E33 (from 3.7.27)**

```python
print(len([n for n in dir(str) if n.startswith('is') and not n.startswith('__')]))
```

**E34 (from 3.7.30)**

```python
s = 'abc'
if s.find('a'):
    print('found a')
else:
    print('not found')
if s.find('c'):
    print('found c')
```

**E35 (from 3.8.2)**

```python
ba = bytearray(b'hello'); ba[0:1] = b'J'; print(ba.decode(), bytes(ba) == b'Jello')
```

**E36 (from 3.9.1)**

```python
print(list({'b': 1, 'a': 2}), list({3, 1, 2}), list(map(str, [1, 2])))
```

**E37 (from 3.9.3)**

```python
a = [1, 2]
a = a.append(3)
print(a)
```

**E38 (from 3.9.5)**

```python
a = [[1, 2], [3]]
print(a.count([1, 2]), a.index([3]), 3 in a)
```

**E39 (from 3.9.7)**

```python
g = [[0] * 2] * 2
g[1][1] = 5
print(g)
```

**E40 (from 3.9.10)**

```python
m = [[0] * 2] * 2
m[0][0] = 1
print(m)
```

**E41 (from 3.9.12)**

```python
m = map(int, ['1', '2'])
print(list(m), list(m))
```

**E42 (from 3.9.14)**

```python
a = [1, 2, 3]
for x in a:
    a.remove(x)
print(a)
```

**E43 (from 3.9.16)**

```python
a = [1, 2, 3]
print(a.remove(2) or a)
```

**E44 (from 3.10.1)**

```python
x = 1,
y = (1)
z = (1,)
print(x == z, x == y, type(y))
```

**E45 (from 3.10.4)**

```python
import sys; print(sys.getsizeof((1, 2)) < sys.getsizeof([1, 2]))
```

**E46 (from 3.10.6)**

```python
from collections import namedtuple
P = namedtuple('P', 'a b')
print(P(1, 2) == (1, 2), P(1, 2) == namedtuple('Q', 'a b')(1, 2))
```

**E47 (from 3.11.1)**

```python
print(len({(1, 2), (2, 1), (1, 2)}), {x % 3 for x in range(10)})
```

**E48 (from 3.11.3)**

```python
a = {1, 2, 3}
a ^= {3, 4}
a &= {1, 4, 9}
print(a)
```

**E49 (from 3.11.5)**

```python
print(len(set('abc') & set('cde')), set('abc') ^ set('cde') == set('abde'))
```

**E50 (from 3.11.7)**

```python
print({} == set(), type({}) == type(set()), bool({}), bool({0}))
```

**E51 (from 3.12.1)**

```python
print(dict.fromkeys('aab', []), len(dict.fromkeys('aab')))
```

**E52 (from 3.12.3)**

```python
d = {}
d.setdefault('list', []).append(1)
d.setdefault('list', []).append(2)
print(d)
```

**E53 (from 3.12.5)**

```python
d = {'a': 1, 'b': 2}
print(max(d, key=d.get), sorted(d, key=d.get, reverse=True))
```

**E54 (from 3.12.7)**

```python
d = dict.fromkeys(['a', 'b'], [])
d['a'].append(1)
print(d)
```

**E55 (from 3.12.9)**

```python
print({'a': 1, 'b': 2} == {'b': 2, 'a': 1}, [1, 2] == [2, 1])
```

**E56 (from 3.12.12)**

```python
print({}.get('a', 1) + {}.get('a', 1), dict.fromkeys('ab', 1)['a'])
```

**E57 (from 3.13.1)**

```python
print(list(range(5, 1)), list(range(1, 5, -1)), list(range(-3, 3, 2)))
```

**E58 (from 3.14.1)**

```python
print(1 + True + 1.0, type(1 + True + 1.0), 3 + 0j == 3)
```

**E59 (from 3.14.3)**

```python
import json; print(json.loads(json.dumps({1: 'a'})))
```

**E60 (from 3.14.5)**

```python
def f(x):
    try:
        return int(x)
    except (TypeError, ValueError):
        return -1
print(f('3'), f('x'), f(None), f(3.9), f([1]))
```

---

## Answer Key (outputs from running the code)

Cover this section while you predict. Each answer is the real output produced by running the question.

### Answers: 3.1.1 What is a data type

- **Q1** `<class 'int'> <class 'float'> <class 'str'>`
- **Q2** `<class 'list'> <class 'tuple'> <class 'dict'> <class 'set'>`
- **Q3** `<class 'NoneType'> <class 'builtin_function_or_method'> <class 'builtin_function_or_method'>`
- **Q4** `<class 'type'> True`
- **Q5** `<class 'float'> <class 'int'> <class 'str'>`

### Answers: 3.1.2 The built-in type map

- **Q1** `range bytes`
- **Q2** `True False`
- **Q3** `False True`
- **Q4** `False True`
- **Q5** `<class 'dict'> <class 'set'> dict_keys`

### Answers: 3.1.3 type(), isinstance() and issubclass()

- **Q1** `True False`
- **Q2** `True True`
- **Q3** `False True`
- **Q4** `True True`
- **Q5** `3`

### Answers: 3.1.4 Mutable and immutable types

- **Q1** `immutable`
- **Q2** `[1, 2]`
- **Q3** `(1, [2, 3])`
- **Q4** `True`
- **Q5** `(1, 2, 3) (1, 2)`

### Answers: 3.1.5 Truthiness of every type

- **Q1** `False True False True`
- **Q2** `False True False False`
- **Q3** `True False False True`
- **Q4** `True False False False`
- **Q5** `default 0`

### Answers: 3.1.6 Literals of every type

- **Q1** `255 3 8`
- **Q2** `<class 'dict'> <class 'set'>`
- **Q3** `<class 'int'> <class 'tuple'> <class 'tuple'>`
- **Q4** `(1,) <class 'tuple'>`
- **Q5** `20 3 10000000000.0`

### Answers: 3.1.7 Sequences, sets and mappings: the common protocols

- **Q1** `2 1 3 4`
- **Q2** `False True True True`
- **Q3** `[1, 3] ['a', 'c']`
- **Q4** `0 1 1`

### Answers: 3.2.1 Integer literals and bases

- **Q1** `5 15 31`
- **Q2** `2000`
- **Q3** `True True`
- **Q4** `39`
- **Q5** `10 3 8`

### Answers: 3.2.2 Arbitrary precision

- **Q1** `1024 1000`
- **Q2** `1180591620717411303424`
- **Q3** `48`
- **Q4** `True 9223372036854775808`
- **Q5** `True`

### Answers: 3.2.3 Arithmetic operators

- **Q1** `13 5 36`
- **Q2** `2.25 2 1`
- **Q3** `4.0 0.5 True`
- **Q4** `-4 512 5`
- **Q5** `<class 'float'> <class 'int'> <class 'float'> <class 'float'>`

### Answers: 3.2.4 Floor division, modulo and negatives; divmod

- **Q1** `3 2 (3, 2)`
- **Q2** `-4 3`
- **Q3** `-4 -3`
- **Q4** `(3, -1) (-4, -1)`
- **Q5** `-3 -4 -4 1`

### Answers: 3.2.5 Exponentiation and pow()

- **Q1** `81 81`
- **Q2** `4 4`
- **Q3** `1 1 1`
- **Q4** `5 1`
- **Q5** `3.0 3.0`

### Answers: 3.2.6 Bitwise operators

- **Q1** `2 7 5`
- **Q2** `32 8`
- **Q3** `-1 -6 0`
- **Q4** `-5 -5 -1`
- **Q5** `False True False -2`

### Answers: 3.2.7 The int() constructor

- **Q1** `7 7 -7`
- **Q2** `5 63 255`
- **Q3** `12 5 12`
- **Q4** `1000 1000 2`
- **Q5** `ValueError: invalid literal for int() with base 10: '3.0'`

### Answers: 3.2.8 Converting to other bases: bin, oct, hex, format

- **Q1** `0b101 0o10 0xff`
- **Q2** `101 ff FF`
- **Q3** `00000101 0b00000101`
- **Q4** `-0b101 -5`
- **Q5** `0b1010b11 8`

### Answers: 3.2.9 int methods and attributes

- **Q1** `4 3 0`
- **Q2** `8 10 3`
- **Q3** `b'\x00\x01' b'\x01\x00'`
- **Q4** `65535 -1`
- **Q5** `OverflowError: int too big to convert`

### Answers: 3.2.10 Built-in numeric functions: abs, round, divmod, pow, sum, min, max

- **Q1** `3 2 8`
- **Q2** `10 20`
- **Q3** `1200 1200 1400`
- **Q4** `-7 3`
- **Q5** `ValueError: max() iterable argument is empty`

### Answers: 3.2.11 math functions for integers

- **Q1** `4 24`
- **Q2** `24 20`
- **Q3** `9 10 10`
- **Q4** `0 1 0`
- **Q5** `ValueError: factorial() not defined for negative values`

### Answers: 3.2.12 Comparing ints and other numbers; chained comparison

- **Q1** `True True True`
- **Q2** `True False`
- **Q3** `2 True True 1.5`
- **Q4** `{1: 'bool'} 1`
- **Q5** `True False True True`

### Answers: 3.2.13 Small-int caching and the 4300-digit string limit

- **Q1** `True True`
- **Q2** `True`
- **Q3** `1205`
- **Q4**
  ```text
  ValueError: Exceeds the limit (4300 digits) for integer string conversion; use
  sys.set_int_max_str_digits() to increase the limit
  ```

### Answers: 3.2.14 Common int pitfalls

- **Q1** `3.5 3`
- **Q2** `0 2 2 4`
- **Q3** `20`
- **Q4** `6.5`
- **Q5** `TypeError: list indices must be integers or slices, not float`

### Answers: 3.3.1 Float literals and scientific notation

- **Q1** `3.5 3.0 <class 'float'>`
- **Q2** `100.0 0.01 5.0`
- **Q3** `1e+16 1000000000000000.0 1e-05`
- **Q4** `3.0 1.0 -4.0 True`
- **Q5** `<class 'float'> <class 'int'> <class 'float'> <class 'float'>`

### Answers: 3.3.2 Binary representation and precision

- **Q1** `0.75 True`
- **Q2** `True False`
- **Q3** `0.30000000000000004 False`
- **Q4** `True 3.3000000000000003 False`
- **Q5** `True False`

### Answers: 3.3.3 The float() constructor, inf and nan

- **Q1** `7.0 2.5 100.0`
- **Q2** `3.5 1.0 -0.5`
- **Q3** `inf -inf nan`
- **Q4** `OverflowError: int too large to convert to float`
- **Q5** `ValueError: could not convert string to float: '1,5'`

### Answers: 3.3.4 inf and nan behaviour

- **Q1** `True True`
- **Q2** `False True`
- **Q3** `inf nan`
- **Q4** `1 nan`
- **Q5** `ZeroDivisionError: float division by zero`

### Answers: 3.3.5 Comparing floats safely: math.isclose

- **Q1** `True`
- **Q2** `False`
- **Q3** `True`
- **Q4** `True True`
- **Q5** `False True`

### Answers: 3.3.6 Rounding: round, floor, ceil, trunc, int

- **Q1** `5 4 5`
- **Q2** `0 2 2 0`
- **Q3** `-2 -1 -1`
- **Q4** `2.67 2.67 0.28`
- **Q5** `6 6 8 8`

### Answers: 3.3.7 float methods and attributes

- **Q1** `True False`
- **Q2** `(1, 2) (1, 8)`
- **Q3** `3.0 0.5`
- **Q4** `True True`
- **Q5** `False`

### Answers: 3.3.8 Limits: sys.float_info, overflow and underflow

- **Q1** `True`
- **Q2** `inf 0.0`
- **Q3** `False True`
- **Q4** `OverflowError: math range error`
- **Q5** `OverflowError: (34, 'Numerical result out of range')`

### Answers: 3.3.9 Formatting floats for display

- **Q1** `3.14 2.0`
- **Q2** `1,234,567.9 5%`
- **Q3** `5.50| 5.50 | 005.50`
- **Q4** `1e-07 0.000000 1.234568e+08`
- **Q5** `2 4 0 2`

### Answers: 3.3.10 The math module for floats

- **Q1** `9.0 13.0`
- **Q2** `0.0 2.0 3.0`
- **Q3** `0.5 45.0`
- **Q4** `True True`
- **Q5** `ValueError: math domain error`

### Answers: 3.3.11 The decimal module: exact decimal arithmetic

- **Q1** `3.3`
- **Q2** `3.30 True`
- **Q3** `2.5 2`
- **Q4** `0.5 False`
- **Q5** `TypeError: unsupported operand type(s) for +: 'decimal.Decimal' and 'float'`

### Answers: 3.3.12 The fractions module: exact rationals

- **Q1** `1/2 3`
- **Q2** `5/6`
- **Q3** `5/4 1`
- **Q4** `True`
- **Q5** `ZeroDivisionError: Fraction(1, 0)`

### Answers: 3.3.13 Common float pitfalls

- **Q1** `0.7999999999999999 0.7000000000000001`
- **Q2** `0.0 1.0`
- **Q3** `True`
- **Q4** `0.30000000000000004 False`
- **Q5** `28 29 29`

### Answers: 3.4.1 Complex literals and attributes

- **Q1** `1.0 2.0`
- **Q2** `5.0 (1-2j)`
- **Q3** `(-1+0j) 2j`
- **Q4** `(5+5j) (-0.5+1.5j)`
- **Q5** `ValueError: complex() arg is a malformed string`

### Answers: 3.4.2 Complex arithmetic, no ordering, and cmath

- **Q1** `(4+6j) (2+4j)`
- **Q2** `3j (3+0j)`
- **Q3** `True True`
- **Q4** `(-4+0j) True`
- **Q5** `TypeError: '<' not supported between instances of 'complex' and 'complex'`

### Answers: 3.5.1 bool is a subclass of int

- **Q1** `2 1 3`
- **Q2** `1 0 1.0`
- **Q3** `3`
- **Q4** `True False True <class 'int'>`
- **Q5** `b {True: 'y'} True!`

### Answers: 3.5.2 Boolean operators: and, or, not

- **Q1** `False True False`
- **Q2** `a b 0`
- **Q3** `1`
- **Q4** `True True 1 0`
- **Q5** `[] empty False`

### Answers: 3.5.3 Bitwise operators on bool, comparisons and any/all

- **Q1** `True False`
- **Q2** `True False False False`
- **Q3** `False True 0`
- **Q4** `-2 -1 False`
- **Q5** `True False`

### Answers: 3.5.4 bool pitfalls

- **Q1** `True False True`
- **Q2** `False True`
- **Q3** `blue`
- **Q4** `True False {True}`
- **Q5** `True True False`

### Answers: 3.6.1 None: the absence of a value

- **Q1** `True False False`
- **Q2** `1 None`
- **Q3** `[1, 2] None`
- **Q4** `<class 'NoneType'> None True`
- **Q5** `TypeError: '>' not supported between instances of 'int' and 'NoneType'`

### Answers: 3.6.2 None as default and sentinel patterns

- **Q1** `none 0`
- **Q2** `[1, 2]`
- **Q3** `[]`
- **Q4** `[1] [2]`
- **Q5** `2 5`

### Answers: 3.6.3 Ellipsis, NotImplemented and slice objects

- **Q1** `ellipsis NotImplementedType`
- **Q2** `ace ace`
- **Q3** `slice(None, None, -1) cba`
- **Q4** `(2, 5, 1) (0, 2, 1)`
- **Q5** `True False`

### Answers: 3.7.1 Creating strings: quotes, triple quotes, concatenation

- **Q1** `abc True`
- **Q2** `5 0 1`
- **Q3** `123 1.0 -0.0`
- **Q4** `5 ['a', ' b']`
- **Q5** `abcdabcd abcdabcd abcdcd`

### Answers: 3.7.2 Escape sequences and raw strings

- **Q1** `3 4`
- **Q2** `['a', 'b'] x\y`
- **Q3** `1 2 False`
- **Q4** `True '\n' '\\n'`
- **Q5** `2 1 2`

### Answers: 3.7.3 str versus repr, print and multi-line text

- **Q1** `'a' a 5 5.0`
- **Q2** `'a\tb' 6`
- **Q3** `xy!`
- **Q4** `"'a'" a`
- **Q5** `[1, 'a'] [1, 'a'] True`

### Answers: 3.7.4 Immutability and identity of strings

- **Q1** `abc`
- **Q2** `abcd abc`
- **Q3** `zbc abc`
- **Q4** `aXc`
- **Q5** `TypeError: 'str' object doesn't support item deletion`

### Answers: 3.7.5 Indexing: positive and negative

- **Q1** `h o o h`
- **Q2** `b b`
- **Q3** `b a`
- **Q4** `'' ''`
- **Q5** `IndexError: string index out of range`

### Answers: 3.7.6 Slicing in every form

- **Q1** `bcd ab ef`
- **Q2** `ef fedcba`
- **Q3** `ace bdf fdb`
- **Q4** `edc fed cdef`
- **Q5** `True True True`

### Answers: 3.7.7 Concatenation and repetition

- **Q1** `ab aaa abab`
- **Q2** `True True 10`
- **Q3** `ab a`
- **Q4** `12 3 11 2`
- **Q5** `TypeError: can only concatenate str (not "int") to str`

### Answers: 3.7.8 len, in, comparison and ordering

- **Q1** `True False False`
- **Q2** `True False True`
- **Q3** `['A', 'B', 'a', 'b']`
- **Q4** `['A', 'a', 'b', 'B']`
- **Q5** `True False True ['10', '2', '9']`

### Answers: 3.7.9 Iterating over strings

- **Q1** `['a', 'b', 'c']`
- **Q2** `[(0, 'a'), (1, 'b')] [('a', 'x'), ('b', 'y')]`
- **Q3** `cba ['a', 'a', 'a', 'b', 'n', 'n']`
- **Q4** `4 imps`
- **Q5** `['a', 'b', 'c', 'd'] ['ab', 'cd'] ['a', 'b', ',', ' ', 'c', 'd']`

### Answers: 3.7.10 Case methods: upper, lower, capitalize, title, swapcase, casefold

- **Q1** `HELLO hello Hello`
- **Q2** `Hello world Hello World`
- **Q3** `AbC AB1C 123`
- **Q4** `SS 2 ss`
- **Q5** `3Rd Place O'Neil Ab-Cd`

### Answers: 3.7.11 Searching: find, rfind, index, rindex, count, in

- **Q1** `2 3 -1`
- **Q2** `3 2`
- **Q3** `2 5 4`
- **Q4** `0 False 4 5`
- **Q5** `ValueError: substring not found`

### Answers: 3.7.12 startswith, endswith, removeprefix, removesuffix

- **Q1** `True True False`
- **Q2** `True False`
- **Q3** `llo hello`
- **Q4** `bana b`
- **Q5** `TypeError: startswith first arg must be str or a tuple of str, not list`

### Answers: 3.7.13 strip, lstrip, rstrip

- **Q1** `'hi' 'hi ' ' hi'`
- **Q2** `a a-b c`
- **Q3** `1.5 1 0.`
- **Q4** `'' hixx o`
- **Q5** `site`

### Answers: 3.7.14 split and rsplit

- **Q1** `['a', 'b', 'c'] ['a', 'b', 'c']`
- **Q2** `['a', 'b'] ['', 'a', '', 'b', '']`
- **Q3** `['a', 'b', 'c-d'] ['a-b', 'c', 'd']`
- **Q4** `[] [''] ['', ''] ['a', '']`
- **Q5** `False 6`

### Answers: 3.7.15 splitlines, partition and rpartition

- **Q1** `['a', 'b', 'c'] ('a', '=', 'b')`
- **Q2** `('a', '=', 'b=c') ('a=b', '=', 'c')`
- **Q3** `('abc', '', '') ('', '', 'abc')`
- **Q4** `['a'] ['a', ''] [] ['']`
- **Q5** `('a', ' ', ' b') b c`

### Answers: 3.7.16 join

- **Q1** `a-b-c ab`
- **Q2** `a,b,c x True`
- **Q3** `0,1,2,3`
- **Q4** `1ab2ab3 abab`
- **Q5** `TypeError: sequence item 0: expected str instance, int found`

### Answers: 3.7.17 replace

- **Q1** `heLLo heLlo`
- **Q2** `bb baba`
- **Q3** `-a-b-c-`
- **Q4** `a b`
- **Q5** `hello`

### Answers: 3.7.18 translate and maketrans

- **Q1** `zbc`
- **Q2** `heo`
- **Q3** `a b`
- **Q4** `xyz`
- **Q5** `ValueError: the first two maketrans arguments must have equal length`

### Answers: 3.7.19 Alignment and padding: center, ljust, rjust, zfill, expandtabs

- **Q1** `007 --hi-- hi..`
- **Q2** `'abc ' ' abc ' ' ab '`
- **Q3** `-005 +005 5`
- **Q4** `'a b' 9 3`
- **Q5** `SyntaxError: invalid decimal literal`

### Answers: 3.7.20 Testing methods: isalpha, isdigit, isdecimal, isnumeric, isalnum, isspace and more

- **Q1** `True False True False`
- **Q2** `False True True False`
- **Q3** `True False False True`
- **Q4** `True False False False`
- **Q5** `False False True 3`

### Answers: 3.7.21 Old-style % formatting

- **Q1** `2 + 3 = 5`
- **Q2** `3.14|ab |0002.5`
- **Q3** `100%% sure 5 'a'`
- **Q4** `TypeError: not all arguments converted during string formatting`
- **Q5** `TypeError: %d format: a real number is required, not str`

### Answers: 3.7.22 str.format()

- **Q1** `x and y ba`
- **Q2** `00042 2.000 a`
- **Q3** `a a b 12`
- **Q4** `{} {5} a |`
- **Q5** `IndexError: Replacement index 1 out of range for positional args tuple`

### Answers: 3.7.23 f-strings and the format-spec mini-language

- **Q1** `5 10 005`
- **Q2** `[ ab] [ab ] [ ab ] [--ab--]`
- **Q3** `1,234,567.9 1.23e+06 1_234_568`
- **Q4** `a=7 a= 7 7 a + 1 = 8`
- **Q5** `3.14|x |{w}`

### Answers: 3.7.24 format_map, the string module and Template

- **Q1** `0123456789 52`
- **Q2** `abc False`
- **Q3** `1-2`
- **Q4** `x $b`
- **Q5** `KeyError: 'a'`

### Answers: 3.7.25 Unicode, encode, decode, ord and chr

- **Q1** `97 A 48`
- **Q2** `1 2 3`
- **Q3** `b'hi' hi <class 'bytes'>`
- **Q4** `b'\xe9' b'\xc3\xa9' �`
- **Q5**
  ```text
  UnicodeEncodeError: 'ascii' codec can't encode character '\xe9' in position 0: ordinal not in
  range(128)
  ```

### Answers: 3.7.26 Unicode normalisation, grapheme caveats and unicodedata

- **Q1** `1 2`
- **Q2** `True`
- **Q3** `LATIN SMALL LETTER A Nd`
- **Q4** `5 2`
- **Q5** `False False`

### Answers: 3.7.27 Complete reference: all 47 str methods

- **Q1** `True False`
- **Q2** `True True`
- **Q3** `ABC ABC a-b`
- **Q4** `12`
- **Q5** `AttributeError: 'str' object has no attribute 'reverse'`

### Answers: 3.7.28 Classic string tasks and idioms

- **Q1** `True`
- **Q2** `ehllo helo`
- **Q3** `2 hELLO wORLD`
- **Q4** `spain eht niar ni niaps`
- **Q5** `True True`

### Answers: 3.7.29 Performance and memory of strings

- **Q1** `6 True`
- **Q2** `1`
- **Q3** `012 <class 'str'>`
- **Q4** `True True`

### Answers: 3.7.30 Common string pitfalls

- **Q1** `abc`
- **Q2** `11 2 111`
- **Q3** `['a', ' b'] ['a', 'b'] ['a', 'b']`
- **Q4** `True False True 5 10`
- **Q5**
  ```text
  not found
  found c
  ```

### Answers: 3.8.1 bytes: immutable sequences of integers 0-255

- **Q1** `97 b'bc' 3`
- **Q2** `b'AB' b'\x00\x00' [65, 66]`
- **Q3** `b'ab' 6162 b'ab'`
- **Q4** `b'hi' hi False`
- **Q5** `ValueError: bytes must be in range(0, 256)`

### Answers: 3.8.2 bytes methods and bytearray

- **Q1** `bytearray(b'abc')`
- **Q2** `[0, 7, 0]`
- **Q3** `[b'a', b'b'] b'AB' b'x'`
- **Q4** `Jello True`
- **Q5** `TypeError: 'bytes' object does not support item assignment`

### Answers: 3.8.3 memoryview and the buffer protocol

- **Q1** `97 True`
- **Q2** `bytearray(b'aBc')`
- **Q3** `bytearray(b'ab') b'Zb'`
- **Q4** `BufferError: Existing exports of data: object cannot be re-sized`

### Answers: 3.9.1 Creating lists

- **Q1** `2 False`
- **Q2** `['h', 'i'] [1, 2, 3] [0, 0]`
- **Q3** `[3] [[]] 1 False`
- **Q4** `['b', 'a'] [1, 2, 3] ['1', '2']`
- **Q5** `TypeError: 'int' object is not iterable`

### Answers: 3.9.2 Indexing and slicing lists

- **Q1** `2 4 [2, 3]`
- **Q2** `[1, 3, 5] [5, 4, 3, 2, 1] [2, 4] [3, 4]`
- **Q3** `[1, 7, 8, 9, 3]`
- **Q4**
  ```text
  [1, 4]
  [1, 5, 6, 4]
  ```
- **Q5** `IndexError: list index out of range`

### Answers: 3.9.3 append, extend, insert and the + / += operators

- **Q1** `[1, 2, 3, 4]`
- **Q2** `[1, [2, 3]] 2`
- **Q3** `[1, 'x', 2, 'y', 3]`
- **Q4** `[1, 2, 3] [1, 2]`
- **Q5** `None`

### Answers: 3.9.4 remove, pop, del and clear

- **Q1** `[1, 3]`
- **Q2** `4 1 [2, 3]`
- **Q3** `[1, 1, 2]`
- **Q4** `[2, 4, 6]`
- **Q5** `[1, 2, 2]`

### Answers: 3.9.5 index, count and membership

- **Q1** `1 2 False`
- **Q2** `4 2`
- **Q3** `True False True`
- **Q4** `1 1 False`
- **Q5** `ValueError: 3 is not in list`

### Answers: 3.9.6 sort, sorted, reverse, reversed

- **Q1** `[1, 2, 3]`
- **Q2** `[3, 2, 1] [3, 1, 2]`
- **Q3** `['A', 'B', 'a', 'b'] ['A', 'a', 'b', 'B']`
- **Q4** `[-1, 2, 3, -5] [3, 2, -1, -5]`
- **Q5**
  ```text
  True [1, 2]
  TypeError: '<' not supported between instances of 'str' and 'int'
  ```

### Answers: 3.9.7 copy: alias, shallow copy and deep copy

- **Q1** `[1, 2]`
- **Q2** `[1] [1, 2]`
- **Q3** `[[1, 9], [2]]`
- **Q4** `[[1], [2]] [[1, 9], [2]]`
- **Q5** `[[0, 5], [0, 5]]`

### Answers: 3.9.8 Operators: +, \*, in, comparison and unpacking

- **Q1** `[1, 2, 3] [0, 0, 0] True`
- **Q2** `True True True`
- **Q3** `1 [2, 3]`
- **Q4** `1 [] 2`
- **Q5** `TypeError: can only concatenate list (not "tuple") to list`

### Answers: 3.9.9 List comprehensions

- **Q1** `[0, 2, 4, 6]`
- **Q2** `['1', '2'] [1, 2, 3]`
- **Q3** `[0, 2, 0]`
- **Q4** `[(1, 0), (2, 0), (2, 1)]`
- **Q5** `SyntaxError: invalid syntax`

### Answers: 3.9.10 Nested lists and matrices

- **Q1** `2 3 2`
- **Q2** `[(1, 3), (2, 4)] [[2, 1], [4, 3]]`
- **Q3** `[[1, 4], [2, 5], [3, 6]]`
- **Q4** `[[1, 0], [1, 0]]`

### Answers: 3.9.11 Lists as stacks and queues; deque

- **Q1** `3 [1, 2]`
- **Q2** `1 [2, 3, 4]`
- **Q3** `[3, 4]`
- **Q4**
  ```text
  [4, 1, 2, 3]
  [2, 3, 4, 1]
  ```
- **Q5** `IndexError: pop from empty list`

### Answers: 3.9.12 enumerate, zip, map, filter and unpacking with lists

- **Q1** `[(0, 'a'), (1, 'b')] [(1, 'a'), (2, 'b')]`
- **Q2** `[(1, 'a'), (2, 'b')] [1, 2]`
- **Q3** `[1, 'a']`
- **Q4** `[1, 2] []`
- **Q5** `ValueError: zip() argument 2 is longer than argument 1`

### Answers: 3.9.13 min, max, sum, len, any, all and statistics on lists

- **Q1** `18 3 9 3`
- **Q2** `2.5 3`
- **Q3** `2.5 a`
- **Q4** `statistics.StatisticsError: mean requires at least one data point`

### Answers: 3.9.14 Mutation during iteration and other aliasing traps

- **Q1** `[1, 2, 3]`
- **Q2** `[1, 2]`
- **Q3** `[0, 2, 3]`
- **Q4** `[2]`

### Answers: 3.9.15 Performance of list operations

- **Q1** `2`
- **Q2** `[1, 3, 4, 5]`
- **Q3** `1 3`

### Answers: 3.9.16 Complete reference: all 11 list methods

- **Q1** `11`
- **Q2** `True False None [1, 2, 3]`
- **Q3** `None None None 4 [0, 1, 2, 3]`
- **Q4** `[1, 3]`

### Answers: 3.9.17 Common list pitfalls

- **Q1** `3`
- **Q2** `[1, 2, '3', '4']`
- **Q3** `[1, 2, 3, 4] [1, 2, 3, 5]`
- **Q4** `TypeError: list.append() takes exactly one argument (2 given)`

### Answers: 3.10.1 Creating tuples

- **Q1** `<class 'tuple'> <class 'tuple'> <class 'int'>`
- **Q2** `(5, 6, 7) 3 5`
- **Q3** `('a', 'b', 'c') (1, [2]) ('a',)`
- **Q4** `1 [2, 3] <class 'list'>`
- **Q5** `True False <class 'int'>`

### Answers: 3.10.2 Indexing, slicing, operators and methods

- **Q1** `2 4 (2, 3) 1`
- **Q2** `(1, 2, 3) (1, 2, 1, 2) True`
- **Q3** `[1, 2, 3] <class 'list'> 5`
- **Q4** `True True True`
- **Q5** `TypeError: can only concatenate tuple (not "list") to tuple`

### Answers: 3.10.3 Immutability: what is and is not frozen

- **Q1** `TypeError: 'tuple' object does not support item assignment`
- **Q2** `([1, 9], 2)`
- **Q3** `([1, 2], 2)`
- **Q4** `TypeError: unhashable type: 'list'`

### Answers: 3.10.4 Tuple versus list: when to use which

- **Q1** `(1, 2) <class 'tuple'>`
- **Q2** `a True False`
- **Q3** `True`
- **Q4** `TypeError: unhashable type: 'list'`

### Answers: 3.10.5 Unpacking, swapping and star expressions

- **Q1** `7`
- **Q2** `2 3`
- **Q3** `x ['y', 'z']`
- **Q4** `1 2 [3, 4] 5`
- **Q5** `ValueError: too many values to unpack (expected 2)`

### Answers: 3.10.6 namedtuple and typing.NamedTuple

- **Q1** `P(a=1, b=2) 1`
- **Q2** `P(a=9, b=2) P(a=1, b=2)`
- **Q3** `True True`
- **Q4** `AttributeError: can't set attribute`

### Answers: 3.10.7 Common tuple pitfalls

- **Q1** `(4,) <class 'tuple'>`
- **Q2** `(1, 2, 3)`
- **Q3** `(1, 2, 3) (1, 2) False`
- **Q4** `AttributeError: 'tuple' object has no attribute 'append'`

### Answers: 3.11.1 Creating sets

- **Q1** `3 <class 'dict'> <class 'set'>`
- **Q2** `['a', 'b', 'n'] 3`
- **Q3** `True 1`
- **Q4** `2 {0, 1, 2}`
- **Q5** `TypeError: unhashable type: 'list'`

### Answers: 3.11.2 Adding and removing: add, update, remove, discard, pop, clear

- **Q1** `[1, 2]`
- **Q2** `{2, 3}`
- **Q3** `[1, 2, 3, 4]`
- **Q4** `None None None [2, 3, 9]`
- **Q5** `KeyError: 3`

### Answers: 3.11.3 Set algebra: union, intersection, difference, symmetric difference

- **Q1** `{1, 2, 3} {2}`
- **Q2** `{1, 3} {1, 3}`
- **Q3** `{1, 2, 3, 5} {1} {1, 2, 3}`
- **Q4** `{1, 4}`
- **Q5** `TypeError: unsupported operand type(s) for |: 'set' and 'list'`

### Answers: 3.11.4 Subsets, supersets and isdisjoint

- **Q1** `True False False`
- **Q2** `True False True`
- **Q3** `False False False`
- **Q4** `True False True True`

### Answers: 3.11.5 Set comprehensions, deduplication and fast membership

- **Q1** `[0, 1, 2]`
- **Q2** `[3, 1, 2] [1, 2, 3]`
- **Q3** `1 True`
- **Q4** `TypeError: unhashable type: 'list'`

### Answers: 3.11.6 frozenset: the immutable set

- **Q1** `2 True`
- **Q2** `frozenset({1, 2}) set`
- **Q3** `True True`
- **Q4** `AttributeError: 'frozenset' object has no attribute 'add'`

### Answers: 3.11.7 Hashing, ordering and equality of sets

- **Q1** `True False`
- **Q2** `2`
- **Q3** `[1, 2, 3] [5] True`
- **Q4** `False False False True`

### Answers: 3.11.8 Complete reference: all 17 set methods

- **Q1** `17`
- **Q2** `8`
- **Q3** `{1, 2, 3} {1, 2, 3} None {1, 2, 3}`
- **Q4** `{1, 2} {1, 2, 3} False`

### Answers: 3.11.9 Common set pitfalls

- **Q1** `<class 'dict'> <class 'set'> <class 'set'>`
- **Q2** `[1, 3, 5] {1}`
- **Q3** `TypeError: unsupported operand type(s) for +: 'set' and 'set'`

### Answers: 3.12.1 Creating dictionaries

- **Q1** `2 1 ['a', 'b']`
- **Q2** `{'a': 1} {1: 2} {'x': 1, 'y': 2}`
- **Q3** `{1: 'c'}`
- **Q4** `{'a': [], 'b': []} 2`
- **Q5** `TypeError: unhashable type: 'list'`

### Answers: 3.12.2 Reading values: [], get, in and KeyError

- **Q1** `1 None 9 True`
- **Q2** `False True 1`
- **Q3** `None x x`
- **Q4** `KeyError: 'b'`

### Answers: 3.12.3 Adding and updating: [], update, setdefault, | and |=

- **Q1** `{'a': 5, 'b': 2}`
- **Q2** `{'a': 2, 'b': 3}`
- **Q3** `5 5 {'k': 5}`
- **Q4** `{'x': 2, 'y': 3} {'x': 1, 'y': 3} {'x': 1}`
- **Q5** `{'list': [1, 2]}`

### Answers: 3.12.4 Removing: pop, popitem, del and clear

- **Q1** `1 {'b': 2}`
- **Q2** `('c', 3) {'a': 1, 'b': 2}`
- **Q3** `None 1 {}`
- **Q4** `('b', 2)`
- **Q5** `KeyError: 'b'`

### Answers: 3.12.5 Views: keys(), values(), items()

- **Q1** `['a', 'b'] [1, 2] [('a', 1), ('b', 2)]`
- **Q2** `['a', 'b']`
- **Q3** `['y'] True`
- **Q4** `b ['b', 'a']`
- **Q5** `TypeError: 'dict_keys' object is not subscriptable`

### Answers: 3.12.6 Changing a dict while iterating

- **Q1** `{'a': 5}`
- **Q2** `['a', 'aa', 'b', 'bb']`
- **Q3** `RuntimeError: dictionary changed size during iteration`

### Answers: 3.12.7 Dict comprehensions, fromkeys, zip and inversion

- **Q1** `{0: 0, 1: 2, 2: 4}`
- **Q2** `{1: 'a', 2: 'b'}`
- **Q3** `{1: 'b'}`
- **Q4** `{'a': [1], 'b': [1]}`

### Answers: 3.12.8 Nested dictionaries, copy and deepcopy

- **Q1** `1 None`
- **Q2** `{'a': [1, 2]}`
- **Q3** `{'a': [1]} {'a': [1, 2]}`
- **Q4** `KeyError: 'b'`

### Answers: 3.12.9 Ordering: insertion order, sorting and reversing

- **Q1** `['b', 'a'] ['a', 'b']`
- **Q2** `[('a', 9), ('b', 2)]`
- **Q3** `['b', 'a']`
- **Q4** `True False`

### Answers: 3.12.10 Key rules: hashability, equal keys and tuple keys

- **Q1** `{1: 'b'}`
- **Q2** `2 2`
- **Q3** `2 a`
- **Q4** `TypeError: unhashable type: 'list'`

### Answers: 3.12.11 collections: defaultdict, Counter, OrderedDict, ChainMap

- **Q1** `Counter({'a': 2, 'b': 1}) [('a', 2)]`
- **Q2** `2 0 {'x': 2, 'y': 0}`
- **Q3** `Counter({'a': 2, 'b': 2}) Counter({'b': 1})`
- **Q4** `1 3 ['a', 'c']`
- **Q5** `None False [] True`

### Answers: 3.12.12 Complete reference: all 11 dict methods

- **Q1** `11`
- **Q2** `None None {}`
- **Q3** `1 3 1 {'b': 3}`
- **Q4** `2 1`

### Answers: 3.12.13 Common dict pitfalls

- **Q1** `1`
- **Q2** `{'x': 1, 'y': 2}`
- **Q3** `5 0 5`
- **Q4** `ValueError: not enough values to unpack (expected 2, got 1)`

### Answers: 3.13.1 range(start, stop, step)

- **Q1** `[0, 1, 2, 3] [1, 2, 3] [0, 4, 8]`
- **Q2** `[10, 7, 4, 1] 0 4`
- **Q3** `2 4 range(1, 4) True False`
- **Q4** `[] [] [-3, -1, 1]`
- **Q5** `TypeError: 'float' object cannot be interpreted as an integer`

### Answers: 3.13.2 Using range correctly: loops, indexes and off-by-one

- **Q1** `10 [2, 3, 4]`
- **Q2** `[1, 2, 3, 4] [0, 4, 8]`
- **Q3** `True True False`
- **Q4**
  ```text
  range(0, 3)
  [0, 1, 2]
  AttributeError: 'range' object has no attribute 'append'
  ```

### Answers: 3.14.1 Implicit and explicit conversion

- **Q1** `<class 'float'> <class 'int'> <class 'float'>`
- **Q2** `8 71 77`
- **Q3** `3.0 3 1.0 1000`
- **Q4** `3.0 <class 'float'> True`
- **Q5** `TypeError: can only concatenate str (not "int") to str`

### Answers: 3.14.2 The conversion matrix

- **Q1** `3 3.0 3.7 True`
- **Q2** `['1', '2'] [1, 2] ['a'] [0, 1]`
- **Q3** `1 0.0 None False True`
- **Q4** `ValueError: could not convert string to float: ''`

### Answers: 3.14.3 Text to values and back: literal_eval, json, eval

- **Q1** `[1, 2] <class 'tuple'>`
- **Q2** `[1, "a", null, true] [1, None, False]`
- **Q3** `{'1': 'a'}`
- **Q4**
  ```text
  json.decoder.JSONDecodeError: Expecting property name enclosed in double quotes: line 1 column 2
  (char 1)
  ```

### Answers: 3.14.4 Converting between containers

- **Q1** `['a', 'b'] (1, 2) True`
- **Q2** `{'a': 2} ['x', 'y']`
- **Q3** `{1: 'a', 2: 'b'}`
- **Q4** `{'a': 'b', 'c': 'd'} [('a', 'b')]`
- **Q5** `TypeError: cannot convert dictionary update sequence element #0 to a sequence`

### Answers: 3.14.5 Safe conversion helpers

- **Q1** `5 2.5 100.0`
- **Q2** `True True False`
- **Q3** `3 -1 -1 3 -1`
- **Q4** `ValueError: invalid literal for int() with base 10: '1,000'`

### Answers: 3.14.6 Type checking: isinstance, duck typing and annotations

- **Q1** `True False`
- **Q2** `hi {'x': <class 'int'>}`
- **Q3** `True True False`
- **Q4** `True True False True`

### Answers: 3.14.7 Choosing the right data type

- **Q1** `3 4`
- **Q2** `(3, 3)`
- **Q3** `{'a': [0, 3], 'b': [1], 'c': [2]}`
- **Q4** `TypeError: unhashable type: 'list'`

---

## Final exam answers

- **E1** `<class 'float'> <class 'int'> <class 'str'>`
- **E2** `3`
- **E3** `default 0`
- **E4** `0 1 1`
- **E5** `True`
- **E6** `-3 -4 -4 1`
- **E7** `1000 1000 2`
- **E8** `65535 -1`
- **E9** `0 1 0`
- **E10** `1205`
- **E11** `<class 'float'> <class 'int'> <class 'float'> <class 'float'>`
- **E12** `1 nan`
- **E13** `6 6 8 8`
- **E14** `False True`
- **E15** `True True`
- **E16** `True`
- **E17** `(5+5j) (-0.5+1.5j)`
- **E18** `[] empty False`
- **E19** `True True False`
- **E20** `2 5`
- **E21** `abcdabcd abcdabcd abcdcd`
- **E22** `[1, 'a'] [1, 'a'] True`
- **E23** `True True True`
- **E24** `True False True ['10', '2', '9']`
- **E25** `3Rd Place O'Neil Ab-Cd`
- **E26** `bana b`
- **E27** `False 6`
- **E28** `1ab2ab3 abab`
- **E29** `'a b' 9 3`
- **E30** `100%% sure 5 'a'`
- **E31** `3.14|x |{w}`
- **E32** `b'\xe9' b'\xc3\xa9' �`
- **E33** `12`
- **E34**
  ```text
  not found
  found c
  ```
- **E35** `Jello True`
- **E36** `['b', 'a'] [1, 2, 3] ['1', '2']`
- **E37** `None`
- **E38** `1 1 False`
- **E39** `[[0, 5], [0, 5]]`
- **E40** `[[1, 0], [1, 0]]`
- **E41** `[1, 2] []`
- **E42** `[2]`
- **E43** `[1, 3]`
- **E44** `True False <class 'int'>`
- **E45** `True`
- **E46** `True True`
- **E47** `2 {0, 1, 2}`
- **E48** `{1, 4}`
- **E49** `1 True`
- **E50** `False False False True`
- **E51** `{'a': [], 'b': []} 2`
- **E52** `{'list': [1, 2]}`
- **E53** `b ['b', 'a']`
- **E54** `{'a': [1], 'b': [1]}`
- **E55** `True False`
- **E56** `2 1`
- **E57** `[] [] [-3, -1, 1]`
- **E58** `3.0 <class 'float'> True`
- **E59** `{'1': 'a'}`
- **E60** `3 -1 -1 3 -1`