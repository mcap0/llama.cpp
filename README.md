use original docs pls. [https://github.com/ggml-org/llama.cpp](https://github.com/ggml-org/llama.cpp)

I vibe coded this fix. I needed it for gemma4 in my pixel6a phone where I didn't want to start new conversations where my context window was full.

It seems to work whenever single message sent is not over context window (would still return error if you sent more tokens than those set with `-c` flag). If the new message is < context window, truncate magic will happen server side, and you won't need to start a new chat in a full context window.
Truncation is said to happen some tokens after the start of the prompt, but with these vibe coded fixes you never know...

To use, append the `--truncate-input` flag.

