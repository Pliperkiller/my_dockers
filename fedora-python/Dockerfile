# Usar Fedora como imagen base
FROM fedora:latest

# Instalar Python, pip y Java 8
RUN dnf update -y && \
    dnf install -y python3 python3-pip java-1.8.0-openjdk && \
    dnf clean all

# Establecer JAVA_HOME (opcional, pero recomendado para aplicaciones que lo requieran)
ENV JAVA_HOME=/usr/lib/jvm/java-1.8.0-openjdk
ENV PATH=$JAVA_HOME/bin:$PATH

# Instalar JupyterLab
RUN pip3 install jupyterlab

# Configurar el comando por defecto para iniciar JupyterLab
CMD ["jupyter-lab", "--ip=0.0.0.0", "--port=8888", "--no-browser", "--allow-root"]
