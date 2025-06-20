# SmolVLM

A small and fast vision-language AI model.

---

## Models

This project requires two large model files, which cannot be included directly due to size:

| Model              | Description          | Download Link                                                                                      |
|--------------------|----------------------|--------------------------------------------------------------------------------------------------|
| SmolVLM main model  | Core vision-language model weights | [Download here](https://drive.google.com/file/d/14hsZXbkM6iSo5wANdjt5su70saDCbReQ/view?usp=drive_link) |
| mmproj model       | Vision modality model (mmproj)      | [Download here](https://drive.google.com/file/d/18_01L9kV1MW1j611QLRfwyC2DDUsiVZ5/view?usp=drive_link)      |

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
    ├── SmolVLM-500M-Instruct-f16.gguf
    └── mmproj-SmolVLM-500M-Instruct-f16.gguf
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
    -m models/SmolVLM-500M-Instruct-f16.gguf \
    --mmproj models/mmproj-SmolVLM-500M-Instruct-f16.gguf
```

This will start the server on:
```bash
http://127.0.0.1:8080
```
