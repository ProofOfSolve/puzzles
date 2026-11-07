# ProofOfSolve

Bitcoin puzzle hunts you solve with Google Street View: **[proofofsolve.com](https://proofofsolve.com)**

Each puzzle has 12 clues. Each clue leads to a spot on Google Street View that gives one word from the BIP39 English list. The word may be written there, or it may be the name of something you see. The 12 words, in clue order, are the seed for a real Bitcoin wallet, and the first correct answer sent on the site wins it.

This page is the public record. It lists every prize wallet and answer fingerprint before a puzzle opens, and the answer, salt, winner and payout after it's solved. GitHub keeps the full history of every change, so anyone can see what was posted and when.

## Puzzles

Puzzles 1 and 2 opened **Saturday, October 24, 2026 at 6:00 AM Central (11:00 UTC)**. From then on, one puzzle opens each Saturday at **9:00 AM Central**: Puzzle 3 on **October 31, 2026 (14:00 UTC)**, Puzzle 4 on **November 7, 2026 (15:00 UTC)**, Puzzle 5 on **November 14, 2026 (15:00 UTC)**, Puzzle 6 on **November 21, 2026 (15:00 UTC)**, and Puzzle 7 on **November 28, 2026 (15:00 UTC)**. The places of Puzzles 4 to 7 stay hidden until each one opens. Puzzles 1 to 3 carry about $125 in bitcoin each, Puzzles 4 to 6 about $75 each, and Puzzle 7 about $50. Click an address to see its balance on the blockchain.

| # | Puzzle | Entry | Prize wallet | Status |
|---|---|---|---|---|
| 1 | Meridian, Mississippi | Free | [bc1qphjz3cxsj8ls498uker4l703cqpg3fqx2g8tza](https://mempool.space/address/bc1qphjz3cxsj8ls498uker4l703cqpg3fqx2g8tza) | **Solved** Oct 25 · [paid out](https://mempool.space/tx/b41c387d8b8f3e331e96fd1dcbed24af426e6ea6dba12138d52483304c41407a) |
| 2 | Alcatraz Island | Free | [bc1q6830c0qx9975llvq8a0q0urmaxpa6yhgtgusx4](https://mempool.space/address/bc1q6830c0qx9975llvq8a0q0urmaxpa6yhgtgusx4) | **Solved** Oct 24 · [paid out](https://mempool.space/tx/8cb8dd217cf10b3641cf5df37816b3ed837425020c2a5ea4fb9aa9d150df271c) |
| 3 | Mount Vernon, Virginia | Free | [bc1qqs2f7a3n6p3s694kh8rvcyccnf4n5n733nc0ut](https://mempool.space/address/bc1qqs2f7a3n6p3s694kh8rvcyccnf4n5n733nc0ut) | **Solved** Oct 31 · [paid out](https://mempool.space/tx/728920e3007ab127496be3c568a04d7c7243fe4c754a54462bcd819e2301e317) |
| 4 | Lafayette, Louisiana | Free | [bc1qhkzhl98n8uf59an6zgvy9287q547h2aceycrfa](https://mempool.space/address/bc1qhkzhl98n8uf59an6zgvy9287q547h2aceycrfa) | **Solved** Nov 7 · [paid out](https://mempool.space/tx/835fd988a61bf6ef75871e4cfcfe6982369796869a97a96747bc812d01392044) |
| 5 | Hidden until reveal day | Free | [bc1qgzuefkmgr0x4usv5gwyyr7rk78tyz9vxjrpt0k](https://mempool.space/address/bc1qgzuefkmgr0x4usv5gwyyr7rk78tyz9vxjrpt0k) | Opens Nov 14 |
| 6 | Hidden until reveal day | Free | [bc1qr9w0wdd2nqpmgdwe2x7nm82kl9aqyusnru8y2z](https://mempool.space/address/bc1qr9w0wdd2nqpmgdwe2x7nm82kl9aqyusnru8y2z) | Opens Nov 21 |
| 7 | Hidden until reveal day | TBD | [bc1qytrawhjlh2kfhzesgyj6e748l0fpekz26spvj6](https://mempool.space/address/bc1qytrawhjlh2kfhzesgyj6e748l0fpekz26spvj6) | Opens Nov 28 |

### Answer fingerprints (SHA-256)

| Puzzle | Fingerprint |
|---|---|
| 1 · Meridian, Mississippi | `f5398c3db138e13a56cbff7bd697aa6031f249d345e48bb95059bb534e7559ef` |
| 2 · Alcatraz Island | `5b9434ac8b5decbff40bd3e09d29d21446f866bf580d4415cef0de9703b54fe0` |
| 3 · Mount Vernon, Virginia | `d59268255545de753d9a4c00fb1bcdc7015e0b46fd337f5ba21a051ad89440a7` |
| 4 · Lafayette, Louisiana | `0acb960d15fe0b59e46e4e31c6f8aa749435b9f608b479dc313481ba1fa7a924` |
| 5 · Hidden until reveal day | `1c5fd6bd7a8818257aa9b1ce5865d4be60fee022e1bc7302a7c7648da534df42` |
| 6 · Hidden until reveal day | `6696ec098a09b0541bcb091fafd5f903b7ea6cb70e77e60f706b5293740e2f26` |
| 7 · Hidden until reveal day | `186ffdc2faab03160d14d30254a29b5e9fca568993498b3195aa680afaa733b7` |

The same list is in [puzzles.json](puzzles.json), for anyone who wants to check it with code.

## Corrections

If a clue ever needs fixing (for example, because Google changed the Street View imagery it depends on), the fix goes on the puzzle's page under Corrections, right above the clues, and is listed here with its date.

None so far.

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

Each result lists the winner's chosen name (or "Anonymous"), the solve time, the payout transaction, the answer and the salt.

### 1 · Meridian, Mississippi

- **Solved:** Sunday, October 25, 2026 at 6:31:51 AM Central (11:31:51 UTC), 24 hours 31 minutes after it opened
- **Winner:** trittic
- **Payout:** [b41c387d8b…4c41407a](https://mempool.space/tx/b41c387d8b8f3e331e96fd1dcbed24af426e6ea6dba12138d52483304c41407a), 151,458 sats to the winner's wallet
- **Answer:** `rich hill palm slide waste antique head horse flag pool eagle track`
- **Salt:** `cqjn-4r9u-zbf2-msmx-tt36-7qgp`
- **Check:** SHA-256 of the salt followed by the answer gives `f5398c3db138e13a56cbff7bd697aa6031f249d345e48bb95059bb534e7559ef`, the fingerprint posted before it opened.
- **Every spot, with pictures:** [proofofsolve.com/puzzle?id=meridian](https://proofofsolve.com/puzzle?id=meridian)

### 2 · Alcatraz Island

- **Solved:** Saturday, October 24, 2026 at 6:31:38 AM Central (11:31:38 UTC), 31 minutes after it opened
- **Winner:** Anonymous
- **Payout:** [8cb8dd217c…50df271c](https://mempool.space/tx/8cb8dd217cf10b3641cf5df37816b3ed837425020c2a5ea4fb9aa9d150df271c), 151,527 sats to the winner's wallet
- **Answer:** `island bird sleep zero bar prison only club peace city phone toilet`
- **Salt:** `a9d4-6sq5-k6mr-2tfg-rbur-jk6z`
- **Check:** SHA-256 of the salt followed by the answer gives `5b9434ac8b5decbff40bd3e09d29d21446f866bf580d4415cef0de9703b54fe0`, the fingerprint posted before it opened.
- **Every spot, with pictures:** [proofofsolve.com/puzzle?id=alcatraz](https://proofofsolve.com/puzzle?id=alcatraz)

### 3 · Mount Vernon, Virginia

- **Solved:** Saturday, October 31, 2026 at 12:00:02 PM Central (17:00:02 UTC), 3 hours after it opened
- **Winner:** Nightsolver
- **Payout:** [728920e300…2301e317](https://mempool.space/tx/728920e3007ab127496be3c568a04d7c7243fe4c754a54462bcd819e2301e317), 151,346 sats to the winner's wallet
- **Answer:** `wall oval brick river vault pink dog corn august other arrow wheat`
- **Salt:** `tq47-g89b-mtsm-mrzu-xrv7-uhsj`
- **Check:** SHA-256 of the salt followed by the answer gives `d59268255545de753d9a4c00fb1bcdc7015e0b46fd337f5ba21a051ad89440a7`, the fingerprint posted before it opened.
- **Every spot, with pictures:** [proofofsolve.com/puzzle?id=mount-vernon](https://proofofsolve.com/puzzle?id=mount-vernon)

### 4 · Lafayette, Louisiana

- **Solved:** Saturday, November 7, 2026 at 9:47:32 AM Central (15:47:32 UTC), 47 minutes after it opened
- **Winner:** Tres
- **Payout:** [835fd988a6…01392044](https://mempool.space/tx/835fd988a61bf6ef75871e4cfcfe6982369796869a97a96747bc812d01392044), 92,290 sats to the winner's wallet
- **Answer:** `hockey arch hospital bike horse love chicken ranch shop pink property coin`
- **Salt:** `cqgx-jc5y-48kq-uaue-ufa6-dvc4`
- **Check:** SHA-256 of the salt followed by the answer gives `0acb960d15fe0b59e46e4e31c6f8aa749435b9f608b479dc313481ba1fa7a924`, the fingerprint posted before it opened.
- **Every spot, with pictures:** [proofofsolve.com/puzzle?id=puzzle-4](https://proofofsolve.com/puzzle?id=puzzle-4)

## Rules in short

- Never visit a puzzle location in person. Everything can be solved from Street View.
- Free puzzles: 3 tries per email address every 24 hours. Paid puzzles: 3 tries per entry code every 24 hours.
- 18 or older. Full rules: [proofofsolve.com/rules](https://proofofsolve.com/rules)

Talk about the puzzles with other players on our message board: **[proofofsolve.com/board](https://proofofsolve.com/board)**.

Questions: support@proofofsolve.com
