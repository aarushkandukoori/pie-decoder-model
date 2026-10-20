# Qwen3.5-0.8B for Pie's WebGPU engine

[Qwen/Qwen3.5-0.8B](https://huggingface.co/Qwen/Qwen3.5-0.8B) as a [Pie](https://github.com/pie-project/pie)
artifact, for running in a browser tab with Pie's WebGPU engine. It is the model behind
[Watch the decoder](https://aarushkandukoori.github.io/pie-decoder/)
([source](https://github.com/aarushkandukoori/pie-decoder)).

- File - `qwen3.5-0.8b.wgpu.zt`, 618 MiB, sha256 `845562ff27f36172f78c896ba7af516dc1cc6ec2df1aa388beab562170aebcc1`
- Deployment - `qwen35-d0.8b-vision-u4g64-kv-bf16` (weights in 4 bits, groups of 64; KV cache in bf16)
- Made with - `pie model import Qwen/Qwen3.5-0.8B` from pie-project/pie at `281c92a2d`, a native build with
  `--features wgpu`

GitHub allows 100 MB per file, so the file is stored as 13 pieces of 48 MiB (`.00` to `.12`) plus a manifest
(`qwen3.5-0.8b.wgpu.zt.json`), made with
[split-model.mjs](https://github.com/aarushkandukoori/pie-decoder/blob/main/split-model.mjs). The page's service
worker joins them back into one file. To get the file itself:

```bash
cat qwen3.5-0.8b.wgpu.zt.[0-9][0-9] > qwen3.5-0.8b.wgpu.zt
```

This is not an official Qwen or Pie release. The weights are Qwen's, under Apache 2.0 (see `LICENSE`); this file
changes their format and precision.
