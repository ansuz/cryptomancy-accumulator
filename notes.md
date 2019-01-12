P = 3
Q = 5
N = 15
G = 17

U = [7, 11, 13] = 1001
C = 2

# reveal one of the members of U
R = 7
S = 143 # the product of all the remaining elements in U

# given G and S (where N is publically known)
P = mod(G^S, N)
P = 8

C' = mod(P^R, N)
C' = 2

---

qminus1 = 4
pminus1 = 2
totient = 8

exp = G

[7, 11, 13].forEach(function (prime) {
    exp *= prime;
    exp %= totient;
}); //  exp = 1

// as above
7 % 8 = 7
7 * 11 % 8 = 5
5 * 13  % 8 = 1

---

primes = [7, 11, 13]

witness1 = function (i) {
    var inv = primes[i].modInverse(totient).multiply(exp).mod(totient);
    return G.modPow(inv, N);
};

witness1(1)  // inv = 3
 // G.modPow(inv, N)
 // 8

---

// should be equivalent to
witness2 = function (j) {
    var wit = G;
    primes.forEach(function (prime, i) {
        if (i === j) { return; }
        wit = wit.modPow(primes[j], N);
    });
    return wit;
};

witness(1)
// G.modPow(7, N).modPow(13, N); // 8

---

// verification


