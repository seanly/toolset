# trivy 

## sbom

```
docker run --rm -it -v $(pwd):/code seanly/toolset:trivy \
    /usr/bin/trivy sbom \
    --skip-db-update --skip-java-db-update --offline-scan \
    /code/target/bom.json \
    -s CRITICAL,HIGH --cache-dir /root/.cache/trivy
```

## air-gap

https://aquasecurity.github.io/trivy/v0.48/docs/advanced/air-gap/