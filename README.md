# arc-docs

Documents related to the Authenticated Received Chain (ARC) protocol

---

Effective with draft version -10, we have switched to mmark for the dialect. New build directions:

  % mmark arc-usage-10.md > arc-usage-10.xml

  % xml2rfc --v3 --html arc-usage-10.xml

---

Typical workflow (for kramdown dialect, used prior to -10):

- Edit document

  % emacs arc-usage-05.md

- Render into IETF-flavored XML a la RFC2629 -> RFC7991

  % kramdown-rfc2629 arc-usage-05.md >arc-usage-05.xml

- Grind that XML into a formatted RFC/I-D

  % xml2rfc arc-usage-05.xml --text

---

