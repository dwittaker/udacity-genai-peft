ARG VARIANT="1-3.12-bullseye"
FROM mcr.microsoft.com/vscode/devcontainers/python:${VARIANT}

ARG VENV_PATH="/home/vscode/venv"

COPY requirements.txt /tmp/requirements.txt
# COPY requirements-dev.txt /tmp/requirements-dev.txt
# COPY app/ /workspace/app/

RUN su vscode -c "python3 -m venv ${VENV_PATH} && \
    ${VENV_PATH}/bin/pip install --disable-pip-version-check -r /tmp/requirements.txt"
     
# RUN chmod +x /workspace/app/app.py

# WORKDIR /workspace/app/

# Run the app when the container starts - optional
# CMD ["streamlit", "run", "app.py"]

RUN echo "source ${VENV_PATH}/bin/activate" >> /home/vscode/.bashrc

# EXPOSE 8501