docs: bindings
	npm install
	npx typedoc --out ../../docs ../bindings/wasm/livesplit_core.ts

bindings:
	@(cd ../bind_gen && cargo run)

copy-node: bindings
	cp ../bindings/node/livesplit_core.js ./node/livesplit_core.js
	cp ../bindings/node/livesplit_core.ts ./node/livesplit_core.ts
	cp ../../target/release/liblivesplit_core.dylib ./node/livesplit_core.dylib
	@(cd ./node && npm install && npx tsc)
