FROM aquasec/trivy as trivy
RUN mkdir -p /cache \
    && trivy --cache-dir /cache image --download-db-only \
    && trivy --cache-dir /cache image --download-java-db-only

FROM seanly/scratch

COPY --from=trivy /usr/local/bin/trivy /usr/bin/
COPY --from=trivy /contrib /
COPY --from=trivy /cache /root/.cache/trivy