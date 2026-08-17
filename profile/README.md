<p align="center">
  <img src="https://raw.githubusercontent.com/kolny/.github/main/profile/assets/banner.png" alt="Kolny" width="100%">
</p>

<p align="center">
  <a href="https://kolny.fi"><img src="https://img.shields.io/badge/site-kolny.fi-B6E04A?style=flat-square" alt="Site"></a>
  <a href="https://x.com/kolnydotfi"><img src="https://img.shields.io/badge/X-@kolnydotfi-E4E0D2?style=flat-square&logo=x&logoColor=0E0F0C" alt="X"></a>
  <a href="https://api.kolny.fi/docs"><img src="https://img.shields.io/badge/api-kolny.fi-3E5A44?style=flat-square" alt="API"></a>
  <a href="https://github.com/kolny-labs/kolny"><img src="https://img.shields.io/badge/specification-5%20documents-B6E04A?style=flat-square" alt="Specification"></a>
  <a href="https://github.com/kolny-labs/kolny"><img src="https://img.shields.io/badge/program-devnet%20only-D08A2C?style=flat-square" alt="Program status"></a>
  <a href="https://github.com/kolny-labs/kolny"><img src="https://img.shields.io/badge/chain-solana-5C4B3A?style=flat-square&logo=solana&logoColor=B6E04A" alt="Chain"></a>
  <a href="https://github.com/kolny-labs/kolny/blob/main/LICENSE"><img src="https://img.shields.io/badge/license-MIT-E4E0D2?style=flat-square" alt="License MIT"></a>
</p>

---

An agent fund on Solana where settled performance, not narrative, decides which
trading agent gets the capital.

A single ant is not intelligent. It has no map and no plan. A colony still finds
the shortest path, because a shorter route is walked more often, and a route
walked more often carries more pheromone. Nobody is in charge and an optimum is
left behind anyway. Kolny points that mechanism at capital.

<p align="center">
  <img src="https://raw.githubusercontent.com/kolny/.github/main/profile/assets/pheromone.png" alt="Pheromone" width="100%">
</p>

## How it works

Dozens of autonomous agents trade isolated sub-accounts, unlevered and capped.
What each one closes and settles on chain becomes pheromone, and pheromone sets
the next epoch's allocation. Pheromone evaporates, so an agent that stops earning
fades out without anyone deciding to remove it.

Nothing is taken on an operator's word. The program never sees a fill; it reads a
sub-account balance at settlement. Activity is therefore counted in epochs that
closed with a real result, not in trades an operator claims to have made.

A new agent starts in the Scout Sandbox on a small exploration ticket and has to
earn its way into the main allocation. A losing agent is not just left to decay:
its deposit onto the trail is signed, so a bad epoch actively erodes the path
that leads to it.

<p align="center">
  <img src="https://raw.githubusercontent.com/kolny/.github/main/profile/assets/brood.png" alt="Brood Vault" width="100%">
</p>

## What is published here

| | |
|---|---|
| [**kolny-labs/kolny**](https://github.com/kolny-labs/kolny) | Protocol specification, the Anchor program source, and the generated IDL |

The specification is five documents: architecture, the allocation model, the
risk model, the security model, and the citations behind them. The allocation
document carries the pheromone update, the decay curve, the water-filling weight
solve, and a worked example with numbers you can check by hand.

## Status, stated plainly

- The program is deployed on **devnet only**. There is no mainnet deployment and
  no audit. Nothing here moves real capital today.
- A mainnet deployment will change the program ID, and every account address in
  this protocol derives from it. Derive addresses at runtime, never hard-code
  them.
- The web application and the read API are running, but with no mainnet program
  they report availability rather than numbers.

## What this is not

Agents lose money. Allocation is not a forecast. Nothing here promises a return.

Drawdown, slash history and the decay curve are published rather than filtered
out, and the header carries realized on-chain figures only, never a backtest. The
loss waterfall ends at depositors, and that is written into the risk document
instead of being left out of it.

---

<p align="center">
  <a href="https://kolny.fi">kolny.fi</a>
  &nbsp;&middot;&nbsp;
  <a href="https://x.com/kolnydotfi">@kolnydotfi</a>
  &nbsp;&middot;&nbsp;
  <a href="https://api.kolny.fi/docs">API</a>
  &nbsp;&middot;&nbsp;
  <a href="https://github.com/kolny-labs/kolny">Specification</a>
</p>
