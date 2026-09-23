BOCCIA — STABLE RELEASE CHANNEL

Play: https://vvitalik25-ux.github.io/boccia-stable/
Development: https://github.com/vvitalik25-ux/boccia-game

Baseline: boccia-game commit 40e97de327e65dd366c82638159038f7c20d59a6.
Game files are copied from the published version. Experimental local ball physics is excluded.

RELEASE POLICY
This repository receives only completed, tested major releases. Develop and test changes in boccia-game first. There is no automatic synchronization from development. Update stable deliberately after reviewing the complete release. Preserve the previous release commit for rollback. GitHub Pages publishes main; every change to game files on main is a production release.

SHARED ONLINE SERVER
Both clients use https://boccia-online.v-vitalik25.workers.dev with protocol exact-1v1-v4. Do not deploy experimental or incompatible server changes to this shared Worker. Changes to server physics, rules, protocol, or session handling must remain compatible with stable and must be tested against both clients before release. Use a separate test Worker or versioned room engine for incompatible experiments.

VALIDATION
Check build consistency, controls, clocks, timing, tie-breaks, networking, offline play, and a real two-player online match including reconnect. Test mobile and desktop layouts before promoting a release. The inherited entry-tests.cjs uses an older transport mock and needs updating before it can serve as a release gate. Do not treat a failed test as a pass.

Initial verification: build, settings, timing, network, clock and tie-break checks passed. Live shared-server checks passed for room creation, joining, readiness, duplicate throw handling, restart and next match. This does not guarantee connectivity on every mobile network.
