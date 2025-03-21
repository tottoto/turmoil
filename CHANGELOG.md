# 0.6.6 (March 10, 2025)

### Added

- Add UDP multicast, broadcast simulation ([#224], [#226])
- Improve host ports exhausted panic message ([#218])
- Add explicit tracing output when runtime shuts down due to no clients ([#213])
- Update Axum example to `0.8` ([#221])


[#226]: https://github.com/tokio-rs/turmoil/pull/226
[#224]: https://github.com/tokio-rs/turmoil/pull/224
[#221]: https://github.com/tokio-rs/turmoil/pull/221
[#218]: https://github.com/tokio-rs/turmoil/pull/218
[#213]: https://github.com/tokio-rs/turmoil/pull/213

### Fixed

- TcpListener: fix a race condition where a peer going away causes the next connection to hang ([#224])
- `sim_elapsed()`: Synchronize host clock against global clock following restart ([#216])
- Small typo fixes ([#214])

[#224]: https://github.com/tokio-rs/turmoil/pull/224
[#216]: https://github.com/tokio-rs/turmoil/pull/216
[#214]: https://github.com/tokio-rs/turmoil/pull/214

# 0.6.5 (January 28, 2025)

### Added

- Add peek to TcpStream ([#206])

### Fixed

- Various clippy and dependency chores

[#206]: https://github.com/tokio-rs/turmoil/pull/206

# 0.6.4 (October 9, 2024)

### Added

- Add established_tcp_stream_count{,_on} ([#188])
- Allow one way partitionings ([#187])
- Implement Debug for UdpSocket ([#179])

[#179]: https://github.com/tokio-rs/turmoil/pull/179
[#187]: https://github.com/tokio-rs/turmoil/pull/187
[#188]: https://github.com/tokio-rs/turmoil/pull/188

# 0.6.3 (July 15, 2024)

### Added

- Add try_write to TcpStream ([#176])
- Add ability to run hosts in random order ([#173])
- Add API parity stubs for UDP sockets/TCP streams ([#174])

[#173]: https://github.com/tokio-rs/turmoil/pull/173
[#174]: https://github.com/tokio-rs/turmoil/pull/174
[#176]: https://github.com/tokio-rs/turmoil/pull/176

# 0.6.2 (April 3, 2024)

### Added

- Enable tokio io driver ([#171])

### Fixed

- Make sim_elapsed function safe to call outside of simulation ([#170])

[#170]: https://github.com/tokio-rs/turmoil/pull/170
[#171]: https://github.com/tokio-rs/turmoil/pull/171 

# 0.6.1 (January 10, 2024)

### Added

- Documentation on using tracing with Turmoil ([#155] [#164])
- Add a check for port exhaustion ([#157])
- Add `turmoil::sim_elapsed`` for retrieving total simulation virtual time ([#164])
- Update Axum example to use axum 0.7 and hyper 1 ([#154])

[#154]: https://github.com/tokio-rs/turmoil/pull/154
[#155]: https://github.com/tokio-rs/turmoil/pull/155
[#157]: https://github.com/tokio-rs/turmoil/pull/157
[#164]: https://github.com/tokio-rs/turmoil/pull/164

# 0.6.0 (November 17, 2023)

### Added 

- Documentation to the sim builder ([#152])

### Fixed

- Avoid trying to spawn on teardown when rt is gone ([#153])
- Deliver loopback packets in the next step ([#153])

### Breaking

- Remove `rng` from sim builder as it wasn't applied when building.
    This is technically a bug fix, but will break consumers.
    Use `build_with_rng` instead ([#150])

[#150]: https://github.com/tokio-rs/turmoil/pull/150
[#152]: https://github.com/tokio-rs/turmoil/pull/152
[#153]: https://github.com/tokio-rs/turmoil/pull/153

# 0.5.8 (November 6, 2023)

### Fixed

- Fix subtraction overflow bug with latency ([#147]) 
- Fix ephemeral port leak upon tcp stream shutdown ([#145]) 

[#147]: https://github.com/tokio-rs/turmoil/pull/147
[#145]: https://github.com/tokio-rs/turmoil/pull/145

# 0.5.7 (October 20, 2023)

### Added

- Add reverse DNS resolution capabilities ([#141])

### Fixed

- Fix duplicate FIN in the drop glue ([#142])
- Extend loopback workaround ([#140])

[#142]: https://github.com/tokio-rs/turmoil/pull/142
[#141]: https://github.com/tokio-rs/turmoil/pull/141
[#140]: https://github.com/tokio-rs/turmoil/pull/140

# 0.5.6 (July 24, 2023)

### Added

- Return io::Error instead of panicking ([#130])
- Add network manipulation capabilities to Sim ([#129])
- Tracing improvments ([#124])

[#124]: https://github.com/tokio-rs/turmoil/pull/124
[#129]: https://github.com/tokio-rs/turmoil/pull/129
[#130]: https://github.com/tokio-rs/turmoil/pull/130

# 0.5.5 (June 6, 2023)

### Added

- Make socket buffer capacity configurable ([#121])

### Fixed

- Fix reverse dns lookups on static binds ([#120])

[#120]: https://github.com/tokio-rs/turmoil/pull/120
[#121]: https://github.com/tokio-rs/turmoil/pull/121

# 0.5.4 (May 23, 2023)

### Added

- Support ephemeral port assignments on bind ([#110])
- Add support for Ipv6 network/binds ([#113])
- Add support for loopback ([#118]) 

### Fixed

- Filter out equal IpAddrs for regex matching ([#116]) 
- Remove inconsistent address resolution ([#114])
- Fix bug in binding an in use port ([#117]) 

[#110]: https://github.com/tokio-rs/turmoil/pull/110
[#113]: https://github.com/tokio-rs/turmoil/pull/113
[#114]: https://github.com/tokio-rs/turmoil/pull/114
[#116]: https://github.com/tokio-rs/turmoil/pull/116
[#117]: https://github.com/tokio-rs/turmoil/pull/117
[#118]: https://github.com/tokio-rs/turmoil/pull/118

# 0.5.3 (Mar 22, 2023)

### Added

- Expose whether a host has software running ([#108])
- DNS improvements ([#109])

### Fixed

- Fix AsyncRead impl for TcpStream ([#107])

[#107]: https://github.com/tokio-rs/turmoil/pull/107
[#108]: https://github.com/tokio-rs/turmoil/pull/108
[#109]: https://github.com/tokio-rs/turmoil/pull/109

# 0.5.2 (Mar 13, 2023)

### Added

- Add more support for UDP([#100], [#101], [#102])

[#100]: https://github.com/tokio-rs/turmoil/pull/100
[#101]: https://github.com/tokio-rs/turmoil/pull/101
[#102]: https://github.com/tokio-rs/turmoil/pull/102

# 0.5.1 (Mar 1, 2023)

### Added

- gRPC example ([#81])
- axum example ([#91])

### Fixed

- Handle task cancellation due to crashing a host ([#85])
- Remove runtime after host crashes ([#89])

[#81]: https://github.com/tokio-rs/turmoil/pull/81
[#85]: https://github.com/tokio-rs/turmoil/pull/85
[#89]: https://github.com/tokio-rs/turmoil/pull/89
[#91]: https://github.com/tokio-rs/turmoil/pull/91

# 0.5 (Feb 8, 2023)

### Added

- Expose a mechanism to manually drive the Sim ([#76])
- Add option to query hosts via regex ([#77])
- Add network topology introspection ([#78])

[#76]: https://github.com/tokio-rs/turmoil/pull/76
[#77]: https://github.com/tokio-rs/turmoil/pull/77
[#78]: https://github.com/tokio-rs/turmoil/pull/78

### Changed

- The following methods use a new trait (`ToIpAddrs`) for host lookup which
  includes the same implementations as `ToIpAddr`.
  - `Sim#bounce`
  - `Sim#crash`
  - `Sim#set_link_fail_rate`
  - `Sim#set_max_message_latency`
  - `repair`
  - `partition`
  - `release`
  - `hold`

# 0.4 (Jan 10, 2023)

### Added

- Add more type conversions for ToSocketAddrs ([#71])
- Add host error support ([#67])

### Changed

- Make tokio unstable opt in ([#73])
- Rename ToSocketAddr to ToSocketAddrs ([#60])

[#73]: https://github.com/tokio-rs/turmoil/pull/73
[#71]: https://github.com/tokio-rs/turmoil/pull/71
[#67]: https://github.com/tokio-rs/turmoil/pull/67
[#60]: https://github.com/tokio-rs/turmoil/pull/60

# 0.3.3 (Dec 7, 2022)

### Fixed

- Fix host elapsed time across software restarts ([#65])

[#65]: https://github.com/tokio-rs/turmoil/pull/65

# 0.3.2 (Nov 14, 2022)

### Added

- Expose the sim's epoch and elapsed duration ([#54])

[#54]: https://github.com/tokio-rs/turmoil/pull/54

# 0.3.1 (Nov 9, 2022)

### Added

- Add local/peer addrs to tcp types
- Expose host elapsed time

### Changed

- Use tracing levels for different network events ([#53])

[#53]: https://github.com/tokio-rs/turmoil/pull/53

### Fixed

- Fix host crash behavior ([#52])

[#52]: https://github.com/tokio-rs/turmoil/pull/52

# 0.3.0 (Oct 28, 2022)

### Added

- Bind to multiple ports per host
- Simulated networking (UDP and TCP) that mirror tokio::net
- Client host error handling

### Changed

- Logging uses `tracing` for writing events

# 0.2.0 (Aug 11, 2022)

- Initial release
