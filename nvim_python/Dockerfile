FROM python:3.10.14-alpine3.19

RUN apk update ; \
	apk add curl tar ripgrep wget git fzf py3-pip build-base neovim

# neovimの環境をそろえる
RUN git clone https://github.com/SubTaro/docker_nvim.git ~/tmp; \
	mv ~/tmp/dotfiles ~/dotfiles; \
	rm -rf ~/tmp; \
	. ~/dotfiles/setup.sh; \
	nvim +:Lazy +":MasonInstall python-lsp-server" +":MasonInstall debugpy" +:qa

WORKDIR /workdir
