# Poppy agent conformance test identity

A throwaway test identity for a Personal Agent, used for Personal Agent Protocol (Poppy)
conformance runs.

This repository holds only the public client metadata (`agent.json`) and the public key
(`jwks.json`) of a test Personal Agent. **The private key is not included and is not published
anywhere.** The identity holds no account at any Company, has access to nothing, and can do only
one thing: sign a delegation for a conformance run.

It exists because an agent-side conformance checker needs a reachable `jwks_uri` to verify a
delegation against, as spec 5.2 step 1 describes. A run that uses an identity nobody can fetch
leaves that rule unjudgeable, so the checker abstains on it and says the abstention is its own
limit. This identity closes that.

The checker itself is at https://github.com/vishkaty/poppy-agent-conformance, Apache 2.0. It
checks a Personal Agent against published Personal Agent Protocol 1.0, which is the side the
protocol authors own kit does not cover: their kit checks a Company.

No verdict about anyone else software is published from that checker, and none will be. A report
goes to the builder who asked for the run and nowhere else.
