FROM nvidia/cuda:11.3.0-cudnn8-devel-ubuntu20.04 

RUN ln -sf /usr/share/zoneinfo/Asia/Tokyo /etc/localtime

# パッケージの追加とタイムゾーンの設定
# 必要に応じてインストールするパッケージを追加してください
RUN apt-get update && apt-get install -y \ 
    tzdata \
    git \ 
    wget \
    python3-pip \
    libgl1-mesa-dev \
&&  apt-get clean \
&&  rm -rf /var/lib/apt/lists/*
# JupyterLab関連のパッケージ（いくつかの拡張機能を含む）
# 必要に応じて、JupyterLabの拡張機能などを追加してください
RUN pip3 install --upgrade pip \
&&  pip install --no-cache-dir \
    black \
    jupyterlab \
    jupyterlab_code_formatter \
    jupyterlab-git \
    lckr-jupyterlab-variableinspector \
    jupyterlab_widgets \
    ipywidgets \
    import-ipynb

# 基本パッケージ
# Pythonでよく利用する基本的なパッケージです
# JupyterLabの動作には影響しないので、必要に応じてカスタマイズしてください
RUN pip install --no-cache-dir \
    numpy \
    pandas \
    scipy \
    scikit-learn \
    pycaret \
    matplotlib \
    japanize_matplotlib \
    mlxtend \
    seaborn \
    plotly \
    requests \
    beautifulsoup4 \
    Pillow \
    opencv-python \
    opencv-contrib-python \
    lxml
# 追加パッケージ（必要に応じて）
# 各環境に特化したパッケージがある場合、この部分に追加します
RUN pip install --no-cache-dir \
    pydeps \
    graphviz \
    pandas_profiling \
    shap \
    umap \
    xgboost \
    lightgbm
RUN pip install --no-cache-dir \
    torch==1.11.0+cu113 torchvision==0.12.0+cu113  -f https://download.pytorch.org/whl/torch_stable.html

RUN pip install --no-cache-dir \
    tensorflow
# 研究室用追加パッケージ
RUN pip install --no-cache-dir \
    pip install praat-parselmouth
