# ProofOfSolve

Bitcoin puzzle hunts you solve with Google Street View: **[proofofsolve.com](https://proofofsolve.com)**

Each puzzle has 12 clues. Each clue leads to a spot on Google Street View that hides one word. The 12 words, in clue order, are the seed for a real Bitcoin wallet, and the first correct answer sent on the site wins it.

This page is the public record. It lists every prize wallet and answer fingerprint before a puzzle opens, and the answer, salt, winner and payout after it's solved. GitHub keeps the full history of every change, so anyone can see what was posted and when.

## Puzzles

The first three open **Saturday, October 24, 2026 at 6:00 AM Central (11:00 UTC)**, with about $125 in bitcoin each. Puzzle 4 opens **Saturday, October 31, 2026 at 6:00 AM Central (11:00 UTC)** and Puzzle 5 opens **Saturday, November 7, 2026 at 6:00 AM Central (12:00 UTC)**, with about $75 each. Click an address to see its balance on the blockchain.

| # | Puzzle | Entry | Prize wallet | Status |
|---|---|---|---|---|
| 1 | Meridian, Mississippi | Free | [bc1qphjz3cxsj8ls498uker4l703cqpg3fqx2g8tza](https://mempool.space/address/bc1qphjz3cxsj8ls498uker4l703cqpg3fqx2g8tza) | Opens Oct 24 |
| 2 | Mount Vernon, Virginia | Free | [bc1qqs2f7a3n6p3s694kh8rvcyccnf4n5n733nc0ut](https://mempool.space/address/bc1qqs2f7a3n6p3s694kh8rvcyccnf4n5n733nc0ut) | Opens Oct 24 |
| 3 | Alcatraz Island | $10 | [bc1q6830c0qx9975llvq8a0q0urmaxpa6yhgtgusx4](https://mempool.space/address/bc1q6830c0qx9975llvq8a0q0urmaxpa6yhgtgusx4) | Opens Oct 24 |
| 4 | Lafayette, Louisiana | $5 | [bc1qhkzhl98n8uf59an6zgvy9287q547h2aceycrfa](https://mempool.space/address/bc1qhkzhl98n8uf59an6zgvy9287q547h2aceycrfa) | Opens Oct 31 |
| 5 | Orange Beach, Alabama | $5 | [bc1qgzuefkmgr0x4usv5gwyyr7rk78tyz9vxjrpt0k](https://mempool.space/address/bc1qgzuefkmgr0x4usv5gwyyr7rk78tyz9vxjrpt0k) | Opens Nov 7 |

### Answer fingerprints (SHA-256)

| Puzzle | Fingerprint |
|---|---|
| 1 · Meridian, Mississippi | `f5398c3db138e13a56cbff7bd697aa6031f249d345e48bb95059bb534e7559ef` |
| 2 · Mount Vernon, Virginia | `d59268255545de753d9a4c00fb1bcdc7015e0b46fd337f5ba21a051ad89440a7` |
| 3 · Alcatraz Island | `5b9434ac8b5decbff40bd3e09d29d21446f866bf580d4415cef0de9703b54fe0` |
| 4 · Lafayette, Louisiana | `0acb960d15fe0b59e46e4e31c6f8aa749435b9f608b479dc313481ba1fa7a924` |
| 5 · Orange Beach, Alabama | `1c5fd6bd7a8818257aa9b1ce5865d4be60fee022e1bc7302a7c7648da534df42` |

The same list is in [puzzles.json](puzzles.json), for anyone who wants to check it with code.

## How the fingerprint works

1. The answer is the 12 seed words in lowercase, in clue order, with one space between words.
2. Before a puzzle opens, we make a random salt (24 letters and numbers in dashed groups, like `abcd-efgh-jkmn-pqrs-tuvw-xyz2`).
3. The fingerprint is the SHA-256 hash of the salt followed directly by the answer, with nothing in between.
4. We publish the fingerprint before the puzzle opens and keep the salt secret. Without the salt, nobody can use the fingerprint to test guesses.
5. After the puzzle is solved and paid out, we publish the answer and the salt here and on the site. Anyone can then run the hash and confirm it matches the fingerprint posted before the puzzle opened. That proves the answer never changed.

## Check a solved puzzle yourself

On the site, each solved puzzle has a **Check fingerprint** button. Or use your own computer:

**Mac or Linux (Terminal)**
```
printf '%s' 'THE-SALT' 'word1 word2 word3 word4 word5 word6 word7 word8 word9 word10 word11 word12' | shasum -a 256
```

**Any computer with Python**
```
python3 -c "import hashlib,sys; print(hashlib.sha256((sys.argv[1]+sys.argv[2]).encode()).hexdigest())" 'THE-SALT' 'word1 word2 ... word12'
```

The result should match the fingerprint in the table above.

## Results

No puzzles solved yet. Each result will list the winner's chosen name (or "Anonymous"), the solve time, the payout transaction, the answer and the salt.

## Rules in short

- Never visit a puzzle location in person. Everything can be solved from Street View.
- Free puzzles: 3 tries per email address every 24 hours. Paid puzzles: 3 tries per entry code every 24 hours.
- 18 or older. Full rules: [proofofsolve.com/rules](https://proofofsolve.com/rules)

Questions: support@proofofsolve.com
