# Fast-LLM powered by Candle 🦀

Yo! I really have no clue what I'm doing here, but here's me trying to make the quantised llm example in candle into its own package.

None of the work here is original and all attributions should go to Laurent & Nicolas who made this gem of a library and with ready-to-use examples.

## What does it do?

It allows you to run popular GGUF checkpoints on the Hugging Face Hub via Candle. It allows you to infer from the checkpoints both via Metal as well as on CPU (although CPU is much much slower).
This is an alpha release of the package and I expect quite a lot of this to change in the short term.

## How do you run this bad boi?

Step 1: `git clone https://github.com/Vaibhavs10/fast-llm.rs/`

Step 2: `cd fast-llm.rs`

Step 3: `cargo run --features metal --release ----which 7b-chat --prompt "What is the meaning of life according to a dog?" --sample-len 100`

Note: you can remove the `--features metal` to run inference on CPU.


