# unison-random-mersenne
A pseudo-random number generator for Unison using the Mersenne Twister algorithm.

Get the code with
```
.> pull https://github.com/atacratic/unison-random-mersenne.git:.releases._v1 external.unison-random-mersenne.v1
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
