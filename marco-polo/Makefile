rust-version:
	@echo "Rust command-line utility versions:"
	rustc --version 			#rust compiler
	cargo --version 			#rust package manager
	rustfmt --version			#rust code formatter
	rustup --version			#rust toolchain manager
	clippy-driver --version		#rust linter

format:
	cargo fmt --quiet

lint:
	cargo clippy --quiet
run:
	cargo run

release-arm:
	cargo lambda build --release --arm64

deploy:
	cargo lambda deploy \
	--iam-role arn:aws:iam::427755450963:role/service-role/rust-aws-lambda-role-xgglj8h5

invoke:
	cargo lambda invoke --remote \
		--data-ascii '{"name": "Marco"}' \
		--output-format json \
		marco-polo

all: format lint test run
