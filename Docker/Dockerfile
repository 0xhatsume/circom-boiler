#FROM shardlabs/cairo-cli:latest
FROM ghcr.io/foundry-rs/foundry:latest
#FROM --platform=linux/amd64 foundry:latest

# update bins
RUN apk add gmp-dev g++ gcc curl curl-dev

# add rust
RUN curl --proto '=https' --tlsv1.2 https://sh.rustup.rs -sSf | sh -s -- -y
ENV PATH="/root/.cargo/bin:${PATH}"

# add circom
RUN git clone https://github.com/iden3/circom.git /home/circom && \
cd /home/circom && cargo build --release && \
cargo install --path circom
