# iroh-address-lookups

> **This is a fork, and it carries no functional change.**
>
> It exists to repoint five dependency lines — `iroh`, `iroh-base`, `iroh-dns`
> in the two member manifests — from crates.io at
> [`fofoca-network/iroh`](https://github.com/fofoca-network/iroh). Nothing else
> differs from upstream `n0-computer/iroh-address-lookups`, and nothing here is
> upstreamable: n0 will never point their crates at our fork.
>
> **Why it has to exist.** These two crates sit between
> [`fofoca`](https://github.com/fofoca-network/fofoca) and iroh. fofoca needs a
> forked iroh (relay-teardown and mapped-addrs fixes); these named the crates.io
> one, so every graph containing both got *two* irohs, and the `AddressLookup`
> impls stopped satisfying the trait the forked `Endpoint` hands back — an
> `E0308` on types that look identical. A dependency declaration cannot redirect
> a third party's edge; only `[patch.crates-io]` can, and cargo honours that
> only in a workspace root and never inherits it. So the alternative was every
> consumer of fofoca restating the same three patch lines by hand, silently
> broken the moment one drifted.
>
> **Delete this fork** the moment the underlying iroh patches land upstream and
> fofoca can name the published crates again.

Optional Address Lookup services for [iroh](https://github.com/n0-computer/iroh).

- [`iroh-mainline-address-lookup`](./iroh-mainline-address-lookup/README.md) — pkarr-based publish/lookup over the BitTorrent Mainline DHT.
- [`iroh-mdns-address-lookup`](./iroh-mdns-address-lookup/README.md) — mDNS-based discovery for endpoints on the local network.

## License

Copyright 2025 N0, INC.

This project is licensed under either of

 * Apache License, Version 2.0, ([LICENSE-APACHE](LICENSE-APACHE) or
   http://www.apache.org/licenses/LICENSE-2.0)
 * MIT license ([LICENSE-MIT](LICENSE-MIT) or
   http://opensource.org/licenses/MIT)

at your option.

## Contribution

Unless you explicitly state otherwise, any contribution intentionally submitted for inclusion in this project by you, as defined in the Apache-2.0 license, shall be dual licensed as above, without any additional terms or conditions.
