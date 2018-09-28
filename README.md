# arc-docs

Documents related to the Authenticated Received Chain (ARC) protocol

---

Typical workflow:

- Edit document

  % emacs arc-usage-05.md

- Render into IETF-flavored XML a la RFC2629 -> RFC7991

  % kramdown-rfc2629 arc-usage-05.md >arc-usage-05.xml

- Grind that XML into a formatted RFC/I-D

  % xml2rfc arc-usage-05.xml --text


