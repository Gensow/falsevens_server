FROM ubuntu:22.04

# 必要なライブラリだけインストール
RUN apt update && apt install -y \
    libxcursor1 libxinerama1 libxrandr2 libxi6 \
    libgl1-mesa-glx libx11-6 libxrender1 libxext6 \
    && rm -rf /var/lib/apt/lists/*

# 作業ディレクトリ
WORKDIR /app

# pckとGodotサーバーバイナリをコピー
COPY server.pck .
COPY server.x86_64 .

# 実行権限を付与
RUN chmod +x server.x86_64

# サーバー起動
CMD ["./server.x86_64", "--headless", "--path", ".", "res://scenes/server/ServerMain.tscn"]
