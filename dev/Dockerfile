FROM debian:bookworm-slim

ENV LANG=C.UTF-8
ENV LC_ALL=C.UTF-8

# upLaTeX, latexmk, 必須フォントパッケージのインストール
RUN apt-get update && apt-get upgrade -y && \
    apt-get install -y --no-install-recommends \
    texlive-lang-japanese \
    texlive-latex-extra \
    texlive-fonts-recommended \
    texlive-fonts-extra \
    latexmk \
    perl \
    && apt-get clean \
    && rm -rf /var/lib/apt/lists/*

# 日本語標準フォント（原ノ味）と太字のマップを有効化
RUN kanji-config-updmap-sys haranoaji
