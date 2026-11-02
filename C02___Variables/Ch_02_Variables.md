
# Python Chapter 2: Variables

**PYTHON | CHAPTER 02**

## Variables — The Complete Deep Dive

Every topic of Chapter 2, taught step by step: what it is, a runnable example, the real output, then every variation and consequence, followed by graded questions with a verified answer key.

| Topics | Sections | Verified demos | Graded questions |
|:---:|:---:|:---:|:---:|
| 92 | 8 | 153 | 325 |

*Edition of 31 October 2026. Every output shown in this book was produced by running the code on Python 3.12.3. Sizes and timings can differ on other versions; the concepts do not.*

---

## Contents

- **[How to Use This Book](#how-to-use-this-book)**
  - [Core idea of the whole chapter](#core-idea-of-the-whole-chapter)
- **[Section 2.1 Concept of Variables](#section-21-concept-of-variables)**
  - [2.1.1 What is a variable (name binding, not a box)](#211-what-is-a-variable-name-binding-not-a-box)
  - [2.1.2 Variable as reference to an object](#212-variable-as-reference-to-an-object)
  - [2.1.3 id() and type(): first tools](#213-id-and-type-first-tools)
  - [2.1.4 Names vs values](#214-names-vs-values)
  - [2.1.5 Dynamic typing (contrast with static typing)](#215-dynamic-typing-contrast-with-static-typing)
  - [2.1.6 Strong typing (Python is strongly + dynamically typed)](#216-strong-typing-python-is-strongly--dynamically-typed)
  - [2.1.7 Objects: identity, type, value](#217-objects-identity-type-value)
  - [2.1.8 Everything is an object: first proof](#218-everything-is-an-object-first-proof)
  - [2.1.9 Variables are not declared](#219-variables-are-not-declared)
  - [2.1.10 Multiple names for the same object](#2110-multiple-names-for-the-same-object)
  - [2.1.11 Rebinding does not affect other names](#2111-rebinding-does-not-affect-other-names)
  - [2.1.12 Variable lifetime and reference counting intro](#2112-variable-lifetime-and-reference-counting-intro)
  - [2.1.13 Mental-model exercises (mini-lab)](#2113-mental-model-exercises-mini-lab)
- **[Section 2.2 Naming](#section-22-naming)**
  - [2.2.1 Valid identifier rules](#221-valid-identifier-rules)
  - [2.2.2 Case sensitivity](#222-case-sensitivity)
  - [2.2.3 snake_case convention (PEP 8)](#223-snake_case-convention-pep-8)
  - [2.2.4 Constant naming (UPPER_CASE, Final)](#224-constant-naming-upper_case-final)
  - [2.2.5 Reserved keywords as names (error)](#225-reserved-keywords-as-names-error)
  - [2.2.6 Dunder names (__x__): intro](#226-dunder-names-__x__-intro)
  - [2.2.7 Private-ish naming (_x, __x, __x__)](#227-private-ish-naming-_x-__x-__x__)
  - [2.2.8 Beginner pitfalls: shadowing built-ins (list, id, input)](#228-beginner-pitfalls-shadowing-built-ins-list-id-input)
  - [2.2.9 Naming for readability](#229-naming-for-readability)
  - [2.2.10 Throwaway name _](#2210-throwaway-name-_)
  - [2.2.11 Unicode names and normalisation](#2211-unicode-names-and-normalisation)
  - [2.2.12 Naming in competitive programming](#2212-naming-in-competitive-programming)
- **[Section 2.3 Assignment](#section-23-assignment)**
  - [2.3.1 Simple assignment](#231-simple-assignment)
  - [2.3.2 Multiple assignment: a = b = c = 0](#232-multiple-assignment-a--b--c--0)
  - [2.3.3 Tuple unpacking: a, b = 1, 2](#233-tuple-unpacking-a-b--1-2)
  - [2.3.4 Swap idiom: a, b = b, a](#234-swap-idiom-a-b--b-a)
  - [2.3.5 Starred unpacking: a, *b = [1,2,3]](#235-starred-unpacking-a-b--123)
  - [2.3.6 Augmented assignment (+=, -=, *=, //=, **=, &=, |=, ^=, >>=,](#236-augmented-assignment----------)
  - [<<=, @=)](#-)
  - [2.3.7 Chained comparison: 1 < x < 10](#237-chained-comparison-1--x--10)
  - [2.3.8 Reassignment vs mutation](#238-reassignment-vs-mutation)
  - [2.3.9 del keyword](#239-del-keyword)
  - [2.3.10 None as default](#2310-none-as-default)
  - [2.3.11 Nested unpacking](#2311-nested-unpacking)
  - [2.3.12 Unpacking in function calls and literals](#2312-unpacking-in-function-calls-and-literals)
  - [2.3.13 Assignment targets that are not names](#2313-assignment-targets-that-are-not-names)
  - [2.3.14 Walrus operator := first look](#2314-walrus-operator--first-look)
  - [2.3.15 Annotated assignment x: int = 5](#2315-annotated-assignment-x-int--5)
  - [2.3.16 Evaluation order puzzles](#2316-evaluation-order-puzzles)
  - [2.3.17 Assignment inside loops and conditionals](#2317-assignment-inside-loops-and-conditionals)
  - [2.3.18 Assignment mini-lab](#2318-assignment-mini-lab)
- **[Section 2.4 Scope (Variables Lifespan)](#section-24-scope-variables-lifespan)**
  - [2.4.1 Local / Enclosing / Global / Built-in (LEGB)](#241-local--enclosing--global--built-in-legb)
  - [2.4.2 global keyword](#242-global-keyword)
  - [2.4.3 nonlocal keyword](#243-nonlocal-keyword)
  - [2.4.4 Shadowing](#244-shadowing)
  - [2.4.5 UnboundLocalError pitfall](#245-unboundlocalerror-pitfall)
  - [2.4.6 Module-level variables](#246-module-level-variables)
  - [2.4.7 __main__ scope (intro)](#247-__main__-scope-intro)
  - [2.4.8 Block scope does not exist](#248-block-scope-does-not-exist)
  - [2.4.9 Comprehension scope and the loop variable leak](#249-comprehension-scope-and-the-loop-variable-leak)
  - [2.4.10 Closures: first look](#2410-closures-first-look)
  - [2.4.11 Class scope](#2411-class-scope)
  - [2.4.12 Exception variable scope](#2412-exception-variable-scope)
  - [2.4.13 Namespaces and dir()/vars()/globals()/locals()](#2413-namespaces-and-dirvarsglobalslocals)
  - [2.4.14 Global state in competitive programming](#2414-global-state-in-competitive-programming)
  - [2.4.15 Scope mini-lab](#2415-scope-mini-lab)
- **[Section 2.5 Mutability and Identity](#section-25-mutability-and-identity)**
  - [2.5.1 Mutable vs immutable (contrast table)](#251-mutable-vs-immutable-contrast-table)
  - [2.5.2 id() behaviour](#252-id-behaviour)
  - [2.5.3 is vs == (contrast, big pitfall)](#253-is-vs--contrast-big-pitfall)
  - [2.5.4 Small integer interning (-5..256)](#254-small-integer-interning--5256)
  - [2.5.5 String interning](#255-string-interning)
  - [2.5.6 Copy pitfalls (a = b for lists)](#256-copy-pitfalls-a--b-for-lists)
  - [2.5.7 Shallow vs deep copy (preview)](#257-shallow-vs-deep-copy-preview)
  - [2.5.8 Hashability](#258-hashability)
  - [2.5.9 Immutability is shallow](#259-immutability-is-shallow)
  - [2.5.10 Mutation through function parameters](#2510-mutation-through-function-parameters)
  - [2.5.11 Defensive copying](#2511-defensive-copying)
  - [2.5.12 Immutable tricks and performance](#2512-immutable-tricks-and-performance)
  - [2.5.13 Object identity in containers](#2513-object-identity-in-containers)
  - [2.5.14 Mutability mini-lab](#2514-mutability-mini-lab)
- **[Section 2.6 Memory Model Internals](#section-26-memory-model-internals)**
  - [2.6.1 Objects on the heap, names in namespaces](#261-objects-on-the-heap-names-in-namespaces)
  - [2.6.2 Reference counting](#262-reference-counting)
  - [2.6.3 Cyclic garbage collector](#263-cyclic-garbage-collector)
  - [2.6.4 Object header and size of basic objects](#264-object-header-and-size-of-basic-objects)
  - [2.6.5 Integer storage in CPython](#265-integer-storage-in-cpython)
  - [2.6.6 id reuse after deletion](#266-id-reuse-after-deletion)
  - [2.6.7 Weak references and del](#267-weak-references-and-del)
  - [2.6.8 Memory profiling tools](#268-memory-profiling-tools)
- **[Section 2.7 Annotations, Constants and Typing for Variables](#section-27-annotations-constants-and-typing-for-variables)**
  - [2.7.1 Variable annotations](#271-variable-annotations)
  - [2.7.2 typing.Final and constants](#272-typingfinal-and-constants)
  - [2.7.3 Type aliases](#273-type-aliases)
  - [2.7.4 Optional, Union and the | syntax](#274-optional-union-and-the--syntax)
  - [2.7.5 Runtime vs static typing](#275-runtime-vs-static-typing)
  - [2.7.6 Mini-lab: annotate a script](#276-mini-lab-annotate-a-script)
- **[Section 2.8 Inspecting Variables](#section-28-inspecting-variables)**
  - [2.8.1 type, isinstance, id, dir, vars, repr](#281-type-isinstance-id-dir-vars-repr)
  - [2.8.2 globals() and locals() as dicts](#282-globals-and-locals-as-dicts)
  - [2.8.3 inspect module first look](#283-inspect-module-first-look)
  - [2.8.4 f"{x=}" debugging](#284-fx-debugging)
  - [2.8.5 Trace tools: pdb, sys.settrace, tracemalloc](#285-trace-tools-pdb-syssettrace-tracemalloc)
  - [2.8.6 Chapter 2 mini-lab: Variable Playground](#286-chapter-2-mini-lab-variable-playground)
- **[Chapter 2 Summary: The 30 Rules](#chapter-2-summary-the-30-rules)**
  - [Error Message Decoder](#error-message-decoder)
- **[Final Exam (45 mixed HARD and TRAP questions)](#final-exam-45-mixed-hard-and-trap-questions)**
- **[Answer Key (outputs from running the code)](#answer-key-outputs-from-running-the-code)**
  - [Final exam answers](#final-exam-answers)

---

## How to Use This Book

Each topic follows the same teaching order, matching your index: **what it is**, then **a runnable example**, then **the verified output**, then **every variation and consequence**, then **graded practice**. Green-edged boxes are code, blue-edged boxes are the exact output the code printed.

- Read the explanation, then try each example yourself before looking at the printed output.
- In the Practice list, cover the answer key at the end of the book, write your prediction, and only then run the question.
- Levels: BASIC (direct), MID (needs the model), HARD (combines ideas), TRAP (looks easy, hides a pitfall).
- Addresses and ids vary between runs, so examples compare ids instead of printing them.
- If an output surprises you, that is the point: stop and redraw the name-to-object arrows.

### Core idea of the whole chapter
<img width="1536" height="1024" alt="memory_variables" src="https://github.com/user-attachments/assets/6a7d9197-7cd1-4e4e-8831-002652c44468" />



## Section 2.1 Concept of Variables

### 2.1.1 What is a variable (name binding, not a box)

A variable in Python is a NAME that is bound to an object. The object lives somewhere in memory; the name is just a label that points to it. This is different from the "box" picture used in C, where a variable is a fixed memory slot holding a value.

Step 1: Python evaluates the right-hand side and produces (or finds) an object. Step 2: it binds the name on the left to that object in the current namespace. Assignment never copies the object.

> **Key rule:** Rule: "x = expr" means "make the name x refer to the object that expr produced".

**Example 2.1.1.1: Binding a name, then rebinding it to an object of another type**
<!-- <img width="1536" height="1024" alt="dynamic_typing_in_python" src="https://github.com/user-attachments/assets/d1df406c-27d3-453e-903c-ea9bc99641ee" /> -->

```python
x = 10
print(x, type(x))
x = "ten"
print(x, type(x))
```

**Output:**

```text
10 <class 'int'>
ten <class 'str'>
```

**Example 2.1.1.2: Two names, one object: the box model cannot explain this**
<img width="241" height="320" alt="file_0000000051a88210994c2e3074c95f41" src="https://github.com/user-attachments/assets/85d9b285-1a30-4a3c-be97-d5f71fe75dfe" />


```python
a = [1, 2]
b = a
b.append(3)
print(a, b, a is b)
```

**Output:**

```text
[1, 2, 3] [1, 2, 3] True
```

**Example 2.1.1.3: Rebinding one name leaves the other untouched for immutable objects and it changes for mutable objects**
<img width="1980" height="1155" alt="rebinding_vs_mutation" src="https://github.com/user-attachments/assets/8c21656c-1106-4476-9e4a-bc984e0d6f10" />


```python
x = 5
y = x
x = 7
print(x, y)
```

**Output:**

```text
7 5
```

> **Watch out:** The "box" model predicts that b = a copies the list into a second box. It does not; both names point at the same list.

#### Practice 2.1.1

**2.1.1-Q1 BASIC**

```python
x = 5; y = x; x = 7; print(y)
```

**2.1.1-Q2 BASIC**

```python
a = [1]; b = a; b.append(2); print(a)
```

**2.1.1-Q3 MID**

```python
a = [1]; b = a; b = b + [2]; print(a, b)
```

**2.1.1-Q4 HARD**

```python
a = [1]; b = a; b += [2]; print(a, b)
```

**2.1.1-Q5 TRAP**

```python
a = "hi"; b = a; b += "!"; print(a, b)
```
<!-- <img width="1280" height="784" alt="exercise 2 1 1" src="https://github.com/user-attachments/assets/bf12134d-69f4-4e4e-b2e0-36acba49215f" /> -->



### 2.1.2 Variable as reference to an object

Think of every name as an arrow from the name to an object. Assignment moves or creates an arrow. Objects do not know which names point at them (they only keep a count). Containers also hold arrows: a list slot is an arrow to an object.

Draw it: after a = [1, 2]; b = a there is ONE list object and TWO arrows into it. After b = [1, 2] there are TWO list objects, each with one arrow.
<img width="1600" height="2000" alt="unnested_lists_whiteboard" src="https://github.com/user-attachments/assets/c79bd308-81dd-4caf-9bb5-9f7721fa7ca2" />

<img width="1600" height="2000" alt="nested_lists_level1_whiteboard" src="https://github.com/user-attachments/assets/4d2ded70-d545-4635-9fc8-5d3ba8250c08" />
<img width="1600" height="2000" alt="nested_lists_level2_whiteboard" src="https://github.com/user-attachments/assets/c292ccbd-929c-43b5-8f3f-58ee4d679b24" />















**Example 2.1.2.1: Same object versus equal objects**

```python
a = [1, 2]
b = a
c = [1, 2]
print(a == b, a is b)
print(a == c, a is c)
```

**Output:**

```text
True True
True False
```

**Example 2.1.2.2: A list holds references, not copies**
<img width="1600" height="1080" alt="example_2_1_2_2_whiteboard" src="https://github.com/user-attachments/assets/e49114b7-8d40-4fb0-a814-d376ff1cc59f" />


```python
x = [0]
row = [x, x]
x.append(1)
print(row)
```

**Output:**

```text
[[0, 1], [0, 1]]
```

**Example 2.1.2.3: The same arrow idea for strings and ints (immutable, but still references)**
<img width="1600" height="2260" alt="immutable_string_integers_whiteboard" src="https://github.com/user-attachments/assets/a8e94e3d-9e07-4f25-8eff-47315bbbad90" />




```python
s = "python"
t = s
print(s is t)
t = t.upper()
print(s, t, s is t)
```

**Output:**

```text
True
python PYTHON False
```

#### Practice 2.1.2

**2.1.2-Q1 BASIC**

```python
a = [1]; c = [1]; print(a == c, a is c)
```

**2.1.2-Q2 MID**

```python
x = [0]; row = [x, x]; row[0].append(9); print(row)
```

**2.1.2-Q3 MID**

```python
x = [0]; row = [x[:], x[:]]; row[0].append(9); print(row)
```

**2.1.2-Q4 HARD**

```python
a = [1]; b = [a, a]; a = [2]; print(b)
```
<img width="966" height="1280" alt="6284835231063807639" src="https://github.com/user-attachments/assets/ca451447-5863-4bdf-9a3a-6365f6deff7c" />



### 2.1.3 id() and type(): first tools

type(obj) tells you which class the object belongs to. id(obj) returns an integer that identifies the object during its lifetime; in CPython it is the memory address. Two names refer to the same object exactly when their ids are equal, which is what the "is" operator tests.

Never print raw ids in notes and expect them to repeat: they differ between runs and machines. Compare them instead.

**Example 2.1.3.1: type() and id() comparisons (we print comparisons, not raw addresses)**

```python
a = 5
b = a
c = [1]
d = c
print(type(a), type(c))
print(id(a) == id(b), id(c) == id(d), id(a) == id(c))
print(a is b, c is d)
```

**Output:**

```text
<class 'int'> <class 'list'>
True True False
True True
```

**Example 2.1.3.2: type of a name does not exist; only the object has a type**

```python
x = 3
print(type(x))
x = 3.0
print(type(x))
```

**Output:**

```text
<class 'int'>
<class 'float'>
```

#### Practice 2.1.3

**2.1.3-Q1 BASIC**

```python
a = [1]; b = a; print(id(a) == id(b))
```

**2.1.3-Q2 BASIC**

```python
print(type(5), type(5.0), type("5"), type([5]))
```

**2.1.3-Q3 MID**

```python
a = [1]; b = list(a); print(a == b, id(a) == id(b))
```

**2.1.3-Q4 HARD**

```python
print(type(type(5)))
```



### 2.1.4 Names vs values

A value is the content of an object (5, "hi", [1, 2]). A name is a label in a namespace. Functions receive references to the objects passed in ("call by object reference"), so the function parameter is a new name for the same object.

**Example 2.1.4.1: A parameter is another name for the caller's object**

```python
def show(p):
    print(p is data)
data = [1, 2]
show(data)
```

**Output:**

```text
True
```

**Example 2.1.4.2: Reassigning the parameter does not affect the caller; mutating does**
<img width="1600" height="2742" alt="case1_int_plus_equals" src="https://github.com/user-attachments/assets/92a8bbe3-c5f6-4aea-8d52-0ee2f0ae111d" />
<img width="1600" height="2658" alt="case2_list_plus_equals" src="https://github.com/user-attachments/assets/2af71a53-909b-48ca-a982-2936679bc145" />
<img width="1600" height="2730" alt="case3_list_reassign" src="https://github.com/user-attachments/assets/d1e37389-cc9c-494d-a62e-b926e3fa8b85" />
<img width="1600" height="2672" alt="case4_slice_assign" src="https://github.com/user-attachments/assets/12f1a3e3-e6cf-46a4-9f45-d39448fecdae" />
<img width="1600" height="1362" alt="case5_summary" src="https://github.com/user-attachments/assets/425e0193-8af7-4999-8b1f-ecb97fddfaec" />





```python
def f(p):
    p = p + [99]
def g(p):
    p.append(99)
data = [1]
f(data); print(data)
g(data); print(data)
```

**Output:**

```text
[1]
[1, 99]
```

#### Practice 2.1.4

**2.1.4-Q1 BASIC**

```python
def f(n): n += 1
x = 1; f(x); print(x)
```

**2.1.4-Q2 MID**

```python
def f(l): l += [1]
x = []; f(x); print(x)
```

**2.1.4-Q3 MID**

```python
def f(l): l = l + [1]
x = []; f(x); print(x)
```

**2.1.4-Q4 HARD**

```python
def f(l): l[:] = [7]
x = [1, 2]; f(x); print(x)
```

### 2.1.5 Dynamic typing (contrast with static typing)

In a statically typed language (C, Java) the variable has a declared type and the compiler rejects wrong assignments. In Python the TYPE BELONGS TO THE OBJECT; a name can be rebound to any object at any time. Type errors appear at run time, when an operation meets an unsupported object.

Optional type hints (x: int) are read by tools like mypy, not enforced by the interpreter.
<!-- <img width="1600" height="2658" alt="IMG_20261031_194846826" src="https://github.com/user-attachments/assets/e439668e-c20b-41dd-b0f2-10a38dfa07b8" /> -->


**Example 2.1.5.1: One name, three types**

```python
v = 1
print(type(v).__name__)
v = "one"
print(type(v).__name__)
v = [1]
print(type(v).__name__)
```

**Output:**

```text
int
str
list
```

**Example 2.1.5.2: Hints are not enforced**
**                                              Hints are also called as annotated assignments                 **
<img width="1600" height="2743" alt="A1_annotated_basics" src="https://github.com/user-attachments/assets/69a5c57e-e0b6-4dd1-8cce-281a378a779a" />
<img width="1600" height="3313" alt="A2_annotated_enforce_novalue" src="https://github.com/user-attachments/assets/90078bd6-fb9d-4a74-bebd-caca6dcf20da" />
<img width="1600" height="3629" alt="A3_annotated_collections_variations" src="https://github.com/user-attachments/assets/a949239b-55d9-4713-8947-fe673246d074" />
<img width="1600" height="2898" alt="W1_walrus_basics" src="https://github.com/user-attachments/assets/bc69fb69-f641-4499-a834-d84a641ec1f7" />
<img width="1600" height="3381" alt="W2_walrus_loops_rules (1)" src="https://github.com/user-attachments/assets/22ebddf6-5b57-49c5-80e6-f1d25d692bcf" />
<img width="1600" height="3805" alt="W3_walrus_traps" src="https://github.com/user-attachments/assets/71448fc8-7bb9-458f-bbcf-ebc0444f66f8" />
<img width="1600" height="3694" alt="W4_walrus_patterns" src="https://github.com/user-attachments/assets/824be4af-130a-48e4-ac45-eabede642b8e" />
<img width="1600" height="3402" alt="P1_practice_annotated" src="https://github.com/user-attachments/assets/fdf0806b-efd3-46e7-ab2a-e6148f1cc5d5" />
<img width="1600" height="4102" alt="P2_practice_walrus" src="https://github.com/user-attachments/assets/0ad643c8-21d0-475b-99e7-ae1662863bdb" />
<img width="1600" height="5052" alt="P3_answers_annotated" src="https://github.com/user-attachments/assets/ccc43af1-439c-491f-9ceb-89f23dce7336" />
<img width="1600" height="6117" alt="P4_answers_walrus" src="https://github.com/user-attachments/assets/03561753-b4de-4eb5-8513-9d8a98efa964" />









```python
x: int = "hello"
print(x, type(x).__name__)
print(__annotations__)
```

**Output:**

```text
hello str
{'x': <class 'int'>}
```

**Example 2.1.5.3: Dynamic typing errors surface at the operation**

```python
def add(a, b):
    return a + b
print(add(2, 3))
print(add("2", "3"))
print(add(2, "3"))
```

**Output:**

```text
5
23
TypeError: unsupported operand type(s) for +: 'int' and 'str'
```

#### Practice 2.1.5

**2.1.5-Q1 BASIC**

```python
x = 1; x = "a"; print(x)
```

**2.1.5-Q2 MID**

```python
def f(a, b): return a * b
print(f(3, "ab"), f("ab", 3))
```

**2.1.5-Q3 MID**

```python
x: int = 2.5; print(x)
```

**2.1.5-Q4 HARD**

```python
def f(a, b): return a + b
print(f([1], [2]), f((1,), (2,)))
```

### 2.1.6 Strong typing (Python is strongly + dynamically typed)

Strong typing means the language does not silently convert between unrelated types. "1" + 1 raises TypeError in Python; JavaScript would return "11". Python does promote numbers (int to float to complex) because they form one numeric family.

**Example 2.1.6.1: No silent coercion between str and int**

```python
try:
    print("1" + 1)
except TypeError as e:
    print("TypeError:", e)
print("1" * 3)
print(1 + 2.5, 1 + 2j, True + 1)
```

**Output:**

```text
TypeError: can only concatenate str (not "int") to str
111
3.5 (1+2j) 2
```

**Example 2.1.6.2: Conversion must be explicit**

```python
print(int("1") + 1)
print("1" + str(1))
```

**Output:**

```text
2
11
```

#### Practice 2.1.6

**2.1.6-Q1 BASIC**

```python
print("a" * 3)
```

**2.1.6-Q2 MID**

```python
print(1 + True)
```

**2.1.6-Q3 MID**

```python
print(2 * "ab" + "c")
```

**2.1.6-Q4 HARD**

```python
print("5" + 5)
```

### 2.1.7 Objects: identity, type, value

Every object has three attributes: IDENTITY (never changes, id()), TYPE (never changes, type()), VALUE (can change only if the object is mutable). Names have none of these; they only point.

**Example 2.1.7.1: Mutating changes the value, not identity**

```python
l = [1]
i0 = id(l)
l.append(2)
print(l, id(l) == i0)
```

**Output:**

```text
[1, 2] True
```

**Example 2.1.7.2: Immutable objects: "changing" makes a new object**

```python
s = "ab"
i0 = id(s)
s += "c"
print(s, id(s) == i0)
```

**Output:**

```text
abc False
```

#### Practice 2.1.7

**2.1.7-Q1 BASIC**

```python
l = [1]; i = id(l); l.append(2); print(id(l) == i)
```

**2.1.7-Q2 MID**

```python
t = (1, 2); i = id(t); t += (3,); print(t, id(t) == i)
```

**2.1.7-Q3 HARD**

```python
x = 5; i = id(x); x += 1; print(id(x) == i)
```

### 2.1.8 Everything is an object: first proof

Numbers, strings, functions, classes, modules and even types are objects with attributes and methods. This is why you can pass a function as an argument or call a method on a literal.

**Example 2.1.8.1: Methods on literals, functions as objects**

```python
print((5).bit_length(), "abc".upper())
print(type(len), type(type), type(int))
f = len
print(f([1, 2, 3]))
print(hasattr(5, "__add__"), isinstance(int, object))
```

**Output:**

```text
3 ABC
<class 'builtin_function_or_method'> <class 'type'> <class 'type'>
3
True True
```

#### Practice 2.1.8

**2.1.8-Q1 BASIC**

```python
print((255).bit_length())
```

**2.1.8-Q2 MID**

```python
f = str.upper; print(f("hi"))
```

**2.1.8-Q3 MID**

```python
print(type(print).__name__)
```

**2.1.8-Q4 HARD**

```python
print(isinstance(int, type), isinstance(type, object), isinstance(object, type))
```

### 2.1.9 Variables are not declared

There is no declaration statement. The first assignment creates the name. Using a name that was never bound raises NameError. Deleting a name (del) removes the binding.

**Example 2.1.9.1: NameError and creation by assignment**

```python
try:
    print(y)
except NameError as e:
    print("NameError:", e)
y = 1
print(y)
del y
try:
    print(y)
except NameError as e:
    print("NameError:", e)
```

**Output:**

```text
NameError: name 'y' is not defined
1
NameError: name 'y' is not defined
```

#### Practice 2.1.9

**2.1.9-Q1 BASIC**

```python
x = 1; del x; print("x" in dir())
```

**2.1.9-Q2 MID**

```python
if False:
    z = 1
try:
    print(z)
except NameError as e:
    print(type(e).__name__)
```

**2.1.9-Q3 HARD**

```python
try:
    print(w)
except NameError:
    print("no w")
w = 3
print(w)
```

### 2.1.10 Multiple names for the same object

Aliasing means two or more names point to one object. For immutable objects it is invisible. For mutable objects it is the source of many bugs because a change through one name appears through all.

**Example 2.1.10.1: a = b = [] shares one list**

```python
a = b = []
a.append(1)
print(b, a is b)
```

**Output:**

```text
[1] True
```

**Example 2.1.10.2: Independent lists need independent objects**

```python
a = []
b = []
a.append(1)
print(b, a is b)
```

**Output:**

```text
[] False
```

**Example 2.1.10.3: Detecting aliasing with is**

```python
x = [1, 2]
y = x
z = x.copy()
print(x is y, x is z, x == z)
```

**Output:**

```text
True False True
```

#### Practice 2.1.10

**2.1.10-Q1 BASIC**

```python
a = b = []; a.append(1); print(b)
```

**2.1.10-Q2 MID**

```python
a = b = 0; a += 1; print(a, b)
```

**2.1.10-Q3 MID**

```python
a, b = [], []; a.append(1); print(b)
```

**2.1.10-Q4 HARD**

```python
a = b = [[0]]; a[0].append(1); print(b)
```

**2.1.10-Q5 TRAP**

```python
a = b = [1]; a = a + [2]; print(b)
```

### 2.1.11 Rebinding does not affect other names

Rebinding (x = ...) moves one arrow. It never changes other names that pointed at the old object. Mutation (x.append) changes the object everyone points at. Always ask: am I moving an arrow or changing the object?

**Example 2.1.11.1: Rebind vs mutate, side by side**

```python
a = [1]; b = a
a = [2]
print("after rebind:", a, b)
a = [1]; b = a
a.append(2)
print("after mutate:", a, b)
```

**Output:**

```text
after rebind: [2] [1]
after mutate: [1, 2] [1, 2]
```

#### Practice 2.1.11

**2.1.11-Q1 BASIC**

```python
a = 1; b = a; a = 2; print(b)
```

**2.1.11-Q2 MID**

```python
a = [1]; b = a; a = a + [2]; print(b)
```

**2.1.11-Q3 MID**

```python
a = [1]; b = a; a.extend([2]); print(b)
```

**2.1.11-Q4 HARD**

```python
a = [1]; b = a; a *= 2; print(b)
```

### 2.1.12 Variable lifetime and reference counting intro

CPython counts how many references each object has. When the count reaches zero the object is freed immediately. del removes a NAME, not the object; the object disappears only when no references remain. sys.getrefcount(x) reports one extra reference because passing x as an argument creates a temporary one.

**Example 2.1.12.1: Observing reference counts (differences, not absolutes)**

```python
import sys
x = []
base = sys.getrefcount(x)
y = x
print(sys.getrefcount(x) - base)
z = [x, x]
print(sys.getrefcount(x) - base)
del y, z
print(sys.getrefcount(x) - base)
```

**Output:**

```text
1
3
0
```

**Example 2.1.12.2: A weak reference shows when the object really dies**

```python
import weakref
class Box: pass
b = Box()
w = weakref.ref(b)
c = b
del b
print(w() is not None)
del c
print(w() is None)
```

**Output:**

```text
True
True
```

#### Practice 2.1.12

**2.1.12-Q1 BASIC**

```python
import sys; x = []; r = sys.getrefcount(x); y = x; print(sys.getrefcount(x) - r)
```

**2.1.12-Q2 MID**

```python
x = [1]; y = x; del x; print(y)
```

**2.1.12-Q3 HARD**

```python
import weakref
class B: pass
b = B(); w = weakref.ref(b); del b; print(w() is None)
```

### 2.1.13 Mental-model exercises (mini-lab)

Trace each program by drawing arrows before reading the output. Every answer below was produced by running the code.

#### Practice 2.1.13

**2.1.13-Q1 BASIC**

```python
a = 3; b = a; a = 4; print(a, b)
```

**2.1.13-Q2 BASIC**

```python
a = [1]; b = a; b.append(2); print(a, b)
```

**2.1.13-Q3 MID**

```python
a = [1, 2]; b = a[:]; b.append(3); print(a, b)
```

**2.1.13-Q4 MID**

```python
a = (1, [2]); b = a; b[1].append(3); print(a)
```

**2.1.13-Q5 MID**

```python
a = "x"; b = a; a += "y"; print(a, b)
```

**2.1.13-Q6 HARD**

```python
a = [1]; b = [a] * 3; a.append(2); print(b)
```

**2.1.13-Q7 HARD**

```python
a = [1]; b = [a[:]] * 3; b[0].append(2); print(b)
```

**2.1.13-Q8 HARD**

```python
x = [1]; y = x; x = x + [2]; y += [3]; print(x, y)
```

**2.1.13-Q9 TRAP**

```python
a = b = c = [0]; b = b + [1]; c += [2]; print(a, b, c)
```

**2.1.13-Q10 TRAP**

```python
a = [1]; b = a; a, b = b, a + [9]; print(a, b)
```

---

## Section 2.2 Naming

### 2.2.1 Valid identifier rules

An identifier may contain letters, digits and underscore, must not start with a digit, and must not be a keyword. Unicode letters are allowed. str.isidentifier() checks syntax (not keywords); keyword.iskeyword() checks reserved words.

**Example 2.2.1.1: Testing candidate names**

```python
import keyword
for s in ["name", "_x", "x1", "1x", "my-var", "class", "naïve", "π"]:
    print(f"{s!r:10} identifier={s.isidentifier()} keyword={keyword.iskeyword(s)}")
```

**Output:**

```text
'name'     identifier=True keyword=False
'_x'       identifier=True keyword=False
'x1'       identifier=True keyword=False
'1x'       identifier=False keyword=False
'my-var'   identifier=False keyword=False
'class'    identifier=True keyword=True
'naïve'    identifier=True keyword=False
'π'        identifier=True keyword=False
```

#### Practice 2.2.1

**2.2.1-Q1 BASIC**

```python
print("var_1".isidentifier(), "1var".isidentifier())
```

**2.2.1-Q2 MID**

```python
import keyword; print(keyword.iskeyword("None"), keyword.iskeyword("print"))
```

**2.2.1-Q3 MID**

```python
print("a b".isidentifier(), "a_b".isidentifier())
```

**2.2.1-Q4 HARD**

```python
import keyword; print(keyword.iskeyword("match"), "match".isidentifier())
```

### 2.2.2 Case sensitivity

age, Age and AGE are three different names. Typos in case create new names silently when you assign, and NameError when you read.

**Example 2.2.2.1: Three different names**

```python
age = 1; Age = 2; AGE = 3
print(age, Age, AGE)
try:
    print(agE)
except NameError as e:
    print("NameError:", e)
```

**Output:**

```text
1 2 3
NameError: name 'agE' is not defined
```

#### Practice 2.2.2

**2.2.2-Q1 BASIC**

```python
a = 1; A = 2; print(a + A)
```

**2.2.2-Q2 MID**

```python
total = 5
Total = total + 1
print(total, Total)
```

**2.2.2-Q3 HARD**

```python
x = 1
X = x
x = 2
print(X)
```

### 2.2.3 snake_case convention (PEP 8)

PEP 8: variables, functions and modules use lower_snake_case; classes use CapWords; constants use UPPER_SNAKE_CASE. Conventions are enforced by linters, not the interpreter.

**Example 2.2.3.1: Style table demonstrated**

```python
user_name = "ana"
MAX_RETRIES = 3
class HttpClient: pass
print(user_name, MAX_RETRIES, HttpClient.__name__)
```

**Output:**

```text
ana 3 HttpClient
```

#### Practice 2.2.3

**2.2.3-Q1 BASIC**

```python
print("snake_case".islower(), "SnakeCase".islower())
```

**2.2.3-Q2 MID**

```python
print("MAX_SIZE".isupper())
```

**2.2.3-Q3 HARD**

```python
print("CapWords".isidentifier(), "CapWords"[0].isupper())
```

### 2.2.4 Constant naming (UPPER_CASE, Final)

Python has no real constants. UPPER_CASE is a promise to other programmers. typing.Final lets a type checker reject reassignment; at run time nothing stops it.
## 2.2.4 Constant Naming (`UPPER_CASE`, `Final`)

Python does not have built-in syntax that makes an ordinary variable truly constant. Instead, Python provides naming conventions and type annotations to communicate that a value should not be reassigned.

There are two important concepts:

1. `UPPER_CASE` — a naming convention that communicates that a variable is intended to remain unchanged.
2. `typing.Final` — a special type annotation that allows static type checkers to detect reassignment.

Let's understand both.

### 1. What Is a Constant?

A constant is a value that is intended to remain unchanged throughout a program.

For example:

```python
PI = 3.14159
GRAVITY = 9.8
MAX_USERS = 100
DATABASE_NAME = "students"
```

Notice that all variable names are written in uppercase.

Why?

Because uppercase naming communicates to other programmers:

**"This variable is intended to remain unchanged. Please don't reassign it."**

However, Python does not enforce this convention.

Consider:

```python
RATE = 0.2

RATE = 0.5

print(RATE)
```

Output:

```text
0.5
```

Python allows this without raising an error.

Why?

Because `RATE` is simply an ordinary variable written in uppercase.

UPPER_CASE is a naming convention, not a restriction enforced by Python.

### 2. What Is `typing.Final`?

Python provides something called `Final` inside its `typing` module.

It allows programmers to communicate that a variable should not be reassigned.

Example:

```python
from typing import Final

RATE: Final = 0.2
```

Let's understand this statement.

**Part A:**

```python
from typing import Final
```

We import `Final` from Python's built-in `typing` module.

**Part B:**

```python
RATE: Final = 0.2
```

This is a variable annotation.

It communicates:

"RATE is intended to be final. Do not reassign it."

The important distinction is that `Final` is primarily checked by static type-checking tools. It does not automatically prevent reassignment when Python executes the program.

### 3. Understanding the Original Example

**Example 2.2.4.1: Final Is Checked by Tools Only**

```python
from typing import Final

RATE: Final = 0.2

RATE = 0.5

print(RATE)
```

Output:

```text
0.5
```

Let's execute this code conceptually, line by line.

**Line 1:**

```python
from typing import Final
```

Imports `Final` from the `typing` module.

**Line 2:**

```python
RATE: Final = 0.2
```

Creates a variable named `RATE` and marks it as final for static type checking.

**Line 3:**

```python
RATE = 0.5
```

We attempt to reassign the variable.

Python allows this at runtime!

However, a static type checker should report an error because we are reassigning a variable marked as `Final`.

**Line 4:**

```python
print(RATE)
```

Python prints:

```text
0.5
```

The program executes successfully, even though a static type checker would complain about the reassignment.

### 4. Python Interpreter vs Static Type Checker

This is the most important distinction to understand.

There are two different processes involved:

**A. Python Interpreter**

The Python interpreter executes your code.

It does not enforce `Final` as a runtime restriction.

Therefore:

```python
from typing import Final

RATE: Final = 0.2

RATE = 0.5

print(RATE)
```

Executes successfully and prints:

```text
0.5
```

**B. Static Type Checker**

A static type checker examines your code to detect potential mistakes without needing to execute it.

For example:

- `mypy`
- `Pyright`

These tools understand the meaning of `Final` and can report an error when a variable marked as final is reassigned.

Conceptually:

```text
                 YOUR PYTHON CODE
                        |
             -----------------------
             |                     |
             v                     v
       Python Interpreter    Static Type Checker
             |                     |
             v                     v
       Executes code         Examines code
             |                     |
             v                     v
       Allows reassignment  Reports reassignment
             |                     |
             v                     v
          Output                Warning/Error
            0.5
```

Remember:

**Python allows the reassignment at runtime, but a static type checker detects that it violates the `Final` annotation.**

### 5. Difference Between UPPER_CASE and Final

| Code | Meaning | Runtime Reassignment |
|---|---|---|
| `rate = 0.2` | Ordinary variable | Allowed |
| `RATE = 0.2` | Constant naming convention | Allowed |
| `RATE: Final = 0.2` | Final annotation | Allowed, but type checker reports an error |

Both UPPER_CASE and `Final` communicate that a variable should remain unchanged.

The difference is that `Final` provides additional information that static type-checking tools can understand.

### 6. Important: Final Does Not Freeze Objects!

This is another interesting aspect of Python.

Consider:

```python
from typing import Final

numbers: Final = [1, 2, 3]

numbers.append(4)

print(numbers)
```

Output:

```text
[1, 2, 3, 4]
```

Why did this work?

Because `Final` prevents reassignment according to static type-checking rules. It does not make the object immutable.

To understand this, we need to distinguish between two operations:

**A. Reassignment**

Reassignment changes what a variable refers to.

```python
from typing import Final

numbers: Final = [1, 2, 3]

numbers = [4, 5, 6]  # Static type checker error
```

Here, we are attempting to make `numbers` refer to an entirely different list.

**B. Mutation**

Mutation changes the existing object without changing what the variable refers to.

```python
from typing import Final

numbers: Final = [1, 2, 3]

numbers.append(4)

print(numbers)
```

Output:

```text
[1, 2, 3, 4]
```

This is allowed because we are modifying the existing list rather than reassigning the variable.

Compare:

| Operation | What happens? | Static Type Checker |
|---|---|---|
| `numbers = [4, 5, 6]` | Reassigns the variable | Reports an error |
| `numbers.append(4)` | Mutates the existing list | Allowed |

This connects directly to the concepts of mutable objects, immutable objects, and references.

### 7. Quick Knowledge Check

**Question: What happens when we execute this code?**

```python
from typing import Final

DATA: Final = [10, 20]

DATA.append(30)

print(DATA)
```

Options:

1. Python raises an error.
2. Static type checker raises an error.
3. Prints `[10, 20, 30]`.
4. Prints `[10, 20]`.

**Correct Answer: Option 3**

Output:

```text
[10, 20, 30]
```

Explanation:

`append()` modifies the existing list. It does not reassign the variable `DATA`.

Therefore, the operation is allowed.

`Final` does not make the list immutable.

---

### Key Takeaways

1. Python does not have built-in syntax that makes ordinary variables truly constant.
2. `UPPER_CASE` is a naming convention used to communicate that a variable should not change.
3. `typing.Final` is a type annotation that allows static type checkers to detect reassignment.
4. Python itself does not enforce `Final` as a runtime restriction.
5. `Final` does not make mutable objects immutable.
6. Reassignment and mutation are two different operations.

**The most important thing to remember:**

UPPER_CASE tells programmers not to change something. `Final` tells static type checkers to report attempts to reassign it. Neither makes an ordinary Python variable truly constant at runtime.

**Example 2.2.4.1: Final is checked by tools only**

```python
from typing import Final
RATE: Final = 0.2
RATE = 0.5
print(RATE)
```

**Output:**

```text
0.5
```

#### Practice 2.2.4

**2.2.4-Q1 BASIC**

```python
PI = 3.14; PI = 3; print(PI)
```

**2.2.4-Q2 MID**

```python
from typing import Final
X: Final = 1
X += 1
print(X)
```

**2.2.4-Q3 HARD**

```python
import math; math.pi = 3; print(math.pi)
```

### 2.2.5 Reserved keywords as names (error)

Hard keywords (class, def, if, for, None, True, ...) cannot be names. Soft keywords (match, case, type, \_) can still be names but should not. A trailing underscore (class\_) is the standard workaround.

**Example 2.2.5.1: What happens**

```python
import keyword
print(len(keyword.kwlist), keyword.softkwlist)
try:
    compile("class = 1", "<s>", "exec")
except SyntaxError as e:
    print("SyntaxError:", e.msg)
class_ = 1
print(class_)
match = 5
print(match)
```

**Output:**

```text
35 ['_', 'case', 'match', 'type']
SyntaxError: invalid syntax
1
5
```

#### Practice 2.2.5

**2.2.5-Q1 BASIC**

```python
import keyword; print("def" in keyword.kwlist)
```

**2.2.5-Q2 MID**

```python
import keyword; print("print" in keyword.kwlist)
```

**2.2.5-Q3 MID**

```python
try:
    compile("None = 1", "<s>", "exec")
except SyntaxError as e:
    print("SyntaxError")
```

**2.2.5-Q4 HARD**

```python
import keyword; print("_" in keyword.softkwlist, "match" in keyword.softkwlist)
```

### 2.2.6 Dunder names (\_\_x\_\_): intro

Names that begin and end with double underscores belong to Python (\_\_name\_\_, \_\_doc\_\_, \_\_init\_\_, \_\_add\_\_). Use them to hook into language behaviour, but never invent your own.

**Example 2.2.6.1: Built-in dunder attributes**

```python
def f():
    "doc text"
print(f.__name__, f.__doc__)
print(__name__)
print((5).__add__(3), (5).__class__)
```

**Output:**

```text
f doc text
__main__
8 <class 'int'>
```

#### Practice 2.2.6

**2.2.6-Q1 BASIC**

```python
print((2).__mul__(4))
```

**2.2.6-Q2 MID**

```python
print("abc".__len__())
```

**2.2.6-Q3 HARD**

```python
print(5 .__eq__(5.0), 5 .__eq__("5"))
```

### 2.2.7 Private-ish naming (\_x, \_\_x, \_\_x\_\_)

\_x: "internal use" hint. \_\_x inside a class: name mangling to \_ClassName\_\_x, which avoids accidental clashes in subclasses. \_\_x\_\_: reserved dunder. None of these are true privacy.

**Example 2.2.7.1: Mangling in action**

```python
class A:
    def __init__(self):
        self.pub = 1
        self._prot = 2
        self.__priv = 3
a = A()
print(a.pub, a._prot)
print([n for n in vars(a)])
print(a._A__priv)
try:
    print(a.__priv)
except AttributeError as e:
    print("AttributeError:", e)
```

**Output:**

```text
1 2
['pub', '_prot', '_A__priv']
3
AttributeError: 'A' object has no attribute '__priv'
```

#### Practice 2.2.7

**2.2.7-Q1 BASIC**

```python
class A:
    _x = 1
print(A._x)
```

**2.2.7-Q2 MID**

```python
class A:
    def __init__(self): self.__v = 1
print(sorted(vars(A())))
```

**2.2.7-Q3 HARD**

```python
class A:
    __v = 1
class B(A): pass
print(hasattr(B, "__v"), hasattr(B, "_A__v"))
```

### 2.2.8 Beginner pitfalls: shadowing built-ins (list, id, input)

Assigning to a name like list, id, input, sum or max hides the built-in in that scope. Later calls fail with confusing errors. del the name to restore the built-in.

**Example 2.2.8.1: The classic list bug**

```python
list = [1, 2, 3]
try:
    print(list("abc"))
except TypeError as e:
    print("TypeError:", e)
del list
print(list("abc"))
```

**Output:**

```text
TypeError: 'list' object is not callable
['a', 'b', 'c']
```

**Example 2.2.8.2: Safe check**

```python
import builtins
print(hasattr(builtins, "sum"), hasattr(builtins, "total"))
```

**Output:**

```text
True False
```

#### Practice 2.2.8

**2.2.8-Q1 BASIC**

```python
sum = 10; del sum; print(sum([1, 2]))
```

**2.2.8-Q2 MID**

```python
max = 3
try:
    print(max(1, 2))
except TypeError:
    print("shadowed")
```

**2.2.8-Q3 HARD**

```python
id = 5
print(type(id).__name__)
del id
print(type(id).__name__)
```

### 2.2.9 Naming for readability

Use descriptive names; put units in names (timeout_s); boolean names read as questions (is_ready, has_items); avoid l, O, I as single letters (look like 1 and 0). Loop variables can be short (i, k, x) when the scope is tiny.

**Example 2.2.9.1: Same code, two names**

```python
d = 86400
total_seconds_per_day = 24 * 60 * 60
print(d == total_seconds_per_day)
```

**Output:**

```text
True
```

#### Practice 2.2.9

**2.2.9-Q1 BASIC**

```python
is_ready = True; print(not is_ready)
```

**2.2.9-Q2 MID**

```python
timeout_s = 30; timeout_ms = timeout_s * 1000; print(timeout_ms)
```

### 2.2.10 Throwaway name \_

\_ marks "I do not care". In the REPL it holds the last result. It is also a common loop variable and unpacking target.

**Example 2.2.10.1: Common uses**

```python
for _ in range(3):
    print("hi", end=" ")
print()
a, _, c = (1, 2, 3)
print(a, c)
first, *_ = [10, 20, 30]
print(first)
```

**Output:**

```text
hi hi hi
1 3
10
```

#### Practice 2.2.10

**2.2.10-Q1 BASIC**

```python
a, _ = (1, 2); print(a)
```

**2.2.10-Q2 MID**

```python
_, _, z = (1, 2, 3); print(z)
```

**2.2.10-Q3 HARD**

```python
for _ in range(2): pass
print(_)
```

### 2.2.11 Unicode names and normalisation

Python accepts Unicode letters in identifiers and normalises them with NFKC, so different spellings can be the same name. Lookalike characters (Latin a vs Cyrillic a) create different names, a source of bugs and attacks. Prefer ASCII.

**Example 2.2.11.1: NFKC folding and lookalikes**

```python
import unicodedata
ﬁ = 1
print(fi)
a1 = "latin"
а = "cyrillic"
print(a1, "a" == "\u0430", unicodedata.name("\u0430"))
```

**Output:**

```text
1
latin False CYRILLIC SMALL LETTER A
```

#### Practice 2.2.11

**2.2.11-Q1 BASIC**

```python
print("ñ".isidentifier())
```

**2.2.11-Q2 MID**

```python
print("ﬁ".isidentifier())
```

**2.2.11-Q3 HARD**

```python
import unicodedata; print(unicodedata.normalize("NFKC", "ﬁ"))
```

### 2.2.12 Naming in competitive programming

Short names (n, m, a, dp, ans) are accepted because functions are small and time is limited. Keep a consistent convention: n sizes, i j k indices, a b arrays, ans result. Outside contests, prefer readable names.

**Example 2.2.12.1: A typical contest header**

```python
n = 5
a = [3, 1, 4, 1, 5]
ans = sum(a)
print(n, ans)
```

**Output:**

```text
5 14
```

#### Practice 2.2.12

**2.2.12-Q1 BASIC**

```python
n = 3; a = [1] * n; print(a)
```

**2.2.12-Q2 MID**

```python
a = [1, 2, 3]; ans = max(a) - min(a); print(ans)
```

---

## Section 2.3 Assignment

### 2.3.1 Simple assignment

"x = 10" has two steps. First the right side is fully evaluated to an object. Then the name is bound to that object. Assignment is a statement: it produces no value, so "print(x = 5)" is a syntax error (the walrus operator := is the expression form).

**Example 2.3.1.1: Evaluation order**

```python
x = 10
y = x + 1
x = x * 2
print(x, y)
```

**Output:**

```text
20 11
```

**Example 2.3.1.2: Assignment is a statement**

```python
try:
    compile("if z = 5: pass", "<s>", "exec")
except SyntaxError:
    print("SyntaxError: assignment is not an expression")
print(compile("(z := 5)", "<s>", "eval") is not None)
```

**Output:**

```text
SyntaxError: assignment is not an expression
True
```

#### Practice 2.3.1

**2.3.1-Q1 BASIC**

```python
x = 2; x = x * x; print(x)
```

**2.3.1-Q2 MID**

```python
x = 1; x = x + x; x = x + x; print(x)
```

**2.3.1-Q3 HARD**

```python
x = 3; y = (x := x + 1) * 2; print(x, y)
```

### 2.3.2 Multiple assignment: a = b = c = 0

Chained assignment evaluates the right side ONCE and binds every name, left to right, to that single object. Safe for immutable values; with a mutable value all names are aliases.

**Example 2.3.2.1: Immutable value is harmless**

```python
a = b = c = 0
a += 1
print(a, b, c)
```

**Output:**

```text
1 0 0
```

**Example 2.3.2.2: Mutable value is shared**

```python
a = b = c = []
a.append(1)
print(a, b, c, a is c)
```

**Output:**

```text
[1] [1] [1] True
```

**Example 2.3.2.3: Build independent objects with a comprehension or separate lines**

```python
a, b, c = [], [], []
a.append(1)
print(a, b, c)
```

**Output:**

```text
[1] [] []
```

#### Practice 2.3.2

**2.3.2-Q1 BASIC**

```python
a = b = 5; a = 6; print(b)
```

**2.3.2-Q2 MID**

```python
a = b = [1]; b.append(2); print(a)
```

**2.3.2-Q3 MID**

```python
a = b = [1]; b = b + [2]; print(a)
```

**2.3.2-Q4 HARD**

```python
a = b = c = [0]; c += [1]; print(a, b)
```

**2.3.2-Q5 TRAP**

```python
a = b = {"k": 1}; b["k"] = 2; print(a)
```

### 2.3.3 Tuple unpacking: a, b = 1, 2

The right side builds a tuple (packing), then its items are bound to the targets (unpacking). Any iterable works on the right. The count must match exactly or ValueError is raised.

**Example 2.3.3.1: Basic, any iterable, wrong counts**

```python
a, b = 1, 2
print(a, b)
x, y, z = "abc"
print(x, y, z)
p, q = {"k1": 1, "k2": 2}
print(p, q)
try:
    a, b = [1, 2, 3]
except ValueError as e:
    print("ValueError:", e)
try:
    a, b, c = [1, 2]
except ValueError as e:
    print("ValueError:", e)
```

**Output:**

```text
1 2
a b c
k1 k2
ValueError: too many values to unpack (expected 2)
ValueError: not enough values to unpack (expected 3, got 2)
```

#### Practice 2.3.3

**2.3.3-Q1 BASIC**

```python
a, b = "xy"; print(b)
```

**2.3.3-Q2 MID**

```python
a, b = {"u": 1, "v": 2}.values(); print(a + b)
```

**2.3.3-Q3 MID**

```python
a, b = (1,); print(a)
```

**2.3.3-Q4 HARD**

```python
a, b = range(2, 4); print(a * b)
```

### 2.3.4 Swap idiom: a, b = b, a

The right side tuple (b, a) is built first using the current values, then the names are bound. That is why no temporary variable is needed. Bytecode uses a SWAP instruction for two or three items.

**Example 2.3.4.1: Swap and Fibonacci step**

```python
a, b = 1, 2
a, b = b, a
print(a, b)
a, b = 0, 1
for _ in range(8):
    a, b = b, a + b
print(a, b)
```

**Output:**

```text
2 1
21 34
```

**Example 2.3.4.2: Why order matters**

```python
a, b = 1, 2
a = b
b = a
print(a, b)
```

**Output:**

```text
2 2
```



#### Practice 2.3.4

**2.3.4-Q1 BASIC**

```python
a, b = 3, 4; a, b = b, a; print(a, b)
```

**2.3.4-Q2 MID**

```python
a, b, c = 1, 2, 3; a, b, c = c, a, b; print(a, b, c)
```

**2.3.4-Q3 HARD**

```python
a, b = 1, 2; a, b = b, a + b; print(a, b)
```

**2.3.4-Q4 TRAP**

```python
a = 1; b = 2; a = b; b = a; print(a, b)
```

### 2.3.5 Starred unpacking: a, \*b = [1,2,3]

One starred target collects the leftover items into a LIST (even when the source is a tuple or string). Only one star is allowed per target list. The star can sit at the start, middle or end; with no leftovers it collects [].

**Example 2.3.5.1: Positions of the star**

```python
a, *b = [1, 2, 3]
print(a, b)
*h, t = "abcd"
print(h, t)
first, *mid, last = (1, 2, 3, 4, 5)
print(first, mid, last)
x, *rest = [1]
print(x, rest)
```

**Output:**

```text
1 [2, 3]
['a', 'b', 'c'] d
1 [2, 3, 4] 5
1 []
```

**Example 2.3.5.2: Errors**

```python
try:
    compile("*a, *b = [1, 2]", "<s>", "exec")
except SyntaxError as e:
    print("SyntaxError:", e.msg)
try:
    a, *b, c = [1]
except ValueError as e:
    print("ValueError:", e)
```

**Output:**

```text
SyntaxError: multiple starred expressions in assignment
ValueError: not enough values to unpack (expected at least 2, got 1)
```

#### Practice 2.3.5

**2.3.5-Q1 BASIC**

```python
a, *b = [1, 2, 3]; print(b)
```

**2.3.5-Q2 MID**

```python
*a, b = "xyz"; print(a, b)
```

**2.3.5-Q3 MID**

```python
a, *b = (1,); print(b)
```

**2.3.5-Q4 HARD**

```python
a, *b, c = range(5); print(a, b, c)
```

### 2.3.6 Augmented assignment (+=, -=, \*=, //=, \*\*=, &=, \|=, ^=, >>=,

### \<\<=, @=)

x += y is x = x + y with the target evaluated once, BUT the object may be mutated in place: Python first tries x.\_\_iadd\_\_(y). Mutable types (list, set, dict, bytearray) implement in-place versions; immutable types (int, str, tuple) fall back to x = x + y and rebind.

**Example 2.3.6.1: Every operator**

```python
x = 20
x += 2; print(x)
x -= 5; print(x)
x *= 2; print(x)
x //= 3; print(x)
x **= 2; print(x)
x %= 7; print(x)
x &= 6; x |= 9; x ^= 5; print(x)
x <<= 2; x >>= 1; print(x)
```

**Output:**

```text
22
17
34
11
121
2
14
28
```

**Example 2.3.6.2: In place vs rebind**

```python
l = [1]; m = l
l += [2]
print(m)
t = (1,); u = t
t += (2,)
print(u, t)
```

**Output:**

```text
[1, 2]
(1,) (1, 2)
```

**Example 2.3.6.3: Matrix operator exists but no builtin type uses it**

```python
try:
    x = 1; x @= 2
except TypeError as e:
    print("TypeError:", e)
```

**Output:**

```text
TypeError: unsupported operand type(s) for @=: 'int' and 'int'
```

#### Practice 2.3.6

**2.3.6-Q1 BASIC**

```python
x = 5; x *= 3; x -= 1; print(x)
```

**2.3.6-Q2 MID**

```python
l = [1]; m = l; l += [2]; print(m)
```

**2.3.6-Q3 MID**

```python
s = {1}; t = s; s |= {2}; print(t)
```

**2.3.6-Q4 HARD**

```python
l = [1]; m = l; l = l + [2]; print(m)
```

**2.3.6-Q5 TRAP**

```python
t = ([1], 2)
try:
    t[0] += [9]
except TypeError as e:
    print("TypeError")
print(t)
```

### 2.3.7 Chained comparison: 1 \< x \< 10

a \< b \< c means (a \< b) and (b \< c), with b evaluated only once. Chains work with any comparison operators, including == and in.

**Example 2.3.7.1: Basic and evaluation count**

```python
x = 5
print(1 < x < 10, 1 < x < 3)
def f():
    print("f called")
    return 5
print(1 < f() < 10)
```

**Output:**

```text
True False
f called
True
```

**Example 2.3.7.2: Surprising chains**

```python
print(1 < 2 > 1)
print(3 == 3 < 4)
print(1 == 1 in [1])
print(1 < 2 < 3 < 2)
```

**Output:**

```text
True
True
True
False
```

#### Practice 2.3.7

**2.3.7-Q1 BASIC**

```python
print(1 < 2 < 3)
```

**2.3.7-Q2 MID**

```python
print(5 > 3 > 4)
```

**2.3.7-Q3 MID**

```python
print(0 < 0 < 1 or 1)
```

**2.3.7-Q4 HARD**

```python
print(1 == 1 == True)
```

**2.3.7-Q5 HARD**

```python
print(False == False in [False])
```

### 2.3.8 Reassignment vs mutation

Reassignment: the NAME moves to a new object. Mutation: the OBJECT itself changes. Use id() or "is" to tell which happened. This is the single most important idea in the chapter.

**Example 2.3.8.1: Same experiment on a list and a string**

```python
l = [1]; i = id(l)
l.append(2)
print("list mutated, same object:", id(l) == i)
l = l + [3]
print("list rebound, same object:", id(l) == i)
s = "ab"; j = id(s)
s += "c"
print("str rebound, same object:", id(s) == j)
```

**Output:**

```text
list mutated, same object: True
list rebound, same object: False
str rebound, same object: False
```

**Example 2.3.8.2: Which methods mutate**

```python
l = [3, 1, 2]
print(l.sort(), l)
print(sorted([3, 1, 2]))
print(l.reverse(), l)
```

**Output:**

```text
None [1, 2, 3]
[1, 2, 3]
None [3, 2, 1]
```

**Example 2.3.8.3: Mutation visible through every alias**

```python
a = [1]; b = a
a.append(2)
a = a + [3]
print(a, b)
```

**Output:**

```text
[1, 2, 3] [1, 2]
```

#### Practice 2.3.8

**2.3.8-Q1 BASIC**

```python
l = [1]; l.append(2); print(l)
```

**2.3.8-Q2 MID**

```python
l = [3, 1]; r = l.sort(); print(r, l)
```

**2.3.8-Q3 MID**

```python
a = [1]; b = a; a = a + [2]; print(b)
```

**2.3.8-Q4 HARD**

```python
a = [1]; b = a; a += [2]; a = a + [3]; print(a, b)
```

**2.3.8-Q5 TRAP**

```python
x = [1, 2]; y = x.append(3); print(y)
```

### 2.3.9 del keyword

del removes a binding (or a container item/slice). It does not directly destroy objects; they go away only when the reference count reaches zero. After del the name raises NameError.

**Example 2.3.9.1: Forms of del**

```python
x = 1; del x
l = [0, 1, 2, 3, 4]
del l[0]; print(l)
del l[1:3]; print(l)
d = {"a": 1, "b": 2}
del d["a"]; print(d)
a = [1]; b = a
del a
print(b)
```

**Output:**

```text
[1, 2, 3, 4]
[1, 4]
{'b': 2}
[1]
```

#### Practice 2.3.9

**2.3.9-Q1 BASIC**

```python
l = [1, 2, 3]; del l[1]; print(l)
```

**2.3.9-Q2 MID**

```python
l = list(range(6)); del l[::2]; print(l)
```

**2.3.9-Q3 MID**

```python
a = [1]; b = a; del a; print(b)
```

**2.3.9-Q4 HARD**

```python
l = [1, 2, 3]; del l[:]; print(l)
```

### 2.3.10 None as default

None is the standard "no value yet" marker. It is a singleton, falsy, and distinct from 0, "" and []. Test with "is None".

**Example 2.3.10.1: None versus other falsy values**

```python
for v in [None, 0, "", []]:
    print(repr(v), bool(v), v is None)
result = None
if result is None:
    print("not computed yet")
```

**Output:**

```text
None False True
0 False False
'' False False
[] False False
not computed yet
```

#### Practice 2.3.10

**2.3.10-Q1 BASIC**

```python
print(None is None)
```

**2.3.10-Q2 MID**

```python
x = None; print(x == 0, x is None)
```

**2.3.10-Q3 HARD**

```python
print(None == False, not None)
```

### 2.3.11 Nested unpacking

Unpacking patterns can be nested to mirror the data structure. They are also used in for loops over enumerate, zip and dict.items().

**Example 2.3.11.1: Nested structures**

```python
(a, (b, c)) = (1, (2, 3))
print(a, b, c)
for i, (k, v) in enumerate({"x": 1, "y": 2}.items()):
    print(i, k, v)
for a, b in zip("ab", [1, 2]):
    print(a, b)
[(p, q), r] = [(1, 2), 3]
print(p, q, r)
```

**Output:**

```text
1 2 3
0 x 1
1 y 2
a 1
b 2
1 2 3
```

#### Practice 2.3.11

**2.3.11-Q1 BASIC**

```python
(a, b), c = (1, 2), 3; print(a + b + c)
```

**2.3.11-Q2 MID**

```python
for k, v in {"a": 1}.items(): print(k, v)
```

**2.3.11-Q3 HARD**

```python
(a, *b), c = ("xyz", 9); print(a, b, c)
```

### 2.3.12 Unpacking in function calls and literals

\* unpacks an iterable into positional arguments or list/tuple/set items; \*\* unpacks a dict into keyword arguments or dict items (PEP 448).

**Example 2.3.12.1: Calls and literals**

```python
def f(a, b, c): return a + b + c
print(f(*[1, 2, 3]), f(**{"a": 1, "b": 2, "c": 3}))
print([*"ab", *[1, 2]])
print({**{"a": 1}, **{"b": 2, "a": 9}})
print({*[1, 2], 3})
```

**Output:**

```text
6 6
['a', 'b', 1, 2]
{'a': 9, 'b': 2}
{1, 2, 3}
```

#### Practice 2.3.12

**2.3.12-Q1 BASIC**

```python
print([*range(3)])
```

**2.3.12-Q2 MID**

```python
print({**{"a": 1}, "a": 2})
```

**2.3.12-Q3 HARD**

```python
print([*"hi", *(1, 2)], (*[1], *[2]))
```

### 2.3.13 Assignment targets that are not names

The left side can be a name, an item (x[0]), a slice (x[1:3]), an attribute (obj.a) or a tuple/list of those. You cannot assign to literals, function calls or expressions.

**Example 2.3.13.1: Legal targets**

```python
l = [0, 1, 2, 3]
l[0] = 9
l[1:3] = ["a", "b", "c"]
print(l)
class O: pass
o = O(); o.v = 5
print(o.v)
d = {}
d["k"] = 1
d["k"], l[0] = 2, 100
print(d, l[0])
```

**Output:**

```text
[9, 'a', 'b', 'c', 3]
5
{'k': 2} 100
```

**Example 2.3.13.2: Illegal**

```python
for code in ["1 = x", "f() = 1", "x + 1 = 2"]:
    try:
        compile(code, "<s>", "exec")
    except SyntaxError as e:
        print(code, "->", e.msg)
```

**Output:**

```text
1 = x -> cannot assign to literal here. Maybe you meant '==' instead of '='?
f() = 1 -> cannot assign to function call here. Maybe you meant '==' instead of '='?
x + 1 = 2 -> cannot assign to expression here. Maybe you meant '==' instead of '='?
```

#### Practice 2.3.13

**2.3.13-Q1 BASIC**

```python
l = [1, 2, 3]; l[1:2] = [7, 8]; print(l)
```

**2.3.13-Q2 MID**

```python
l = [1, 2, 3]; l[:] = []; print(l)
```

**2.3.13-Q3 HARD**

```python
l = list(range(6)); l[::2] = ["a", "b", "c"]; print(l)
```

### 2.3.14 Walrus operator := first look

:= assigns inside an expression and gives the value. Useful in while loops and comprehensions to avoid repeating a computation. Parenthesise it in most places. The name is bound in the enclosing function scope.

**Example 2.3.14.1: Where it helps**

```python
data = [1, 5, 8, 12]
if (n := len(data)) > 3:
    print("long list", n)
print([y for x in data if (y := x * 2) > 10])
print(y)
```

**Output:**

```text
long list 4
[16, 24]
24
```

**Example 2.3.14.2: Needs parentheses at statement level**

```python
try:
    compile("x := 5", "<s>", "exec")
except SyntaxError as e:
    print("SyntaxError:", e.msg)
print((x := 5))
```

**Output:**

```text
SyntaxError: invalid syntax
5
```

#### Practice 2.3.14

**2.3.14-Q1 BASIC**

```python
print((n := 4) + 1, n)
```

**2.3.14-Q2 MID**

```python
print([(y := x) for x in range(3)], y)
```

**2.3.14-Q3 HARD**

```python
print(any((m := v) > 2 for v in [1, 3, 5]), m)
```

### 2.3.15 Annotated assignment x: int = 5

Syntax name: type = value. Stored in \_\_annotations\_\_ at module/class level; not enforced. A bare "x: int" declares an annotation without creating the name.

**Example 2.3.15.1: Annotations**

```python
x: int = 5
y: str
print(x)
print(__annotations__)
try:
    print(y)
except NameError as e:
    print("NameError:", e)
```

**Output:**

```text
5
{'x': <class 'int'>, 'y': <class 'str'>}
NameError: name 'y' is not defined
```

#### Practice 2.3.15

**2.3.15-Q1 BASIC**

```python
z: int = 3; print(z)
```

**2.3.15-Q2 MID**

```python
a: int = "s"; print(a)
```

**2.3.15-Q3 HARD**

```python
v: list[int]; print("v" in dir(), "v" in __annotations__)
```

### 2.3.16 Evaluation order puzzles

RHS is evaluated first, then targets are assigned left to right. When a later target depends on an earlier one, the result can surprise you.

**Example 2.3.16.1: Order of binding**

```python
i = 0
l = [0, 0, 0]
i, l[i] = 1, 9
print(i, l)
```

**Output:**

```text
1 [0, 9, 0]
```

**Example 2.3.16.2: The same, written the other way round**

```python
i = 0
l = [0, 0, 0]
l[i], i = 9, 1
print(i, l)
```

**Output:**

```text
1 [9, 0, 0]
```

**Example 2.3.16.3: Fibonacci**

```python
a, b = 1, 1
a, b = b, a + b
print(a, b)
```

**Output:**

```text
1 2
```

#### Practice 2.3.16

**2.3.16-Q1 BASIC**

```python
a, b = 1, 2; a, b = b, a; print(a, b)
```

**2.3.16-Q2 MID**

```python
i = 0; l = [0, 0]; i, l[i] = 1, 5; print(i, l)
```

**2.3.16-Q3 HARD**

```python
l = [0, 0]; i = 0; l[i], i = 7, 1; print(i, l)
```

**2.3.16-Q4 TRAP**

```python
a = [1, 2]; a[0], a[1] = a[1], a[0]; print(a)
```

### 2.3.17 Assignment inside loops and conditionals

Python has function-level scope, not block scope. Names created inside if/for/while remain after the block (if the block ran).

**Example 2.3.17.1: Loop variable survives**

```python
for i in range(3):
    last = i * 10
print(i, last)
```

**Output:**

```text
2 20
```

**Example 2.3.17.2: Name defined in a branch that did not run**

```python
if False:
    z = 1
try:
    print(z)
except NameError as e:
    print("NameError:", e)
```

**Output:**

```text
NameError: name 'z' is not defined
```

**Example 2.3.17.3: Empty loop leaves the name unbound**

```python
for q in []:
    pass
print("q" in dir())
```

**Output:**

```text
False
```

#### Practice 2.3.17

**2.3.17-Q1 BASIC**

```python
for i in range(3): pass
print(i)
```

**2.3.17-Q2 MID**

```python
for i in range(0): pass
print("i" in dir())
```

**2.3.17-Q3 HARD**

```python
x = 10
for x in range(3): pass
print(x)
```

### 2.3.18 Assignment mini-lab

Fifteen puzzles. Predict first, then compare.

#### Practice 2.3.18

**2.3.18-Q1 BASIC**

```python
a = b = 1; b += 1; print(a, b)
```

**2.3.18-Q2 BASIC**

```python
x, y = 1, 2; x, y = y, x; print(x, y)
```

**2.3.18-Q3 MID**

```python
a, *b = "hey"; print(a, b)
```

**2.3.18-Q4 MID**

```python
x = [1]; y = x; x += [2]; print(y)
```

**2.3.18-Q5 MID**

```python
a, (b, *c) = 1, (2, 3, 4); print(a, b, c)
```

**2.3.18-Q6 MID**

```python
i = 0; i += i + 1; print(i)
```

**2.3.18-Q7 HARD**

```python
a = [1, 2]; a[0], a[1] = a[1], a[0]; print(a)
```

**2.3.18-Q8 HARD**

```python
i = 1; l = [0, 0, 0]; i, l[i] = 2, 5; print(i, l)
```

**2.3.18-Q9 HARD**

```python
x = (y := 3) + y; print(x)
```

**2.3.18-Q10 HARD**

```python
a = [[]] * 2; a[0].append(1); print(a)
```

**2.3.18-Q11 TRAP**

```python
a = b = []; a += [1]; b = b + [2]; print(a, b)
```

**2.3.18-Q12 TRAP**

```python
t = (1, 2); a, b = t; t = (b, a); print(a, b, t)
```

**2.3.18-Q13 TRAP**

```python
x = 1; x = x if x > 1 else x + 10; print(x)
```

**2.3.18-Q14 TRAP**

```python
a, b, *c = [1, 2]; print(c)
```

**2.3.18-Q15 TRAP**

```python
n = 5; n -= n; n += 1; print(n)
```

---

## Section 2.4 Scope (Variables Lifespan)

### 2.4.1 Local / Enclosing / Global / Built-in (LEGB)

When Python reads a name it searches four scopes in order: Local (current function), Enclosing (outer functions), Global (module), Built-in (len, print, ...). The first match wins. Assigning to a name inside a function makes it local to that function.

**Example 2.4.1.1: One name at four levels**

```python
x = "global"
def outer():
    x = "enclosing"
    def inner():
        x = "local"
        print(x)
    inner()
    print(x)
outer()
print(x)
```

**Output:**

```text
local
enclosing
global
```

**Example 2.4.1.2: Built-in is the last resort**

```python
print(len([1, 2]))
def f():
    return len
print(f() is len)
```

**Output:**

```text
2
True
```

**Example 2.4.1.3: Namespaces as dicts**

```python
x = 1
def f():
    y = 2
    return locals()
print(f())
print("x" in globals())
```

**Output:**

```text
{'y': 2}
True
```

#### Practice 2.4.1

**2.4.1-Q1 BASIC**

```python
x = 1
def f(): return x
print(f())
```

**2.4.1-Q2 MID**

```python
x = 1
def f():
    x = 2
f()
print(x)
```

**2.4.1-Q3 MID**

```python
def outer():
    v = "e"
    def inner(): return v
    return inner()
print(outer())
```

**2.4.1-Q4 HARD**

```python
x = "g"
def f():
    print(x)
    x = "l"
try:
    f()
except UnboundLocalError:
    print("UnboundLocalError")
```

### 2.4.2 global keyword

Reading a global needs no declaration. Rebinding one inside a function does: "global x" tells Python the name refers to the module-level x. Mutating a global object (list.append) needs no declaration because no rebinding happens.

**Example 2.4.2.1: Rebind needs global; mutate does not**

```python
count = 0
log = []
def bump():
    global count
    count += 1
    log.append(count)
bump(); bump()
print(count, log)
```

**Output:**

```text
2 [1, 2]
```

**Example 2.4.2.2: Without global**

```python
n = 0
def f():
    n = 99
f()
print(n)
```

**Output:**

```text
0
```

#### Practice 2.4.2

**2.4.2-Q1 BASIC**

```python
g = 1
def f():
    global g
    g = 2
f()
print(g)
```

**2.4.2-Q2 MID**

```python
l = []
def f(): l.append(1)
f(); f(); print(l)
```

**2.4.2-Q3 HARD**

```python
n = 0
def f():
    n += 1
try:
    f()
except UnboundLocalError:
    print("error")
```

### 2.4.3 nonlocal keyword

nonlocal x rebinds a variable of the nearest enclosing function (never the module). Used for closures that keep state.

**Example 2.4.3.1: Counter closure**

```python
def make_counter():
    c = 0
    def inc():
        nonlocal c
        c += 1
        return c
    return inc
f = make_counter()
print(f(), f(), f())
g = make_counter()
print(g())
```

**Output:**

```text
1 2 3
1
```

**Example 2.4.3.2: nonlocal cannot target module level**

```python
try:
    compile("x = 1\ndef f():\n    nonlocal x\n", "<s>", "exec")
except SyntaxError as e:
    print("SyntaxError:", e.msg)
```

**Output:**

```text
SyntaxError: no binding for nonlocal 'x' found
```

#### Practice 2.4.3

**2.4.3-Q1 BASIC**

```python
def f():
    a = 1
    def g():
        nonlocal a
        a = 5
    g()
    return a
print(f())
```

**2.4.3-Q2 MID**

```python
def f():
    a = 1
    def g():
        a = 5
    g()
    return a
print(f())
```

**2.4.3-Q3 HARD**

```python
def mk():
    t = []
    def add(x):
        t.append(x)
        return len(t)
    return add
a = mk(); print(a(1), a(1), mk()(1))
```

### 2.4.4 Shadowing

A local name hides an outer name of the same spelling. Shadowing built-ins (list, sum) or standard modules (a file named random.py) is a frequent source of baffling errors.

**Example 2.4.4.1: Local hides global**

```python
v = "outer"
def f():
    v = "inner"
    return v
print(f(), v)
```

**Output:**

```text
inner outer
```

**Example 2.4.4.2: Parameter shadows global**

```python
n = 10
def f(n): return n * 2
print(f(3), n)
```

**Output:**

```text
6 10
```

**Example 2.4.4.3: A file named like a module (simulated)**

```python
import sys, types
fake = types.ModuleType("random")
fake.__dict__["note"] = "I am your file, not the stdlib"
sys.modules["random"] = fake
import random
print(hasattr(random, "randint"), random.note)
```

**Output:**

```text
False I am your file, not the stdlib
```

#### Practice 2.4.4

**2.4.4-Q1 BASIC**

```python
x = 1
def f(x): return x + 1
print(f(5), x)
```

**2.4.4-Q2 MID**

```python
len = 3
print(len)
del len
print(len([1, 2]))
```

**2.4.4-Q3 HARD**

```python
def f():
    sum = 0
    for i in [1, 2]: sum += i
    return sum
print(f(), sum([5]))
```

### 2.4.5 UnboundLocalError pitfall

If a function assigns to a name ANYWHERE in its body, that name is local for the WHOLE function. Reading it before the assignment raises UnboundLocalError. Fix with global/nonlocal, or pass it as a parameter.

**Example 2.4.5.1: The error**

```python
x = 10
def f():
    print(x)
    x = 20
try:
    f()
except UnboundLocalError as e:
    print("UnboundLocalError:", e)
```

**Output:**

```text
UnboundLocalError: cannot access local variable 'x' where it is not associated with a value
```

**Example 2.4.5.2: Three fixes**

```python
x = 10
def a():
    global x
    print(x); x = 20
def b(x):
    print(x); x = 20
    return x
def c():
    y = x
    print(y); y = 20
a(); print(b(x)); c()
```

**Output:**

```text
10
20
20
20
```

#### Practice 2.4.5

**2.4.5-Q1 BASIC**

```python
a = 1
def f():
    print(a)
f()
```

**2.4.5-Q2 MID**

```python
a = 1
def f():
    a += 1
try:
    f()
except UnboundLocalError:
    print("UnboundLocalError")
```

**2.4.5-Q3 HARD**

```python
a = 1
def f():
    if False:
        a = 2
    return a
try:
    f()
except UnboundLocalError:
    print("UnboundLocalError")
```

### 2.4.6 Module-level variables

Names assigned at the top level of a file live in the module's namespace (globals()). Importing runs the module once and caches it; importing again returns the same module and its state.

**Example 2.4.6.1: Module state is shared by all importers**

```python
import types, sys
m = types.ModuleType("counter")
exec("count = 0\ndef bump():\n    global count\n    count += 1\n    return count", m.__dict__)
sys.modules["counter"] = m
import counter
counter.bump(); counter.bump()
import counter as c2
print(c2.count, c2 is counter)
```

**Output:**

```text
2 True
```

#### Practice 2.4.6

**2.4.6-Q1 BASIC**

```python
import math; print(math.pi > 3)
```

**2.4.6-Q2 MID**

```python
import sys; import math as m1; import math as m2; print(m1 is m2)
```

**2.4.6-Q3 HARD**

```python
import sys; print("math" in sys.modules or True)
```

### 2.4.7 \_\_main\_\_ scope (intro)

A script run directly is the module \_\_main\_\_ and its \_\_name\_\_ equals "\_\_main\_\_". When the same file is imported, \_\_name\_\_ is the module's file name. The guard if \_\_name\_\_ == "\_\_main\_\_": runs code only when executed directly.

**Example 2.4.7.1: Simulating both situations**

```python
code = 'print("name is", __name__)\nif __name__ == "__main__":\n    print("running as script")'
exec(code, {"__name__": "__main__"})
exec(code, {"__name__": "mymodule"})
```

**Output:**

```text
name is __main__
running as script
name is mymodule
```

#### Practice 2.4.7

**2.4.7-Q1 BASIC**

```python
print(__name__)
```

**2.4.7-Q2 MID**

```python
print("__main__" == __name__)
```

### 2.4.8 Block scope does not exist

if, for, while, with, try do not create scopes. Functions, lambdas, classes and comprehensions do.

**Example 2.4.8.1: Block versus function**

```python
if True:
    inside_if = 1
print(inside_if)
def f():
    inside_f = 1
f()
print("inside_f" in dir())
```

**Output:**

```text
1
False
```

**Example 2.4.8.2: Comprehension has its own scope**

```python
r = [t for t in range(3)]
print("t" in dir())
```

**Output:**

```text
False
```

#### Practice 2.4.8

**2.4.8-Q1 BASIC**

```python
if True:
    a = 5
print(a)
```

**2.4.8-Q2 MID**

```python
[k for k in range(3)]
print("k" in dir())
```

**2.4.8-Q3 HARD**

```python
with open(__file__ if False else "/dev/null") as fh: name = fh.name
print(name, "fh" in dir())
```

### 2.4.9 Comprehension scope and the loop variable leak

In Python 3 comprehension variables do not leak. A walrus target inside a comprehension, however, binds in the enclosing scope. In a class body, comprehensions cannot see class-level names (except the outermost iterable).

**Example 2.4.9.1: Leak and no-leak**

```python
x = "outer"
l = [x for x in range(3)]
print(x)
r = [(last := v) for v in range(3)]
print(last)
```

**Output:**

```text
outer
2
```

**Example 2.4.9.2: Class-body gotcha**

```python
class C:
    base = 10
    try:
        vals = [base + i for i in range(3)]
    except NameError as e:
        print("NameError:", e)
    vals2 = [i + 1 for i in range(base)]
print(C.vals2[:3])
```

**Output:**

```text
NameError: name 'base' is not defined
[1, 2, 3]
```

#### Practice 2.4.9

**2.4.9-Q1 BASIC**

```python
x = 5; [x for x in range(2)]; print(x)
```

**2.4.9-Q2 MID**

```python
[w := i for i in range(3)]; print(w)
```

### 2.4.10 Closures: first look

A closure is an inner function that remembers variables from its enclosing scope. It captures the VARIABLE, not the value at definition time (late binding), which surprises people in loops.

**Example 2.4.10.1: Late binding**

```python
fs = [lambda: i for i in range(3)]
print([f() for f in fs])
```

**Output:**

```text
[2, 2, 2]
```

**Example 2.4.10.2: Fix with a default argument**

```python
fs = [lambda i=i: i for i in range(3)]
print([f() for f in fs])
```

**Output:**

```text
[0, 1, 2]
```

**Example 2.4.10.3: Fix with a factory**

```python
def make(i):
    return lambda: i
print([make(i)() for i in range(3)])
```

**Output:**

```text
[0, 1, 2]
```

**Example 2.4.10.4: Inspect the captured variable**

```python
def outer():
    v = 7
    return lambda: v
f = outer()
print(f.__closure__[0].cell_contents)
```

**Output:**

```text
7
```

#### Practice 2.4.10

**2.4.10-Q1 BASIC**

```python
f = (lambda x: lambda y: x + y)(1); print(f(2))
```

**2.4.10-Q2 MID**

```python
fs = [lambda: n for n in "ab"]; print(fs[0]())
```

**2.4.10-Q3 HARD**

```python
fs = []
for i in range(2):
    fs.append(lambda: i)
i = 9
print(fs[0](), fs[1]())
```

### 2.4.11 Class scope

A class body runs like a function whose namespace becomes the class attributes. Methods do not see class-level names as plain variables; use self.name or ClassName.name.

**Example 2.4.11.1: Class attribute vs method lookup**

```python
class A:
    n = 5
    def get(self):
        try:
            return n
        except NameError:
            return "NameError, use self.n -> %d" % self.n
print(A().get())
```

**Output:**

```text
NameError, use self.n -> 5
```

**Example 2.4.11.2: Shared mutable class attribute**

```python
class B:
    items = []
a, b = B(), B()
a.items.append(1)
print(b.items, B.items)
```

**Output:**

```text
[1] [1]
```

#### Practice 2.4.11

**2.4.11-Q1 BASIC**

```python
class A:
    x = 1
print(A.x, A().x)
```

**2.4.11-Q2 MID**

```python
class A:
    x = 1
a = A(); a.x = 2
print(A.x, a.x)
```

**2.4.11-Q3 HARD**

```python
class A:
    l = []
a, b = A(), A(); a.l += [1]; print(b.l)
```

### 2.4.12 Exception variable scope

"except E as e" binds e only inside the except block; Python deletes it at the end to avoid reference cycles. Save it under another name if you need it later.

**Example 2.4.12.1: Deleted after the block**

```python
try:
    1 / 0
except ZeroDivisionError as e:
    saved = e
print("e" in dir(), type(saved).__name__)
```

**Output:**

```text
False ZeroDivisionError
```

#### Practice 2.4.12

**2.4.12-Q1 BASIC**

```python
try:
    int("x")
except ValueError as err:
    pass
print("err" in dir())
```

**2.4.12-Q2 MID**

```python
e = 5
try:
    1 / 0
except ZeroDivisionError as e:
    pass
print("e" in dir())
```

### 2.4.13 Namespaces and dir()/vars()/globals()/locals()

Every scope is a mapping from names to objects. globals() is the module dict; locals() is the function's local names (a snapshot you must not write to); vars(obj) is obj.\_\_dict\_\_; dir(obj) lists attribute names.

**Example 2.4.13.1: Inspecting**

```python
a = 1
def f(p):
    q = 2
    return sorted(locals())
print(f(0))
print("a" in globals(), globals()["a"])
class K:
    z = 1
    def __init__(self): self.w = 2
print(vars(K()), "z" in dir(K()))
```

**Output:**

```text
['p', 'q']
True 1
{'w': 2} True
```

#### Practice 2.4.13

**2.4.13-Q1 BASIC**

```python
x = 1; print("x" in globals())
```

**2.4.13-Q2 MID**

```python
def f(a, b): return sorted(locals())
print(f(1, 2))
```

**2.4.13-Q3 HARD**

```python
def f():
    x = 1
    locals()["x"] = 99
    return x
print(f())
```

### 2.4.14 Global state in competitive programming

Local variables are faster than globals in CPython, so contest solutions put code inside main(). Deep recursion needs an explicit stack or a raised recursion limit.

**Example 2.4.14.1: Timing the same loop (shape of the result, not exact numbers)**

```python
import timeit
g = 0
def with_global():
    global g
    for _ in range(100000): g += 1
def with_local():
    l = 0
    for _ in range(100000): l += 1
tg = timeit.timeit(with_global, number=20)
tl = timeit.timeit(with_local, number=20)
print("local faster:", tl < tg)
```

**Output:**

```text
local faster: True
```

#### Practice 2.4.14

**2.4.14-Q1 BASIC**

```python
import sys; print(sys.getrecursionlimit() >= 1000)
```

**2.4.14-Q2 MID**

```python
def f(n): return n if n == 0 else f(n - 1)
try:
    f(5000)
except RecursionError:
    print("RecursionError")
```

### 2.4.15 Scope mini-lab

Twelve programs. Predict, then check.

#### Practice 2.4.15

**2.4.15-Q1 BASIC**

```python
x = 1
def f(): return x + 1
print(f())
```

**2.4.15-Q2 BASIC**

```python
def f():
    y = 1
f()
print("y" in dir())
```

**2.4.15-Q3 MID**

```python
x = 1
def f():
    global x
    x = 5
f(); print(x)
```

**2.4.15-Q4 MID**

```python
def f():
    v = 1
    def g(): return v + 1
    return g()
print(f())
```

**2.4.15-Q5 MID**

```python
a = 5
def f(a=a): return a
a = 6
print(f())
```

**2.4.15-Q6 HARD**

```python
def f():
    return [i for i in range(2)], "i" in dir()
print(f())
```

**2.4.15-Q7 HARD**

```python
x = 0
def f():
    x = 1
    def g():
        nonlocal x
        x += 1
        return x
    return g()
print(f(), x)
```

**2.4.15-Q8 HARD**

```python
def f():
    try:
        return z
    except NameError:
        return "NameError"
z = 1
print(f())
```

**2.4.15-Q9 TRAP**

```python
def f(l=[]):
    l.append(1)
    return l
f(); print(f())
```

**2.4.15-Q10 TRAP**

```python
fs = [lambda x=x: x for x in range(3)]
print([f() for f in fs])
```

**2.4.15-Q11 TRAP**

```python
n = 1
def f():
    n = n + 1
try:
    f()
except Exception as e:
    print(type(e).__name__)
```

**2.4.15-Q12 TRAP**

```python
def f():
    a = 1
    def g():
        return a
    a = 2
    return g()
print(f())
```

---

## Section 2.5 Mutability and Identity

### 2.5.1 Mutable vs immutable (contrast table)

An immutable object cannot change its value after creation: int, float, complex, bool, str, bytes, tuple, frozenset, range, None. A mutable object can: list, dict, set, bytearray, and most user-defined instances. "Changing" an immutable value means creating a new object and rebinding the name.

Why it matters: dictionary keys and set members must be hashable (effectively immutable); function arguments of mutable types can be changed by the callee; immutable objects can be safely shared and interned.

**Example 2.5.1.1: Proof table: try to modify each type**

```python
tests = [
 ("int",   lambda: (lambda x: x.__setattr__("a", 1))(5)),
 ("str",   lambda: "abc".__setitem__(0, "x")),
 ("tuple", lambda: (1, 2).__setitem__(0, 9)),
 ("bytes", lambda: b"ab".__setitem__(0, 1)),
 ("list",  lambda: [1, 2].__setitem__(0, 9)),
 ("dict",  lambda: {}.__setitem__("k", 1)),
 ("set",   lambda: {1}.add(2)),
 ("bytearray", lambda: bytearray(b"ab").__setitem__(0, 1)),
]
for name, f in tests:
    try:
        f(); print(f"{name:10} mutable")
    except (TypeError, AttributeError) as e:
        print(f"{name:10} immutable ({type(e).__name__})")
```

**Output:**

```text
int        immutable (AttributeError)
str        immutable (AttributeError)
tuple      immutable (AttributeError)
bytes      immutable (AttributeError)
list       mutable
dict       mutable
set        mutable
bytearray  mutable
```
# Python Mutable vs Immutable Objects

This explanation explores one important Python concept:

**Mutable vs Immutable objects**

In simple language:

-   **Mutable:** An object whose contents you can change after creating
    it.
-   **Immutable:** An object whose contents you cannot change after
    creating it.

------------------------------------------------------------------------

## 1. First, understand the big picture

The code creates a collection of tests:

``` python
tests = [
    ("int", lambda: ...),
    ("str", lambda: ...),
    ("tuple", lambda: ...),
]
```

Each test contains two things:

1.  The name of a Python data type.
2.  A small function that tries to modify an object of that type.

For example:

``` python
("list", lambda: [1, 2].__setitem__(0, 9))
```

This means:

"Take a list and try to change its first element to `9`."

## 2. What is `lambda`?

A lambda is simply a small function written in one line.

**Normal function:**

``` python
def add():
    return 10 + 20
```

**Lambda function:**

``` python
add = lambda: 10 + 20
```

Both return `30` when called.

So:

``` python
lambda: [1, 2].__setitem__(0, 9)
```

means:

"Create a function that, when called, tries to change the first element
of `[1, 2]` to `9`."

Notice that it doesn't execute immediately. It executes when we call
that function.

## 3. What is `__setitem__`?

This looks scary, but it is actually quite simple.

You normally write:

``` python
my_list = [1, 2]
my_list[0] = 9
```

Python provides a special method called `__setitem__` for this kind of
item assignment:

``` python
my_list.__setitem__(0, 9)
```

Both mean:

**Change the element at index `0` to `9`.**

So whenever you see:

``` python
.__setitem__(0, 9)
```

Think:

``` python
[0] = 9
```

One more thing:

-   `__setitem__` changes an item at a particular position.
-   `add()` adds an element to a set.
-   `__setattr__` attempts to set an object's attribute.

These are different operations.

------------------------------------------------------------------------

## 4. Now let's examine every test

### Test 1: Integer

``` python
("int", lambda: (lambda x: x.__setattr__("a", 1))(5))
```

This is a little unusual.

The inner lambda receives `5` as `x`, then attempts to attach an
attribute named `a` to that integer.

Integers do not allow arbitrary new attributes, so this attempt raises
an `AttributeError`.

**Result: Immutable.**

### Test 2: String

``` python
("str", lambda: "abc".__setitem__(0, "x"))
```

The intention is equivalent to trying:

``` python
text = "abc"
text[0] = "x"
```

Can we change the first character of an existing string this way?

No. Strings are immutable.

In this particular test, Python raises `AttributeError` because strings
do not provide `__setitem__`.

**Result: Immutable.**

### Test 3: Tuple

``` python
("tuple", lambda: (1, 2).__setitem__(0, 9))
```

The intention is equivalent to:

``` python
numbers = (1, 2)
numbers[0] = 9
```

Tuples do not allow modification of their elements.

In this particular test, Python raises `AttributeError` because tuples
do not provide `__setitem__`.

**Result: Immutable.**

### Test 4: Bytes

``` python
("bytes", lambda: b"ab".__setitem__(0, 1))
```

`bytes` represents an immutable sequence of byte values.

The intention is equivalent to:

``` python
data = b"ab"
data[0] = 1
```

You cannot modify an existing `bytes` object.

In this particular test, Python raises `AttributeError` because `bytes`
does not provide `__setitem__`.

**Result: Immutable.**

### Test 5: List

``` python
("list", lambda: [1, 2].__setitem__(0, 9))
```

Equivalent:

``` python
numbers = [1, 2]
numbers[0] = 9
```

Now the list becomes:

``` python
[9, 2]
```

Lists allow modification.

**Result: Mutable.**

### Test 6: Dictionary

``` python
("dict", lambda: {}.__setitem__("k", 1))
```

Equivalent:

``` python
data = {}
data["k"] = 1
```

Now the dictionary becomes:

``` python
{"k": 1}
```

Dictionaries allow adding and modifying key-value pairs.

**Result: Mutable.**

### Test 7: Set

``` python
("set", lambda: {1}.add(2))
```

Equivalent:

``` python
numbers = {1}
numbers.add(2)

print(numbers)
```

Output:

``` python
{1, 2}
```

Sets allow adding and removing elements.

**Result: Mutable.**

### Test 8: Bytearray

``` python
("bytearray", lambda: bytearray(b"ab").__setitem__(0, 1))
```

Equivalent:

``` python
data = bytearray(b"ab")
data[0] = 1
```

Unlike `bytes`, `bytearray` allows modification.

**Result: Mutable.**

------------------------------------------------------------------------

## 5. Now understand the loop

This is the part that runs all eight tests.

``` python
for name, f in tests:
```

Remember each item looks like this:

``` python
("list", lambda: [1, 2].__setitem__(0, 9))
```

Python unpacks it:

-   `name` receives `"list"`.
-   `f` receives the lambda function.

Now:

``` python
try:
    f()
    print(f"{name:10} mutable")
```

`f()` executes the test.

If it succeeds, Python prints `mutable`.

But what if it fails?

``` python
except (TypeError, AttributeError) as e:
    print(f"{name:10} immutable ({type(e).__name__})")
```

Python catches either a `TypeError` or an `AttributeError` and prints
`immutable` along with the error type.

A small formatting detail:

``` python
{name:10}
```

means reserve 10 character spaces for the name so the output lines up
neatly.

And:

``` python
type(e).__name__
```

gets the error class name, such as `AttributeError` or `TypeError`.

## 6. Final summary

  Data type     Mutable or immutable?
  ------------- -----------------------
  `int`         Immutable
  `str`         Immutable
  `tuple`       Immutable
  `bytes`       Immutable
  `list`        Mutable
  `dict`        Mutable
  `set`         Mutable
  `bytearray`   Mutable

### Mutable

`list`, `dict`, `set`, `bytearray`

Their contents can be changed after creation.

### Immutable

`int`, `str`, `tuple`, `bytes`

Their contents cannot be changed after creation.

------------------------------------------------------------------------

## 7. Test your understanding: Object references

Consider:

``` python
x = [10, 20, 30]
y = x

y[0] = 999

print(x)
```

What will Python print?

The answer is:

``` python
[999, 20, 30]
```

Why?

Because `y = x` does not create a new list. Both names refer to the
**same list**.

So changing the list through `y` also changes what you see through `x`.

This connects mutability with Python's object references, which is the
next important piece of the puzzle.

------------------------------------------------------------------------

## Important note about the original test

The test uses different operations for different types:

-   `__setattr__` for the integer test.
-   `__setitem__` for strings, tuples, bytes, lists, dictionaries, and
    bytearrays.
-   `add()` for the set test.

For the immutable string, tuple, and bytes tests, the specific error is
`AttributeError` because those objects do not have a `__setitem__`
method. The tests still demonstrate that these objects cannot be
modified in the attempted way.

Also, each lambda creates or uses a fresh object during its test. The
code is checking whether the attempted operation succeeds; it is not
comparing two variables that refer to the same object.
# Practical Applications of `setattr()` and `lambda` in Python

Let's understand where `setattr()` and `lambda` are useful in real
Python programs.

------------------------------------------------------------------------

## 1. `setattr()` --- setting an attribute dynamically

Normally, we create an object's attributes directly:

``` python
class Student:
    pass

s = Student()

s.name = "Sakshi"
s.age = 20
s.course = "Data Science"
```

Here, we write each attribute name ourselves.

But what if the information comes from a dictionary, and we don't know
all the keys in advance?

We can use `setattr()`.

### Example: creating object attributes from a dictionary

``` python
class Student:
    pass

s = Student()

student_data = {
    "name": "Sakshi",
    "age": 20,
    "course": "Data Science",
    "marks": 95
}

for key, value in student_data.items():
    setattr(s, key, value)
```

### What happens?

The dictionary contains key-value pairs:

``` text
student_data
    |
    +-- "name"   -> "Sakshi"
    +-- "age"    -> 20
    +-- "course" -> "Data Science"
    +-- "marks"  -> 95
```

The loop takes one pair at a time.

For example, on the first iteration:

``` python
key = "name"
value = "Sakshi"

setattr(s, key, value)
```

This is equivalent to:

``` python
s.name = "Sakshi"
```

On another iteration:

``` python
key = "age"
value = 20

setattr(s, key, value)
```

This is equivalent to:

``` python
s.age = 20
```

After the loop, the object has these attributes:

``` python
print(s.name)    # Sakshi
print(s.age)     # 20
print(s.course)  # Data Science
print(s.marks)   # 95
```

**Main idea:** `setattr(object, attribute_name, value)` lets us set an
attribute when its name is stored in a variable.

------------------------------------------------------------------------

## 2. `lambda` --- a small function written in one line

A normal function:

``` python
def is_passed(marks):
    return marks >= 40
```

The same function using `lambda`:

``` python
is_passed = lambda marks: marks >= 40
```

Both can be called like this:

``` python
print(is_passed(75))  # True
print(is_passed(25))  # False
```

A lambda function has this general structure:

``` python
lambda parameters: expression
```

-   `lambda` starts the function.
-   `parameters` are the inputs.
-   The expression is evaluated and its result is returned
    automatically.

A lambda is useful when a small function is needed briefly, especially
when passing a function to another function.

------------------------------------------------------------------------

## 3. Practical example: filtering marks

Suppose we have students' marks:

``` python
marks = [45, 90, 67, 32, 88, 95, 51]
```

We want to keep only marks greater than 60.

We can use `filter()` with a lambda:

``` python
result = list(filter(lambda x: x > 60, marks))

print(result)
```

Output:

``` text
[90, 67, 88, 95]
```

### Understand the execution

The expression:

``` python
lambda x: x > 60
```

is a function. It receives one value and checks whether that value is
greater than 60.

`filter()` gives each item from `marks` to this function.

``` text
45  -> 45 > 60? -> False -> rejected
90  -> 90 > 60? -> True  -> kept
67  -> 67 > 60? -> True  -> kept
32  -> 32 > 60? -> False -> rejected
88  -> 88 > 60? -> True  -> kept
95  -> 95 > 60? -> True  -> kept
51  -> 51 > 60? -> False -> rejected
```

`filter()` produces the items for which the function returns `True`.
`list()` converts that result into a list.

------------------------------------------------------------------------

## 4. Using `setattr()` and `lambda` together

Let's combine both ideas.

``` python
class Student:
    pass

s = Student()

data = {
    "name": "Sakshi",
    "marks": 85,
    "attendance": 90
}

# Add dictionary values as object attributes
for key, value in data.items():
    setattr(s, key, value)

# Create a small function to check whether the student passed
has_passed = lambda student: student.marks >= 40

print(s.name)
print(has_passed(s))
```

Output:

``` text
Sakshi
True
```

### What happened, step by step?

**Step 1:** We created an empty `Student` class and an object named `s`.

**Step 2:** We stored student information in the dictionary `data`.

**Step 3:** The loop used `setattr()` to add the dictionary information
to `s`.

The object now has:

``` text
s
|
+-- name       = "Sakshi"
+-- marks      = 85
+-- attendance = 90
```

**Step 4:** We created this lambda function:

``` python
has_passed = lambda student: student.marks >= 40
```

It accepts a student object, reads its `marks` attribute, and checks
whether the marks are at least 40.

**Step 5:** We called it:

``` python
has_passed(s)
```

Since `s.marks` is `85`, the expression `85 >= 40` is `True`.

------------------------------------------------------------------------

## 5. Important distinction: `setattr()` versus `__setattr__()`

These are related, but they are written differently.

``` python
class Student:
    pass

s = Student()

s.name = "Sakshi"
setattr(s, "name", "Sakshi")
s.__setattr__("name", "Sakshi")
```

All three lines set the object's `name` attribute in this simple
example.

-   `s.name = "Sakshi"` is the usual attribute-assignment syntax.
-   `setattr(s, "name", "Sakshi")` is the built-in function.
-   `s.__setattr__("name", "Sakshi")` directly calls the special method.

`setattr()` is generally the clearest choice when the attribute name is
stored in a variable.

------------------------------------------------------------------------

## 6. When are these useful?

  -----------------------------------------------------------------------
  Tool                                Useful when...
  ----------------------------------- -----------------------------------
  `setattr()`                         Attribute names come from data,
                                      dictionaries, or configuration

  `lambda`                            You need a short function for a
                                      small operation

  `filter()` + `lambda`               You want to select items that
                                      satisfy a condition

  `setattr()` + loop                  You want to populate an object's
                                      attributes from many key-value
                                      pairs
  -----------------------------------------------------------------------

These tools are useful, but they are not compulsory. A normal `def`
function and direct attribute assignment are often clearer when the
logic is larger or used repeatedly.

------------------------------------------------------------------------

## 7. Tiny practice questions

Try answering these before looking up the concepts again.

**Question 1**

``` python
class Book:
    pass

b = Book()
setattr(b, "title", "Python Basics")

print(b.title)
```

What will be printed?

**Question 2**

``` python
double = lambda x: x * 2
print(double(7))
```

What will be printed?

**Question 3**

``` python
numbers = [2, 5, 8, 11]
answer = list(filter(lambda x: x % 2 == 0, numbers))
print(answer)
```

Which numbers will remain?

------------------------------------------------------------------------

## Final takeaway

-   `setattr()` sets an object's attribute using a name that can be
    stored in a variable.
-   `lambda` creates a small anonymous function.
-   `filter()` can use a function to decide which items to keep.
-   You can combine these tools, but choose the clearest approach for
    the problem.


**Example 2.5.1.2: Hashability follows mutability**

```python
for obj in [1, "a", (1, 2), frozenset({1}), [1], {1}, {"a": 1}]:
    try:
        hash(obj); h = "hashable"
    except TypeError:
        h = "unhashable"
    print(type(obj).__name__, h)
```

**Output:**

```text
int hashable
str hashable
tuple hashable
frozenset hashable
list unhashable
set unhashable
dict unhashable
```
# Python Hashability: Complete Beginner-to-Advanced Guide

## Example 2.5.1.2 --- Hashability and Mutability

Let's study this example carefully:

``` python
for obj in [1, "a", (1, 2), frozenset({1}), [1], {1}, {"a": 1}]:
    try:
        hash(obj)
        h = "hashable"
    except TypeError:
        h = "unhashable"

    print(type(obj).__name__, h)
```

Expected output:

``` text
int hashable
str hashable
tuple hashable
frozenset hashable
list unhashable
set unhashable
dict unhashable
```

The important question is: **Why can Python calculate a hash for some
objects but not others?**

To understand that, we need to understand hash values, hashability,
mutability, equality, dictionaries, and sets.

------------------------------------------------------------------------

# 1. First: What is a hash?

A hash is an integer calculated from an object by Python's hashing
mechanism.

Try:

``` python
print(hash(10))
print(hash("hello"))
print(hash((1, 2)))
```

You will see integer values. The exact values can vary between Python
processes, especially for strings.

For example, you might see something like:

``` text
10
-123456789012345678
123456789
```

These numbers are only illustrative. Your output may be different.

Conceptually:

``` text
              OBJECT
                 |
                 v
             hash(obj)
                 |
                 v
          INTEGER HASH VALUE
```

For example:

``` python
hash("apple")
```

asks Python to calculate the hash value of the string `"apple"`.

**Important:** A hash is not the object's identity, memory address, or a
unique ID.

Two different objects can have the same hash. This is called a **hash
collision**.

------------------------------------------------------------------------

# 2. What does hashable mean?

An object is hashable if it:

1.  Has a hash value that remains stable during its lifetime.
2.  Can be compared for equality.
3.  Follows the rule that equal objects must have equal hash values.

The important equality rule is:

``` text
If a == b is True,
then hash(a) == hash(b) must also be True.
```

The reverse is NOT guaranteed:

``` text
hash(a) == hash(b)
```

does not prove that:

``` text
a == b
```

Two unequal objects can have the same hash.

### A small example

``` python
a = 10
b = 10

print(a == b)
print(hash(a) == hash(b))
```

Output:

``` text
True
True
```

Both objects compare equal, so their hash values must be equal.


------------------------------------------------------------------------

# 3. What is mutability?

Mutability means whether an object can be changed after it has been
created.

## Mutable objects

A mutable object can have its contents changed.

Example:

``` python
numbers = [10, 20, 30]

numbers[0] = 999

print(numbers)
```

Output:

``` text
[999, 20, 30]
```

The same list object now contains different data.

Other common mutable built-in types:

-   `list`
-   `dict`
-   `set`
-   `bytearray`

## Immutable objects

An immutable object cannot have its value changed after creation.

Example:

``` python
name = "Python"

# This would fail:
# name[0] = "J"
```

You cannot replace one character inside the existing string.

Other common immutable built-in types:

-   `int`
-   `float`
-   `bool`
-   `str`
-   `tuple`
-   `bytes`
-   `frozenset`

Be careful: immutable does not mean that a variable can never refer to
another object.

``` python
name = "Python"
name = "Java"

print(name)
```

Output:

``` text
Java
```

This is allowed because the variable `name` is now referring to a
different string. The original string was not modified.

------------------------------------------------------------------------

# 4. The connection between mutability and hashability

Why are mutable built-in containers such as lists, dictionaries, and
sets unhashable?

Imagine that Python allowed a list to be used as a dictionary key.

``` python
my_list = [10, 20]

data = {
    my_list: "student"
}
```

This is not allowed:

``` text
TypeError: unhashable type: 'list'
```

Why?

A dictionary uses hashes to help locate keys. If a key's hash changed
after insertion, Python could look in the wrong place when trying to
find that key.

Consider this hypothetical situation:

``` text
STEP 1: Insert a mutable list as a dictionary key
        List = [10, 20]
        Hash = H1

STEP 2: Change the list
        List = [99, 20]
        Hash might now be H2

STEP 3: Search for the key
        Dictionary may look in the location associated
        with H2, although the entry was stored using H1.
```

That would break the dictionary's lookup behavior.

Therefore, Python's built-in `list`, `dict`, and `set` types are
unhashable.

**Important correction to the shortcut:** Hashability does not simply
mean "immutable = hashable and mutable = unhashable." It is a little
more nuanced. The hash must remain stable, and equality and hashing must
agree.

------------------------------------------------------------------------

# 5. Understand every object in Example 2.5.1.2

Let's inspect the original list one item at a time.

``` python
[
    1,
    "a",
    (1, 2),
    frozenset({1}),
    [1],
    {1},
    {"a": 1}
]
```

## Object 1: `1` --- integer

``` python
obj = 1

print(type(obj).__name__)
print(hash(obj))
```

-   Type: `int`
-   Mutable or immutable: immutable
-   Hashable: yes

An integer's value cannot be changed in place.

``` python
x = 10
# x is not an object whose numeric value can be edited in place.
```

Therefore, Python supports hashing integers.

## Object 2: `"a"` --- string

``` python
obj = "a"

print(type(obj).__name__)
print(hash(obj))
```

-   Type: `str`
-   Mutable or immutable: immutable
-   Hashable: yes

Strings cannot be modified in place.

``` python
word = "cat"

# This fails:
# word[0] = "b"
```

This makes strings suitable as dictionary keys:

``` python
student = {
    "name": "Sakshi",
    "course": "Python",
    "marks": 95
}
```

Here, `"name"`, `"course"`, and `"marks"` are string keys.

## Object 3: `(1, 2)` --- tuple

``` python
obj = (1, 2)

print(type(obj).__name__)
print(hash(obj))
```

-   Type: `tuple`
-   Mutable or immutable: immutable
-   Hashable: yes, in this example

A tuple cannot have its elements replaced:

``` python
numbers = (1, 2)

# This fails:
# numbers[0] = 100
```

However, there is an important rule:

**A tuple is hashable only if all of its elements are hashable.**

Compare:

``` python
print(hash((1, 2)))       # Works
print(hash((1, "abc")))   # Works
```

But:

``` python
hash((1, [2, 3]))         # TypeError
```

Why?

The tuple contains a list, and lists are unhashable.

Visualize it:

``` text
Tuple: (1, 2)
       |  |
       |  +---- int  -> hashable
       +------- int  -> hashable

All elements are hashable
          |
          v
    Tuple is hashable
```

Now:

``` text
Tuple: (1, [2, 3])
       |    |
       |    +---- list -> unhashable
       +--------- int  -> hashable

One element is unhashable
          |
          v
    Tuple is unhashable
```

This is a very important interview and practical-programming concept.

## Object 4: `frozenset({1})` --- frozen set
# frozenset, explained from zero

I'll go one small step at a time, and I won't use a word until I've explained it.

## Step 1: What is a set?

A **set** is a bag of items where:
- each item appears only once (no duplicates)
- the order doesn't matter

```python
fruits = {"apple", "banana", "apple"}
print(fruits)    # {'apple', 'banana'}  (the second apple vanished)
```

## Step 2: Mutable and immutable

- **Mutable** means you can change it after creating it.
- **Immutable** means you cannot. To "change" it, you must make a new one.

Think of a **whiteboard** (mutable: erase and rewrite) and a **printed photo** (immutable: you can't change it, only print a new one).

A normal set is a whiteboard:

```python
numbers = {1, 2, 3}
numbers.add(4)
print(numbers)    # {1, 2, 3, 4}
```

## Step 3: What is a frozenset?

A **frozenset** is a set that has been frozen. You create it once, and then it can never change.

```python
numbers = frozenset({1, 2, 3})
print(numbers)    # frozenset({1, 2, 3})
numbers.add(4)    # ERROR: AttributeError
```

It fails because a frozenset simply doesn't have an `add` method. It has no `remove` or `clear` either.

What a frozenset **can** do is everything that only *looks* at it, or that makes a *new* one:

```python
a = frozenset({1, 2, 3})
print(2 in a)                # True
print(len(a))                # 3
print(a | frozenset({9}))    # frozenset({1, 2, 3, 9})  <- a NEW frozenset
print(a)                     # frozenset({1, 2, 3})     <- the original is untouched
```

Like a set, order and duplicates don't matter:

```python
print(frozenset({1, 2}) == frozenset({2, 1}))   # True
print(frozenset([5, 5, 5]))                     # frozenset({5})
```

## Step 4: Why would anyone want that?

Because Python has two places where changeable things are **not allowed**:

1. as a **dictionary key**
2. as an **item inside a set**

A normal set can't go there, but a frozenset can:

```python
data = {frozenset({1, 2}): "pair"}
print(data[frozenset({1, 2})])      # pair
print(data[frozenset({2, 1})])      # pair  (order doesn't matter)
```

Compare with a normal set:

```python
data = {{1, 2}: "pair"}   # ERROR: TypeError: unhashable type: 'set'
```

## Step 5: What does "hashable" mean?

This is the word that caused the confusion, so here it is slowly.

Python stores dictionary keys and set items using a number made from the item, called its **hash**. Think of it as a **locker number** made from the item's contents. To find an item later, Python recomputes the locker number and goes straight to that locker.

Now imagine the item could **change** after being stored. Its contents change, so its locker number changes, and Python looks in the wrong locker and can't find it. So Python only allows items whose contents can never change. Those are called **hashable**.

- `hash(...)` is the function that gives the locker number.
- A frozenset is frozen, so its number never changes, and it is hashable.
- A normal set can change, so it is **unhashable**.

```python
obj = frozenset({1})
print(type(obj).__name__)    # frozenset
print(hash(obj))             # some big number; it is the same every time for this value
```

That is what the first example in your text shows: type `frozenset`, immutable, hashable.

## Step 6: "Hashable only when all its elements are hashable"

A frozenset is frozen, but what is *inside* it must also be unchangeable, or the locker number could still shift.

A **list** can change (`append`, etc.), so a list is unhashable. That is why you can't put a list inside a frozenset:

```python
frozenset({[1, 2]})       # ERROR: TypeError: unhashable type: 'list'
frozenset({(1, 2)})       # works: a tuple is immutable
frozenset({1, "a", 2.5})  # works: numbers and strings are immutable
```

## Step 7: Similar pairs (changeable twin and frozen twin)

| Changeable (mutable) | Frozen (immutable) | What it is |
|---|---|---|
| `set` | `frozenset` | bag of unique items |
| `list` | `tuple` | ordered row of items |
| `bytearray` | `bytes` | row of raw bytes |

`str` (text) and numbers are immutable too. The same reasoning applies to all of them: **immutable usually means hashable, mutable means unhashable**.

One catch, which is the tuple example from your text: a tuple is only hashable if everything inside it is hashable.

```python
hash((1, 2))        # works
hash((1, [2, 3]))   # ERROR: the list inside is unhashable
```

## Practice questions (with solutions)

**Warm-up**

1. What does this print?
   ```python
   print(frozenset([1, 1, 2]))
   ```
   **A:** `frozenset({1, 2})` (duplicates removed).

2. Which line fails?
   ```python
   a = frozenset({1, 2})
   a.add(3)
   ```
   **A:** `a.add(3)`. A frozenset has no `add`.

3. Is `{1, 2}` mutable or immutable? What about `frozenset({1, 2})`? **A:** The first is mutable, the second immutable.

**Medium**

4. What does this print?
   ```python
   a = frozenset({1, 2})
   b = a | {3}
   print(a, b)
   ```
   **A:** `frozenset({1, 2}) frozenset({1, 2, 3})`. The original is unchanged, and the result is a new frozenset.

5. True or False?
   ```python
   print(frozenset({1, 2}) == frozenset({2, 1}))
   ```
   **A:** `True`. Order doesn't matter.

6. What does this print?
   ```python
   d = {frozenset({"a", "b"}): 10}
   print(d[frozenset({"b", "a"})])
   ```
   **A:** `10`.

7. Which of these work?
   ```python
   frozenset({1, 2})
   frozenset({(1, 2)})
   frozenset({[1, 2]})
   ```
   **A:** The first two work. The third fails because a list is unhashable.

**Harder**

8. What does this print?
   ```python
   print(len(frozenset("hello")))
   ```
   **A:** `4`. The letters are h, e, l, o (the repeated `l` counts once).

9. Does this work? Explain.
   ```python
   s = {frozenset({1}), frozenset({1}), frozenset({2})}
   print(len(s))
   ```
   **A:** It works and prints `2`. A frozenset is allowed inside a set, and the two identical ones collapse into one.

10. Does this work?
    ```python
    s = {{1}, {2}}
    ```
    **A:** No: `TypeError: unhashable type: 'set'`. A normal set can't be an item of a set. Use `{frozenset({1}), frozenset({2})}` instead.

**Tricky**

11. Does this work?
    ```python
    hash(frozenset({(1, 2), (3, 4)}))
    ```
    **A:** Yes. Both items are tuples of numbers, so everything inside is hashable.

12. Does this work?
    ```python
    hash(frozenset({(1, [2])}))
    ```
    **A:** No. The tuple contains a list, so the tuple is unhashable, so the frozenset can't be built.

13. Is this `True` or `False`?
    ```python
    print({1, 2} == frozenset({1, 2}))
    ```
    **A:** `True`. A set and a frozenset with the same items are equal. They are different types but hold the same things.

14. In one sentence: why does Python not allow a normal set as a dictionary key? **A:** Because it can change, its locker number (hash) could change, and Python could never find it again.

``` python
obj = frozenset({1})

print(type(obj).__name__)
print(hash(obj))
```

-   Type: `frozenset`
-   Mutable or immutable: immutable
-   Hashable: yes, in this example

A normal set is mutable:

``` python
numbers = {1, 2, 3}
numbers.add(4)

print(numbers)
```

A `frozenset` is an immutable version of a set:

``` python
numbers = frozenset({1, 2, 3})

# This fails:
# numbers.add(4)
```

It can be used as a dictionary key or as an element inside another set:

``` python
data = {
    frozenset({1, 2}): "pair"
}

print(data[frozenset({1, 2})])
```

Output:

``` text
pair
```

Like tuples, a `frozenset` is hashable only when all its elements are
hashable.

``` python
hash(frozenset({1, 2, 3}))  # Works
```

A `frozenset` cannot contain a list in the first place because a list is
unhashable.

## Object 5: `[1]` --- list

``` python
obj = [1]

print(type(obj).__name__)
print(hash(obj))
```

This raises:

``` text
TypeError: unhashable type: 'list'
```

-   Type: `list`
-   Mutable or immutable: mutable
-   Hashable: no

A list can change:

``` python
numbers = [1, 2, 3]
numbers.append(4)

print(numbers)
```

Output:

``` text
[1, 2, 3, 4]
```

Since a list is mutable, Python does not give the built-in list type a
hash.

Lists are therefore not allowed as dictionary keys or set elements.

## Object 6: `{1}` --- set

``` python
obj = {1}

print(type(obj).__name__)
print(hash(obj))
```

This raises:

``` text
TypeError: unhashable type: 'set'
```

-   Type: `set`
-   Mutable or immutable: mutable
-   Hashable: no

A set can be modified:

``` python
numbers = {1, 2, 3}
numbers.add(4)

print(numbers)
```

Output:

``` text
{1, 2, 3, 4}
```

A normal set cannot be used as a dictionary key or as an element of
another set.

But a `frozenset` can.

## Object 7: `{"a": 1}` --- dictionary

``` python
obj = {"a": 1}

print(type(obj).__name__)
print(hash(obj))
```

This raises:

``` text
TypeError: unhashable type: 'dict'
```

-   Type: `dict`
-   Mutable or immutable: mutable
-   Hashable: no

A dictionary can be changed:

``` python
student = {"name": "Sakshi"}

student["marks"] = 95

print(student)
```

Output:

``` text
{'name': 'Sakshi', 'marks': 95}
```

A dictionary itself cannot be a key in another dictionary or an element
of a set.

However, its keys must be hashable.

------------------------------------------------------------------------

# 6. Complete comparison table

  Object             Type            Mutable?   Hashable?
  ------------------ ------------- ---------- -----------
  `1`                `int`                 No         Yes
  `"a"`              `str`                 No         Yes
  `(1, 2)`           `tuple`               No         Yes
  `frozenset({1})`   `frozenset`           No         Yes
  `[1]`              `list`               Yes          No
  `{1}`              `set`                Yes          No
  `{"a": 1}`         `dict`               Yes          No

Remember the important exception:

  Object                  Hashable? Reason
  --------------------- ----------- -----------------------------
  `(1, 2)`                      Yes Both elements are hashable
  `(1, [2, 3])`                  No Contains an unhashable list
  `frozenset({1, 2})`           Yes Its elements are hashable

------------------------------------------------------------------------

# 7. Why do dictionaries need hashable keys?

This is one of the most important practical applications of hashability.

Consider:

``` python
student = {
    "name": "Sakshi",
    "age": 20,
    "marks": 95
}
```

The dictionary stores key-value pairs.

``` text
DICTIONARY
    |
    +---- "name"  -> "Sakshi"
    |
    +---- "age"   -> 20
    |
    +---- "marks" -> 95
```

When Python handles a key, it uses the key's hash as part of the lookup
process.

For example:

``` python
student["name"]
```

Python uses the hash of `"name"` to help find the corresponding entry.

Try:

``` python
print(hash("name"))
```

A dictionary key must be hashable so that its hash remains stable while
it is being used as a key.

### Valid dictionary keys

``` python
data = {
    1: "integer key",
    "name": "string key",
    (1, 2): "tuple key",
    frozenset({3, 4}): "frozenset key"
}
```

### Invalid dictionary keys

``` python
# Each of these would raise TypeError:

# {[1, 2]: "list key"}
# {{1, 2}: "set key"}
# {{"name": "Sakshi"}: "dictionary key"}
```

------------------------------------------------------------------------

# 8. Why do sets need hashable elements?

A set stores unique elements.

``` python
numbers = {10, 20, 30}

numbers.add(40)

print(numbers)
```

Sets use hashing to help organize and check their elements.

Therefore, set elements must be hashable.

Valid:

``` python
items = {
    10,
    "Python",
    (1, 2),
    frozenset({3, 4})
}
```

Invalid:

``` python
# This raises TypeError:
# items = {[1, 2], [3, 4]}
```

### Want to store a group of values inside a set?

Use a tuple if the values should be an ordered, immutable group:

``` python
points = {
    (2, 5),
    (4, 8),
    (7, 9)
}
```

Or use `frozenset` if you need an immutable set:

``` python
groups = {
    frozenset({1, 2}),
    frozenset({3, 4})
}
```

------------------------------------------------------------------------

# 9. Hash collisions: hashes are not unique

A common misunderstanding is:

"If two objects have the same hash, they must be the same object."

That is incorrect.

A hash collision happens when two unequal objects produce the same hash
value.

``` text
Object A -----> Hash value 123
Object B -----> Hash value 123

A and B may still be unequal.
```

Python dictionaries handle collisions by checking equality as well as
using hashes.

The required rule is:

``` python
a == b  # True
```

must imply:

``` python
hash(a) == hash(b)
```

But equal hash values do not imply equal objects.

Never use a hash value as a unique identifier for an object.

------------------------------------------------------------------------

# 10. A practical application: finding duplicate values

Hashable values can be stored in a set, which is useful for removing
duplicates.

``` python
names = ["Asha", "Ravi", "Asha", "Neha", "Ravi"]

unique_names = set(names)

print(unique_names)
```

Possible output:

``` text
{'Asha', 'Ravi', 'Neha'}
```

The order may vary because sets are unordered collections.

Why does this work?

-   Strings are hashable.
-   A set can store hashable elements.
-   Adding an already-present equal element does not create a second
    copy.

For a list of hashable values, a set is a convenient way to obtain
unique values.

------------------------------------------------------------------------

# 11. A practical application: counting values with a dictionary

A dictionary can count how often each item appears.

``` python
words = ["python", "java", "python", "c", "java", "python"]

counts = {}

for word in words:
    if word in counts:
        counts[word] += 1
    else:
        counts[word] = 1

print(counts)
```

Output:

``` text
{'python': 3, 'java': 2, 'c': 1}
```

The words are strings, so they are hashable and can be used as
dictionary keys.

This pattern is useful in:

-   Counting words in text
-   Counting categories in a dataset
-   Frequency analysis
-   Data cleaning
-   Summarizing repeated values

------------------------------------------------------------------------

# 12. A practical application: using tuples as dictionary keys

Suppose you want to store a value for each grid coordinate.

A coordinate contains two values: row and column.

``` python
grid_values = {
    (0, 0): "Start",
    (0, 1): "Empty",
    (1, 0): "Obstacle",
    (1, 1): "Goal"
}

print(grid_values[(1, 1)])
```

Output:

``` text
Goal
```

Why can `(1, 1)` be a key?

Because it is a tuple containing two hashable integers.

This is useful in:

-   Grid-based programs
-   Game development
-   Graph algorithms
-   Caching results based on multiple inputs
-   Storing coordinate-based information

A list such as `[1, 1]` cannot be used as the key. A tuple `(1, 1)` can.

------------------------------------------------------------------------

# 13. Important advanced exception: a mutable object can be hashable

Do not memorize this incorrect rule:

``` text
Mutable   = always unhashable
Immutable = always hashable
```
# Hash collisions: same hash, different objects

## The idea

A **hash** is a locker number made from an object. A **hash collision** is when two objects get the **same locker number** but are **not equal**.

```
Object A -----> Hash value 123
Object B -----> Hash value 123

A == B  ?  False   (they are still different objects)
```

The rule Python requires is one-directional:

```
a == b   ->  hash(a) == hash(b)     (must always be true)
hash(a) == hash(b)   ->  a == b     (NOT guaranteed, this is a collision)
```

---

## Example 1: A real collision built into Python

In CPython (the standard Python), the integers `-1` and `-2` have the same hash:

```python
print(hash(-1))        # -2
print(hash(-2))        # -2
print(hash(-1) == hash(-2))   # True   <- same hash
print(-1 == -2)               # False  <- different values
```

Both are perfectly normal hashable ints, same hash, yet unequal.
(Why? `-1` is reserved internally as an error signal, so Python changes its hash to `-2`.)

And a dictionary still keeps them apart correctly:

```python
d = {-1: "minus one", -2: "minus two"}
print(len(d))      # 2
print(d[-1])       # minus one
print(d[-2])       # minus two
```

---

## Example 2: Two objects of your own class with the same hash

Here we create a `Point` class whose hash only looks at `x`. So points with the same `x` but different `y` collide.

```python
class Point:
    def __init__(self, x, y):
        self.x = x
        self.y = y

    def __eq__(self, other):
        return isinstance(other, Point) and (self.x, self.y) == (other.x, other.y)

    def __hash__(self):
        return hash(self.x)      # ignores y on purpose


a = Point(1, 2)
b = Point(1, 5)

print(hash(a) == hash(b))   # True   <- collision: same hash
print(a == b)               # False  <- unequal objects
```

Both `a` and `b` are hashable, they share a hash, and they are not equal.

### Python still handles them correctly

Python first uses the hash to pick the locker, then uses `==` to check which item in the locker is the right one:

```python
d = {a: "first", b: "second"}
print(len(d))      # 2   (two separate keys, not one)
print(d[a])        # first
print(d[b])        # second
```

---

## Example 3: The extreme case (every object collides)

A legal but terrible hash function: always return the same number.

```python
class Bad:
    def __init__(self, name):
        self.name = name

    def __eq__(self, other):
        return isinstance(other, Bad) and self.name == other.name

    def __hash__(self):
        return 1                 # everyone shares locker 1


x = Bad("x")
y = Bad("y")

print(hash(x), hash(y))     # 1 1
print(x == y)               # False

d = {x: "X", y: "Y"}
print(d[x], d[y])           # X Y   (still correct, just slower)
```

Correct results, but Python must check every item in the locker one by one, so lookups become slow. Collisions are **allowed**, but too many of them hurt performance.

---

## Example 4: The rule that cannot be broken

Equal objects **must** have equal hashes. Here is a case where that holds:

```python
print(1 == 1.0 == True)                  # True
print(hash(1), hash(1.0), hash(True))    # 1 1 1

d = {1: "a", 1.0: "b"}
print(d)                                 # {1: 'b'}  (they count as the SAME key)
```

If equal objects had different hashes, Python would look in the wrong locker and lose track of keys. That is why `__eq__` and `__hash__` must agree.

---

## Key takeaways

| Statement | True? |
|---|---|
| Equal objects must have equal hashes | Yes |
| Equal hashes means equal objects | **No** (collision) |
| Dicts and sets check `==` after matching hashes | Yes |
| Hash is safe to use as a unique ID | **No** |

> **Never use a hash value as a unique identifier for an object.** Two different objects can share the same hash. If you need a unique ID, use something designed for it, such as `id(obj)` (unique while the object is alive) or a `uuid`.

## Practice

1. Does `hash(-1) == hash(-2)` mean `-1 == -2`?
   **A:** No. It is a collision. The hashes match, the values don't.

2. If `a == b` is `True`, can `hash(a)` differ from `hash(b)`?
   **A:** No. That would break Python's rule.

3. If `hash(a) == hash(b)`, can `a == b` be `False`?
   **A:** Yes. That is exactly a hash collision.

4. Why does the dictionary in Example 2 still return the right values?
   **A:** After finding the locker by hash, Python compares the keys with `==` to pick the correct one.


That is not universally true for every Python object.

A programmer can create a custom mutable class that is hashable. But
doing so carelessly can cause serious dictionary and set lookup
problems.

For example:

``` python
class Student:
    def __init__(self, name):
        self.name = name

    def __hash__(self):
        return 100

    def __eq__(self, other):
        if not isinstance(other, Student):
            return NotImplemented
        return self.name == other.name


s = Student("Sakshi")

print(hash(s))
```

This class defines its own hash and equality behavior.

But notice the danger: the `name` attribute can be changed.

``` python
students = {s}

s.name = "Aditi"
```

Now the object's equality behavior has changed while it is stored in the
set. This can make lookup behavior surprising or unreliable.

**Best practice:** If an object's hash is based on data, do not change
that data while the object is being used as a dictionary key or set
element.

For ordinary beginner-level Python, remember that built-in lists,
dictionaries, and sets are unhashable, while common immutable built-ins
such as integers and strings are hashable.

------------------------------------------------------------------------

# 14. How to check hashability yourself

You can write a reusable function:

``` python
def check_hashability(obj):
    try:
        hash(obj)
        return True
    except TypeError:
        return False


print(check_hashability(10))
print(check_hashability("Python"))
print(check_hashability((1, 2)))
print(check_hashability([1, 2]))
```

Output:

``` text
True
True
True
False
```

Why catch `TypeError`?

Python raises `TypeError` when an object does not support hashing. The
`try` block tests it, and the `except` block handles that expected
failure.

------------------------------------------------------------------------

# 15. Understand the original code line by line

Here is the original example with clearer formatting:

``` python
objects = [
    1,
    "a",
    (1, 2),
    frozenset({1}),
    [1],
    {1},
    {"a": 1}
]

for obj in objects:

    try:
        hash(obj)
        h = "hashable"

    except TypeError:
        h = "unhashable"

    print(type(obj).__name__, h)
```

Let's understand each line.

### Line 1: Create the collection

``` python
objects = [1, "a", (1, 2), frozenset({1}), [1], {1}, {"a": 1}]
```

This is a list containing objects of different types.

### Line 2: Loop through the objects

``` python
for obj in objects:
```

Python takes one object at a time and assigns it to `obj`.

### Line 3: Try to calculate a hash

``` python
hash(obj)
```

Python attempts to calculate the object's hash.

### Line 4: If hashing succeeds

``` python
h = "hashable"
```

The object supports hashing, so we store the text `"hashable"` in `h`.

### Line 5: If hashing raises `TypeError`

``` python
except TypeError:
    h = "unhashable"
```

Python jumps to this block when hashing is unsupported.

### Line 6: Print the type name and result

``` python
print(type(obj).__name__, h)
```

Break it down:

``` python
type(obj)
```

Gets the object's type.

``` python
type(obj).__name__
```

Gets the type's name as a string.

For example:

``` python
print(type(10).__name__)       # int
print(type("hi").__name__)     # str
print(type([1, 2]).__name__)   # list
```

Finally, `print()` displays the type name and the hashability result.

------------------------------------------------------------------------

# 16. Common mistakes and misunderstandings

### Mistake 1: Thinking every tuple is hashable

Incorrect:

``` python
hash((1, [2, 3]))
```

A tuple containing an unhashable list is itself unhashable.

### Mistake 2: Thinking every immutable object must be hashable

Immutability alone does not guarantee hashability. A custom class can
define equality without providing a compatible hash method, for example.

### Mistake 3: Thinking equal hashes mean equal objects

Incorrect. Hash collisions are possible.

### Mistake 4: Thinking a dictionary's values must be hashable

No. Dictionary keys must be hashable. Values can be mutable or
unhashable.

This is valid:

``` python
data = {
    "scores": [80, 90, 95],
    "profile": {"city": "Patna"}
}
```

The keys are strings. The values are a list and a dictionary.

### Mistake 5: Thinking a set can contain a list

This fails:

``` python
# { [1, 2] }
```

But a set can contain a tuple of hashable values:

``` python
{(1, 2)}
```

------------------------------------------------------------------------

# 17. Quick revision sheet

``` text
HASHABILITY
    |
    +-- An object supports hash(obj)
    |
    +-- Its hash remains stable during its lifetime
    |
    +-- Equal objects must have equal hashes
    |
    +-- Needed for dictionary keys and set elements


COMMON HASHABLE TYPES
    int
    float
    bool
    str
    bytes
    tuple* 
    frozenset*


COMMON UNHASHABLE BUILT-IN TYPES
    list
    dict
    set
    bytearray

* A tuple is hashable only if all its elements are hashable.
* A frozenset is hashable only if all its elements are hashable.
```

## The three rules worth remembering

1.  Dictionary keys must be hashable.
2.  Set elements must be hashable.
3.  A tuple or frozenset is hashable only when all of its elements are
    hashable.

------------------------------------------------------------------------

# 18. Practice questions

Try these yourself before checking the answers.

### Question 1

Which of these are hashable?

``` python
items = [
    (1, 2, 3),
    (1, [2, 3]),
    frozenset({1, 2}),
    "hello",
    {"x": 10}
]
```

### Question 2

What happens here?

``` python
data = {}
data[[1, 2]] = "hello"
```

### Question 3

Why does this work?

``` python
data = {}
data[(1, 2)] = "hello"
```

### Question 4

What is the difference between these two?

``` python
set()
frozenset()
```

### Question 5

Is this statement true or false?

"If two objects have the same hash, they must be equal."

### Question 6

Can a dictionary contain a list as a value?

``` python
data = {
    "marks": [80, 90, 95]
}
```

------------------------------------------------------------------------

# 19. Answers to practice questions

**Answer 1**

-   `(1, 2, 3)` --- hashable
-   `(1, [2, 3])` --- unhashable
-   `frozenset({1, 2})` --- hashable
-   `"hello"` --- hashable
-   `{"x": 10}` --- unhashable

**Answer 2**

It raises `TypeError` because a list is unhashable and cannot be a
dictionary key.

**Answer 3**

It works because the tuple contains two hashable integers.

**Answer 4**

-   `set()` creates a mutable set.
-   `frozenset()` creates an immutable set.

**Answer 5**

False. Different objects can have the same hash due to hash collisions.

**Answer 6**

Yes. Dictionary values do not have to be hashable. Only dictionary keys
must be hashable.

------------------------------------------------------------------------

## Final takeaway

Hashability is the property that allows an object to participate safely
in hash-based collections such as dictionaries and sets.

Mutability is closely related to hashability because changing an
object's hash while it is being used as a key or set element would cause
problems.

But remember: **hashability is not simply another word for
immutability.** The real requirements are a stable hash and consistent
equality behavior.


#### Practice 2.5.1

**2.5.1-Q1 BASIC**

```python
s = "abc"
try:
    s[0] = "x"
except TypeError:
    print("immutable")
```

**2.5.1-Q2 MID**

```python
print(hash((1, 2)) == hash((1, 2)))
```

**2.5.1-Q3 MID**

```python
d = {}
try:
    d[[1]] = 1
except TypeError as e:
    print("TypeError")
```

**2.5.1-Q4 HARD**

```python
t = (1, [2]); t[1].append(3); print(t)
```

### 2.5.2 id() behaviour

id is stable for the object's whole life and unique among live objects. After an object is freed its id may be reused by a new object. In CPython id is the address, but that is an implementation detail.
# id(), hash() and __eq__(): what is the difference?

All three seem like "ways to tell objects apart", but each one answers a **different question**.

## The three questions

| Tool | The question it answers | Real-life version |
|---|---|---|
| `id(x)` | "Which exact object is this?" | A person's unique ID card number. Nobody else has it. |
| `hash(x)` | "Which locker should I look in?" | The PIN code of their area. Many people share one. |
| `x == y` | "Do these two count as the same thing?" | "Do these two forms describe the same person?" |

`x == y` is the same as Python calling `x.__eq__(y)`, and `hash(x)` is the same as Python calling `x.__hash__()`.

## One line each

- **`id(x)`**: returns a number for the exact object in memory. Python decides it, and you can't change it.
- **`hash(x)`**: runs `x.__hash__()`, which returns a number used to pick a locker in dicts and sets.
- **`x.__eq__(y)`**: returns True or False for "do I count as equal to y?".

---

## Part 1: A plain class (nothing overridden)

By default, Python bases everything on `id`:

```python
class Plain:
    pass

a = Plain()
b = Plain()

print(id(a) == id(b))      # False
print(a == b)              # False  (default __eq__ compares identity)
print(hash(a) == hash(b))  # False  (default __hash__ is derived from id)
```

So by default, "equal" means "the exact same object". Two separate objects are never equal.

## Part 2: Overriding `__eq__` and `__hash__`

You can change what "equal" and "hash" mean so they stop depending on `id`:

```python
class Student:
    def __init__(self, name):
        self.name = name

    def __eq__(self, other):
        return self.name == other.name

    def __hash__(self):
        return hash(self.name)

a = Student("Sakshi")
c = Student("Sakshi")

print(id(a) == id(c))      # False -> still two different objects
print(a.__eq__(c))         # True  -> your rule: same name = equal
print(hash(a) == hash(c))  # True  -> your rule: same name = same locker
```

`id` did not change, because Python controls it. Only `__eq__` and `__hash__` follow your rules.

Think of `a` and `c` as two paper forms that both say "Sakshi":
- **id says:** "These are two different forms."
- **hash says:** "Both go to the same locker."
- **== says:** "They describe the same person, so equal."

None of these contradicts the others, because they answer different questions.

## Part 3: How a set or dict uses them

To check "is Sakshi already in the set?", Python does two steps:

1. Use **hash** to jump to the right locker.
2. Use **==** to check whether anyone in that locker is the same person.

```python
s = {Student("Sakshi"), Student("Rahul"), Student("Sakshi")}
print(len(s))   # 2  (the two Sakshi students count as one)
```

`id` is not part of this. It is only used for "same exact object?" checks.

## Part 4: Two things about `id()` that surprise people

### 4a. Changing an object does NOT change its id

`id` identifies the object itself, not what is inside it. Mutating a list keeps the same object, so the id stays the same:

```python
a = [1]
i = id(a)
a.append(2)
print(a)            # [1, 2]  (the contents changed)
print(id(a) == i)   # True    (but it is still the same object)
```

Think of a person who changes clothes: the ID card number stays the same.

### 4b. Ids of temporary objects can repeat

`id` is unique only among objects that are **alive at the same time**. Once an object is destroyed, its memory can be reused by a new object, and the new one may get the same id:

```python
class T: pass

x = id(T())   # T() is created, its id is saved, then the object is destroyed immediately
y = id(T())   # a new T() is created, possibly in the same freed memory
print("ids of temporaries can repeat:", x == y)
# usually prints: ids of temporaries can repeat: True
```

Here we saved only the **number**, not the object. So after each line the `T()` object disappears, and Python may reuse the same memory spot for the next one. (This is common in CPython but not guaranteed.)

Compare with keeping both objects alive:

```python
p = T()
q = T()
print(id(p) == id(q))   # False -> both alive, so ids must differ
```

Think of ID cards: a card number is unique among **living** people. After someone leaves, their number may be given to a new person later.

**Lesson:** never store `id(obj)` and assume it identifies that object forever. It only does while the object is alive.

---

## Summary table

| | Who controls it | Can two objects share it? | Question |
|---|---|---|---|
| `id()` | Python | Never (while both are alive) | Same exact object? |
| `__hash__()` | You (default uses id) | Yes | Which locker? |
| `__eq__()` | You (default uses id) | Yes | Count as equal? |

## The only rule linking them

> If `a == b` is True, then `hash(a) == hash(b)` **must** be True.

The reverse is **not** required: the same hash does **not** mean equal objects (that is a hash collision).

## Quick practice

1. Can two live objects have the same `id()`?
   **A:** No. `id` is unique among objects that exist at the same time.

2. Can two different objects have the same `hash()`?
   **A:** Yes. That is a hash collision, and it is allowed.

3. In a plain class with no overrides, is `a == b` true for two separate objects?
   **A:** No. The default `__eq__` compares identity.

4. If you override `__eq__` to compare names, what must you do with `__hash__`?
   **A:** Make it consistent, for example `hash(self.name)`, so equal objects have equal hashes.

5. Does overriding `__eq__` change `id()`?
   **A:** No. `id` is controlled by Python only.

6. After `a = [1]` and `a.append(2)`, is `id(a)` different from before?
   **A:** No. The list is the same object, only its contents changed.

7. Why can `id(T()) == id(T())` be `True`?
   **A:** Each temporary object is destroyed right after its id is read, so the next one can reuse the same memory and get the same id. Ids are unique only among objects alive at the same time.

**Example 2.5.2.1: Stable and reusable**

```python
a = [1]
i = id(a)
a.append(2)
print(id(a) == i)
class T: pass
x = id(T())
y = id(T())
print("ids of temporaries can repeat:", x == y)
```

**Output:**

```text
True
ids of temporaries can repeat: True
```

**Example 2.5.2.2: Equal values are not the same object (built at run time)**

```python
a = int("500")
b = int("500")
print(a == b, id(a) == id(b))
```

**Output:**

```text
True False
```

#### Practice 2.5.2

**2.5.2-Q1 BASIC**

```python
a = []; print(id(a) == id(a))
```

**2.5.2-Q2 MID**

```python
a = [1]; b = a; a = None; print(b)
```

**2.5.2-Q3 HARD**

```python
print(id([]) == id([]))
```

### 2.5.3 is vs == (contrast, big pitfall)

== asks "do these have equal values?" (calls \_\_eq\_\_). "is" asks "are these the very same object?" (compares ids). Use "is" only for None, True, False and sentinel objects. Comparing numbers or strings with "is" gives answers that depend on interpreter optimisations.

**Example 2.5.3.1: Equal but not identical**

```python
a = [1, 2]; b = [1, 2]
print(a == b, a is b)
x = int("1000"); y = int("1000")
print(x == y, x is y)
```

**Output:**

```text
True False
True False
```

**Example 2.5.3.2: is with literals warns**

```python
import warnings
with warnings.catch_warnings(record=True) as w:
    warnings.simplefilter("always")
    compile("x is 1", "<s>", "eval")
    print(w[0].category.__name__)
```

**Output:**

```text
SyntaxWarning
```

**Example 2.5.3.3: Custom \_\_eq\_\_ can lie, is cannot**

```python
class Always:
    def __eq__(self, other): return True
o = Always()
print(o == None, o is None)
```

**Output:**

```text
True False
```

#### Practice 2.5.3

**2.5.3-Q1 BASIC**

```python
print([] == [], [] is [])
```

**2.5.3-Q2 MID**

```python
a = (1, 2); b = (1, 2); print(a == b)
```

**2.5.3-Q3 MID**

```python
print(None is None, 0 is None, 0 == None)
```

**2.5.3-Q4 HARD**

```python
x = float("nan"); print(x == x, x is x)
```

**2.5.3-Q5 TRAP**

```python
a = int("300"); b = int("300"); print(a is b, a == b)
```

### 2.5.4 Small integer interning (-5..256)

CPython pre-creates int objects for -5 to 256 and reuses them. So two names bound to such values at run time share one object. Outside the range, each computation usually creates a new object. Inside ONE compiled block (a script or one cell) identical constants are merged by the compiler, which can make 257 is 257 True. Use int("257") to escape that.

**Example 2.5.4.1: Edges of the cache (built at run time to avoid constant folding)**

```python
for n in [-6, -5, 0, 256, 257, 1000]:
    a = int(str(n)); b = int(str(n))
    print(n, a is b)
```

**Output:**

```text
-6 False
-5 True
0 True
256 True
257 False
1000 False
```

**Example 2.5.4.2: Constant folding confuses the picture**

```python
a = 257
b = 257
print("same code block:", a is b)
```

**Output:**

```text
same code block: True
```

**Example 2.5.4.3: Not part of the language**

```python
import sys
print(sys.version_info[:2] >= (3, 8))
print("Never rely on 'is' for numbers; the range is a CPython detail.")
```

**Output:**

```text
True
Never rely on 'is' for numbers; the range is a CPython detail.
```

#### Practice 2.5.4

**2.5.4-Q1 BASIC**

```python
a = int("5"); b = int("5"); print(a is b)
```

**2.5.4-Q2 MID**

```python
a = int("256"); b = int("256"); print(a is b)
```

**2.5.4-Q3 MID**

```python
a = int("257"); b = int("257"); print(a is b)
```

**2.5.4-Q4 HARD**

```python
x = 1000; y = 1000; print(x is y)
```

**2.5.4-Q5 HARD**

```python
print(int("-5") is int("-5"), int("-6") is int("-6"))
```

### 2.5.5 String interning

CPython interns strings that look like identifiers (letters, digits, underscore) when they are compile-time constants, and you can intern any string with sys.intern. Equal strings built at run time are often different objects. Interning makes == faster (pointer check first) and saves memory when millions of equal strings occur.
# 2.5.5 String interning, explained for beginners

I'll go one small step at a time, and I won't use a word until I've explained it.

---

## Step 1: Two words you need first

**Compile time** = Python reads your whole file and prepares it *before* running anything. Think of it as a chef reading the recipe and prepping ingredients before cooking.

**Run time** = Python is actually executing your lines, one by one. This is the cooking.

Why this matters: Python can do some work early, at compile time, but only with things it can already see written in the code, like `"hel" + "lo"`. Things that need actual running, like `"".join([...])`, wait until run time.

---

## Step 2: Remember `is` vs `==`

You already know these two:

| | Question |
|---|---|
| `a == b` | Do they contain the **same text**? |
| `a is b` | Are they the **exact same object** in memory? |

Two strings can be **equal** (`==` is True) but still be **two separate objects** (`is` is False), like two photocopies of the same page.

---

## Step 3: What is "interning"?

**Interning** means: Python keeps **one single master copy** of a string, and everyone who needs that text points to the same master copy.

Real-life picture:

```
WITHOUT interning                    WITH interning

 a -> "hello"  (copy 1)               a ----\
 b -> "hello"  (copy 2)               b -----+--> "hello"  (one master copy)
 c -> "hello"  (copy 3)               c ----/
```

Why bother? Two reasons:

1. **Speed.** To check `a == b`, Python first checks "are these the same object?" (a quick pointer check). If yes, it says True immediately, without reading every letter.
2. **Memory.** If a million rows all contain `"India"`, you store one copy instead of a million.

Python keeps the master copies in a special lookup table (think of it as a notice board of "master strings"). When a string is *interned*, Python looks on the board: "Is there already a master copy of this text? Use that one. If not, put this one on the board."

---

## Step 4: When does Python intern automatically?

The rule from your text:

> CPython interns strings that **look like identifiers** (letters, digits, underscore) when they are **compile-time constants**.

Break that sentence into two conditions. Both must be true:

| Condition | Meaning | Example that passes | Example that fails |
|---|---|---|---|
| Looks like an identifier | only letters, digits, `_` | `"hello"`, `"var_1"` | `"hello world"` (has a space) |
| Compile-time constant | written directly in the code | `"hello"` | `"".join([...])` (built while running) |

So `"hello"` typed directly in code gets interned. But a string created by `join`, `input()`, reading a file, etc. is **not** interned automatically. That is why your text says: *"Equal strings built at run time are often different objects."*

> **CPython** is simply the standard, most common version of Python (the one you download from python.org). These behaviors are about CPython.

---

## Step 5: Example 2.5.5.1 (compile-time vs run-time)

```python
a = "hello"
b = "hel" + "lo"
c = "".join(["hel", "lo"])
print(a is b, a is c, a == c)
```

Output:

```
True False True
```

Trace it line by line:

**`a = "hello"`**
Written directly, and it looks like an identifier. Python interns it. `a` points to the master copy.

**`b = "hel" + "lo"`**
Both pieces are written directly in the code. Python is smart: at compile time it pre-computes `"hel" + "lo"` into `"hello"` (this is called **constant folding**). The result is again the constant `"hello"`, so it points to the **same master copy**.
So `a is b` -> **True**.

**`c = "".join(["hel", "lo"])`**
`join` is a function call. Python can't know its result until it actually runs. At run time it builds a **brand-new string** `"hello"`. Nobody put it on the master board.
So `a is c` -> **False**.

**`a == c`**
Same letters, so -> **True**.

Picture:

```
a ----\
b -----+--> "hello"  (master copy)

c ------->  "hello"  (a separate new object, same letters)
```

---

## Step 6: Example 2.5.5.2 (the one with the space, a little tricky)

```python
x = "hello world"; y = "hello world"
print(x is y)
```

Output:

```
True
```

Wait. `"hello world"` has a space, so it does **not** look like an identifier, so the interning rule from Step 4 does not apply. Yet `x is y` is True. Why?

Because there is a **second, separate mechanism** at work:

> Inside one block of code, Python's compiler notices that the same constant appears twice and stores it **only once** (it merges duplicate constants).

So:

| Mechanism | What it does | Applies to |
|---|---|---|
| **Interning** | one master copy shared everywhere via the notice board | identifier-looking constants |
| **Constant merging** | the same constant used twice in one code block is stored once | any constant in the same code block |

`x` and `y` are both the constant `"hello world"` in the same code block, so they share one object.

Two cautions:
- This sharing is guaranteed only **within one code block**. In a different function or file, `"hello world"` may be a separate object.
- The title says "even with spaces" to warn you not to think spaces always break sharing. They only stop the *interning* mechanism, not the *merging* mechanism.

---

## Step 7: Example 2.5.5.3 (`sys.intern` forces sharing)

You can intern any string yourself using `sys.intern(...)`. It means: "Look at the notice board. If a master copy of this text exists, give me that one. Otherwise put mine there and give me mine."

```python
import sys
c = "".join(["he", "llo wor", "ld"])
d = "".join(["hello", " ", "world"])
print(c is d)
print(sys.intern(c) is sys.intern(d))
```

Output:

```
False
True
```

Trace:

**`c = "".join([...])`** -> built at run time, a new object `"hello world"`.
**`d = "".join([...])`** -> built at run time, another new object `"hello world"`.
Both have the same text but are two separate objects.

`c is d` -> **False**.

Now the interning:

1. `sys.intern(c)`: board has no `"hello world"` yet, so `c` becomes the master copy. Returns `c`.
2. `sys.intern(d)`: board already has `"hello world"` (that's `c`). Returns the master copy, which is `c`.

Both calls return the **same object**, so `sys.intern(c) is sys.intern(d)` -> **True**.

Picture:

```
c ------> "hello world"   <--- master copy on the board
d ------> "hello world"   (separate object, same text)

sys.intern(c) -----> master copy
sys.intern(d) -----> master copy   (same one!)
```

Important: `sys.intern` does **not** change `c` or `d` themselves. It only **returns** the master copy. `d` still points to its own object unless you reassign (`d = sys.intern(d)`).

---

## Step 8: Practice questions with full solutions

### Q1 (BASIC)

```python
import sys; a = sys.intern("x y"); b = sys.intern("x " + "y"); print(a is b)
```

**Step by step:**

1. `"x " + "y"` are two constants written in the code. At compile time Python folds them into `"x y"`.
2. `sys.intern("x y")` -> puts/gets the master copy of `"x y"`.
3. `sys.intern("x " + "y")` -> the text is `"x y"` too, so it fetches the **same master copy**.
4. Same object -> `a is b` is **True**.

**Answer: `True`**

**Why this is a good question:** even if the strings were built in different ways, `sys.intern` makes equal text share one object.

---

### Q2 (MID)

```python
a = "".join(["a", "b"]); b = "ab"; print(a == b, a is b)
```

**Step by step:**

1. `a = "".join(["a", "b"])` -> built **at run time**. A new string object `"ab"`.
2. `b = "ab"` -> a constant written in the code, looks like an identifier, so it's **interned** (master copy).
3. `a == b` -> same text `"ab"` -> **True**.
4. `a is b` -> `a` is a new run-time object, `b` is the master copy -> different objects -> **False**.

**Answer: `True False`**

Picture:

```
b -----> "ab"   (master copy)
a -----> "ab"   (new run-time object)
```

Note: this `False` is what CPython normally gives. The rule is "often different objects", not "guaranteed different", which is why you should never rely on `is` for comparing strings.

---

### Q3 (HARD)

```python
import sys; a = "".join(["a b"]); print(sys.intern(a) is sys.intern("a b"))
```

This one looks scary because of the one-item `join` and the space. Take it in pieces.

**Piece 1: what is `a`?**
`"".join(["a b"])` joins a list with just **one item**. Joining one item has nothing to glue, so the result is just `"a b"`. (CPython even has a shortcut here: if the list has exactly one real string, it may hand back that same string.) Either way, `a` holds the text `"a b"`.

**Piece 2: the space doesn't matter here.**
`"a b"` has a space, so it's not auto-interned (Step 4). But the question uses `sys.intern`, which interns **any** string regardless of what it looks like.

**Piece 3: the two `sys.intern` calls.**

1. `sys.intern(a)` -> asks the board for master copy of `"a b"`. Gets (or creates) one.
2. `sys.intern("a b")` -> same text `"a b"`, asks the board again -> gets **the same master copy**.

**Piece 4: compare.**
Both calls returned the same object, so `is` -> **True**.

**Answer: `True`**

**The key insight (this is why it's marked hard):** you do **not** need to figure out whether `a` itself is the same object as the literal `"a b"`. Whatever it is, `sys.intern` always returns the **one master copy for that text**, so both sides are guaranteed to be the same object.

---

## Step 9: Summary table

| Situation | Same object (`is`)? | Why |
|---|---|---|
| `"hello"` and `"hello"` in code | Yes | identifier-like constant, interned |
| `"hel" + "lo"` vs `"hello"` | Yes | folded at compile time into the same constant |
| `"".join(["hel","lo"])` vs `"hello"` | Usually no | built at run time |
| `"hello world"` twice in the same code block | Yes | duplicate constants merged |
| Equal strings built at run time | Usually no | separate objects |
| `sys.intern(x) is sys.intern(y)` for equal text | **Always yes** | one master copy per text |

## Step 10: Golden rules

1. **Never use `is` to compare string values.** Use `==`. Whether two equal strings are the same object is an implementation detail and can change between Python versions or situations.
2. `is` on strings is only for learning how interning works, not for real comparisons.
3. Use `sys.intern` only when you have a real reason: millions of repeated strings (to save memory) or lots of equality checks on the same strings (to speed them up).
4. Interning affects only **identity** (`is`, `id`). It never changes what `==` says, since equal text stays equal.

## Quick recap in one picture

```
 Compile time (before running)          Run time (while running)
 -----------------------------          ------------------------
 "hello"          -> interned           "".join([...])    -> new object
 "hel" + "lo"     -> folded to "hello"  input(), file     -> new object
 same constant twice in one block       text built by code -> new object
   -> merged into one object

 sys.intern(s)  -> always gives you THE master copy for that text
```

## Extra practice (try on your own)

1. `a = "py"; b = "p" + "y"; print(a is b)`
   **Answer:** `True`. Folded at compile time into the same interned constant.

2. `import sys; a = "".join(["he", "llo"]); print(a is "hello")` (ignore any warning Python prints about `is` with a literal)
   **Answer:** `False` normally. `a` is built at run time. This is also why you should use `==`.

3. `import sys; a = "".join(["he", "llo"]); print(sys.intern(a) is "hello")`
   **Answer:** `True`. `sys.intern(a)` returns the master copy of `"hello"`, and the literal `"hello"` is that same interned constant. (Python may print a warning about using `is` with a literal; the result is still `True`.)

4. `import sys; a = "".join(["x", " y"]); b = "".join(["x ", "y"]); print(a == b, a is b, sys.intern(a) is sys.intern(b))`
   **Answer:** `True False True`. Same text, two separate run-time objects, but `sys.intern` gives both the same master copy.

**Example 2.5.5.1: Compile-time vs run-time strings**

```python
a = "hello"
b = "hel" + "lo"
c = "".join(["hel", "lo"])
print(a is b, a is c, a == c)
```

**Output:**

```text
True False True
```

**Example 2.5.5.2: Constants inside one code block are shared, even with spaces**

```python
x = "hello world"; y = "hello world"
print(x is y)
```

**Output:**

```text
True
```

**Example 2.5.5.3: sys.intern forces sharing**

```python
import sys
c = "".join(["he", "llo wor", "ld"])
d = "".join(["hello", " ", "world"])
print(c is d)
print(sys.intern(c) is sys.intern(d))
```

**Output:**

```text
False
True
```

#### Practice 2.5.5

**2.5.5-Q1 BASIC**

```python
import sys; a = sys.intern("x y"); b = sys.intern("x " + "y"); print(a is b)
```

**2.5.5-Q2 MID**

```python
a = "".join(["a", "b"]); b = "ab"; print(a == b, a is b)
```

**2.5.5-Q3 HARD**

```python
import sys; a = "".join(["a b"]); print(sys.intern(a) is sys.intern("a b"))
```

### 2.5.6 Copy pitfalls (a = b for lists)

b = a never copies. To get a new list use a.copy(), a[:], list(a) or copy.copy(a). These are SHALLOW: the new list is a new object but its items are the same objects.

**Example 2.5.6.1: Alias vs copies**

```python
a = [1, 2, 3]
alias = a
c1 = a.copy(); c2 = a[:]; c3 = list(a)
a.append(4)
print(alias, c1, c2, c3)
```

**Output:**

```text
[1, 2, 3, 4] [1, 2, 3] [1, 2, 3] [1, 2, 3]
```

**Example 2.5.6.2: The 2D list trap**

```python
bad = [[0] * 3] * 3
bad[0][0] = 1
print(bad)
good = [[0] * 3 for _ in range(3)]
good[0][0] = 1
print(good)
```

**Output:**

```text
[[1, 0, 0], [1, 0, 0], [1, 0, 0]]
[[1, 0, 0], [0, 0, 0], [0, 0, 0]]
```

**Example 2.5.6.3: Default argument sharing**

```python
def add(x, bucket=[]):
    bucket.append(x)
    return bucket
print(add(1), add(2))
```

**Output:**

```text
[1, 2] [1, 2]
```

#### Practice 2.5.6

**2.5.6-Q1 BASIC**

```python
a = [1]; b = a.copy(); b.append(2); print(a)
```

**2.5.6-Q2 MID**

```python
g = [[0]] * 2; g[0][0] = 5; print(g)
```

**2.5.6-Q3 MID**

```python
g = [[0] for _ in range(2)]; g[0][0] = 5; print(g)
```

**2.5.6-Q4 HARD**

```python
a = [[1], [2]]; b = a[:]; b[0].append(9); print(a)
```

**2.5.6-Q5 TRAP**

```python
def f(x, l=[]):
    l.append(x)
    return l
f(1); f(2); print(f(3))
```

### 2.5.7 Shallow vs deep copy (preview)

copy.copy duplicates only the outer container. copy.deepcopy duplicates the whole object graph, keeping shared references shared and handling cycles.

**Example 2.5.7.1: Shallow shares inner objects, deep does not**

```python
import copy
a = [[1], [2]]
s = copy.copy(a); d = copy.deepcopy(a)
a[0].append(99)
print(s, d)
print(s[0] is a[0], d[0] is a[0])
```

**Output:**

```text
[[1, 99], [2]] [[1], [2]]
True False
```

**Example 2.5.7.2: deepcopy preserves internal sharing**

```python
import copy
x = [0]
a = [x, x]
b = copy.deepcopy(a)
print(b[0] is b[1], b[0] is x)
```

**Output:**

```text
True False
```

#### Practice 2.5.7

**2.5.7-Q1 BASIC**

```python
import copy; a = [1, [2]]; b = copy.deepcopy(a); b[1].append(3); print(a)
```

**2.5.7-Q2 MID**

```python
import copy; a = [1, [2]]; b = copy.copy(a); b[1].append(3); print(a)
```

**2.5.7-Q3 HARD**

```python
import copy; a = []; a.append(a); b = copy.deepcopy(a); print(b[0] is b)
```

### 2.5.8 Hashability

An object is hashable if hash(obj) works and equal objects have equal hashes. Dictionary keys and set elements must be hashable. Immutable built-ins are hashable if their contents are. Defining \_\_eq\_\_ without

\_\_hash\_\_ makes a class unhashable.

**Example 2.5.8.1: Rules in practice**

```python
print(hash(1) == hash(1.0) == hash(True))
d = {1: "int", 1.0: "float", True: "bool"}
print(d)
print({(1, 2): "ok"})
try:
    {(1, [2]): "bad"}
except TypeError as e:
    print("TypeError:", e)
```

**Output:**

```text
True
{1: 'bool'}
{(1, 2): 'ok'}
TypeError: unhashable type: 'list'
```

**Example 2.5.8.2: \_\_eq\_\_ without \_\_hash\_\_**

```python
class P:
    def __init__(self, v): self.v = v
    def __eq__(self, o): return self.v == o.v
try:
    {P(1)}
except TypeError as e:
    print("TypeError:", e)
```

**Output:**

```text
TypeError: unhashable type: 'P'
```
# Python identity, equality, hash and type checks: clarification + full cheat sheet

This file has two parts:

- **Part A**: the practice question you didn't understand, explained slowly.
- **Part B**: every look-alike term side by side (`id`, `hash`, `is`, `==`, `isinstance`, ...), their clashes, and how they work together.

---

# PART A: "If you override `__eq__`, what must you do with `__hash__`?"

## The question in plain words

> You told Python: "two Students with the same name are equal."
> Now you must also tell Python: "two Students with the same name go in the same locker."

Why? Because a set or dict does **two steps**:

1. **hash** -> go to a locker
2. **==** -> check who is inside

If two "equal" students go to **different lockers**, step 2 never happens, and Python never notices they are equal.

## A1. Broken version: equal objects, different hashes

```python
class Bad:
    def __init__(self, name):
        self.name = name

    def __eq__(self, other):
        return self.name == other.name

    def __hash__(self):
        return id(self)        # different for every object!


a = Bad("Sakshi")
c = Bad("Sakshi")

print(a == c)                  # True   -> "equal"
print(hash(a) == hash(c))      # False  -> but different lockers!

s = {a, c}
print(len(s))                  # 2      -> set thinks they are different people
```

`a == c` says "same person", but the set stored both. That is the bug: the set looked in two different lockers and never compared them.

## A2. The other mistake: define `__eq__` and forget `__hash__`

```python
class OnlyEq:
    def __init__(self, name):
        self.name = name

    def __eq__(self, other):
        return self.name == other.name


x = OnlyEq("Sakshi")
print(x == OnlyEq("Sakshi"))   # True
hash(x)                        # TypeError: unhashable type: 'OnlyEq'
```

When you define `__eq__` and not `__hash__`, Python **removes** the hash on purpose (sets `__hash__ = None`). Reason: Python refuses to guess a hash that might break the rule. So your object cannot be a dict key or set item until you write `__hash__`.

## A3. Correct version: hash uses the same data as `__eq__`

```python
class Student:
    def __init__(self, name):
        self.name = name

    def __eq__(self, other):
        if not isinstance(other, Student):
            return NotImplemented
        return self.name == other.name

    def __hash__(self):
        return hash(self.name)     # same data that __eq__ compares


a = Student("Sakshi")
c = Student("Sakshi")

print(a == c)                  # True
print(hash(a) == hash(c))      # True  -> same locker
print(len({a, c}))             # 1     -> correctly treated as one person
```

## The golden rule (memorize this)

> **Whatever `__eq__` compares, `__hash__` must use (the same data).**

| `__eq__` compares | `__hash__` should use |
|---|---|
| `name` | `hash(self.name)` |
| `(x, y)` | `hash((self.x, self.y))` |
| `(name, age)` | `hash((self.name, self.age))` |

Safe direction: hash may use **less** data than `__eq__` (that only causes collisions, which are legal). It must never use **more or different** data.

## A4. Extra warning: don't hash data that can change

```python
s = Student("Sakshi")
box = {s}
s.name = "Rahul"        # changed after storing!
print(s in box)         # False -> its locker number changed, Python can't find it
```

So keep the fields used in `__hash__` unchanging (treat the object as immutable).

---

# PART B: All the look-alike terms

## B1. Big picture: what each thing is

| Term | Kind | Question it answers |
|---|---|---|
| `id(x)` | function | What is the memory identity number of this exact object? |
| `x is y` | operator | Are x and y the **exact same object**? |
| `x == y` | operator | Do x and y have **equal value** (by `__eq__`)? |
| `x.__eq__(y)` | method | The method Python calls when you write `x == y` |
| `hash(x)` | function | Which locker number does x go to? |
| `x.__hash__()` | method | The method Python calls when you write `hash(x)` |
| `type(x)` | function | What is the exact class of x? |
| `isinstance(x, C)` | function | Is x an object of class C **or a subclass** of C? |
| `issubclass(A, B)` | function | Is class A a subclass of class B? |

## B2. `id()` vs `is`

`x is y` is basically `id(x) == id(y)` (for objects alive at the same time).

```python
a = [1, 2]
b = [1, 2]
c = a

print(a is b)    # False -> two separate lists
print(a is c)    # True  -> c is another name for the same list
print(id(a) == id(c))   # True
```

Use `is` for the special single objects: `None`, `True`, `False`.

```python
if x is None:      # correct
if x == None:      # works but not recommended
```

## B3. `is` vs `==`

```python
a = [1, 2]
b = [1, 2]
print(a == b)    # True  -> same contents
print(a is b)    # False -> different objects
```

| | `is` | `==` |
|---|---|---|
| Compares | identity (same object) | value (via `__eq__`) |
| Can you customize it? | **No** | **Yes** (`__eq__`) |
| Use for | `None`, `True`, `False`, "same object?" | "same value?" |

Warning: small numbers and some strings may happen to be the same object (Python caches them), so `is` can look like it works on numbers and strings. That is an implementation detail. **Never use `is` to compare numbers or strings.**

## B4. `==` vs `__eq__()`

They are the same thing. `a == b` makes Python call `a.__eq__(b)`.

- If `a.__eq__(b)` returns `NotImplemented`, Python tries `b.__eq__(a)`.
- If both give up, Python falls back to identity (`a is b`).
- `a != b` calls `__ne__`, which by default simply flips the result of `__eq__`.

## B5. `hash()` vs `__hash__()`

Same relationship: `hash(x)` makes Python call `x.__hash__()`.

```python
class Demo:
    def __hash__(self):
        return 100

print(hash(Demo()))   # 100
```

## B6. `isinstance()` vs `type()`

```python
print(isinstance(True, int))   # True   (bool is a subclass of int)
print(type(True) == int)       # False  (exact class is bool)
print(type(True) is bool)      # True
```

| | `type(x) is C` | `isinstance(x, C)` |
|---|---|---|
| Accepts subclasses? | No (exact match only) | Yes |
| Accepts several classes? | No | Yes: `isinstance(x, (int, float))` |
| Usually preferred? | Rarely | **Yes** |

`issubclass` is the same idea but for classes, not objects:

```python
print(issubclass(bool, int))   # True
```

## B7. Where `isinstance` shows up next to `__eq__`

That is why `__eq__` often starts like this:

```python
def __eq__(self, other):
    if not isinstance(other, Student):
        return NotImplemented      # "I don't know how to compare with that"
    return self.name == other.name
```

`NotImplemented` (a value you **return**) is **not** the same as `NotImplementedError` (an error you **raise**). Don't mix them up.

## B8. Special methods vs what triggers them

You almost never call these directly. Python calls them for you.

| You write | Python calls |
|---|---|
| `a == b` | `a.__eq__(b)` |
| `a != b` | `a.__ne__(b)` |
| `hash(a)` | `a.__hash__()` |
| `str(a)` / `print(a)` | `a.__str__()` |
| `repr(a)` | `a.__repr__()` |
| `len(a)` | `a.__len__()` |
| `x in a` | `a.__contains__(x)` |
| `a < b` | `a.__lt__(b)` |

**Important:** `is` and `id()` have **no** special method. You cannot override them. Python always controls identity.

## B9. `__str__` vs `__repr__` (another look-alike pair)

- `__repr__`: for developers, unambiguous (ideally looks like code).
- `__str__`: for end users, readable.
- `print()` uses `__str__`; if missing, it falls back to `__repr__`.

---

## B10. Who controls what

| Thing | Python controls | You can customize |
|---|---|---|
| `id()` | Yes | No |
| `is` | Yes | No |
| `==` / `__eq__` | Default only | **Yes** |
| `hash()` / `__hash__` | Default only | **Yes** |
| `isinstance` | Mostly | Rarely (advanced) |

---

## B11. Clashes and traps (the confusing ones)

**1. Equal values, different objects**
```python
[1] == [1]     # True
[1] is [1]     # False
```

**2. Same hash, not equal (collision)**
```python
hash(-1) == hash(-2)   # True in CPython
-1 == -2               # False
```

**3. Define `__eq__` only -> becomes unhashable** (see A2).

**4. `__eq__` and `__hash__` disagree -> sets/dicts misbehave** (see A1).

**5. `1`, `1.0` and `True` are all equal and share a hash**
```python
d = {1: "a", 1.0: "b", True: "c"}
print(d)    # {1: 'c'}  -> one single key
```

**6. `bool` is an `int`**
```python
isinstance(True, int)   # True
True + True             # 2
```

**7. `type()` vs `isinstance()` with subclasses**
```python
class Animal: pass
class Dog(Animal): pass

d = Dog()
print(type(d) is Animal)       # False
print(isinstance(d, Animal))   # True
```

**8. NaN is not equal to itself**
```python
nan = float("nan")
print(nan == nan)         # False
print(nan is nan)         # True   (same object)
print(nan in [nan])       # True   (membership checks identity first)
```

**9. Ids of temporary objects can repeat** (ids are unique only among objects alive at the same time).

**10. Changing an object doesn't change its id**
```python
a = [1]
i = id(a)
a.append(2)
print(id(a) == i)   # True
```

---

## B12. How they work together (the flow)

When you do `x in some_set` or `some_dict[x]`, Python does roughly this:

```
1. h = hash(x)                       -> go to locker h
2. for each item y in that locker:
       if y is x:   -> FOUND          (identity shortcut)
       if y == x:   -> FOUND          (calls __eq__)
3. nothing matched -> NOT FOUND
```

So all three cooperate:

- **`hash`** picks the locker (speed),
- **`is`** is a quick shortcut (same object, certainly equal),
- **`==`** makes the final decision (same value).

That identity shortcut is also why `nan in [nan]` is `True` even though `nan == nan` is `False`.

## B13. The contract that keeps everything in sync

| Rule | Meaning |
|---|---|
| `a is b` -> `a == b` | The same object is equal to itself (normally) |
| `a == b` -> `hash(a) == hash(b)` | **Required.** Equal objects must share a hash |
| `hash(a) == hash(b)` -> `a == b` | **Not required** (collision allowed) |
| Hash must not change during the object's life | So don't hash mutable fields |

## B14. A template that always works

```python
class Student:
    def __init__(self, name):
        self._name = name           # treat as read-only

    @property
    def name(self):
        return self._name

    def __eq__(self, other):
        if not isinstance(other, Student):
            return NotImplemented
        return self.name == other.name

    def __hash__(self):
        return hash(self.name)      # same data as __eq__
```

Shortcut: Python's `dataclass` can write both for you, with the hash and equality based on the same fields.

```python
from dataclasses import dataclass

@dataclass(frozen=True)
class Student:
    name: str
```

---

## B15. Master comparison table

| | Compares | Customizable? | Returns | Typical use |
|---|---|---|---|---|
| `id(x)` | memory identity | No | int | debugging, "same object?" |
| `is` | identity | No | bool | `x is None` |
| `==` / `__eq__` | value | Yes | bool | normal comparison |
| `hash()` / `__hash__` | locker number | Yes | int | dict keys, set items |
| `type(x) is C` | exact class | No | bool | rare, strict check |
| `isinstance(x, C)` | class or subclass | Rarely | bool | normal type check |
| `issubclass(A, B)` | class relationship | Rarely | bool | class checks |

---

## Practice questions (with answers)

1. If `__eq__` compares `name`, what should `__hash__` use?
   **A:** `hash(self.name)`, the same data `__eq__` compares.

2. What happens if you define `__eq__` but not `__hash__`?
   **A:** Python sets `__hash__` to `None`, so the object becomes unhashable (`TypeError` when hashing).

3. Two objects are equal but have different hashes. What goes wrong?
   **A:** Sets and dicts store them in different lockers and never compare them, so they look like different items.

4. `a = [1]`, `b = [1]`. What are `a == b` and `a is b`?
   **A:** `True` and `False`.

5. Can you override `is`?
   **A:** No. Identity is controlled by Python.

6. `isinstance(True, int)`: True or False? And `type(True) is int`?
   **A:** `True`, and `False` (the exact type is `bool`).

7. What is the difference between `NotImplemented` and `NotImplementedError`?
   **A:** `NotImplemented` is a value returned from `__eq__` and similar methods meaning "I can't compare with that"; `NotImplementedError` is an exception you raise.

8. Why is `nan in [nan]` True while `nan == nan` is False?
   **A:** Membership checks identity (`is`) before `==`, and it is the same object.

9. Is it OK for two unequal objects to have the same hash?
   **A:** Yes. That is a collision. It is allowed, just slower.

10. Why shouldn't you hash a field that can change?
    **A:** If the field changes after the object is stored, its locker number changes and Python can no longer find it.

#### Practice 2.5.8

**2.5.8-Q1 BASIC**

```python
print({1, 1.0, True})
```

**2.5.8-Q2 MID**

```python
print(hash("a") == hash("a"))
```

**2.5.8-Q3 HARD**

```python
print(hash(-1) == hash(-2))
```

### 2.5.9 Immutability is shallow

A tuple cannot change which objects it holds, but if one of them is mutable that object can change. t[0] += [x] on a tuple element performs the in-place extend and then fails when storing back, so you get both an exception AND a changed value.

**Example 2.5.9.1: Tuple holding a list**

```python
t = (1, [2, 3])
t[1].append(4)
print(t)
```

**Output:**

```text
(1, [2, 3, 4])
```

**Example 2.5.9.2: The famous += puzzle**

```python
t = (1, [2])
try:
    t[1] += [3]
except TypeError as e:
    print("TypeError:", e)
print(t)
```

**Output:**

```text
TypeError: 'tuple' object does not support item assignment
(1, [2, 3])
```

#### Practice 2.5.9

**2.5.9-Q1 BASIC**

```python
t = ([],); t[0].append(1); print(t)
```

**2.5.9-Q2 MID**

```python
t = (1, 2); print(t + (3,), t)
```

**2.5.9-Q3 HARD**

```python
t = ([0],); t[0] += [1] if False else []; print(t)
```

### 2.5.10 Mutation through function parameters

Python passes references (call by object reference). A function can mutate a mutable argument in place and the caller sees it. Rebinding the parameter has no effect on the caller.

**Example 2.5.10.1: Mutation vs rebinding**

```python
def mutate(l): l.append(1)
def rebind(l): l = [1]
def aug(l): l += [1]
def plus(l): l = l + [1]
a = []; mutate(a); print(a)
a = []; rebind(a); print(a)
a = []; aug(a); print(a)
a = []; plus(a); print(a)
```

**Output:**

```text
[1]
[]
[1]
[]
```

#### Practice 2.5.10

**2.5.10-Q1 BASIC**

```python
def f(x): x = 5
v = 1; f(v); print(v)
```

**2.5.10-Q2 MID**

```python
def f(d): d["k"] = 1
z = {}; f(z); print(z)
```

**2.5.10-Q3 HARD**

```python
def f(l): l[:] = [0]
a = [1, 2]; f(a); print(a)
```

**2.5.10-Q4 TRAP**

```python
def f(s): s += "!"
s = "hi"; f(s); print(s)
```

### 2.5.11 Defensive copying

A function that must not change its argument should copy it first, or accept an immutable type (tuple). Return copies when exposing internal state.

**Example 2.5.11.1: Safe function**

```python
def normalized(values):
    out = list(values)
    out.sort()
    return out
data = [3, 1, 2]
print(normalized(data), data)
```

**Output:**

```text
[1, 2, 3] [3, 1, 2]
```

**Example 2.5.11.2: Freezing state**

```python
class Bag:
    def __init__(self): self._items = []
    def add(self, x): self._items.append(x)
    def items(self): return tuple(self._items)
b = Bag(); b.add(1)
print(b.items())
```

**Output:**

```text
(1,)
```

#### Practice 2.5.11

**2.5.11-Q1 BASIC**

```python
def f(l): return sorted(l)
a = [2, 1]; f(a); print(a)
```

**2.5.11-Q2 MID**

```python
def f(l): l.sort(); return l
a = [2, 1]; f(a); print(a)
```

### 2.5.12 Immutable tricks and performance

Tuples are smaller and slightly faster to create than lists. String += in a loop is O(n^2) in theory (CPython sometimes optimises it); build lists and join. Immutable objects can be cached and shared.

**Example 2.5.12.1: Sizes on this machine**

```python
import sys
print(sys.getsizeof((1, 2, 3)) < sys.getsizeof([1, 2, 3]))
print(sys.getsizeof([]) < sys.getsizeof([1, 2, 3, 4, 5]))
```

**Output:**

```text
True
True
```

**Example 2.5.12.2: Timing join vs +=**

```python
import timeit
def concat():
    s = ""
    for i in range(2000): s += "x"
    return s
def joined():
    return "".join(["x" for _ in range(2000)])
print(concat() == joined())
```

**Output:**

```text
True
```

#### Practice 2.5.12

**2.5.12-Q1 BASIC**

```python
print(len("".join(["a"] * 5)))
```

**2.5.12-Q2 MID**

```python
import sys; print(sys.getsizeof(()) < sys.getsizeof([]))
```

### 2.5.13 Object identity in containers

Containers store references. Membership (in) and index() test identity first, then equality. NaN is the famous case: it is not equal to itself, but a list can still "contain" the same NaN object.

**Example 2.5.13.1: Identity then equality**

```python
nan = float("nan")
print(nan == nan, nan in [nan], float("nan") in [nan])
a = [1]; b = [1]
print([a, a] == [a, b], [a, a][0] is [a, b][1])
```

**Output:**

```text
False True False
True False
```

#### Practice 2.5.13

**2.5.13-Q1 BASIC**

```python
print(1 in [1.0], True in [1])
```

**2.5.13-Q2 MID**

```python
n = float("nan"); print([n].count(n), [float("nan")].count(float("nan")))
```

**2.5.13-Q3 HARD**

```python
a = [1]; l = [a, [1]]; print(l.index([1]), l[0] is l[1])
```

### 2.5.14 Mutability mini-lab

Fifteen puzzles on aliasing, copying, mutation and tuples.

#### Practice 2.5.14

**2.5.14-Q1 BASIC**

```python
a = [1]; b = a; b.append(2); print(a)
```

**2.5.14-Q2 BASIC**

```python
s = "ab"; t = s; t += "c"; print(s)
```

**2.5.14-Q3 MID**

```python
a = [1, 2]; b = a[:]; b[0] = 9; print(a)
```

**2.5.14-Q4 MID**

```python
a = [[1]]; b = a[:]; b[0][0] = 9; print(a)
```

**2.5.14-Q5 MID**

```python
t = (1, 2); u = t; u += (3,); print(t)
```

**2.5.14-Q6 MID**

```python
d = {"a": [1]}; e = dict(d); e["a"].append(2); print(d)
```

**2.5.14-Q7 HARD**

```python
import copy; d = {"a": [1]}; e = copy.deepcopy(d); e["a"].append(2); print(d)
```

**2.5.14-Q8 HARD**

```python
a = [1]; b = [a, a]; b[0].append(2); print(b)
```

**2.5.14-Q9 HARD**

```python
x = [1]; y = x; x = x * 2; print(y)
```

**2.5.14-Q10 HARD**

```python
x = [1]; y = x; x *= 2; print(y)
```

**2.5.14-Q11 TRAP**

```python
t = ([],); t[0] += [1] if True else None; print(t)
```

**2.5.14-Q12 TRAP**

```python
def f(a=[]): a.append(1); return len(a)
print(f(), f(), f())
```

**2.5.14-Q13 TRAP**

```python
a = {1: [0]}; b = a.copy(); b[2] = 5; print(a)
```

**2.5.14-Q14 TRAP**

```python
s = {1, 2}; t = s; s = s | {3}; print(t)
```

**2.5.14-Q15 TRAP**

```python
s = {1, 2}; t = s; s |= {3}; print(t)
```

---

## Section 2.6 Memory Model Internals

### 2.6.1 Objects on the heap, names in namespaces

Objects live in a private heap managed by Python. A namespace is a dictionary mapping names to objects. A function call creates a new local namespace; a module has a global one. sys.getsizeof(obj) returns the size of the object itself, not of things it references.

**Example 2.6.1.1: Shallow size vs total size**

```python
import sys
inner = list(range(1000))
outer = [inner, inner]
print(sys.getsizeof(outer) < sys.getsizeof(inner))
```

**Output:**

```text
True
```

**Example 2.6.1.2: Namespaces are dicts**

```python
x = 1
print(type(globals()).__name__, globals()["x"])
```

**Output:**

```text
dict 1
```

#### Practice 2.6.1

**2.6.1-Q1 BASIC**

```python
print(type(globals()).__name__)
```

**2.6.1-Q2 MID**

```python
x = 5; globals()["y"] = x + 1; print(y)
```

### 2.6.2 Reference counting

Each object stores a count of references. Assigning, passing and storing in containers increment it; rebinding, del and container removal decrement it. At zero the object is freed at once. This is why files and objects are cleaned up promptly in CPython.

**Example 2.6.2.1: Watching the count change**

```python
import sys
class Thing: pass
t = Thing()
r0 = sys.getrefcount(t)
a = t; b = [t]; c = {"k": t}
print(sys.getrefcount(t) - r0)
del a, b, c
print(sys.getrefcount(t) - r0)
```

**Output:**

```text
3
0
```

**Example 2.6.2.2: Immediate destruction**

```python
class Loud:
    def __del__(self): print("freed")
x = Loud()
print("before")
x = None
print("after")
```

**Output:**

```text
before
freed
after
```

#### Practice 2.6.2

**2.6.2-Q1 BASIC**

```python
import sys; t = object(); r = sys.getrefcount(t); a = t; print(sys.getrefcount(t) - r)
```

**2.6.2-Q2 MID**

```python
class L:
    def __del__(self): print("gone")
x = L(); y = x; del x; print("still"); del y
```

### 2.6.3 Cyclic garbage collector

Objects that refer to each other keep each other's count above zero even if nothing else uses them. The gc module finds and frees such cycles in generations. gc.collect() runs a full collection.

**Example 2.6.3.1: A cycle survives until collection**

```python
import gc, weakref
class Node: pass
a = Node(); b = Node(); a.other = b; b.other = a
w = weakref.ref(a)
del a, b
print("alive after del:", w() is not None)
gc.collect()
print("alive after gc.collect():", w() is not None)
print(gc.get_threshold())
```

**Output:**

```text
alive after del: True
alive after gc.collect(): False
(700, 10, 10)
```

#### Practice 2.6.3

**2.6.3-Q1 BASIC**

```python
import gc; print(gc.isenabled())
```

**2.6.3-Q2 MID**

```python
import gc, weakref
class N: pass
a = N(); a.me = a
w = weakref.ref(a); del a; gc.collect(); print(w() is None)
```

### 2.6.4 Object header and size of basic objects

Every object carries a header (reference count and type pointer). Sizes depend on version and platform; the numbers below are from this machine's Python 3.12 (64-bit). Use them for relative comparisons only.

**Example 2.6.4.1: Sizes (bytes)**

```python
import sys
for name, o in [("None", None), ("0", 0), ("1", 1), ("2**30", 2**30), ("2**60", 2**60), ("1.5",
    1.5), ("''", ""), ("'a'", "a"), ("[]", []), ("[1]", [1]), ("()", ()), ("{}", {}), ("set()",
    set())]:
    print(f"{name:8} {sys.getsizeof(o)}")
```

**Output:**

```text
None     16
0        28
1        28
2**30    32
2**60    36
1.5      24
''       41
'a'      42
[]       56
[1]      64
()       40
{}       64
set()    216
```

**Example 2.6.4.2: A list stores 8-byte references**

```python
import sys
for n in [0, 1, 2, 3, 4, 5, 9, 17]:
    print(n, sys.getsizeof([0] * n))
```

**Output:**

```text
0 56
1 64
2 72
3 80
4 88
5 96
9 128
17 192
```

#### Practice 2.6.4

**2.6.4-Q1 BASIC**

```python
import sys; print(sys.getsizeof(1) == sys.getsizeof(2))
```

**2.6.4-Q2 MID**

```python
import sys; print(sys.getsizeof(2**100) > sys.getsizeof(2))
```

### 2.6.5 Integer storage in CPython

CPython stores an int as an array of 30-bit "digits" plus a sign, so ints have no fixed upper limit. Memory grows by 4 bytes per extra 30 bits. 2\*\*100 is one object with four digits.

**Example 2.6.5.1: Growth per 30 bits**

```python
import sys
base = sys.getsizeof(0)
for bits in [0, 30, 60, 90, 120]:
    n = 2 ** bits
    print(bits, sys.getsizeof(n))
print((2**100).bit_length(), 2**100)
```

**Output:**

```text
0 28
30 32
60 36
90 40
120 44
101 1267650600228229401496703205376
```

**Example 2.6.5.2: No overflow**

```python
print(2**200 + 1)
print(len(str(2**1000)))
```

**Output:**

```text
1606938044258990275541962092341162602522202993782792835301377
302
```

#### Practice 2.6.5

**2.6.5-Q1 BASIC**

```python
print((2**64).bit_length())
```

**2.6.5-Q2 MID**

```python
import sys; print(sys.getsizeof(2**59) == sys.getsizeof(2**30 + 1))
```

### 2.6.6 id reuse after deletion

Freed memory is reused. So id(a) == id(b) can be True for two DIFFERENT objects if the first died before the second was created. Never use id comparison to decide that two objects are "the same" unless both are alive.

**Example 2.6.6.1: Dead object, reused address**

```python
class T: pass
a = id(T())
b = id(T())
print(a == b)
x = T(); i = id(x); del x
y = T()
print(id(y) == i)
```

**Output:**

```text
True
True
```

#### Practice 2.6.6

**2.6.6-Q1 BASIC**

```python
print(id([]) == id([]))
```

**2.6.6-Q2 MID**

```python
a = [1]; b = [1]; print(id(a) == id(b))
```

### 2.6.7 Weak references and del

A weak reference does not keep an object alive. weakref.ref(obj)() returns the object or None after it dies. Useful for caches and observers.

**Example 2.6.7.1: Cache that does not leak**

```python
import weakref
class Img: pass
cache = weakref.WeakValueDictionary()
i = Img(); cache["a"] = i
print(len(cache))
del i
print(len(cache))
```

**Output:**

```text
1
0
```

#### Practice 2.6.7

**2.6.7-Q1 BASIC**

```python
import weakref
class X: pass
x = X(); r = weakref.ref(x); print(r() is x)
```

**2.6.7-Q2 MID**

```python
import weakref
try:
    weakref.ref([])
except TypeError as e:
    print("TypeError")
```

### 2.6.8 Memory profiling tools

sys.getsizeof is shallow. tracemalloc tracks allocations by line. For deep size, walk the object graph. Measure before you optimise.

**Example 2.6.8.1: tracemalloc basics**

```python
import tracemalloc
tracemalloc.start()
data = [str(i) for i in range(10000)]
cur, peak = tracemalloc.get_traced_memory()
tracemalloc.stop()
print(cur > 100_000, peak >= cur)
```

**Output:**

```text
True True
```

**Example 2.6.8.2: A simple deep size helper**

```python
import sys
def deep(o, seen=None):
    seen = seen or set()
    if id(o) in seen: return 0
    seen.add(id(o))
    s = sys.getsizeof(o)
    if isinstance(o, dict): s += sum(deep(k, seen) + deep(v, seen) for k, v in o.items())
    elif isinstance(o, (list, tuple, set, frozenset)): s += sum(deep(i, seen) for i in o)
    return s
print(deep([[1, 2], [1, 2]]) > sys.getsizeof([[1, 2], [1, 2]]))
```

**Output:**

```text
True
```

#### Practice 2.6.8

**2.6.8-Q1 BASIC**

```python
import tracemalloc; print(tracemalloc.is_tracing())
```

**2.6.8-Q2 MID**

```python
import sys; print(sys.getsizeof([[1] * 100]) < sys.getsizeof([1] * 100))
```

---

## Section 2.7 Annotations, Constants and Typing for Variables

### 2.7.1 Variable annotations

name: type = value attaches a hint stored in \_\_annotations\_\_ (module, class) and ignored at run time. Local variable annotations inside functions are not stored.

**Example 2.7.1.1: Where annotations live**

```python
x: int = 1
y: "list[str]" = []
print(__annotations__)
class P:
    a: int
    b: str = "s"
print(P.__annotations__)
def f():
    z: int = 1
    return z
print(f.__annotations__, f())
```

**Output:**

```text
{'x': <class 'int'>, 'y': 'list[str]'}
{'a': <class 'int'>, 'b': <class 'str'>}
{} 1
```

#### Practice 2.7.1

**2.7.1-Q1 BASIC**

```python
v: int = 3; print(v, __annotations__)
```

**2.7.1-Q2 MID**

```python
class C:
    a: int
print(hasattr(C, "a"), C.__annotations__)
```

### 2.7.2 typing.Final and constants

Final marks a name as not to be reassigned (checked by mypy/pyright). ClassVar marks class-level attributes. At run time they do nothing.

**Example 2.7.2.1: Final is advisory**

```python
from typing import Final, ClassVar
LIMIT: Final = 10
LIMIT = 11
print(LIMIT)
class C:
    count: ClassVar[int] = 0
print(C.count)
```

**Output:**

```text
11
0
```

#### Practice 2.7.2

**2.7.2-Q1 BASIC**

```python
from typing import Final; X: Final = 1; print(X)
```

**2.7.2-Q2 MID**

```python
from typing import Final; X: Final[int] = 1; X = 2; print(X)
```

### 2.7.3 Type aliases

An alias gives a name to a type expression. Use x: TypeAlias = ... (3.10+) or the type statement (3.12+). Aliases are for readers and type checkers.

**Example 2.7.3.1: Three spellings (3.12 syntax shown)**

```python
from typing import TypeAlias
Vector: TypeAlias = list[float]
type Matrix = list[Vector]
def norm(v: Vector) -> float: return sum(x * x for x in v) ** 0.5
print(norm([3.0, 4.0]))
print(Matrix, Matrix.__value__)
```

**Output:**

```text
5.0
Matrix list[list[float]]
```

#### Practice 2.7.3

**2.7.3-Q1 BASIC**

```python
IntList = list[int]; print(IntList)
```

**2.7.3-Q2 MID**

```python
type A = int | str; print(A.__value__)
```

### 2.7.4 Optional, Union and the \| syntax

Optional[int] means int or None. From 3.10 write int \| None. After "if x is not None" a type checker narrows the type. At run time unions are only hints.

**Example 2.7.4.1: Equivalent forms**

```python
from typing import Optional, Union
print(Optional[int] == Union[int, None], (int | None) == Optional[int])
def f(x: int | None = None) -> int:
    return 0 if x is None else x
print(f(), f(5))
print(isinstance(3, int | str), isinstance(None, int | None))
```

**Output:**

```text
True True
0 5
True True
```

#### Practice 2.7.4

**2.7.4-Q1 BASIC**

```python
print(isinstance(1, int | str))
```

**2.7.4-Q2 MID**

```python
print(int | None)
```

### 2.7.5 Runtime vs static typing

Static checkers (mypy, pyright) analyse annotations without running code; the interpreter ignores them. Gradual typing lets you add hints in steps. Python 3.14 evaluates annotations lazily (PEP 649). This machine runs 3.12, so annotations here are evaluated at definition time.

**Example 2.7.5.1: Hints do not protect you at run time**

```python
def double(x: int) -> int:
    return x * 2
print(double(3), double("ab"), double([1]))
```

**Output:**

```text
6 abab [1, 1]
```

**Example 2.7.5.2: Reading hints with typing.get_type_hints**

```python
import typing
def f(a: int, b: "str" = "x") -> bool: ...
print(typing.get_type_hints(f))
```

**Output:**

```text
{'a': <class 'int'>, 'b': <class 'str'>, 'return': <class 'bool'>}
```

#### Practice 2.7.5

**2.7.5-Q1 BASIC**

```python
def f(x: int) -> int: return x
print(f("a"))
```

**2.7.5-Q2 MID**

```python
def f(x: int): ...
print(f.__annotations__)
```

### 2.7.6 Mini-lab: annotate a script

Task: add annotations to five small functions, run mypy, fix three reported errors. Below is a typed starting file and the runtime result.

**Example 2.7.6.1: Typed script**

```python
from typing import Iterable
def total(xs: Iterable[float]) -> float: return sum(xs)
def mean(xs: list[float]) -> float: return total(xs) / len(xs)
def clamp(x: float, lo: float = 0.0, hi: float = 1.0) -> float: return max(lo, min(x, hi))
def label(n: int | None) -> str: return "none" if n is None else str(n)
print(total([1, 2.5]), mean([1.0, 3.0]), clamp(5), label(None), label(3))
```

**Output:**

```text
3.5 2.0 1.0 none 3
```

#### Practice 2.7.6

**2.7.6-Q1 BASIC**

```python
def f(a: int, b: int = 2) -> int: return a * b
print(f(4))
```

**2.7.6-Q2 MID**

```python
def g(x: "int | None") -> str: return "n" if x is None else "v"
print(g(None), g(1))
```

---

## Section 2.8 Inspecting Variables

### 2.8.1 type, isinstance, id, dir, vars, repr

type shows the class, isinstance checks class relationship, id the identity, dir lists attributes, vars the \_\_dict\_\_, repr a developer-friendly string. Use repr (not str) when debugging: it shows quotes and escapes.

**Example 2.8.1.1: One object, many probes**

```python
x = [1, "a"]
print(type(x), isinstance(x, list), isinstance(x, (list, tuple)))
print(repr("hi\n"), str("hi\n"))
print([n for n in dir(x) if not n.startswith("_")][:5])
class A:
    def __init__(self): self.v = 1
print(vars(A()), repr(A())[:12])
```

**Output:**

```text
<class 'list'> True True
'hi\n' hi

['append', 'clear', 'copy', 'count', 'extend']
{'v': 1} <__main__.A
```

#### Practice 2.8.1

**2.8.1-Q1 BASIC**

```python
print(repr("a"), str("a"))
```

**2.8.1-Q2 MID**

```python
print(isinstance(True, int), type(True) == int)
```

**2.8.1-Q3 HARD**

```python
print(sorted(vars(type("T", (), {"a": 1}))()))
```

### 2.8.2 globals() and locals() as dicts

globals() returns the live module dict, so writing to it creates names. locals() inside a function is a snapshot; changing it does not change local variables (and from 3.13 each call returns an independent snapshot).

**Example 2.8.2.1: Writing**

```python
globals()["made"] = 42
print(made)
def f():
    a = 1
    snap = locals()
    snap["a"] = 99
    return a
print(f())
```

**Output:**

```text
42
1
```

#### Practice 2.8.2

**2.8.2-Q1 BASIC**

```python
globals()["k"] = 3; print(k)
```

**2.8.2-Q2 MID**

```python
def f():
    x = 1
    d = locals()
    return list(d)
print(f())
```

### 2.8.3 inspect module first look

inspect gives signatures, source code, members and call stack information. Good for tooling and exploration, rarely needed in everyday code.

**Example 2.8.3.1: Signature and members**

```python
import inspect
def f(a, b=2, *args, **kw): pass
print(inspect.signature(f))
print([n for n, _ in inspect.getmembers(int) if n == "bit_length"])
print(inspect.isfunction(f), inspect.isclass(int))
```

**Output:**

```text
(a, b=2, *args, **kw)
['bit_length']
True True
```

#### Practice 2.8.3

**2.8.3-Q1 BASIC**

```python
import inspect; print(inspect.isfunction(len), inspect.isbuiltin(len))
```

**2.8.3-Q2 MID**

```python
import inspect; print(list(inspect.signature(lambda a, b=1: 0).parameters))
```

### 2.8.4 f"{x=}" debugging

f"{expr=}" prints the expression text, an equals sign and the repr of the value (3.8+). Combine with format specs.

**Example 2.8.4.1: Self-documenting expressions**

```python
x = 3.14159; name = "ana"
print(f"{x=}")
print(f"{x=:.2f}")
print(f"{name=} {len(name)=}")
print(f"{x * 2 = }")
```

**Output:**

```text
x=3.14159
x=3.14
name='ana' len(name)=3
x * 2 = 6.28318
```

#### Practice 2.8.4

**2.8.4-Q1 BASIC**

```python
n = 5; print(f"{n=}")
```

**2.8.4-Q2 MID**

```python
s = "a"; print(f"{s=!s}")
```

### 2.8.5 Trace tools: pdb, sys.settrace, tracemalloc

pdb (breakpoint()) pauses execution so you can inspect names. sys.settrace calls a function for each line event. tracemalloc shows where memory is allocated.

**Example 2.8.5.1: A tiny line tracer**

```python
import sys
log = []
def tracer(frame, event, arg):
    if event == "line": log.append(frame.f_lineno)
    return tracer
def work():
    a = 1
    b = a + 1
    return b
sys.settrace(tracer); work(); sys.settrace(None)
print(len(log))
```

**Output:**

```text
3
```

#### Practice 2.8.5

**2.8.5-Q1 BASIC**

```python
print(callable(breakpoint))
```

**2.8.5-Q2 MID**

```python
import sys; print(sys.gettrace())
```

### 2.8.6 Chapter 2 mini-lab: Variable Playground

Build a tool that prints type, a stable identity token, size and mutability for any expression, and detects aliasing between two names. Reference implementation:

**Example 2.8.6.1: variable_playground.py (reference solution, run)**

```python
import sys
MUTABLE = (list, dict, set, bytearray)
def info(name, obj):
    return f"{name}: type={type(obj).__name__:9} size={sys.getsizeof(obj):4}
        mutable={isinstance(obj, MUTABLE)}"
def same(n1, o1, n2, o2):
    return f"{n1} is {n2}: {o1 is o2}   {n1} == {n2}: {o1 == o2}"
a = [1, 2]; b = a; c = [1, 2]; d = (1, 2); s = "hi"
for n, o in [("a", a), ("c", c), ("d", d), ("s", s)]:
    print(info(n, o))
print(same("a", a, "b", b))
print(same("a", a, "c", c))
```

**Output:**

```text
a: type=list      size=  72 mutable=True
c: type=list      size=  72 mutable=True
d: type=tuple     size=  56 mutable=False
s: type=str       size=  43 mutable=False
a is b: True   a == b: True
a is c: False   a == c: True
```

#### Practice 2.8.6

**2.8.6-Q1 BASIC**

```python
a = [1]; b = a; print(a is b)
```

**2.8.6-Q2 MID**

```python
a = (1, 2); b = (1, 2); print(a == b)
```

**2.8.6-Q3 HARD**

```python
a = "ab"; b = "a" + "b"; print(a == b)
```

---

## Chapter 2 Summary: The 30 Rules

1. A variable is a name bound to an object, never a box holding a value.

2. Assignment evaluates the right side first, then binds the name.

3. Assignment never copies an object.

4. Types belong to objects, not names.

5. Python is dynamically and strongly typed: no silent str/int mixing.

6. Type hints are not enforced at run time.

7. id() is identity; type() is class; value may change only for mutable objects.

8. Rebinding moves an arrow; mutation changes the object.

9. a = b = [] creates aliases.

10. Use list.copy(), a[:], or copy.deepcopy to copy.

11. [[0]\*3]\*3 repeats one row three times.

12. Tuple unpacking needs matching counts unless one starred target is used.

13. The starred target always collects a list.

14. a, b = b, a evaluates the right tuple before binding.

15. x += y mutates mutable objects in place and rebinds immutable ones.

16. Chained comparison a \< b \< c evaluates b once.

17. del removes a name, not necessarily the object.

18. None is a singleton: test with is None.

19. Scope is function-level; blocks do not create scope.

20. LEGB: Local, Enclosing, Global, Built-in.

21. Assigning anywhere in a function makes the name local there.

22. global/nonlocal are needed to rebind, not to read or mutate.

23. Closures capture variables, not values (late binding).

24. Do not shadow built-ins (list, id, sum, max, input).

25. is is for None/True/False/sentinels; == is for values.

26. Never rely on small-int or string interning.

27. Immutability is shallow: a tuple can hold a mutable list.

28. Dict keys and set members must be hashable.

29. Mutable default arguments are shared across calls.

30. Reference counting frees objects at zero; the cycle collector handles cycles.

### Error Message Decoder

---

## Final Exam (45 mixed HARD and TRAP questions)

One question taken from each of 45 topics. Predict all outputs on paper, then check against the answer key. Score: 40+ mastery, 32-39 solid, below 32 revisit Sections 2.3 to 2.5.

**E1 (from 2.1.1)**

```python
a = "hi"; b = a; b += "!"; print(a, b)
```

**E2 (from 2.1.2)**

```python
a = [1]; b = [a, a]; a = [2]; print(b)
```

**E3 (from 2.1.3)**

```python
print(type(type(5)))
```

**E4 (from 2.1.4)**

```python
def f(l): l[:] = [7]
x = [1, 2]; f(x); print(x)
```

**E5 (from 2.1.5)**

```python
def f(a, b): return a + b
print(f([1], [2]), f((1,), (2,)))
```

**E6 (from 2.1.6)**

```python
print("5" + 5)
```

**E7 (from 2.1.7)**

```python
x = 5; i = id(x); x += 1; print(id(x) == i)
```

**E8 (from 2.1.8)**

```python
print(isinstance(int, type), isinstance(type, object), isinstance(object, type))
```

**E9 (from 2.1.9)**

```python
try:
    print(w)
except NameError:
    print("no w")
w = 3
print(w)
```

**E10 (from 2.1.10)**

```python
a = b = [1]; a = a + [2]; print(b)
```

**E11 (from 2.1.11)**

```python
a = [1]; b = a; a *= 2; print(b)
```

**E12 (from 2.1.12)**

```python
import weakref
class B: pass
b = B(); w = weakref.ref(b); del b; print(w() is None)
```

**E13 (from 2.1.13)**

```python
a = [1]; b = a; a, b = b, a + [9]; print(a, b)
```

**E14 (from 2.2.1)**

```python
import keyword; print(keyword.iskeyword("match"), "match".isidentifier())
```

**E15 (from 2.2.2)**

```python
x = 1
X = x
x = 2
print(X)
```

**E16 (from 2.2.3)**

```python
print("CapWords".isidentifier(), "CapWords"[0].isupper())
```

**E17 (from 2.2.4)**

```python
import math; math.pi = 3; print(math.pi)
```

**E18 (from 2.2.5)**

```python
import keyword; print("_" in keyword.softkwlist, "match" in keyword.softkwlist)
```

**E19 (from 2.2.6)**

```python
print(5 .__eq__(5.0), 5 .__eq__("5"))
```

**E20 (from 2.2.7)**

```python
class A:
    __v = 1
class B(A): pass
print(hasattr(B, "__v"), hasattr(B, "_A__v"))
```

**E21 (from 2.2.8)**

```python
id = 5
print(type(id).__name__)
del id
print(type(id).__name__)
```

**E22 (from 2.2.10)**

```python
for _ in range(2): pass
print(_)
```

**E23 (from 2.2.11)**

```python
import unicodedata; print(unicodedata.normalize("NFKC", "ﬁ"))
```

**E24 (from 2.3.1)**

```python
x = 3; y = (x := x + 1) * 2; print(x, y)
```

**E25 (from 2.3.2)**

```python
a = b = {"k": 1}; b["k"] = 2; print(a)
```

**E26 (from 2.3.3)**

```python
a, b = range(2, 4); print(a * b)
```

**E27 (from 2.3.4)**

```python
a = 1; b = 2; a = b; b = a; print(a, b)
```

**E28 (from 2.3.5)**

```python
a, *b, c = range(5); print(a, b, c)
```

**E29 (from 2.3.6)**

```python
t = ([1], 2)
try:
    t[0] += [9]
except TypeError as e:
    print("TypeError")
print(t)
```

**E30 (from 2.3.7)**

```python
print(False == False in [False])
```

**E31 (from 2.3.8)**

```python
x = [1, 2]; y = x.append(3); print(y)
```

**E32 (from 2.3.9)**

```python
l = [1, 2, 3]; del l[:]; print(l)
```

**E33 (from 2.3.10)**

```python
print(None == False, not None)
```

**E34 (from 2.3.11)**

```python
(a, *b), c = ("xyz", 9); print(a, b, c)
```

**E35 (from 2.3.12)**

```python
print([*"hi", *(1, 2)], (*[1], *[2]))
```

**E36 (from 2.3.13)**

```python
l = list(range(6)); l[::2] = ["a", "b", "c"]; print(l)
```

**E37 (from 2.3.14)**

```python
print(any((m := v) > 2 for v in [1, 3, 5]), m)
```

**E38 (from 2.3.15)**

```python
v: list[int]; print("v" in dir(), "v" in __annotations__)
```

**E39 (from 2.3.16)**

```python
a = [1, 2]; a[0], a[1] = a[1], a[0]; print(a)
```

**E40 (from 2.3.17)**

```python
x = 10
for x in range(3): pass
print(x)
```

**E41 (from 2.3.18)**

```python
n = 5; n -= n; n += 1; print(n)
```

**E42 (from 2.4.1)**

```python
x = "g"
def f():
    print(x)
    x = "l"
try:
    f()
except UnboundLocalError:
    print("UnboundLocalError")
```

**E43 (from 2.4.2)**

```python
n = 0
def f():
    n += 1
try:
    f()
except UnboundLocalError:
    print("error")
```

**E44 (from 2.4.3)**

```python
def mk():
    t = []
    def add(x):
        t.append(x)
        return len(t)
    return add
a = mk(); print(a(1), a(1), mk()(1))
```

**E45 (from 2.4.4)**

```python
def f():
    sum = 0
    for i in [1, 2]: sum += i
    return sum
print(f(), sum([5]))
```

---

## Answer Key (outputs from running the code)

Cover this section while you predict. Each answer is the real output produced by running the question.

### 2.1.1 What is a variable (name binding, not a box)

```text
Q1 5
Q2 [1, 2]
Q3 [1] [1, 2]
Q4 [1, 2] [1, 2]
Q5 hi hi!
```

### 2.1.2 Variable as reference to an object

```text
Q1 True False
Q2 [[0, 9], [0, 9]]
Q3 [[0, 9], [0]]
Q4 [[1], [1]]
```

### 2.1.3 id() and type(): first tools

```text
Q1 True
Q2 <class 'int'> <class 'float'> <class 'str'> <class 'list'>
Q3 True False
Q4 <class 'type'>
```

### 2.1.4 Names vs values

```text
Q1 1
Q2 [1]
Q3 []
Q4 [7]
```

### 2.1.5 Dynamic typing (contrast with static typing)

```text
Q1 a
Q2 ababab ababab
Q3 2.5
Q4 [1, 2] (1, 2)
```

### 2.1.6 Strong typing (Python is strongly + dynamically typed)

```text
Q1 aaa
Q2 2
Q3 ababc
Q4 TypeError: can only concatenate str (not "int") to str
```

### 2.1.7 Objects: identity, type, value

```text
Q1 True
Q2 (1, 2, 3) False
Q3 False
```

### 2.1.8 Everything is an object: first proof

```text
Q1 8
Q2 HI
Q3 builtin_function_or_method
Q4 True True True
```

### 2.1.9 Variables are not declared

```text
Q1 False
Q2 NameError
Q3 no w
   3
```

### 2.1.10 Multiple names for the same object

```text
Q1 [1]
Q2 1 0
Q3 []
Q4 [[0, 1]]
Q5 [1]
```

### 2.1.11 Rebinding does not affect other names

```text
Q1 1
Q2 [1]
Q3 [1, 2]
Q4 [1, 1]
```

### 2.1.12 Variable lifetime and reference counting intro

```text
Q1 1
Q2 [1]
Q3 True
```

### 2.1.13 Mental-model exercises (mini-lab)

```text
Q1 4 3
Q2 [1, 2] [1, 2]
Q3 [1, 2] [1, 2, 3]
Q4 (1, [2, 3])
Q5 xy x
Q6 [[1, 2], [1, 2], [1, 2]]
Q7 [[1, 2], [1, 2], [1, 2]]
Q8 [1, 2] [1, 3]
Q9 [0, 2] [0, 1] [0, 2]
Q10 [1] [1, 9]
```

### 2.2.1 Valid identifier rules

```text
Q1 True False
Q2 True False
Q3 False True
Q4 False True
```

### 2.2.2 Case sensitivity

```text
Q1 3
Q2 5 6
Q3 1
```

### 2.2.3 snake_case convention (PEP 8)

```text
Q1 True False
Q2 True
Q3 True True
```

### 2.2.4 Constant naming (UPPER_CASE, Final)

```text
Q1 3
Q2 2
Q3 3
```

### 2.2.5 Reserved keywords as names (error)

```text
Q1 True
Q2 False
Q3 SyntaxError
Q4 True True
```

### 2.2.6 Dunder names (\_\_x\_\_): intro

```text
Q1 8
Q2 3
Q3 NotImplemented NotImplemented
```

### 2.2.7 Private-ish naming (\_x, \_\_x, \_\_x\_\_)

```text
Q1 1
Q2 ['_A__v']
Q3 False True
```

### 2.2.8 Beginner pitfalls: shadowing built-ins (list, id, input)

```text
Q1 3
Q2 shadowed
Q3 int
   builtin_function_or_method
```

### 2.2.9 Naming for readability

```text
Q1 False
Q2 30000
```

### 2.2.10 Throwaway name \_

```text
Q1 1
Q2 3
Q3 1
```

### 2.2.11 Unicode names and normalisation

```text
Q1 True
Q2 True
Q3 fi
```

### 2.2.12 Naming in competitive programming

```text
Q1 [1, 1, 1]
Q2 2
```

### 2.3.1 Simple assignment

```text
Q1 4
Q2 4
Q3 4 8
```

### 2.3.2 Multiple assignment: a = b = c = 0

```text
Q1 5
Q2 [1, 2]
Q3 [1]
Q4 [0, 1] [0, 1]
Q5 {'k': 2}
```

### 2.3.3 Tuple unpacking: a, b = 1, 2

```text
Q1 y
Q2 3
Q3 ValueError: not enough values to unpack (expected 2, got 1)
Q4 6
```

### 2.3.4 Swap idiom: a, b = b, a

```text
Q1 4 3
Q2 3 1 2
Q3 2 3
Q4 2 2
```

### 2.3.5 Starred unpacking: a, \*b = [1,2,3]

```text
Q1 [2, 3]
Q2 ['x', 'y'] z
Q3 []
Q4 0 [1, 2, 3] 4
```

### 2.3.6 Augmented assignment (+=, -=, \*=, //=, \*\*=, &=, \|=, ^=, >>=, \<\<=, @=)

```text
Q1 14
Q2 [1, 2]
Q3 {1, 2}
Q4 [1]
Q5 TypeError
   ([1, 9], 2)
```

### 2.3.7 Chained comparison: 1 \< x \< 10

```text
Q1 True
Q2 False
Q3 1
Q4 True
Q5 True
```

### 2.3.8 Reassignment vs mutation

```text
Q1 [1, 2]
Q2 None [1, 3]
Q3 [1]
Q4 [1, 2, 3] [1, 2]
Q5 None
```

### 2.3.9 del keyword

```text
Q1 [1, 3]
Q2 [1, 3, 5]
Q3 [1]
Q4 []
```

### 2.3.10 None as default

```text
Q1 True
Q2 False True
Q3 False True
```

### 2.3.11 Nested unpacking

```text
Q1 6
Q2 a 1
Q3 x ['y', 'z'] 9
```

### 2.3.12 Unpacking in function calls and literals

```text
Q1 [0, 1, 2]
Q2 {'a': 2}
Q3 ['h', 'i', 1, 2] (1, 2)
```

### 2.3.13 Assignment targets that are not names

```text
Q1 [1, 7, 8, 3]
Q2 []
Q3 ['a', 1, 'b', 3, 'c', 5]
```

### 2.3.14 Walrus operator := first look

```text
Q1 5 4
Q2 [0, 1, 2] 2
Q3 True 3
```

### 2.3.15 Annotated assignment x: int = 5

```text
Q1 3
Q2 s
Q3 False True
```

### 2.3.16 Evaluation order puzzles

```text
Q1 2 1
Q2 1 [0, 5]
Q3 1 [7, 0]
Q4 [2, 1]
```

### 2.3.17 Assignment inside loops and conditionals

```text
Q1 2
Q2 False
Q3 2
```

### 2.3.18 Assignment mini-lab

```text
Q1 1 2
Q2 2 1
Q3 h ['e', 'y']
Q4 [1, 2]
Q5 1 2 [3, 4]
Q6 1
Q7 [2, 1]
Q8 2 [0, 0, 5]
Q9 6
Q10 [[1], [1]]
Q11 [1] [1, 2]
Q12 1 2 (2, 1)
Q13 11
Q14 []
Q15 1
```

### 2.4.1 Local / Enclosing / Global / Built-in (LEGB)

```text
Q1 1
Q2 1
Q3 e
Q4 UnboundLocalError
```

### 2.4.2 global keyword

```text
Q1 2
Q2 [1, 1]
Q3 error
```

### 2.4.3 nonlocal keyword

```text
Q1 5
Q2 1
Q3 1 2 1
```

### 2.4.4 Shadowing

```text
Q1 6 1
Q2 3
   2
Q3 3 5
```

### 2.4.5 UnboundLocalError pitfall

```text
Q1 1
Q2 UnboundLocalError
Q3 UnboundLocalError
```

### 2.4.6 Module-level variables

```text
Q1 True
Q2 True
Q3 True
```

### 2.4.7 \_\_main\_\_ scope (intro)

```text
Q1 __main__
Q2 True
```

### 2.4.8 Block scope does not exist

```text
Q1 5
Q2 False
Q3 /dev/null True
```

### 2.4.9 Comprehension scope and the loop variable leak

```text
Q1 5
Q2 2
```

### 2.4.10 Closures: first look

```text
Q1 3
Q2 b
Q3 9 9
```

### 2.4.11 Class scope

```text
Q1 1 1
Q2 1 2
Q3 [1]
```

### 2.4.12 Exception variable scope

```text
Q1 False
Q2 False
```

### 2.4.13 Namespaces and dir()/vars()/globals()/locals()

```text
Q1 True
Q2 ['a', 'b']
Q3 1
```

### 2.4.14 Global state in competitive programming

```text
Q1 True
Q2 RecursionError
```

### 2.4.15 Scope mini-lab

```text
Q1 2
Q2 False
Q3 5
Q4 2
Q5 5
Q6 ([0, 1], False)
Q7 2 0
Q8 1
Q9 [1, 1]
Q10 [0, 1, 2]
Q11 UnboundLocalError
Q12 2
```

### 2.5.1 Mutable vs immutable (contrast table)

```text
Q1 immutable
Q2 True
Q3 TypeError
Q4 (1, [2, 3])
```

### 2.5.2 id() behaviour

```text
Q1 True
Q2 [1]
Q3 True
```

### 2.5.3 is vs == (contrast, big pitfall)

```text
Q1 True False
Q2 True
Q3 True False False
Q4 False True
Q5 False True
```

### 2.5.4 Small integer interning (-5..256)

```text
Q1 True
Q2 True
Q3 False
Q4 True
Q5 True False
```

### 2.5.5 String interning

```text
Q1 True
Q2 True False
Q3 True
```

### 2.5.6 Copy pitfalls (a = b for lists)

```text
Q1 [1]
Q2 [[5], [5]]
Q3 [[5], [0]]
Q4 [[1, 9], [2]]
Q5 [1, 2, 3]
```

### 2.5.7 Shallow vs deep copy (preview)

```text
Q1 [1, [2]]
Q2 [1, [2, 3]]
Q3 True
```

### 2.5.8 Hashability

```text
Q1 {1}
Q2 True
Q3 True
```

### 2.5.9 Immutability is shallow

```text
Q1 ([1],)
Q2 (1, 2, 3) (1, 2)
Q3 TypeError: 'tuple' object does not support item assignment
```

### 2.5.10 Mutation through function parameters

```text
Q1 1
Q2 {'k': 1}
Q3 [0]
Q4 hi
```

### 2.5.11 Defensive copying

```text
Q1 [2, 1]
Q2 [1, 2]
```

### 2.5.12 Immutable tricks and performance

```text
Q1 5
Q2 True
```

### 2.5.13 Object identity in containers

```text
Q1 True True
Q2 1 0
Q3 0 False
```

### 2.5.14 Mutability mini-lab

```text
Q1 [1, 2]
Q2 ab
Q3 [1, 2]
Q4 [[9]]
Q5 (1, 2)
Q6 {'a': [1, 2]}
Q7 {'a': [1]}
Q8 [[1, 2], [1, 2]]
Q9 [1]
Q10 [1, 1]
Q11 TypeError: 'tuple' object does not support item assignment
Q12 1 2 3
Q13 {1: [0]}
Q14 {1, 2}
Q15 {1, 2, 3}
```

### 2.6.1 Objects on the heap, names in namespaces

```text
Q1 dict
Q2 6
```

### 2.6.2 Reference counting

```text
Q1 1
Q2 still
   gone
```

### 2.6.3 Cyclic garbage collector

```text
Q1 True
Q2 True
```

### 2.6.4 Object header and size of basic objects

```text
Q1 True
Q2 True
```

### 2.6.5 Integer storage in CPython

```text
Q1 65
Q2 True
```

### 2.6.6 id reuse after deletion

```text
Q1 True
Q2 False
```

### 2.6.7 Weak references and del

```text
Q1 True
Q2 TypeError
```

### 2.6.8 Memory profiling tools

```text
Q1 False
Q2 True
```

### 2.7.1 Variable annotations

```text
Q1 3 {'v': <class 'int'>}
Q2 False {'a': <class 'int'>}
```

### 2.7.2 typing.Final and constants

```text
Q1 1
Q2 2
```

### 2.7.3 Type aliases

```text
Q1 list[int]
Q2 int | str
```

### 2.7.4 Optional, Union and the \| syntax

```text
Q1 True
Q2 int | None
```

### 2.7.5 Runtime vs static typing

```text
Q1 a
Q2 {'x': <class 'int'>}
```

### 2.7.6 Mini-lab: annotate a script

```text
Q1 8
Q2 n v
```

### 2.8.1 type, isinstance, id, dir, vars, repr

```text
Q1 'a' a
Q2 True False
Q3 TypeError: 'mappingproxy' object is not callable
```

### 2.8.2 globals() and locals() as dicts

```text
Q1 3
Q2 ['x']
```

### 2.8.3 inspect module first look

```text
Q1 False True
Q2 ['a', 'b']
```

### 2.8.4 f"{x=}" debugging

```text
Q1 n=5
Q2 s=a
```

### 2.8.5 Trace tools: pdb, sys.settrace, tracemalloc

```text
Q1 True
Q2 None
```

### 2.8.6 Chapter 2 mini-lab: Variable Playground

```text
Q1 True
Q2 True
Q3 True
```

### Final exam answers

```text
E1 hi hi!
E2 [[1], [1]]
E3 <class 'type'>
E4 [7]
E5 [1, 2] (1, 2)
E6 TypeError: can only concatenate str (not "int") to str
E7 False
E8 True True True
E9 no w
   3
E10 [1]
E11 [1, 1]
E12 True
E13 [1] [1, 9]
E14 False True
E15 1
E16 True True
E17 3
E18 True True
E19 NotImplemented NotImplemented
E20 False True
E21 int
    builtin_function_or_method
E22 1
E23 fi
E24 4 8
E25 {'k': 2}
E26 6
E27 2 2
E28 0 [1, 2, 3] 4
E29 TypeError
    ([1, 9], 2)
E30 True
E31 None
E32 []
E33 False True
E34 x ['y', 'z'] 9
E35 ['h', 'i', 1, 2] (1, 2)
E36 ['a', 1, 'b', 3, 'c', 5]
E37 True 3
E38 False True
E39 [2, 1]
E40 2
E41 1
E42 UnboundLocalError
E43 error
E44 1 2 1
E45 3 5
```

