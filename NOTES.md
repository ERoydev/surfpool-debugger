

# Overriding dependencies

When you override dependecies using patch.crates-io to use your git forks instead you need to make sure that in cargo tree this dependency comes from the forked patch only if it has another occurrence outside of that it will fail.
Example
`solana-bpf-loader-program v3.0.6 (https://github.com/ERoydev/agave.git?branch=ver-3.0.6#0bf8b0dc)` -> this comes from my fork
`solana-account v3.1.0 (*)` -> this is how it looks by default where you got to trace the graph

surfpool-cli → surfpool-core → litesvm → solana-bpf-loader-program


# What i did

- i started applying patches one by one and on each inspecting the `cargo tree` if all occurrences of litesvm for example are coming from my fork
- i saw that my code expects bpf-loader-program 3.0.6 so i had to create a fork with that version and make sure my forked bpf-loader-program is on his version. This way i successfully patched and override this used dependency inside other dependencies in order to override it FOR ALL.