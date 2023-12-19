# trivy 

## sbom

```
trivy sbom --skip-db-update --skip-java-db-update --offline-scan target/bom.json -s CRITICAL,HIGH
```