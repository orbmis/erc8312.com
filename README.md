# Website for ERC-8312 — Bounded Agent Actions

The website for **[ERC-8312: Bounded Agent Actions](https://github.com/0x2kNJ/ERCs/blob/7678357d01a787b7d99ae277ad0cadf44e1beabc/ERCS/erc-8312.md)** — a proposed Ethereum standard for on-chain *envelopes* that bind agent intent to a verifiable state cursor across calls and across protocols.

🔗 **Live site:** [erc8312.com](https://erc8312.com)

## About the standard

ERC-8312 defines a standard interface (`IBoundedAgentAction`) for registering and updating **bounded agent actions**. Each action is an on-chain envelope containing a principal, an immutable capability commitment, a mutable state commitment (the *cursor*), an expiry, and lifecycle status.

Unlike a per-call check, an envelope *meters* the authority an agent has consumed across many actions and across protocols — reducing integration complexity between upstream authorization standards and downstream invariant-maintaining substrates from `O(upstream × downstream)` to `O(upstream + downstream)`.

- **Status:** Draft
- **Type:** Standards Track (ERC)
- **Requires:** ERC-165
- **Authors:** Matthias Hauser ([@0x2kNJ](https://x.com/0x2kNJ)), Simon Brown ([@orbmis](https://x.com/orbmis))
- **Discussion:** [Ethereum Magicians](https://ethereum-magicians.org/t/erc-8312-bounded-agent-actions/28851)
- **Reference implementation:** [Atlas-Protocol-AI/bounded-agent-actions](https://github.com/Atlas-Protocol-AI/bounded-agent-actions)

## This repository

A single self-contained static page. No build step, no dependencies, no framework.

```
├── index.html      # the entire site (markup, CSS, and JS inline)
├── robots.txt      # discourages search-engine indexing
├── erc-8312.md     # the ERC specification source
└── README.md
```

### Features

- One-page overview: problem, solution, concepts, interface, composability, and the budget substrate profile
- Dark / light theme toggle with system-preference detection and `localStorage` persistence
- Fully responsive, no external JS dependencies (fonts loaded from Google Fonts)

## Running locally

Because it's a static file, just open it directly:

```sh
open index.html
```

Or serve it over HTTP (useful for testing):

```sh
python3 -m http.server 8000
# then visit http://localhost:8000
```

## Deployment

The site is deployed on **Vercel** via the GitHub integration — every push to `main` triggers an automatic deploy. There is no build command or output directory to configure; Vercel serves `index.html` from the repository root.

## License

The ERC-8312 specification is released under [CC0 1.0](https://creativecommons.org/publicdomain/zero/1.0/) (public domain). This website's content follows the same waiver.
