FROM golang:1.22.3-alpine3.20

RUN apk update ; \
	apk add curl tar ripgrep wget git fzf py3-pip build-base neovim

# neovimの環境をそろえる
RUN git clone https://github.com/SubTaro/dotfiles.git ~/dotfiles; \
	. ~/dotfiles/setup.sh; \
	nvim +:Lazy +":MasonInstall gopls" +:qa

WORKDIR /workdir
