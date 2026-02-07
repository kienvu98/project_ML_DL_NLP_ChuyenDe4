FROM nvidia/cuda:12.4.1-cudnn-runtime-ubuntu22.04

# ===== System packages =====
RUN apt-get update && apt-get install -y \
    python3 \
    python3-pip \
    python3-dev \
    git \
    curl \
    vim \
    && rm -rf /var/lib/apt/lists/*

# ===== Python =====
RUN python3 -m pip install --upgrade pip

WORKDIR /workspace

# ===== Python dependencies =====
COPY docker/dl/requirements.txt /tmp/requirements.txt
RUN pip install --no-cache-dir -r /tmp/requirements.txt

# ===== Environment =====
ENV PYTHONPATH=/workspace
ENV PYTHONUNBUFFERED=1

CMD ["bash"]
