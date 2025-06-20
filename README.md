# SmolVLM

A small and fast vision-language AI model.

---

## Models

This project requires two large model files, which cannot be included directly due to size:

| Model              | Description          | Download Link                                                                                      |
|--------------------|----------------------|--------------------------------------------------------------------------------------------------|
| SmolVLM main model  | Core vision-language model weights | [Download here](https://drive.google.com/file/d/15ussrdsv4Y4pAA2741-JqSMpUs_CmxDJ/view?usp=drive_link) |
| mmproj model       | Vision modality model (mmproj)      | [Download here](https://drive.google.com/file/d/1iG2p2Z4mUqdhSqhlxgItgBsQge6Z7d8X/view?usp=drive_link)      |

---

## Setup

1. Clone the repository:

```bash
git clone https://github.com/ouamy/smolvlm.git
cd smolvlm
```

2. Download the model files from the links above and place them in the `models/` directory:

```bash
smolvlm/
└── models/
    ├── ggml-org_SmolVLM2-2.2B-Instruct-GGUF_SmolVLM2-2.2B-Instruct-Q4_K_M.gguf
    └── ggml-org_SmolVLM2-2.2B-Instruct-GGUF_mmproj-SmolVLM2-2.2B-Instruct-Q8_0.gguf
```

3. Copy all the .so files to /usr/local/lib and run ldconfig

```bash
sudo cp build/bin/lib*.so /usr/local/lib/
sudo ldconfig
```

---

## Run

Start the server with both models:
```bash
build/bin/llama-server \
    -m models/ggml-org_SmolVLM2-2.2B-Instruct-GGUF_SmolVLM2-2.2B-Instruct-Q4_K_M.gguf \
    --mmproj models/ggml-org_SmolVLM2-2.2B-Instruct-GGUF_mmproj-SmolVLM2-2.2B-Instruct-Q8_0.gguf
```

This will start the server on:
```bash
http://127.0.0.1:8080
```
