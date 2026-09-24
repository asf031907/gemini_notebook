# 🗺️ Official PortSwigger Web Security Master Roadmap

Welcome to the **PortSwigger Web Security Master Program**. As your dedicated PortSwigger Academy Mentor and Web Security Coach, I have structured your learning journey into a rigorous, methodology-first master roadmap[cite: 11].

Our primary objective is **not merely collecting solved labs**, but developing true, transferable web application security skills: **Understand $\rightarrow$ Identify $\rightarrow$ Analyze $\rightarrow$ Exploit safely in the lab $\rightarrow$ Troubleshoot $\rightarrow$ Adapt $\rightarrow$ Explain root cause $\rightarrow$ Explain impact $\rightarrow$ Understand mitigation $\rightarrow$ Reproduce independently $\rightarrow$ Solve unfamiliar variations**[cite: 11].

Below is your complete **PortSwigger Academy Master Roadmap**, built directly from current PortSwigger Web Security Academy topics and learning materials[cite: 3, 4, 11].

---

## Phase 0 — Web Security & Burp Foundations

* **Topics**: Getting Started with the Web Security Academy, HTTP Fundamentals, Burp Suite Core Methodology 3 ...[cite: 3].
* **Learning Materials**: Academy Getting Started Guide, Burp Suite UI Overview, Intercepting Requests & Responses, Burp Repeater Video Tutorials 5 6[cite: 3].
* **Apprentice Labs**: Traffic interception, request modification, and response analysis in Burp Proxy & Repeater 5 6[cite: 3].
* **Practitioner Labs**: N/A (Foundational phase)[cite: 3].
* **Required Burp Skills**: Proxy listener configuration, Target Scope setting, HTTP history filtering, Repeater request editing, Decoder text transformations (URL, HTML, Base64)[cite: 3].
* **Required HTTP Knowledge**: HTTP Request/Response anatomy, HTTP Methods (`GET`, `POST`, etc.), Status Codes (`200`, `302`, `403`, `500`), Key Headers (`Host`, `Cookie`, `Content-Type`), Cookie/Session mechanics[cite: 3].
* **Mastery Criteria**: Intercept, inspect, modify, and resend any HTTP traffic cleanly using Burp Suite without UI friction[cite: 3].
* **Revision Requirements**: Knowledge check on HTTP status codes, core request headers, and Burp Suite keyboard shortcuts[cite: 3].
* **Mystery-Lab Readiness**: Baseline[cite: 3].

---

## Phase 1 — Core Server-Side Vulnerabilities

* **Topics**: Path Traversai, OS Command Injection, Information Disclosure, Business Logic Vulnerabilities 4 ...[cite: 4].
* **Learning Materials**: PortSwigger Server-Side Vulnerability Modules 7 ...[cite: 4].
* **Apprentice Labs**:
  * *Path Traversal*: File path traversal, simple case 10[cite: 4].
  * *Command Injection*: OS command injection, simple case 11[cite: 4].
  * *Information Disclosure*: Error messages, debug page, backup files, authentication bypass 12[cite: 4].
  * *Business Logic*: Excessive trust in client-side controls, high-level logic, inconsistent security controls, flawed enforcement 13[cite: 4].
* **Practitioner Labs**:
  * *Path Traversal*: Absolute path bypass, stripped non-recursively, superfluous URL-decode, validation of start of path, null byte bypass 10 14[cite: 4].
  * *Command Injection*: Blind time delays, output redirection, out-of-band interaction & exfiltration 11[cite: 4].
  * *Information Disclosure*: Version control history 13[cite: 4].
  * *Business Logic*: Low-level logic flaws, inconsistent input handling, weak isolation, insufficient workflow validation, flawed state machines, infinite money logic 13 15[cite: 4].
* **Required Burp Skills**: Repeater parameter manipulation, Comparer response diffing, Intruder wordlists for directory/parameter discovery[cite: 4].
* **Required HTTP Knowledge**: Multi-part form-data, query parameters, `Content-Length` headers, application error state analysis[cite: 4].
* **Mastery Criteria**: Systematic identification of missing server-side logic checks, path traversal filter bypasses, and information leak discovery[cite: 4].
* **Revision Requirements**: Review directory traversal filter bypass payloads and business process workflow state machines[cite: 4].
* **Mystery-Lab Readiness**: Apprentice-level readiness for basic server-side flaws[cite: 4].

---

## Phase 2 — Authentication & Access Control

* **Topics**: Authentication Vulnerabilities, Access Control Vulnerabilities, File Upload Vulnerabilities 4 ...[cite: 5].
* **Learning Materials**: Authentication, Access Control, and File Upload Modules 8 ...[cite: 5].
* **Apprentice Labs**:
  * *Authentication*: Username enumeration via different responses, 2FA simple bypass, password reset broken logic 18[cite: 5].
  * *Access Control*: Unprotected admin functionality, unpredictable URLs, parameter/profile role modification, IDOR 14 19[cite: 5].
  * *File Upload*: Web shell execution, Content-Type restriction bypass 20[cite: 5].
* **Practitioner Labs**:
  * *Authentication*: Subtly different responses, response timing, broken brute-force protection (IP block), 2FA broken logic, stay-logged-in cookie brute-forcing, offline password cracking, reset poisoning via middleware 18 21[cite: 5].
  * *Access Control*: URL-based access control bypass, method-based bypass, multi-step process bypass, Referer-based access control 18 19[cite: 5].
  * *File Upload*: Path traversal web shell upload, extension blacklist bypass, obfuscated extension, polyglot web shell 22[cite: 5].
* **Required Burp Skills**: Intruder attack types (Sniper, Pitchfork, Cluster Bomb), Match and Replace rules, Session Handling Rules & Macros[cite: 5].
* **Required HTTP Knowledge**: Verb tampering (`GET` vs `POST` vs `PUT`), Authorization and Cookie headers, `Referer` validation, Session lifecycle state[cite: 5].
* **Mastery Criteria**: Bypassing broken access controls across HTTP verbs, uploading web shells through multi-layer filter bypasses, enumerating users via response timing[cite: 5].
* **Revision Requirements**: Access control matrix checklist, web shell payload execution paths[cite: 5].
* **Mystery-Lab Readiness**: Moderate (Capable of solving access control & authentication mystery labs)[cite: 5].

---

## Phase 3 — Input/Injection Vulnerabilities

* **Topics**: SQL Injection (SQLi), XML External Entity (XXE) Injection, Server-Side Request Forgery (SSRF) 4 ...[cite: 6].
* **Learning Materials**: SQLi, XXE, and SSRF Interactive Modules 7 ...[cite: 6].
* **Apprentice Labs**:
  * *SQLi*: Hidden data retrieval, login bypass 25[cite: 6].
  * *XXE*: External entities for file retrieval, XXE to perform SSRF 26[cite: 6].
  * *SSRF*: Basic SSRF against localhost, SSRF against backend systems 27[cite: 6].
* **Practitioner Labs**:
  * *SQLi*: Oracle/MySQL database version querying, listing database contents, UNION attacks (column count, text column, data exfiltration), Blind SQLi (conditional responses, errors, visible errors, time delays, out-of-band), XML encoding filter bypass 25 ...[cite: 6].
  * *XXE*: Blind XXE (out-of-band, parameter entities, DTD exfiltration, error messages), XInclude attacks, XXE via image upload 26[cite: 6].
  * *SSRF*: Blind SSRF with out-of-band detection, blacklist filter bypass, open redirection bypass 27[cite: 6].
* **Required Burp Skills**: Burp Collaborator for out-of-band exfiltration (OAST), Repeater payload injection, Decoder for URL/XML encoding[cite: 6].
* **Required HTTP Knowledge**: SQL parsing mechanics, XML structure & DTD definitions, URL scheme handlers (`http://`, `file://`), internal network architecture topology[cite: 6].
* **Mastery Criteria**: Extracting sensitive data via UNION and blind SQLi techniques, leveraging XXE and SSRF for internal network mapping and file retrieval[cite: 6].
* **Revision Requirements**: SQL comment and string concatenation cheat sheet across database engines, XML external DTD exfiltration templates[cite: 6].
* **Mystery-Lab Readiness**: High for classical injection vectors[cite: 6].

---

## Phase 4 — Client-Side Vulnerabilities

* **Topics**: Cross-Site Scripting (XSS), Cross-Site Request Forgery (CSRF), Clickjacking, CORS, DOM-Based Vulnerabilities, WebSockets 4 ...[cite: 7].
* **Learning Materials**: Client-Side Vulnerability Modules 23 ...[cite: 7].
* **Apprentice Labs**:
  * *XSS*: Reflected & Stored XSS into HTML context/attributes, DOM XSS in `document.write` / `innerHTML` / `jQuery` 30 35[cite: 7].
  * *CSRF*: CSRF with no defenses 36[cite: 7].
  * *Clickjacking*: Basic clickjacking, prefilled forms, frame busters 37[cite: 7].
  * *CORS*: Basic origin reflection, trusted null origin 38[cite: 7].
  * *WebSockets*: Manipulating WebSocket messages 21[cite: 7].
* **Practitioner Labs**:
  * *XSS*: Custom tags, SVG markup, canonical link tag, quote escaping, template literals, cookie theft, password capture, CSRF bypass via XSS, strict CSP dangling markup 35 ...[cite: 7].
  * *CSRF*: Method validation bypass, untied session/cookie tokens, double-submit cookie, SameSite bypasses (Lax method override, Strict client-side redirect / sibling domain), Referer header validation bypasses 36 ...[cite: 7].
  * *Clickjacking*: Triggering DOM XSS via clickjacking, multi-step clickjacking 37[cite: 7].
  * *CORS*: Trusted insecure protocols 38[cite: 7].
  * *DOM-based*: Web messages (XSS, JS URL, JSON.parse), open redirection, cookie manipulation 37 38[cite: 7].
  * *WebSockets*: Cross-site WebSocket hijacking, handshake manipulation 21[cite: 7].
* **Required Burp Skills**: Exploit Server for hosting cross-site payloads, Burp WebSockets tab, DOM Invader for DOM XSS source/sink tracing[cite: 7, 8].
* **Required HTTP Knowledge**: Same-Origin Policy (SOP), CORS headers (`Access-Control-Allow-Origin`, `Access-Control-Allow-Credentials`), Cookie security flags (`SameSite`, `HttpOnly`, `Secure`), WebSocket handshake protocol[cite: 7, 8].
* **Mastery Criteria**: Constructing robust cross-site exploit payloads on the Exploit Server, bypassing XSS context filters, hijacking WebSocket sessions[cite: 8].
* **Revision Requirements**: XSS context escape matrix, CSRF defense bypass decision tree, SOP/CORS rules summary[cite: 8].
* **Mystery-Lab Readiness**: High across client-side mechanics[cite: 8].

---

## Phase 5 — Advanced Server-Side Vulnerabilities

* **Topics**: Insecure Deserialization, Server-Side Template Injection (SSTI), HTTP Host Header Attacks, Web Cache Poisoning, HTTP Request Smuggling 4 ...[cite: 8].
* **Learning Materials**: Advanced Server-Side Vulnerability Modules 32 ...[cite: 8].
* **Apprentice Labs**:
  * *Deserialization*: Modifying serialized objects 44[cite: 8].
  * *Host Header*: Basic password reset poisoning, authentication bypass 15[cite: 8].
* **Practitioner Labs**:
  * *Deserialization*: Modifying data types, application functionality exploitation, PHP arbitrary object injection, Java Apache Commons gadget chains, PHP pre-built chains, Ruby documented chains 12 44[cite: 8].
  * *SSTI*: Basic SSTI, code context, documentation usage, unknown language exploits, info disclosure via user objects 10 11[cite: 8].
  * *Host Header*: Ambiguous request cache poisoning, routing-based SSRF, flawed request parsing SSRF, connection state attacks 15[cite: 8].
  * *Web Cache Poisoning*: Unkeyed headers, unkeyed cookies, multiple headers, unknown headers, unkeyed query strings/parameters, parameter cloaking, fat GET requests, URL normalization 45[cite: 8].
  * *HTTP Request Smuggling*: CL.TE & TE.CL differential response confirmation, front-end control bypass, front-end request rewriting reveal, request capture, reflected XSS delivery, H2.TE response queue poisoning, H2.CL, H2 CRLF injection/splitting, CL.O 46 ...[cite: 8, 9].
* **Required Burp Skills**: HTTP/2 framing controls, Inspector panel, Repeater tab grouping & single-key issuing, Turbo Intruder (for timing-critical request smuggling)[cite: 8, 9].
* **Required HTTP Knowledge**: HTTP/1 vs HTTP/2 parsing differences, Content-Length vs Transfer-Encoding precedence rules, Cache key calculation vs unkeyed inputs, Language-specific serialization formats (PHP, Java, Ruby, Python)[cite: 9].
* **Mastery Criteria**: Detecting and exploiting request smuggling desynchronization, poisoning web caches via unkeyed headers, building gadget chains for RCE via deserialization[cite: 9].
* **Revision Requirements**: Request smuggling CL.TE / TE.CL syntax rules, SSTI polyglot detection strings[cite: 9].
* **Mystery-Lab Readiness**: Advanced server-side readiness[cite: 9].

---

## Phase 6 — Modern Web/API Security

* **Topics**: GraphQL API Vulnerabilities, NoSQL Injection, API Testing, Web LLM Attacks, Web Cache Deception, Race Conditions 4 ...[cite: 9].
* **Learning Materials**: Modern Web & API Security Modules 9 ...[cite: 9].
* **Apprentice Labs**:
  * *GraphQL*: Accessing private GraphQL posts 53[cite: 9].
  * *NoSQLi*: Detecting NoSQL injection, operator injection auth bypass 54[cite: 9].
  * *API Testing*: Exploiting API endpoints using documentation 54[cite: 9].
  * *Web LLM Attacks*: Excessive agency, AI agent destructive actions, sensitive info exfiltration 55 56[cite: 9].
  * *Web Cache Deception*: Path mapping exploitation 56[cite: 9].
  * *Race Conditions*: Limit overrun race conditions 53 54[cite: 9, 10].
* **Practitioner Labs**:
  * *GraphQL*: Accidental field exposure, hidden endpoints, brute-force protection bypass, CSRF over GraphQL 53[cite: 9, 10].
  * *NoSQLi*: Data extraction, operator injection to extract unknown fields 54[cite: 10].
  * *API Testing*: Server-side parameter pollution in query strings, unused endpoints, mass assignment 55[cite: 10].
  * *Web LLM Attacks*: LLM API vulnerabilities, indirect prompt injection, secondary vulnerability triggering, bypassing AI scanner defenses 55 56[cite: 9, 10].
  * *Web Cache Deception*: Path delimiters, origin server normalization, cache server normalization 56[cite: 10].
  * *Race Conditions*: Rate limit bypass, multi-endpoint, single-endpoint, time-sensitive vulnerabilities 53 54[cite: 10].
* **Required Burp Skills**: InQL / GraphQL extensions, Repeater group sending (parallel request group execution for single-packet attacks / HTTP/2 multiplexing), JSON formatting tools[cite: 10].
* **Required HTTP Knowledge**: REST vs GraphQL schemas, JSON payload parsing, LLM system/user prompt mechanics, path mapping discrepancies between reverse proxies and origin servers[cite: 10].
* **Mastery Criteria**: Introspecting GraphQL schemas, executing single-packet race condition attacks, exploiting indirect prompt injections, triggering cache path confusion[cite: 10].
* **Revision Requirements**: Single-packet attack execution workflow, NoSQL operator injection cheatsheet (`$ne`, `$regex`, `$gt`)[cite: 10].
* **Mystery-Lab Readiness**: Very High across modern stack architecture[cite: 10].

---

## Phase 7 — Advanced Topics

* **Topics**: OAuth Authentication, JWT Attacks, Prototype Pollution 4 ...[cite: 10].
* **Learning Materials**: OAuth, JWT, and Prototype Pollution Modules 23 ...[cite: 10].
* **Apprentice Labs**:
  * *OAuth*: Implicit flow authentication bypass 20[cite: 10].
  * *JWT*: Unverified signature, flawed signature verification 22[cite: 10].
  * *Prototype Pollution*: N/A at Apprentice level[cite: 10].
* **Practitioner Labs**:
  * *OAuth*: SSRF via OpenID dynamic registration, forced profile linking, account hijacking via `redirect_uri`, stealing tokens via open redirects 20[cite: 10].
  * *JWT*: Weak signing key brute-force, `jwk` header injection, `jku` header injection, `kid` header path traversal 22 58[cite: 10].
  * *Prototype Pollution*: Client-side via browser APIs, DOM XSS via client-side pollution, alternative vectors, flawed sanitization, third-party libraries, server-side privilege escalation, detection without reflection, flawed input filter bypass, server-side RCE 53 ...[cite: 10].
* **Required Burp Skills**: OAuth flow interception, JWT Editor extension (token modification, resigning, key injection), Browser DevTools JavaScript debugging[cite: 10, 11].
* **Required HTTP Knowledge**: OAuth 2.0 grant types (authorization code, implicit), OpenID Connect flow, JWT structure (Header, Payload, Signature), JavaScript prototype chain (`__proto__`, `Object.prototype`)[cite: 11].
* **Mastery Criteria**: Performing algorithm confusion and header injection on JWTs, hijacking OAuth accounts via redirect manipulation, achieving RCE/privilege escalation via prototype pollution[cite: 11].
* **Revision Requirements**: JWT header parameter attack vectors (`jwk`, `jku`, `kid`), Prototype pollution source-to-sink tracing workflow[cite: 11].
* **Mystery-Lab Readiness**: Comprehensive topic coverage complete[cite: 11].

---

## Phase 8 — Essential Skills

* **Topics**: Essential Skills (Burp Scanner targeted usage, scanning non-standard data structures) 4 57[cite: 11].
* **Learning Materials**: Essential Skills Modules 57 58[cite: 11].
* **Apprentice Labs**: N/A[cite: 11].
* **Practitioner Labs**: Discovering vulnerabilities quickly with targeted scanning, scanning non-standard data structures 58[cite: 11].
* **Required Burp Skills**: Targeted scanning in Burp Suite, custom insertion point configuration, active vs. passive scanning strategies[cite: 11].
* **Required HTTP Knowledge**: Complex nested data structures (JSON, XML, serialized objects), custom encoding boundaries[cite: 11].
* **Mastery Criteria**: Efficiently combining manual testing techniques with targeted automated checks without breaking application logic[cite: 11].
* **Revision Requirements**: Audit of custom scanner insertion points and manual vs. automated testing balance[cite: 11].
* **Mystery-Lab Readiness**: Fully prepared for unguided testing[cite: 11].

---

## Phase 9 — Mystery Labs

* **Topics**: Randomized Mystery Lab Challenge across all vulnerability categories and difficulties (Apprentice, Practitioner, Expert) 25 ...[cite: 1].
* **Learning Materials**: Mystery Lab Portal 25 60[cite: 1].
* **Labs**: Randomized Apprentice, Practitioner, and Expert Mystery Labs 60 61[cite: 1].
* **Required Burp Skills**: Complete Burp Suite toolkit (Proxy, Repeater, Intruder, Collaborator, Decoder, Comparer, DOM Invader, InQL, Turbo Intruder)[cite: 1].
* **Required HTTP Knowledge**: Comprehensive full-stack HTTP behavior and vulnerability signature recognition[cite: 1].
* **Mastery Criteria**: Methodically conducting recon, forming hypotheses, testing targets, and exploiting vulnerabilities without title or context hints 25 60[cite: 1].
* **Revision Requirements**: Full reconnaissance and testing methodology checklist (Recon → Surface Mapping → Input Identification → Hypothesis Testing → Exploitation → Impact Demonstration)[cite: 1].
* **Mystery-Lab Readiness**: Complete Mastery[cite: 1].

---

## Phase 10 — Mixed Vulnerability Challenges

* **Topics**: Cross-Topic Challenges, Practice Certification Exam, Multi-Stage Vulnerability Chains 57 62[cite: 1].
* **Learning Materials**: Practice Exam, Exam Hints & Guidance 57 62[cite: 1].
* **Labs**: Practice Exam environment (multi-step vulnerability chain challenges combining access control, SQLi, XSS, SSRF, Request Smuggling, etc.) 62[cite: 1].
* **Required Burp Skills**: Exploit chaining, rapid manual testing methodology under strict time budgets[cite: 1].
* **Required HTTP Knowledge**: Multi-stage exploit chaining mechanics (e.g., SSRF to internal admin → file upload to RCE; XSS to CSRF → privilege escalation)[cite: 1].
* **Mastery Criteria**: Solving multi-stage vulnerability chains under simulated exam constraints without hints or walkthroughs 57 62[cite: 1].
* **Revision Requirements**: Final audit of testing speed, weak areas, and time-management strategies[cite: 1].
* **Mystery-Lab Readiness**: Certified Master[cite: 1].
