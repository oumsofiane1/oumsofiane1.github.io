# How to break the internet ?

What if I told you that solving one mathematical function could dismantle most of the internet ? Just like Neo, you will see what's behind the matrix. But before, let's talk about Alice and Bob and their secret love affair.

Alice and Bob are in the same class - Alice sits in the first row while Bob sits in the third row. Bob wanted to share romantic notes with Alice, but to do so, he would have to pass his notes through Samira who sits on the second row. But Bob had a problem, he didn't want anyone else to read his notes especially Samira !

As he discussed his dillema, Alice astute as she is, proposed a solution.

Alice suggested "When you send me a note, just shift every letter by 3 positions. example 'a' becomes 'd', 'z' becomes 'c' so 'I love you' becomes 'L oryh brx', then when I get the message I'll just shift it back by 3."

This has worked, until Alice started to entertain a somewhat flirty relationship with David and Stacy both sat behind Bob, obviously she didn't want David's messages read by Bob, she didn't want anybody to read each others messages! she could choose a different number for each person, like shift by 5, by 7..., but then she will have to keep a different number per person, and will have to know who sent what to read it.

This is when one of her girlfriends, Beka, gave her a great idea: what if she used the power of math and number theory to build a system for sending secret messages, and still be the only one capable of decrypting them?

"You can share two public numbers, 17 and 26, with your friends," Beka suggested. "When they want to send you a secret message, they should do the following: Multiply each letter's position in the alphabet by 17 and then find the remainder when dividing by 26. When you receive the message, multiply each number by 23 and find the remainder when dividing by 26, and you'll see what they wrote. As long as you don't share the number 23 with them, they won't be able to read each other's messages."

"How does this work ?" Inquired Alice.

Let's illustrate with an example, say we want to send the number x = 2 as a secret.
```math
2 * 17 mod 26 = 34 mod 26 = 8 (because 34 / 26 = 1 with a remainder of 8)
8 * 23 mod 26 = 184 mod 26 = 2.
```

This works because 23 is the reverse multiplicative of 17 mod 26, which means 
```math
17*23 = 1 (mod 26).
```
When we encrypt a message m; `m * 17 mod 26 = encrypted_message (H)`
```math
H      = m * 17 mod 26
H * 23 = m * 17 * 23 mod 26
       = m * 1 mod 26 
       = m (as long as 0 < m < 26)
```

While this method illustrates the main idea behind asymmetric encryption, it is not secure.
Given n and m, it is possible to find the multiplicative inverse of `m mod n`. 
Anyone with the public key can find the value for the private key. 

Given p and q as two large primary numbers, and n = pq

1. Define ϕ(n) = (p-1) * (q-1)
 
2. Choose e such as 1 < e < ϕ(n) and  e is relatively prime to ϕ(n).

3. Find d such as d is a multiplicative inverse of e mod ϕ(n)


Then,

m<sup>ed</sup> ≡ m mod n

We can encrypt messages by doing H = m<sup>e</sup> mod n to encrypt, and then to decrypt we can use H<sup>d</sup> mod n to decrypt. 

We share (e,n) as our public key, and keep (d, n) as our private key. d is no longer obvious to find, because it is  the reverse multiplicative of `e mod ϕ(n)`,  to find, one would need to know p, q, and to know p and q, one would must factorize n, which is computationally hard for large numbers.