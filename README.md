# nuclei-dast-templates
**Crawl and fuzz all HTTP methods and their possible values:**
```bash
katana -u http://testphp.vulnweb.com -aff -iqp -j -o katana.jsonl && \
nuclei -l katana.jsonl -im jsonl -t nuclei-dast-templates/ -fuzz-param-frequency 10000
```
**Skip fuzzing of HTTP headers and cookies:**
```bash
nuclei -l katana.jsonl -im jsonl -t nuclei-dast-templates/ -dast -etags fuzzing-req-header,fuzzing-req-cookie -fuzz-param-frequency 10000
```
**General Tags**
```bash
fuzzing-req-query
fuzzing-req-body
fuzzing-req-path
fuzzing-req-cookie
fuzzing-req-header
```
**Fuzzing Vulnerability Tags**
```bash
blind-xss
fuzzing-req-crlf
fuzzing-req-csv
fuzzing-req-lfi
fuzzing-req-oob
fuzzing-req-rce
fuzzing-req-redirect
fuzzing-req-reflected
fuzzing-req-ssrf
fuzzing-req-ssti
fuzzing-req-xss
fuzzing-req-xxe
```
**The following tags can be used to perform fuzzing scans on different parts of an HTTP request**
Fuzzing query parameters:
```bash
nuclei -l katana.jsonl -im jsonl -t nuclei-dast-templates -tags fuzzing-req-query -fuzz-param-frequency 10000
```
Fuzzing the request body:
```bash
nuclei -l katana.jsonl -im jsonl -t nuclei-dast-templates -tags fuzzing-req-body -fuzz-param-frequency 10000
```
Fuzzing cookies in the request:
```bash
nuclei -l katana.jsonl -im jsonl -t nuclei-dast-templates -tags fuzzing-req-cookie -fuzz-param-frequency 10000
```
Fuzzing request headers:
```bash
nuclei -l katana.jsonl -im jsonl -t nuclei-dast-templates -tags fuzzing-req-header -fuzz-param-frequency 10000
```
Fuzzing the request path:
```bash
nuclei -l katana.jsonl -im jsonl -t nuclei-dast-templates -tags fuzzing-req-path -fuzz-param-frequency 10000
```
# Features

- Easily customize your scan by using tags that focus on different parts of HTTP requests (query, body, cookies, headers, and path).
- Fuzz multiple areas of HTTP requests to identify vulnerabilities like SQL injection, XSS, and other common web security flaws.
- Works seamlessly with Katana for crawling and Nuclei for vulnerability scanning, providing an efficient and automated security testing pipeline.
- Skip fuzzing on specific request sections (like headers or cookies) by excluding the relevant tags.
