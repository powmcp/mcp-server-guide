# Caption File Check

Connect a remote MCP client to `https://powmcp.com/caption-file-check/mcp`, or use the [app page and its connection options](https://powmcp.com/apps/caption-file-check/).

## Tools

`caption_check` checks one WebVTT, SRT, or TTML/IMSC caption file from a public URL or, in a client that supports native file inputs, an attached file. For example:

```json
{"url":"https://example.com/captions.en.vtt","profile":"netflix-adult-20"}
```

The tool detects the file format and encoding, parses the source, and reports structural issues, cue count, timing problems, line length, and characters-per-second reading speed against the selected profile. The default is `netflix-adult-20`; other available profiles include `netflix-children-17`, `youtube`, and `ebu-tt`. The latter two are advisory heuristics. Files are limited to 2 MB. A full-length track can take up to 60 seconds.

`caption_compare` checks exactly two tracks under the same limits, baseline first. Supply either two public URLs in `urls` or two client-supported attachments in `files`. It compares detected format and encoding, cue counts, cue timing, reading-speed findings, and structural errors. For URL sources:

```json
{"urls":["https://example.com/captions-before.vtt","https://example.com/captions-after.vtt"],"profile":"netflix-adult-20"}
```

Use either URLs or attachments in one call, never both. The comparison aligns cues by index. These checks inspect the source files; they do not judge translation, transcription, caption meaning, or synchronization against the video. A reading-speed threshold is not a promise of platform acceptance. See the [PowMCP app page](https://powmcp.com/apps/caption-file-check/) for the current tool description and interactive examples.
