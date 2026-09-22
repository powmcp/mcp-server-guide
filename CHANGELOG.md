# Registry metadata history

## 2026-09-22 — repository information

These registry descriptor revisions add the official public documentation repository to the existing hosted server listings:

| Server | Previous registry version | Updated registry version |
| --- | --- | --- |
| SSL Certificate Check | 0.2.4 | 0.2.5 |
| Ebook File Check | 0.5.3 | 0.5.4 |
| Caption File Check | 0.3.2 | 0.3.3 |

Published registry metadata is immutable, so adding repository information requires new registry versions. These are metadata revisions only. They do not announce a new hosted implementation deployment or changes to endpoints, tools, authentication, or pricing. The running server's MCP `initialize` response may report a different implementation version.

The descriptors in `servers/` identify each remote endpoint and the shared guide repository. The hosted implementation remains proprietary and is not included here.
