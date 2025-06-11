FROM nvcr.io/nvidia/tritonserver:25.02-vllm-python-py3

# Set the working directory
WORKDIR /app

# Copy the model repository
COPY ./model_repository /models

# Triton server starts automatically, but you can add custom startup scripts here if needed
# For example, to install additional Python packages:
# RUN pip install --no-cache-dir some-python-package

# The entrypoint is already defined in the base image, so you don't need a CMD instruction here

RUN pip install --upgrade bitsandbytes transformers vllm