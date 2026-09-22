# Ebook File Check

Connect a remote MCP client to `https://powmcp.com/epub-check/mcp`, or use the [app page and its connection options](https://powmcp.com/apps/epub-check/).

## Tools

`ebook_check` validates one EPUB from a directly accessible public URL or, in a client that supports native file inputs, an attached file. A URL example:

```json
{"url":"https://example.com/book.epub","maxMessages":200}
```

It runs EPUBCheck 5.3.0 against EPUB 2/3 specification rules. The result includes a pass verdict, detected version, counts by severity, findings with rule IDs and file locations, structural inventory, and a SHA-256 hash for the checked bytes. `maxMessages` bounds returned findings from 1 to 500; the default is 200. The download limit is 25 MB, with further limits on decompressed size and ZIP entries. A check can take up to 110 seconds.

`ebook_compare` validates exactly two EPUB builds under the same limits, baseline first and revised second. Supply either two public URLs in `urls` or two client-supported attachments in `files`. It reports rules that appeared or worsened and rules that were fixed or reduced, along with a per-build verdict. For URL sources:

```json
{"urls":["https://example.com/book-before.epub","https://example.com/book-after.epub"]}
```

Use either URLs or attachments in one call, never both. For attachments, let the client provide its native file object; do not expose a private file just to obtain a public URL.

A pass means only that the exact submitted bytes passed the automated EPUBCheck profile. It does not establish store acceptance, accessibility, editorial quality, or how a reading system will render the book. Human review remains necessary. See the [PowMCP app page](https://powmcp.com/apps/epub-check/) for the current tool description and interactive examples.
