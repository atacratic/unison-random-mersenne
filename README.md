# unison-random-mersenne
A pseudo-random number generator for Unison using the Mersenne Twister algorithm.

Get the code with
```
.> pull https://github.com/atacratic/unison-random-mersenne.git:.releases._v1 external.unison_random_mersenne.v1
```

More info...
```
> display README

  A pseudo-random number generator, using the Mersenne twister algorithm (MT19937).
  
  Do not use for cryptographic purposes. Do not assume it is hard for an attacker to predict future
  values based on previous program outputs.
  
  This *is* suitable for use for statistical purposes, for example Monte Carlo sampling, although it
  has some weaknesses - see the section 'Mersenne Twister' at https://www.pcg-random.org/other-rngs.html.
  
  See also https://en.wikipedia.org/wiki/Mersenne_Twister for more details.
  
  Usage examples:
  
    trunk.random.mersenne.doc.example1 =
    [: Return a list of 10 random Nat values in the range [0, @maxNat]. :]
    random.mersenne.collect nat.next defaultSeed 10
  
    trunk.random.mersenne.doc.example2 =
    [: A computation that draws on a stream of @Nat values. :]
    f : '{Ask Nat} Nat
    f _ =
      use Nat + /
      ask + ask + ask / 3
    [: Run the computation, using the PRNG to provide @Nat values in the range [0, 10] inclusive. :]
    mersenne.provide (nat.nextFromRange 0 11) defaultSeed f
  
  Note that fast performance is not a goal of this implementation, and indeed this algorithm is inherently
  slower than some of the alternatives, due to the state it keeps (624 integers.)
```

What you'll get...

```
  Added definitions:
  
    1.  type _base_additions.Nat32 (+3 metadata)
    2.  type random.mersenne.State (+3 metadata)
    3.  _base_additions.Nat32.Nat32                  : Nat -> #d97e0jhkmd (+3 metadata)
    4.  random.mersenne.State.State                  : [#d97e0jhkmd] -> #80gg7kgilb (+2 metadata)
    5.  README                                       : Doc (+2 metadata)
    6.  _base_additions.Int.inRange                  : Int -> Int -> Int -> Boolean (+3 metadata)
    7.  _base_additions.Int.inRange.doc              : Doc (+2 metadata)
    8.  _base_additions.Int.max                      : Int -> Int -> Int (+2 metadata)
    9.  _base_additions.Int.min                      : Int -> Int -> Int (+2 metadata)
    10. _base_additions.Nat.inRange                  : Nat -> Nat -> Nat -> Boolean (+3 metadata)
    11. _base_additions.Nat.inRange.doc              : Doc (+2 metadata)
    12. _base_additions.Nat.max                      : Nat -> Nat -> Nat (+2 metadata)
    13. _base_additions.Nat.min                      : Nat -> Nat -> Nat (+2 metadata)
    14. _base_additions.Nat32.*                      : #d97e0jhkmd
                                                     -> #d97e0jhkmd
                                                     -> #d97e0jhkmd (+2 metadata)
    15. _base_additions.Nat32.+                      : #d97e0jhkmd
                                                     -> #d97e0jhkmd
                                                     -> #d97e0jhkmd (+2 metadata)
    16. _base_additions.Nat32.<                      : #d97e0jhkmd
                                                     -> #d97e0jhkmd
                                                     -> Boolean (+2 metadata)
    17. _base_additions.Nat32.<=                     : #d97e0jhkmd
                                                     -> #d97e0jhkmd
                                                     -> Boolean (+2 metadata)
    18. _base_additions.Nat32.>                      : #d97e0jhkmd
                                                     -> #d97e0jhkmd
                                                     -> Boolean (+2 metadata)
    19. _base_additions.Nat32.>=                     : #d97e0jhkmd
                                                     -> #d97e0jhkmd
                                                     -> Boolean (+2 metadata)
    20. _base_additions.Nat32.Nat32.doc              : Doc (+2 metadata)
    21. _base_additions.Nat32.and                    : #d97e0jhkmd
                                                     -> #d97e0jhkmd
                                                     -> #d97e0jhkmd (+3 metadata)
    22. _base_additions.Nat32.and.doc                : Doc (+2 metadata)
    23. _base_additions.Nat32.bit                    : Nat -> #d97e0jhkmd (+3 metadata)
    24. _base_additions.Nat32.bit.doc                : Doc (+2 metadata)
    25. _base_additions.Nat32.bit.test1              : [Result] (+3 metadata)
    26. _base_additions.Nat32.bit.test2              : [Result] (+3 metadata)
    27. _base_additions.Nat32.bit.test3              : [Result] (+3 metadata)
    28. _base_additions.Nat32.clearBit               : #d97e0jhkmd
                                                     -> Nat
                                                     -> #d97e0jhkmd (+4 metadata)
    29. _base_additions.Nat32.clearBit.doc           : Doc (+3 metadata)
    30. _base_additions.Nat32.clearBit.test1         : [Result] (+4 metadata)
    31. _base_additions.Nat32.clearBit.test2         : [Result] (+4 metadata)
    32. _base_additions.Nat32.complement             : #d97e0jhkmd -> #d97e0jhkmd (+3 metadata)
    33. _base_additions.Nat32.complement.doc         : Doc (+2 metadata)
    34. _base_additions.Nat32.doc                    : Doc (+3 metadata)
    35. _base_additions.Nat32.isEven                 : #d97e0jhkmd -> Boolean (+2 metadata)
    36. _base_additions.Nat32.maxNat32               : #d97e0jhkmd (+2 metadata)
    37. _base_additions.Nat32.maxNat32.test          : [Result] (+3 metadata)
    38. _base_additions.Nat32.mkNat32                : Nat -> Optional #d97e0jhkmd (+2 metadata)
    39. _base_additions.Nat32.multiply.prop1         : [Result] (+3 metadata)
    40. _base_additions.Nat32.plus.prop1             : [Result] (+3 metadata)
    41. _base_additions.Nat32.shiftLeft              : #d97e0jhkmd
                                                     -> Nat
                                                     -> #d97e0jhkmd (+2 metadata)
    42. _base_additions.Nat32.shiftLeft.prop1        : [Result] (+3 metadata)
    43. _base_additions.Nat32.shiftRight             : #d97e0jhkmd
                                                     -> Nat
                                                     -> #d97e0jhkmd (+2 metadata)
    44. _base_additions.Nat32.shiftRight.prop1       : [Result] (+3 metadata)
    45. _base_additions.Nat32.toNat                  : #d97e0jhkmd -> Nat (+2 metadata)
    46. _base_additions.Nat32.truncate32             : Nat -> #d97e0jhkmd (+2 metadata)
    47. _base_additions.Nat32.truncate32.prop1       : [Result] (+3 metadata)
    48. _base_additions.Nat32.truncate32.prop2       : [Result] (+3 metadata)
    49. _base_additions.Nat32.xor                    : #d97e0jhkmd
                                                     -> #d97e0jhkmd
                                                     -> #d97e0jhkmd (+3 metadata)
    50. _base_additions.Nat32.xor.doc                : Doc (+2 metadata)
    51. _base_additions.all                          : (a ->{𝕖} Boolean)
                                                     ->{𝕖} [a]
                                                     ->{𝕖} Boolean (+2 metadata)
    52. _base_additions.any                          : (a ->{𝕖} Boolean)
                                                     ->{𝕖} [a]
                                                     ->{𝕖} Boolean (+2 metadata)
    53. _base_additions.iterate                      : Nat -> '{e} a ->{e} [a] (+3 metadata)
    54. _base_additions.iterate.doc                  : Doc (+2 metadata)
    55. _base_additions.iterate.test                 : [Result] (+3 metadata)
    56. _base_additions.none                         : (a ->{𝕖} Boolean)
                                                     ->{𝕖} [a]
                                                     ->{𝕖} Boolean (+2 metadata)
    57. _base_additions.until                        : (a ->{e} Boolean)
                                                     -> '{e} a
                                                     ->{e} a (+3 metadata)
    58. _base_additions.until.doc                    : Doc (+2 metadata)
    59. _base_additions.xor                          : Boolean -> Boolean -> Boolean (+3 metadata)
    60. _base_additions.xor.doc                      : Doc (+2 metadata)
    61. _base_additions.xor.test                     : [Result] (+3 metadata)
    62. random.mersenne.State.doc                    : Doc (+2 metadata)
    63. random.mersenne.collect                      : '{#tkpo8b6903 #80gg7kgilb} x
                                                     -> #d97e0jhkmd
                                                     -> Nat
                                                     -> [x] (+3 metadata)
    64. random.mersenne.collect.doc                  : Doc (+3 metadata)
    65. random.mersenne.defaultSeed                  : #d97e0jhkmd (+3 metadata)
    66. random.mersenne.defaultSeed.doc              : Doc (+2 metadata)
    67. random.mersenne.doc                          : Doc (+2 metadata)
    68. random.mersenne.doc.example1                 : [Nat] (+2 metadata)
    69. random.mersenne.doc.example1.test            : [Result] (+3 metadata)
    70. random.mersenne.doc.example2                 : Nat (+2 metadata)
    71. random.mersenne.handler                      : '{#tkpo8b6903 #80gg7kgilb} n
                                                     -> #d97e0jhkmd
                                                     -> Request (#q4pjprlin9 n) a
                                                     -> a (+3 metadata)
    72. random.mersenne.handler.doc                  : Doc (+2 metadata)
    73. random.mersenne.int.next                     : '{#tkpo8b6903 #80gg7kgilb} Int (+3 metadata)
    74. random.mersenne.int.next.doc                 : Doc (+2 metadata)
    75. random.mersenne.nat.next                     : '{#tkpo8b6903 #80gg7kgilb} Nat (+3 metadata)
    76. random.mersenne.nat.next.doc                 : Doc (+2 metadata)
    77. random.mersenne.nat.nextFromRange            : Nat
                                                     -> Nat
                                                     -> '{#tkpo8b6903 #80gg7kgilb} Nat (+3 metadata)
    78. random.mersenne.nat.nextFromRange.doc        : Doc (+2 metadata)
    79. random.mersenne.nat.nextFromRange.doc.caveat : Doc (+2 metadata)
    80. random.mersenne.nat.nextFromRange.prop       : [Result] (+3 metadata)
    81. random.mersenne.nat32                        : #d97e0jhkmd
                                                     -> '{#q4pjprlin9 #d97e0jhkmd} a
                                                     -> a (+3 metadata)
    82. random.mersenne.nat32.doc                    : Doc (+3 metadata)
    83. random.mersenne.nat32.handler                : #d97e0jhkmd
                                                     -> Request (#q4pjprlin9 #d97e0jhkmd) a
                                                     -> a (+2 metadata)
    84. random.mersenne.next                         : '{#tkpo8b6903 #80gg7kgilb} #d97e0jhkmd (+4 metadata)
    85. random.mersenne.next.doc                     : Doc (+3 metadata)
    86. random.mersenne.provide                      : '{#tkpo8b6903 #80gg7kgilb} n
                                                     -> #d97e0jhkmd
                                                     -> '{#q4pjprlin9 n} a
                                                     -> a (+3 metadata)
    87. random.mersenne.provide.doc                  : Doc (+3 metadata)
    88. random.mersenne.seed                         : #d97e0jhkmd
                                                     ->{#tkpo8b6903 #80gg7kgilb} () (+3 metadata)
    89. random.mersenne.seed.doc                     : Doc (+3 metadata)
    90. random.mersenne.seed.tests.size              : [Result] (+4 metadata)
    91. random.mersenne.test.comparison              : ∀ (). () ->{#fgaevis4bl} () (+4 metadata)
    92. random.mersenne.test.comparison.doc          : Doc (+3 metadata)
    93. random.mersenne.test.printOut                : [Nat]
                                                     -> Nat
                                                     ->{#fgaevis4bl} () (+3 metadata)
    94. random.mersenne.test.printOut.doc            : Doc (+3 metadata)
  
```
