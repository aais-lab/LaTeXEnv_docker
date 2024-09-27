FROM debian:bookworm-slim

RUN ln -sf /usr/share/zoneinfo/Asia/Tokyo /etc/localtime

RUN apt update && \
    apt -y upgrade && \
    apt -y install texlive-full
