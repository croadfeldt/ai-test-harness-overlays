# AI Test Harness overlays

Tests for third-party packages, written by the [AI Test Harness](https://github.com/croadfeldt/ai-test-harness)
and proposed here as pull requests. Nothing in this repository was merged by the harness; a person
accepted every file.

## Layout

```
overlays/<ecosystem>/<package>/<major.minor>.x/
  test_*.py or *_test.go   the accepted tests
  packet.md                the review packet the reviewer read
  vex.openvex.json         draft VEX statements for Product Security
  MANIFEST.json            the provenance record per test
  statement.json           in-toto test-result statement
  statement.dsse.json      the signed envelope; signer.pub.pem verifies it
  udlm/                    the same facts as UDLM records
standard/                  tests promoted to the standard suite (blueprint 8.3)
```

## How a change arrives

`harness propose` (blueprint section 5.0, lifecycle B) puts a run's accepted tests and records on a
`harness/` branch and opens a pull request whose text is the packet's plain-terms summary. The
harness pushes that one branch and nothing else. Review it like any contributor's pull request.
