# Log4Shell Audit Evidence — CVE-2021-44228

This note records the authoritative advisory facts for the Log4Shell follow-up audit.

## Advisory record (source: GitHub Advisory Database)

| Field | Value |
| --- | --- |
| **GHSA identifier** | GHSA-jfh8-c2jp-5v3q |
| **CVE identifier** | CVE-2021-44228 |
| **Title / Summary** | Remote code injection in Log4j |
| **Severity** | Critical |
| **CVSS score** | 10.0 |
| **CVSS vector** | CVSS:3.1/AV:N/AC:L/PR:N/UI:N/S:C/C:H/I:H/A:H/E:H |
| **Patched version range** | 2.16.0 and later (>= 2.16.0) |

## Patched / remediated versions

- **Fully patched version range:** `>= 2.16.0`. From Log4j 2.16.0, JNDI lookups are disabled by default and support for message lookups is removed.
- **Earlier partial fix:** 2.15.0 contained an initial fix for CVE-2021-44228, but that patch did not disable attacker-controlled JNDI lookups in all situations.
- **Backports of the fix:** 2.3.1, 2.12.2, and 2.12.3.
- **Affected range:** any version prior to 2.15.0 is affected by this specific issue; Log4j v1 is End Of Life, remains vulnerable to other RCE vectors, and should be migrated to 2.16.0 where possible.

## Affected package

Only `org.apache.logging.log4j:log4j-core` is directly affected. If `log4j-api` is in use, it should be kept at the same version as `log4j-core`.

## Advisory references

- GitHub Advisory: https://github.com/advisories/GHSA-jfh8-c2jp-5v3q
- NVD: https://nvd.nist.gov/vuln/detail/CVE-2021-44228
- Apache Log4j security guide: https://logging.apache.org/log4j/2.x/security.html
- Related advisory (CVE-2021-45046): https://github.com/advisories/GHSA-7rjr-3q55-vv33
