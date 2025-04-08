# HiDream-I1 4Bit Quantized Model

![HiDream-I1 Demo](assets/demo.jpg)


This repository is a fork of `HiDream-I1` quantized to 4 bits, allowing it to run in less than 16GB of VRAM.

> `HiDream-I1` is a new open-source image generative foundation model with 17B parameters that achieves state-of-the-art image generation quality within seconds.

## Models

We offer both the full version and distilled models. For more information about the models, please refer to the link under Usage.

| Name            | Script                                             | Inference Steps | HuggingFace repo       |
| --------------- | -------------------------------------------------- | --------------- | ---------------------- |
| HiDream-I1-Full | [inference.py](./inference.py)                     | 50              | 🤗 [HiDream-I1-Full](https://huggingface.co/HiDream-ai/HiDream-I1-Full)  |
| HiDream-I1-Dev  | [inference.py](./inference.py)                     | 28              | 🤗 [HiDream-I1-Dev](https://huggingface.co/HiDream-ai/HiDream-I1-Dev) |
| HiDream-I1-Fast | [inference.py](./inference.py)                     | 16              | 🤗 [HiDream-I1-Fast](https://huggingface.co/HiDream-ai/HiDream-I1-Fast) |


## Quick Start
Please make sure you have installed [Flash Attention](https://github.com/Dao-AILab/flash-attention). We recommend CUDA versions 12.4 for the manual installation.
```
pip install -r requirements.txt
```

Then you can run the inference scripts to generate images:

``` python 
python -m hi_diffusers "A cat holding a sign that says 'hello world'"

# or you can specify the model
python -m hi_diffusers "A cat holding a sign that says 'hello world'" -m fast
```

> **Note:** The inference script will automatically download `meta-llama/Meta-Llama-3.1-8B-Instruct` model files. If you encounter network issues, you can download these files ahead of time and place them in the appropriate cache directory to avoid download failures during inference.

## Gradio Demo

We also provide a Gradio demo for interactive image generation. You can run the demo with:

``` python
pip install gradio
python gradio_demo.py 
```


## License

The code in this repository and the HiDream-I1 models are licensed under [MIT License](./LICENSE).
