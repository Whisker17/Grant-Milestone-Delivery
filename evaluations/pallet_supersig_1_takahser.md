# Evaluation

- **Status:** Accepted
- **Application Document:** https://github.com/w3f/Grants-Program/blob/master/applications/pallet_supersig.md
- **Milestone:** 1
- **Kusama Identity:** Address
- **Previously successfully merged evaluation:** All by takahser

| Number | Deliverable                       | Accepted               | Link                                                                                                                                                                                                                                                                     | Evaluation Notes                                                                                                                                                                                                  |
| ------ | --------------------------------- | ---------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| 0a.    | License                           | <ul><li>[x] </li></ul> | [Pallet Supersig LICENSE](https://github.com/kabocha-network/pallet_supersig/blob/e8d85c7fd2d896562b038648b0a936f077039e16/LICENSE), [Node LICENSE](https://github.com/decentration/substrate-supersig-template/blob/abdfb445b88c4739b9585e52548314ea1fb98127/LICENSE)   | Apache 2.0                                                                                                                                                                                                        |
| 0b.    | Documentation                     | <ul><li>[x] </li></ul> | [Node README](https://github.com/decentration/substrate-supersig-template/blob/abdfb445b88c4739b9585e52548314ea1fb98127/README.md)                                                                                                                                       | See [Documentation Feedback](#documentation-feedback)                                                                                                                                                             |
| 0c.    | Testing Guide                     | <ul><li>[x] </li></ul> | [Pallet Unit Tests](https://github.com/kabocha-network/pallet_supersig/tree/e8d85c7fd2d896562b038648b0a936f077039e16/src/tests), [testing instructions](https://github.com/kabocha-network/pallet_supersig/blob/f3b4842b971df00287f1ec6e2dcc41c431bce799/README.md#test) | See [Testing Guide Feedback](#testing-guide-feedback)                                                                                                                                                             |
| 0d.    | Docker                            | <ul><li>[x] </li></ul> | [docker-compose.yml](https://github.com/decentration/substrate-supersig-template/blob/abdfb445b88c4739b9585e52548314ea1fb98127/docker-compose.yml)                                                                                                                       | The initially existing issues got resolved. The image is on [dockerhub](https://hub.docker.com/r/decentration/supersig-node), however, there's no README and no link to the repo. It would be nice to have these. |
| 0e.    | Article                           | <ul><li>[x] </li></ul> | [Medium Article](https://decentration.medium.com/supersig-like-multisig-but-with-superpowers-86b9ce0412f6), [Video Tutorial](https://www.loom.com/share/dbcaa6319b1a4644aacb709aa0e38783)                                                                                | -                                                                                                                                                                                                                 |
| 1.     | Substrate module: pallet_supersig | <ul><li>[x] </li></ul> | [Supersig Pallet](https://github.com/kabocha-network/pallet_supersig/tree/e8d85c7fd2d896562b038648b0a936f077039e16)                                                                                                                                                      | Functionality was tested successfully. Clean code.                                                                                                                                                                |
| 2.     | Benchmarking                      | <ul><li>[x] </li></ul> | [benchmarking](https://github.com/kabocha-network/pallet_supersig/blob/e8d85c7fd2d896562b038648b0a936f077039e16/src/benchmarking.rs)                                                                                                                                     | -                                                                                                                                                                                                                 |

Ideally all links inside the above table should include the commit hash,
which was used for testing the delivery. It should also be checked if the software is published under the correct open-source license.

## General Notes

Summarizes the overall performance plus additional feedback/comments

### Documentation Feedback

- Inline documentation of the supersig pallet is sufficient, the code is clean.
- The node template uses the supersig pallet.
- The node can be started using the instructions:
  ```bash
  ~/repos/substrate-supersig-template$ docker run -p 9944:9944 -p 30333:30333 -p 9933:9933 -p 9615:9615  docker.io/decentration/supersig-node:latest --dev --port 30333 --ws-port 9944 --rpc-port 9933
  2022-09-29 12:49:54 Substrate Node
  2022-09-29 12:49:54 ✌️  version 4.0.0-dev-693482e6f9a
  2022-09-29 12:49:54 ❤️  by Substrate DevHub <https://github.com/substrate-developer-hub>, 2017-2022
  2022-09-29 12:49:54 📋 Chain specification: Development
  2022-09-29 12:49:54 🏷  Node name: slow-voice-4171
  2022-09-29 12:49:54 👤 Role: AUTHORITY
  2022-09-29 12:49:54 💾 Database: RocksDb at /tmp/substrate1g11pw/chains/dev/db/full
  2022-09-29 12:49:54 ⛓  Native runtime: substrate-100 (substrate-1.tx1.au1)
  2022-09-29 12:49:54 🔨 Initializing Genesis block/state (state: 0xa9be…2ec2, header-hash: 0x0a81…52d3)
  2022-09-29 12:49:54 👴 Loading GRANDPA authority set from genesis on what appears to be first startup.
  2022-09-29 12:49:54 Using default protocol ID "sup" because none is configured in the chain specs
  2022-09-29 12:49:54 🏷  Local node identity is: 12D3KooWLkAy1idDVARvgrfA68Q2pwWTNWbRZqJUHMhGLsNTwD8m
  2022-09-29 12:49:54 💻 Operating system: linux
  2022-09-29 12:49:54 💻 CPU architecture: x86_64
  2022-09-29 12:49:54 💻 Target environment: gnu
  2022-09-29 12:49:54 💻 CPU: AMD Ryzen 9 5950X 16-Core Processor
  2022-09-29 12:49:54 💻 CPU cores: 16
  2022-09-29 12:49:54 💻 Memory: 128800MB
  2022-09-29 12:49:54 💻 Kernel: 5.4.0-113-generic
  2022-09-29 12:49:54 💻 Linux distribution: Ubuntu 20.04.5 LTS
  2022-09-29 12:49:54 💻 Virtual machine: no
  2022-09-29 12:49:54 📦 Highest known block at #0
  2022-09-29 12:49:54 〽️ Prometheus exporter started at 127.0.0.1:9615
  2022-09-29 12:49:54 Running JSON-RPC HTTP server: addr=127.0.0.1:9933, allowed origins=None
  2022-09-29 12:49:54 Running JSON-RPC WS server: addr=127.0.0.1:9944, allowed origins=None
  <x2022-09-29 12:49:59 💤 Idle (0 peers), best: #0 (0x0a81…52d3), finalized #0 (0x0a81…52d3), ⬇ 43 B/s ⬆ 0
  2022-09-29 12:50:00 🙌 Starting consensus session on top of parent 0x0a8193b8eab0fe4c626c11305b0e613b589efd2d95cd1ce4e32890d5c65a52d3
  2022-09-29 12:50:00 🎁 Prepared block for proposing at 1 (1 ms) [hash: 0xcf29897e5e072a5d9afb7c7d37ff81bf0eda606213cdf8dd98fd51e924332e0b; parent_hash: 0x0a81…52d3; extrinsics (1): [0x19d4…fe14]]
  2022-09-29 12:50:00 🔖 Pre-sealed block for proposal at 1. Hash now 0x2d8e1da4386e520c8f165c2aac17cf139a8de8df915d8b7adfc4e68f42b45748, previously 0xcf29897e5e072a5d9afb7c7d37ff81bf0eda606213cdf8dd98fd51e924332e0b.
  2022-09-29 12:50:00 ✨ Imported #1 (0x2d8e…5748)
  2022-09-29 12:50:04 💤 Idle (0 peers), best: #1 (0x2d8e…5748), finalized #0 (0x0a81…52d3), ⬇ 28 B/s ⬆ 0
  2022-09-29 12:50:06 🙌 Starting consensus session on top of parent 0x2d8e1da4386e520c8f165c2aac17cf139a8de8df915d8b7adfc4e68f42b45748
  ```
- Although the docker container is running, any attempt to connect to the node using polkadotJs apps initially failed.
- When running the node manually using `cargo run --release -- --dev`, these problems didn't occur and polkadotJs apps connected to the node smoothly.
- Finally, in the latest version of the [template](https://github.com/decentration/substrate-supersig-template/tree/6fbce881471ef6b5730bb8bf4b68f2ee20f58025#run-in-docker) the docker issues got resolved.

### Testing Guide Feedback

- Testing instructions were [added](https://github.com/kabocha-network/pallet_supersig/blob/f3b4842b971df00287f1ec6e2dcc41c431bce799/README.md#test)
- All tests succeed:

```bash
~/repos/pallet_supersig$ cargo test
   Updating crates.io index
    Updating git repository `https://github.com/paritytech/substrate`
  Downloaded aho-corasick v0.7.19

  (...)

     Compiling pallet-supersig v1.1.1 (/home/seraya/repos/pallet_supersig)
    Finished test [unoptimized + debuginfo] target(s) in 2m 10s
     Running unittests src/lib.rs (target/debug/deps/pallet_supersig-ebcf7b303f392a07)
    running 36 tests
    test tests::mock::__construct_runtime_integrity_test::runtime_integrity_tests ... ok
    test tests::create_supersig::create_with_empty_list ... ok
    test tests::add_members::add_users_unknown_supersig ... ok
    test tests::leave_supersig::leave_supersig_not_a_member ... ok
    test tests::add_members::add_users_not_allowed ... ok
    test tests::leave_supersig::leave_supersig_last_user ... ok
    test tests::approve_call::approve_not_a_member ... ok
    test tests::delete_supersig::delete_supersig_unknown_supersig ... ok
    test tests::leave_supersig::leave_unknown_supersig ... ok
    test tests::remove_call::remove_unknown_call ... ok
    test tests::approve_call::approve_supersig_doesnt_exist ... ok
    test tests::delete_supersig::cannot_delete_supersig ... ok
    test tests::remove_members::remove_users_leaving_0_users ... ok
    test tests::create_supersig::create_supersig_with_master ... ok
    test tests::remove_members::remove_users_unknown_supersig ... ok
    test tests::remove_call::non_allowed_remove_call ... ok
    test tests::remove_members::remove_users_not_allowed ... ok
    test tests::create_supersig::create_supersig ... ok
    test tests::approve_call::user_already_voted ... ok
    test tests::delete_supersig::cannot_liquidate_supersig ... ok
    test tests::leave_supersig::leave_supersig ... ok
    test tests::remove_call::remove_call ... ok
    test tests::delete_supersig::delete_supersig ... ok
    test tests::approve_call::approve_call ... ok
    test tests::delete_supersig::delete_supersig_with_call ... ok
    test tests::add_members::add_members ... ok
    test tests::remove_members::remove_members ... ok
    test tests::create_supersig::create_multiple_supersig ... ok
    test tests::rpc_calls::get_proposal_state ... ok
    test tests::submit_call::submit_supersig_doesnt_exist ... ok
    test tests::approve_call::approve_call_until_threshold ... ok
    test tests::rpc_calls::list_members ... ok
    test tests::approve_call::approve_call_as_master ... ok
    test tests::submit_call::submit_calls ... ok
    test tests::rpc_calls::get_proposals ... ok
    test tests::rpc_calls::get_account_supersigs ... ok

    test result: ok. 36 passed; 0 failed; 0 ignored; 0 measured; 0 filtered out; finished in 3.80s

    Doc-tests pallet-supersig

    running 0 tests

    test result: ok. 0 passed; 0 failed; 0 ignored; 0 measured; 0 filtered out; finished in 0.00s
```
