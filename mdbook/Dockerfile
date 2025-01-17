FROM rust:1.84-slim AS build

ARG TARGET=aarch64-unknown-linux-musl

RUN apt-get update && \
    apt-get install --assume-yes --no-install-recommends musl-tools && \
    rustup target add "${TARGET}" && \
    cargo install mdbook --locked --target "${TARGET}" --version 0.4.43 && \
    cargo install mdbook-svgbob --locked --target "${TARGET}" --version 0.2.1

FROM alpine:3.21

COPY --from=build /usr/local/cargo/bin/mdbook /usr/local/bin/mdbook
COPY --from=build /usr/local/cargo/bin/mdbook-svgbob /usr/local/bin/mdbook-svgbob

WORKDIR /workdir

ENTRYPOINT []

CMD /bin/sh
