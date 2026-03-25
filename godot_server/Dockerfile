FROM ubuntu:22.04

RUN apt update && apt install -y \
    libxcursor1 libxinerama1 libxrandr2 libxi6 \
    libgl1-mesa-glx libx11-6 libxrender1 libxext6

WORKDIR /app

# pckだけコピー
COPY server.pck .

# Godot Linux版をダウンロード
RUN wget https://downloads.tuxfamily.org/godotengine/4.6/Godot_v4.6.1-stable_linux.x86_64.zip \
    && apt install -y unzip \
    && unzip Godot_v4.6.1-stable_linux.x86_64.zip \
    && mv Godot_v4.6.1-stable_linux.x86_64 server.x86_64 \
    && chmod +x server.x86_64

CMD ["./server.x86_64", "--headless", "--path", ".", "res://scenes/server/ServerMain.tscn"]