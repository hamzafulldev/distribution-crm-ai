# Distribution CRM – on-phone voice understanding model

A small AI model that runs **on the phone, offline**, inside the Distribution CRM app. It reads what a
distributor says (Urdu, Roman Urdu, English, or a mix) and returns its meaning as a short JSON
object, for example:

    He said: "bilal store ka bill bana do"   ->  {"intent":"new_bill","customer":"bilal store"}

- **Base model:** [Qwen/Qwen3.5-2B](https://huggingface.co/Qwen/Qwen3.5-2B) (Apache License 2.0, see `LICENSE`).
- **Changes:** LoRA fine-tuning on about 2,400 made-up shop-talk sentences (no real customer data),
  merged into the base weights, converted with llama.cpp and compressed to Q5_K_M (GGUF).
- **Use:** with llama.cpp / llama.rn, prompt format and answer shapes as in the app's
  `src/voice/ai/prompt.ts`. It is trained for that app only and is not a general chat model.

Download: see Releases.
