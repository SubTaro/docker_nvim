FROM ubuntu:22.04

# nvimのインストール
RUN apt-get update ; \
 	apt-get install -y curl ripgrep tar unzip vim wget git fzf; \
 	apt-get install -y python3-pip

RUN wget https://github.com/neovim/neovim/releases/download/v0.9.5/nvim-linux64.tar.gz &&\
	tar -zxvf nvim-linux64.tar.gz &&\
	mv nvim-linux64/bin/nvim usr/bin/nvim &&\
	mv nvim-linux64/lib/nvim usr/lib/nvim &&\
	mv nvim-linux64/share/nvim/ usr/share/nvim &&\
	rm -rf nvim-linux64 &&\
	rm nvim-linux64.tar.gz

# LSP関係のものを入れる
RUN wget https://go.dev/dl/go1.22.3.linux-amd64.tar.gz; \
	tar -C /usr/local/ -xzf go1.22.3.linux-amd64.tar.gz

ENV PATH $PATH:/usr/local/go/bin
# neovimの環境をそろえる
RUN git clone https://github.com/SubTaro/dotfiles.git ~/dotfiles; \
	. ~/dotfiles/setup.sh; \
	nvim +:Lazy +":MasonInstall gopls" +:qa

WORKDIR /workdir
