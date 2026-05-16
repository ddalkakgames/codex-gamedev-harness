# Traceability Matrix

| Design Intent | System | Art Output | Engineering Output | Validation |
|---|---|---|---|---|
| Star shards guide the path | Star shard collection | Star shard mesh and glow material | Pickup actor | Player can follow shards to the goal |
| Riskier routes give better reward | Energy orb collection | Energy orb mesh and bonus VFX | Bonus pickup actor | Energy orbs are placed near risk |
| Player times hazard avoidance | Hazard system | Hazard device and warning range | Hazard actor | Collision causes failure |
| Short repeated play | Core loop | Result message and feedback | Timer/retry logic | Stage can be cleared in under 60 seconds |
| Goal is obvious | Goal system | Goal gate mesh and clear VFX | Goal actor | Overlap triggers clear |
| Game identity is visible | Art vertical slice | Character, platform, background assets | Replaceable Blueprint structure | First screen does not look like a template-only game |
