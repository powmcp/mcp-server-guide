# PowMCP MCP server guide

PowMCP provides hosted, task-specific MCP servers. This repository documents three of them, their remote connection URLs, and their public MCP Registry descriptors. The hosted server implementation is proprietary and is not contained in this repository. You do not need to install or run code from this repository to use the servers.

| Server | Remote MCP endpoint | Tools | Guide | Registry descriptor |
| --- | --- | --- | --- | --- |
| [SSL Certificate Check](https://powmcp.com/apps/ssl-certificate-check/) | `https://powmcp.com/ssl-certificate-check/mcp` | `ssl_check` | [SSL guide](docs/ssl-certificate-check.md) | [server.json](servers/ssl-certificate-check/server.json) |
| [Ebook File Check](https://powmcp.com/apps/epub-check/) | `https://powmcp.com/epub-check/mcp` | `ebook_check`, `ebook_compare` | [EPUB guide](docs/epub-check.md) | [server.json](servers/epub-check/server.json) |
| [Caption File Check](https://powmcp.com/apps/caption-file-check/) | `https://powmcp.com/caption-file-check/mcp` | `caption_check`, `caption_compare` | [Caption guide](docs/caption-file-check.md) | [server.json](servers/caption-file-check/server.json) |

Each URL is a separate remote MCP server using Streamable HTTP. Add only the URL for the tool you need to an MCP client that supports remote servers. For example, a client that accepts an `mcpServers` JSON entry can use:

```json
{
  "mcpServers": {
    "powmcp-ssl-certificate-check": {
      "type": "http",
      "url": "https://powmcp.com/ssl-certificate-check/mcp"
    }
  }
}
```

Replace the name and URL with one of the other entries above to connect another server. The [individual app pages](https://powmcp.com/apps/) also provide client-specific connection buttons and commands. If your client requests authorization, complete its native sign-in flow. Client support for PowMCP account linking varies; consult the connection instructions on the app page. Usage allowances and any paid options are shown on the [PowMCP apps and usage page](https://powmcp.com/apps/).

The guides explain each tool's input and what its result can establish. For help with connection or results, contact [support@powmcp.com](mailto:support@powmcp.com). See [support and security](docs/support-and-security.md) for reporting guidance.

The [MIT license](LICENSE) applies to documentation, descriptors, and example configuration in this repository. It does not grant a license to the proprietary hosted implementation or to PowMCP's names and logos. References to third-party validation standards and components in the guides do not imply ownership of them by PowMCP.
