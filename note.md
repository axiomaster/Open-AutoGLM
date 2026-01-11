```bash
docker run --runtime nvidia --gpus all -it --rm \
    --network host \
    --shm-size=16g \
    -v ~/models:/models \
    ghcr.io/nvidia-ai-iot/vllm:latest-jetson-orin
```


```bash
python3 -m vllm.entrypoints.openai.api_server \
    --model /models/AutoGLM-Phone-9B \
    --served-model-name autoglm-phone-9b \
    --gpu-memory-utilization 0.7 \
    --max-model-len 8192 \
    --port 8000
```