# syntax=docker/dockerfile-upstream:master
ARG CNPG_TAG
ARG PGVECTORS_TAG
ARG TARGETARCH

FROM ghcr.io/cloudnative-pg/postgresql:$CNPG_TAG

# drop to root to install packages
USER root

# install pgvecto.rs
ADD https://github.com/tensorchord/pgvecto.rs/releases/download/v$PGVECTORS_TAG/vectors-pg${CNPG_TAG}_${PGVECTORS_TAG}_$TARGETARCH.deb ./pgvectors.deb

RUN apt install ./pgvectors.deb

USER postgres
