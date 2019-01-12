# cryptomancy-accumulator

This module implements a cryptographic accumulator, which allows the holder of a private key to prove that a given token is or is not contained within a set without revealing the contents of the set.

Its API is currently unstable.

## API

### hashToPrime (token /* Uint8Array */, cb (error, prime /* Uint8Array */))

### genKeys (source (PRNG), cb({P /* bigint */, Q /* bigint */, N /* bigint */, Totient /* bigint */}))

### accumulate (key /* privateKey */, items /* array of Uint8Arrays */, cb({Acc /* bigint */, Primes /* array of bigints */, Witnesses /* array of bigints */ }))

#### accumulate.publically (publicKey /* bigint */, items /* array of Uint8Arrays */, cb ({Acc /* bigint */, Primes /* array of bigints */, Witnesses /* array of bigints */ }))

### verify (publicKey /* bigint */, acc /* bigint */, witness /* bigint */, item /* Uint8Array */, cb(err, bool))


