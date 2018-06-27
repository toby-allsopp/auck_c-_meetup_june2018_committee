# June 2018 C++ Committee Meeting

Toby Allsopp

Auckland C++ Meetup

2018-06-27

---

# The Committee

----

![WG21 Structure](https://isocpp.org/files/img/wg21-structure-2018-03.png)

----

## Study Groups


* SG1, Concurrency
* _SG2, Modules_
* _SG3, File System_
* _SG4, Networking_
* SG5, Transactional Memory
* SG6, Numerics
* SG7, Compile-time programming
* _SG8, Concepts_

----

* _SG9, Ranges_
* _SG10, Feature Test_
* _SG11, Databases_
* SG12, UB & Vulnerabilities
* _SG13, HMI (Human/Machine Interface)_
* SG14, Game Development & Low Latency
* SG15, Tooling
* SG16, Unicode

----

## Meetings

* 2 or 3 in-person meetings a year
* Meetings open to public but not recorded (ISO rules)
* Next one is in San Diego in November
* See https://isocpp.org/std/meetings-and-participation for lots more information

---

# Added to C++20 in Rapperswil

----

## Contracts

* Voted into the Working Draft for C++20
* [P0380](https://wg21.link/P0380)

```c++
int& push(queue& q, int i)
  [[expects: !q.full()]]
  [[ensures: !q.empty()]]
  [[ensures ret: ret == i]]
{
  // ...
  [[assert: q.ok()]];
}
```

----

## Concepts

* Standard library concepts voted in: [P0898](https://wg21.link/P0898)

```c++
template <class T, class U>
concept Same = /* see below */ ;
template <class Derived, class Base>
concept DerivedFrom = /* see below */ ;
template <class From, class To>
concept ConvertibleTo = /* see below */ ;
template <class T, class U>
concept CommonReference = /* see below */ ;
template <class T, class U>
concept Common = /* see below */ ;
template <class T>
concept Integral = /* see below */ ;
template <class T>
concept SignedIntegral = /* see below */ ;
template <class T>
concept UnsignedIntegral = /* see below */ ;
template <class LHS, class RHS>
concept Assignable = /* see below */ ;
template <class T>
concept Swappable = /* see below */ ;
template <class T, class U>
concept SwappableWith = /* see below */ ;
template <class T>
concept Destructible = /* see below */ ;
template <class T, class... Args>
concept Constructible = /* see below */ ;
template <class T>
concept DefaultConstructible = /* see below */ ;
template <class T>
concept MoveConstructible = /* see below */ ;
template <class T>
concept CopyConstructible = /* see below */ ;
template <class B>
concept Boolean = /* see below */ ;
template <class T, class U>
concept WeaklyEqualityComparableWith = /* see below */ ;
template <class T>
concept EqualityComparable = /* see below */ ;
template <class T, class U>
concept EqualityComparableWith = /* see below */ ;
template <class T>
concept StrictTotallyOrdered = /* see below */ ;
template <class T, class U>
concept StrictTotallyOrderedWith = /* see below */ ;
template <class T>
concept Movable = /* see below */ ;
template <class T>
concept Copyable = /* see below */ ;
template <class T>
concept Semiregular = /* see below */ ;
template <class T>
concept Regular = /* see below */ ;
template <class F, class... Args>
concept Invocable = /* see below */ ;
template <class F, class... Args>
concept RegularInvocable = /* see below */ ;
template <class F, class... Args>
concept Predicate = /* see below */ ;
template <class R, class T, class U>
concept Relation = /* see below */ ;
template <class R, class T, class U>
concept StrictWeakOrder = /* see below */ ;
```

----

## Class non-type template parameters

* C++17 (and earlier): Can only be integral types (or references or pointers)
* C++20: Can also be literal types with defaulted `operator<=>`
* [P0732](https://wg21.link/P0732)

----

## Others

* Feature test macros: [P0941](https://wg21.link/P0941)
* Conditional explicit: [P0892](https://wg21.link/P0892)
* Virtual calls in constant expressions: [P1064](https://wg21.link/P1064)
* `atomic_ref`: [P0019](https://wg21.link/P0019)
* `shift_left` and `shift_right` algorithms: [P0769](https://wg21.link/P0769)
* `type_identity`: [P0887](https://wg21.link/P0887)
* `ispow2`, `ceil2`, `floor2`, `log2p1`: [P0556](https://wg21.link/P0556)
* `bit_cast`: [P0476](https://wg21.link/P0476)

---

# Not (yet) in C++20

----

## Reflection

* Draft Reflection TS sent for National Body ballot: [N4746](https://wg21.link/N4746)
* Includes facilities for static reflection: [P0194](https://wg21.link/P0194)
* Targeting C++23 or C++26

----

## Concepts terse syntax

* Verbose syntax is already in C++20 WD
* Competing proposals: [P0745](https://wg21.link/P0745), [P1079](https://wg21.link/P1079)

----

## Modules

* Work on the TS is ongoing

----

## Coroutines

* Not quite consensus to merge the TS
* Competing proposal: [P1063](https://wg21.link/P1063)

----

## Ranges

* Core concepts merged
* Progress being made on rest of Ranges TS (still expected for C++20)

----

## 2D Graphics

* No consensus to continue work on it: [P0267](https://wg21.link/P0267)
