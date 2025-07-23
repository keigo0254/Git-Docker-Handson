# ベースイメージを指定
FROM python:3.11-slim

# ビルド時にホストのUIDとGIDを受け取るための引数
ARG UID=1000
ARG GID=1000

# UIDとGIDを使って新しいユーザー(user)を作成
# -m オプションでホームディレクトリも作成
RUN groupadd -g ${GID} -o user && \
    useradd --uid ${UID} --gid ${GID} -m -o -s /bin/bash user

# ユーザーをuserに切り替え
USER user

# 作業ディレクトリを設定
WORKDIR /home/user

# コンテナ起動時に実行されるデフォルトのコマンド
CMD ["/bin/bash"]