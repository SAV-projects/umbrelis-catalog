# Umbrelis catalog

The list the Umbrelis Store reads: what can be installed (local models, ComfyUI lanes and model
files, voices, audio models, plugins, MCP servers, agents, skills, cloud providers, engines), with
sizes, SHA-256 digests, versions, licences and published prices.

Two files, nothing else:

- `catalog.json`: the catalog.
- `catalog.json.sig`: an ed25519 signature over the exact bytes of `catalog.json`, base64.

Umbrelis fetches both once a day and accepts the catalog only when the signature verifies against
the public key built into the app. A copy that does not verify is ignored and the last good one
stays. Fetching sends nothing about the user.

No model, workflow or program is hosted here. Every file a listing names downloads from its own
source: the Ollama registry, Hugging Face, the Comfy Registry, GitHub releases, nodejs.org.

The catalog is built and signed from the Umbrelis repository (`npm run store:catalog`,
`npm run store:sign`); see its `docs/STORE.md`.
