## 2026-03-30 - Regex Pre-compilation and HTTP Session Reuse in Scanners

**Learning:** Re-compiling regexes repeatedly inside threaded scanning loops and opening new HTTP connections per payload cause significant CPU overhead and high socket latency in security scanner scripts like `loxs.py`.

**Action:** Always pre-compile regular expression patterns prior to entering worker thread loops and reuse `requests.Session` instances with connection pooling across payload test requests.
