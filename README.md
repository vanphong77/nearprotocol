# nearprotocol
Basic smartcontract on near
phongnguyen12.testnet
npm install -g near-cli
rustup target add wasm32-unknown-unknown
cargo init --lib
cargo test -- --nocapture
env 'RUSTFLAGS=-C link-arg=-s' 
cargo build --target wasm32-unknown-unknown --release
cd ~/.near-credentials --noi luu giu key
RUSTFLAGS='-C link-arg=-s' cargo build --target wasm32-unknown-unknown --release
near create-account rose.phongnguyen12.testnet --masterAccount phongnguyen12.testnet --initialBalance 10
near deploy --wasmFile target/wasm32-unknown-unknown/release/nearprotocol.wasm --accountId rose.phongnguyen12.testnet
near call rose.phongnguyen12.testnet createupdate '{"k": "first_key", "v" : "1"}' --accountId rose.phongnguyen12.testnet
near view rose.phongnguyen12.testnet read '{"k": "first_key"}' --accountId rose.phongnguyen12.testnet
near call rose.phongnguyen12.testnet delete '{"k": "first_key"}' --accountId rose.phongnguyen12.testnet
RUSTFLAGS='-C link-arg=-s' cargo build --target wasm32-unknown-unknown --release 
