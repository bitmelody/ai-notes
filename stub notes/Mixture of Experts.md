
HuggingGPT, JARVIS, ToolFormer, TaskMatrix, Chameleon.
https://www.reddit.com/r/MachineLearning/comments/137rxgw/comment/jiuof1w/?utm_source=reddit&utm_medium=web2x&context=3


Google Switch C 1.6T MoE model
	- https://news.ycombinator.com/item?id=38352794

Switch Transformers
- https://twitter.com/TheTuringPost/status/1670793833964097537?s=20

TAPAS: 
- https://twitter.com/TheTuringPost/status/1670793846303645697


https://twitter.com/amanrsanger/status/1690072804161650690?s=20
- MOE allows models to scale parameter count and performance without scaling inference or training costs. This means I could serve an MOE model significantly faster and cheaper than a quality-equivalent dense model [1]. (2/7)
- Why is this bad for on-device inference? On-device inference is extremely memory limited. Apple’s M2 Mac has just 24GB of GPU RAM. Even with 4-bit quantization we can barely fit a 48B param model. And that model would see latency of <6 tok/s [2] (3/7)
- An A100 has 80GB of memory. We can serve a quality-equivalent MOE model with 100B parameters, taking up 50GB of RAM. It would likely cost around $0.2/1M generated token and less than $0.1/1M tokens running at 26 tok/s. If just maximizing speed, we could hit 173 tok/s! [3] (4/7)
- You can also serve massive MOE models splitting model weights across GPUs. On a single machine, using 640 GB of GPU RAM, you can easily serve >1T parameter MOE model (i.e. near GPT-4 level) with 4-bit quant. And it would cost within a factor of two of serving GPT-3 [