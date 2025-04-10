A pseudo-random generator $G$ is an efficient (which means it runs in polynomial time), **deterministic** algorithm that transforms a short uniform string, into a longer, **uniform-looking** output string.

The key point is that it is deterministic. In this sense, if you feed the same seed into a Pseudo-random generator, then it will output the same output string. This is the exact meaning of a deterministic function.
# But What Exactly is a Pseudo-Random String?
The basic realization is that a pseudo-random string should be able to pass all efficient statistical distinguishing tests. 
## What is a Distribution in Strings
A distribution basically means that you are assigning a probability to every string.
## What is Sampling?
Sampling basically means picking a string from this distribution according to the probability distribution.
# How Do We Judge Pseudo-Randomness
Basically, we need to find and ensure that informally,
> A pseudo-random string is just as good as a uniform-string.

This is basically the main intuition behind the whole concept as *as long as we consider polynomial-time observers.*
[[Stream Ciphers]]
# A Secure Private Key Encryption Scheme using a Pseudo-Random Generator
Consider the one-time pad encryption scheme. This is the strongest mode of encryption that we will ever be able to achieve. But how do we do this without having a key that is at least as long as the message?

We can make use of a pseudo-random generator to make sure we can generate a key of the required length.

If a PPT-adversary was able to distinguish between the two messages, then that would implicitly mean that he is being able to distinguish between the pseudo-random string and the uniform string in polynomial time - which goes against the definition of Pseudo-random generator G.
# Pseudo-Random Functions
These are the generalizations of pseudo-random generators. But it does not make any sense to call a function random, does it?
## How Does a Keyed Function Induce Pseudo-Randomness?
A keyed function $F$ is known as pseudo-random if the function $F_k$ is indistinguishable from a function chosen uniformly at random from the set of all functions having the same domain and range.

There are a total of $2^{n\cdot 2^n}$ uniform functions that map n-bit strings to other n-bit strings. This can be very easily calculated with a little permutation and combination mathematics. There is also a cool and different way to look as there being a string of length $n2^n$. Each of this string represents a single string.
## How Do You Define A Pseudo-Random Function?
If every polynomial time distinguishing algorithm outputs 1 with almost the same probability as for a uniform function picked that has the same domain and the same range.

![[Pseudo-Random Function Check.png]]
# Pseudo-Random Permutations

^617895

^b19181
Let there be a set of all permutations (which are also basically just **bijections**). From prior mathematics, a bijection is simply just a function that is both one-one and onto. 

So now there is a restriction given the fact that the function is one-one. This means that the total number of functions that are possible is
$$(2^n)!$$
Let there be a function $F$ that is keyed. It is called a keyed permutation if the length of the inputs and the lengths of the outputs are all equal and the function is one-one.
If the length of the key is also the same, then it is also known as a **length-preserving keyed function**.
# A Modified One-Time Pad Encryption Scheme Based on Pseudo-Random Functions
Let's just say that there is a scheme in which there is a pseudo-random function keyed function F that is being used. A random string $r$ is sent into this pseudo-random permutation and that one-time pad is used in order to encrypt a message. We need to show and prove that this encryption scheme is CPA-secure.

While being transmitted, both the encrypted message as well as the random string are sent. This random string is then used on the receiving end to decrypt the message again.

Now assume that we have the same algorithm except that instead of the case with the pseudo-random function, we use a truly random function $f$. This would be the modification to our encryption scheme. 
