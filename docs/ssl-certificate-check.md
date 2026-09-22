# SSL Certificate Check

Connect a remote MCP client to `https://powmcp.com/ssl-certificate-check/mcp`, or use the [app page and its connection options](https://powmcp.com/apps/ssl-certificate-check/).

## Tool

`ssl_check` accepts a public URL. For example:

```json
{"url":"https://example.com"}
```

It opens TLS handshakes to the URL's host and explicit port, or port 443 when none is specified. The result reports which of TLS 1.3, 1.2, 1.1, 1.0, and SSLv3 the probed endpoint accepted. It also reports the certificate the endpoint served, including subject, issuer, hostname coverage, issue and expiry dates, and a hostname-match verdict. Its grade reflects protocol support only.

The tool probes one resolved endpoint and does not load the webpage. It does not verify the full certificate chain or revocation, inspect cipher suites, or establish whether every node behind a load balancer has the same certificate. An `http://` input still probes TLS on the selected host and port; it does not test HTTP redirect behavior. A successful result is therefore not a browser trust guarantee or a Qualys SSL Labs grade.

This is useful when checking a certificate renewal, investigating an expiry or hostname mismatch, or seeing whether an endpoint still accepts old TLS protocols. See the [PowMCP app page](https://powmcp.com/apps/ssl-certificate-check/) for the current tool description and interactive example.
