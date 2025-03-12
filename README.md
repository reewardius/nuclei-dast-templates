# nuclei-dast-templates
```
katana -u http://testphp.vulnweb.com -aff -j -o katana.jsonl
nuclei -l katana.jsonl -im jsonl -t nuclei-dast-templates
```
**Nuclei DAST Templates**

![image](https://github.com/user-attachments/assets/fec0e7c1-8f28-41f1-9193-0b1ae5bf2224)

**Tags**
```
fuzzing-req-query
fuzzing-req-body
fuzzing-req-path
fuzzing-req-cookie
fuzzing-req-header
```
**Command to run fuzzing scan**
```
nuclei -l katana.jsonl -im jsonl -t nuclei-dast-templates -tags fuzzing-req-query
nuclei -l katana.jsonl -im jsonl -t nuclei-dast-templates -tags fuzzing-req-body
nuclei -l katana.jsonl -im jsonl -t nuclei-dast-templates -tags fuzzing-req-cookie
nuclei -l katana.jsonl -im jsonl -t nuclei-dast-templates -tags fuzzing-req-header
nuclei -l katana.jsonl -im jsonl -t nuclei-dast-templates -tags fuzzing-req-path
```
![image](https://github.com/user-attachments/assets/dabcb114-f193-485b-ac6d-092198f1638c)
