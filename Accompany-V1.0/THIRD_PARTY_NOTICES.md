# Third-Party Notices

Accompany（桌面智能陪伴聊天机器人）使用了以下第三方开源软件。
本文件旨在履行各开源许可证的声明义务。

---

## Direct Dependencies

### EmotiEffLib
- **Description**: Facial emotion recognition in photos and videos
- **Homepage**: https://github.com/sb-ai-lab/EmotiEffLib
- **License**: Apache License 2.0
- **Copyright**: (c) Andrey Savchenko, Egor Churaev, HSE University

### ONNX Runtime
- **Description**: Cross-platform machine learning model accelerator
- **Homepage**: https://github.com/microsoft/onnxruntime
- **License**: MIT License
- **Copyright**: (c) Microsoft Corporation
- **Note**: Used by both EmotiEffLib (emotion recognition) and ChromaDB (embedding inference).
  The embedding model `ONNXMiniLM_L6_V2` (Apache 2.0) is bundled with ChromaDB.

### ONNX
- **Description**: Open Neural Network Exchange
- **Homepage**: https://github.com/onnx/onnx
- **License**: Apache License 2.0
- **Copyright**: (c) LF AI & Data Foundation

### OpenCV (opencv-python)
- **Description**: Open Source Computer Vision Library
- **Homepage**: https://github.com/opencv/opencv
- **License**: Apache License 2.0
- **Copyright**: (c) OpenCV Team

### PyQt6
- **Description**: Python bindings for the Qt application framework
- **Homepage**: https://www.riverbankcomputing.com/software/pyqt/
- **License**: GNU General Public License v3 (GPLv3) / Riverbank Commercial License
- **Copyright**: (c) Riverbank Computing Limited
- **Notice**: PyQt6 is distributed under GPLv3. If you distribute Accompany as a
  compiled binary, you must either (a) make the complete corresponding source
  code available, or (b) obtain a commercial PyQt license from Riverbank.

### LangChain / LangGraph
- **Description**: Building applications with LLMs through composability
- **Homepage**: https://github.com/langchain-ai/langchain
- **License**: MIT License
- **Copyright**: (c) LangChain Inc.

### ChromaDB
- **Description**: Open-source AI-native vector database
- **Homepage**: https://github.com/chroma-core/chroma
- **License**: Apache License 2.0
- **Copyright**: (c) Chroma Inc.

### NumPy
- **Description**: Fundamental package for scientific computing with Python
- **Homepage**: https://github.com/numpy/numpy
- **License**: BSD 3-Clause License
- **Copyright**: (c) NumPy Developers

### python-dotenv
- **Description**: Reads key-value pairs from .env file
- **Homepage**: https://github.com/theskumar/python-dotenv
- **License**: BSD 3-Clause License
- **Copyright**: (c) Saurabh Kumar

### Loguru
- **Description**: Python logging made (stupidly) simple
- **Homepage**: https://github.com/Delgan/loguru
- **License**: MIT License
- **Copyright**: (c) Delgan

### HTTPX
- **Description**: A next-generation HTTP client for Python
- **Homepage**: https://github.com/encode/httpx
- **License**: BSD 3-Clause License
- **Copyright**: (c) Encode OSS Ltd

### Tenacity
- **Description**: Retrying library for Python
- **Homepage**: https://github.com/jd/tenacity
- **License**: Apache License 2.0
- **Copyright**: (c) Julien Danjou

---

## Major Transitive Dependencies

### Pillow
- **Description**: Python Imaging Library (Fork)
- **Homepage**: https://github.com/python-pillow/Pillow
- **License**: Historical Permission Notice and Disclaimer (HPND)
- **Copyright**: (c) Alex Clark and contributors

### scikit-learn
- **Description**: Machine Learning in Python
- **Homepage**: https://github.com/scikit-learn/scikit-learn
- **License**: BSD 3-Clause License
- **Copyright**: (c) The scikit-learn developers

### SciPy
- **Description**: Fundamental algorithms for scientific computing in Python
- **Homepage**: https://github.com/scipy/scipy
- **License**: BSD 3-Clause License
- **Copyright**: (c) SciPy Developers

### OpenAI Python SDK
- **Description**: The official Python library for the OpenAI API
- **Homepage**: https://github.com/openai/openai-python
- **License**: Apache License 2.0
- **Copyright**: (c) OpenAI

### tiktoken
- **Description**: Fast BPE tokeniser
- **Homepage**: https://github.com/openai/tiktoken
- **License**: MIT License
- **Copyright**: (c) OpenAI

### Pydantic
- **Description**: Data validation using Python type hints
- **Homepage**: https://github.com/pydantic/pydantic
- **License**: MIT License
- **Copyright**: (c) Pydantic Team

### SQLAlchemy
- **Description**: The Python SQL Toolkit and Object Relational Mapper
- **Homepage**: https://github.com/sqlalchemy/sqlalchemy
- **License**: MIT License
- **Copyright**: (c) Michael Bayer

### gRPC / protobuf
- **Description**: High performance, open source universal RPC framework
- **Homepage**: https://github.com/grpc/grpc
- **License**: Apache License 2.0
- **Copyright**: (c) The gRPC Authors

### certifi
- **Description**: Python package for providing Mozilla's CA Bundle
- **Homepage**: https://github.com/certifi/python-certifi
- **License**: Mozilla Public License 2.0 (MPL-2.0)
- **Copyright**: (c) Kenneth Reitz

### urllib3
- **Description**: HTTP library with thread-safe connection pooling
- **Homepage**: https://github.com/urllib3/urllib3
- **License**: MIT License
- **Copyright**: (c) Andrey Petrov

### aiohttp
- **Description**: Async HTTP client/server framework
- **Homepage**: https://github.com/aio-libs/aiohttp
- **License**: Apache License 2.0
- **Copyright**: (c) aiohttp maintainers

### h5py
- **Description**: Read and write HDF5 files from Python
- **Homepage**: https://github.com/h5py/h5py
- **License**: BSD 3-Clause License
- **Copyright**: (c) Andrew Collette and contributors

### pandas
- **Description**: Powerful data structures for data analysis
- **Homepage**: https://github.com/pandas-dev/pandas
- **License**: BSD 3-Clause License
- **Copyright**: (c) The pandas development team

### Matplotlib
- **Description**: Python plotting package
- **Homepage**: https://github.com/matplotlib/matplotlib
- **License**: Python Software Foundation License (PSF) / not used as runtime dependency
- **Copyright**: (c) The Matplotlib development team

### Requests
- **Description**: Python HTTP for Humans
- **Homepage**: https://github.com/psf/requests
- **License**: Apache License 2.0
- **Copyright**: (c) Kenneth Reitz

### Uvicorn
- **Description**: The lightning-fast ASGI server
- **Homepage**: https://github.com/encode/uvicorn
- **License**: BSD 3-Clause License
- **Copyright**: (c) Encode OSS Ltd

### Rich
- **Description**: Render rich text and beautiful formatting in the terminal
- **Homepage**: https://github.com/Textualize/rich
- **License**: MIT License
- **Copyright**: (c) Will McGugan

### tqdm
- **Description**: Fast, Extensible Progress Bar
- **Homepage**: https://github.com/tqdm/tqdm
- **License**: Mozilla Public License 2.0 (MPL-2.0) / MIT
- **Copyright**: (c) tqdm developers

---

## Full License Texts

The full text of each open-source license can be found at:

| License | URL |
|---------|-----|
| Apache License 2.0 | https://www.apache.org/licenses/LICENSE-2.0 |
| MIT License | https://opensource.org/licenses/MIT |
| BSD 3-Clause | https://opensource.org/licenses/BSD-3-Clause |
| GPLv3 | https://www.gnu.org/licenses/gpl-3.0.html |
| MPL-2.0 | https://www.mozilla.org/en-US/MPL/2.0/ |
| PSF License | https://opensource.org/licenses/Python-2.0 |

---

## Accompany License

Accompany is distributed under the Apache License 2.0.

```
Copyright 2025-2026 Accompany Project

Licensed under the Apache License, Version 2.0 (the "License");
you may not use this file except in compliance with the License.
You may obtain a copy of the License at

    http://www.apache.org/licenses/LICENSE-2.0

Unless required by applicable law or agreed to in writing, software
distributed under the License is distributed on an "AS IS" BASIS,
WITHOUT WARRANTIES OR CONDITIONS OF ANY KIND, either express or implied.
See the License for the specific language governing permissions and
limitations under the License.
```

---

*Last updated: 2026-07-09. If you discover any missing or incorrect
attributions, please file an issue or submit a pull request.*
