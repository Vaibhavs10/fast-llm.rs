# Fast-LLM powered by Candle 🦀

Yo! I really have no clue what I'm doing here, but here's me learning to rust by making [candles](https://github.com/huggingface/candle) quantised llm example into its own package.

None of the work here is original and all attributions should go to [Laurent](https://github.com/LaurentMazare) & [Nicolas](https://github.com/Narsil) who made this gem of a library and with ready-to-use examples.

## What does it do?

It allows you to run popular GGUF checkpoints on the Hugging Face Hub via Candle. It allows you to infer from the checkpoints both via Metal as well as on CPU (although CPU is much much slower).

This is an alpha release and I expect quite a lot of this to change in the short term.

## How do you run this bad boi?

Step 1: `git clone https://github.com/Vaibhavs10/fast-llm.rs/`

Step 2: `cd fast-llm.rs`

Step 3: `cargo run --features metal --release ----which 7b-chat --prompt "What is the meaning of life according to a dog?" --sample-len 100`

Note: you can remove the `--features metal` to run inference on CPU.

## Which models are supported?

1. Mistral 7B
2. Llama 7B/ 13B/ 34B
3. CodeLlama 7B/ 13B/ 34B
4. Mixtral 8x7B

You can also bring your own GGUF checkpoint by passing a `--model`.