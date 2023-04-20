FROM tensorflow/tensorflow:latest-gpu-jupyter

RUN apt-get update
# ユーザーを作成
ARG UID=1000
RUN useradd -m -u ${UID} user

# 作成したユーザーに切り替える
# このユーザーはRUN, CMD, ENTRYPOINT, docker run, exec の実行ユーザ。
USER ${UID}

# プロジェクトフォルダを/codeに追加する。ユーザー権限で扱えるようchownオプションを使う。
# ADDの実行権者はrootなのでオプションが必要。
ADD  --chown=user:user . /work
# 作成したフォルダに移動し、パッケージリストをインストールする。
#WORKDIR /work

RUN pip install --upgrade pip
RUN pip install pandas
RUN pip install jupyterlab
RUN pip install matplotlib
RUN pip install numpy>=1.18.1
RUN pip install keras>=2.3.1
RUN pip install scikit-learn>=0.22.1
RUN pip install opencv-python>=4.1.2.30
RUN pip install imagehash>=4.0
RUN pip install pillow>=7.0.0
RUN pip install pyscreenshot>=1.0
