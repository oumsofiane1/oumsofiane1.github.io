## How to Break the Internet?

What if I told you that solving just *one* mathematical problem could dismantle most of the internet? Just like Neo in *The Matrix*, you'd begin to see the underlying code behind everything.

But first, meet Alice and Bob — two students in the same class. Alice sits in the front row, and Bob three rows back. Bob wants to pass romantic notes to Alice. The problem? He has to pass them through Samira, who sits in the middle... and Bob doesn’t trust Samira not to peek.

So Alice, being astute, comes up with a clever trick:

> “Just shift each letter in your message by 3. Like ‘a’ becomes ‘d’, ‘b’ becomes ‘e’, and so on. ‘I love you’ becomes ‘L oryh brx’. I’ll shift the letters back when I get it.”

That worked — until things got complicated. Alice started flirting with David and Stacy, who sat behind Bob. Now *everyone* was passing secret notes, and Alice didn’t want them reading each other’s messages. She could use a different shift for each person — maybe 5 for David, 7 for Stacy — but she'd need to remember who used what, and how to decode it.

That’s when her friend Beka had an idea:

> “Why not use *math* to handle this? You can create a public method everyone uses to encrypt, but only *you* can decrypt.”

Beka explained: “Pick two numbers — say 17 and 26. Share them with everyone. To send you a message, your friends multiply each letter’s alphabet index by 17, then take the remainder when dividing by 26. You, and only you, know the secret number 23 — the modular inverse of 17 mod 26. You can use it to reverse the encryption.”

Let’s see this in action with a number:
Say Bob wants to send you the number `x = 2`.

* Step 1: Encrypt → `2 * 17 mod 26 = 34 mod 26 = 8`
* Step 2: Decrypt → `8 * 23 mod 26 = 184 mod 26 = 2`

It works because 17 and 23 are modular inverses modulo 26:
`17 * 23 ≡ 1 (mod 26)`

Which means:

```
H      = m * 17 mod 26
H * 23 = m * 17 * 23 mod 26 = m * 1 mod 26 = m
```

Voilà — a one-way door only Alice can walk through.

---

This trick of using modular inverses is powerful, but it isn’t secure when the numbers are small. If everyone knows 17 and 26, it’s not hard to figure out 23. So how can we make this truly secure?

Enter Euler’s theorem and the RSA algorithm — the backbone of modern internet encryption.

### How RSA Works (Simplified)

1. **Choose two large prime numbers**, `p` and `q`
2. **Compute** `n = p * q` and `ϕ(n) = (p - 1)(q - 1)`
3. **Pick a number** `e` such that `1 < e < ϕ(n)` and `gcd(e, ϕ(n)) = 1`
4. **Find `d`**, the modular inverse of `e` mod `ϕ(n)`

Now:

* Public key = `(e, n)`
* Private key = `(d, n)`

To **encrypt**:
`H = m^e mod n`

To **decrypt**:
`m = H^d mod n`

This works because:
`(m^e)^d ≡ m (mod n)`

And why is this secure? Because while `e` and `n` are public, finding `d` without knowing `ϕ(n)` — which requires factoring `n` — is extremely hard when `n` is a product of two very large primes.

---

This mathematical rabbit hole is why encryption keeps your bank info, DMs, and private memes safe. Unless, of course, someone ever *does* break the math…

Or invents a quantum computer that can.
