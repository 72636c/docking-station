FROM rust:1.48-slim AS build

ARG TARGET=x86_64-unknown-linux-musl

RUN apt-get update && \
    apt-get install --assume-yes --no-install-recommends musl-tools && \
    rustup target add "${TARGET}" && \
    cargo install mdbook --target "${TARGET}" --version 0.4.5 && \
    cargo install mdbook-svgbob --target "${TARGET}" --version 0.1.1

FROM alpine:3.12

COPY --from=build /usr/local/cargo/bin/mdbook /usr/local/bin/mdbook
COPY --from=build /usr/local/cargo/bin/mdbook-svgbob /usr/local/bin/mdbook-svgbob

WORKDIR /workdir

ENTRYPOINT []

CMD /bin/sh
