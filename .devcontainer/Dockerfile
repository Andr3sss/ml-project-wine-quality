# Base image - Python 3.11 oficial
FROM python:3.11-slim-bookworm

# Metadata
LABEL maintainer="Andrés Quisilema & José Quishpe"
LABEL description="ML Final Project - Wine Quality DevContainer"

# Evitar prompts interactivos
ENV DEBIAN_FRONTEND=noninteractive
ENV PYTHONUNBUFFERED=1
ENV PIP_NO_CACHE_DIR=1

# Instalar dependencias del sistema
RUN apt-get update && apt-get install -y \
    git \
    curl \
    build-essential \
    && rm -rf /var/lib/apt/lists/*

# Instalar UV (package manager moderno)
RUN curl -LsSf https://astral.sh/uv/install.sh | sh
ENV PATH="/root/.cargo/bin:$PATH"

# Crear directorio de trabajo
WORKDIR /workspace

# Copiar archivos de configuración primero (para cache de Docker)
COPY pyproject.toml ./

# Crear virtual environment con UV
RUN uv venv .venv --python 3.11

# Instalar dependencias con UV
RUN uv pip install --python .venv/bin/python -r pyproject.toml

# Activar venv por default
ENV PATH="/workspace/.venv/bin:$PATH"
ENV VIRTUAL_ENV="/workspace/.venv"

# Exponer puerto de Jupyter
EXPOSE 8888

# Verificar instalación
RUN python --version && \
    uv --version && \
    python -c "import polars; print(f'Polars {polars.__version__}')" && \
    python -c "import sklearn; print(f'Scikit-learn {sklearn.__version__}')"

# Comando por default
CMD ["/bin/bash"]
