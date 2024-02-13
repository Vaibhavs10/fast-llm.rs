# Fast-LLM powered by Candle 🦀

Yo! I really have no clue what I'm doing here, but here's me learning to rust by making [candle's](https://github.com/huggingface/candle) quantised llm examples into its own package.

None of the work here is original and all attributions should go to [Laurent](https://github.com/LaurentMazare) & [Nicolas](https://github.com/Narsil) who made this gem of a library and with ready-to-use examples.

## What does it do?

It allows you to run popular GGUF checkpoints on the Hugging Face Hub via Candle. Works on Macs with Metal or on CPU (although CPU is much much slower).

This is an alpha release and I expect quite a lot of this to change in the short term.

## How do you run this bad boi?

Step 1: `git clone https://github.com/Vaibhavs10/fast-llm.rs/`

Step 2: `cd fast-llm.rs`

Step 3: `cargo run --features metal --release -- --which 7b-chat --prompt "What is the meaning of life according to a dog?" --sample-len 100`

Note: you can remove the `--features metal` to run inference on CPU.

Check [how to install Rust](#installing-rust) and [how to use the CLI](#how-to-use-the-cli) if you need to.

## Which models are supported?

1. Mistral 7B
2. Llama 7B/ 13B/ 34B
3. CodeLlama 7B/ 13B/ 34B
4. Mixtral 8x7B

You can also bring your own GGUF checkpoint by passing a `--model`.

## More details

### Installing Rust

[Just follow the official instructions](https://www.rust-lang.org/tools/install).

### How to use the CLI

When you use `cargo run`, command-line arguments go to `cargo`. Use `--` to send them to the `fast-llm` binary. The following will compile the code in release mode (a `cargo` option), and then list all the options `fast-llm` supports.

```bash
cargo run --release -- --help
```

By default, `fast-llm` sends your prompt to the LLM, prints the response and quits. You can use _interactive_ or _chat_ mode too:

* `cargo run --release -- --prompt interactive`. Runs in interactive mode. You can ask multiple independent queries, previous context is not retained.

* `cargo run --release -- --prompt chat`. Runs in chat mode. Carries conversation history, just like when using ChatGPT or [HuggingChat](https://huggingface.co/chat/). In this mode you'll get best results with one of the _Instruct_ versions of the models, Zephyr, or OpenChat, as all these models are designed for chat.