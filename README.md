# My NeoVim Config (A NeoVim Config for Colemak Users)

#### [中文版README](./README_cn.md) by [@EvanMeek](https://github.com/EvanMeek)

![demo](./demo.png)

Please **DO NOT** just copy this config without really looking at it! Please, at least, read this README file!


#### 安装brew
```
/bin/bash -c "$(curl -fsSL https://gitee.com/cunkai/HomebrewCN/raw/master/Homebrew.sh)"

git config --global --unset http.proxy
git config --global http.proxy 'http://127.0.0.1:port'

# intel
git config --global --add safe.directory /usr/local/Homebrew/Library/Taps/homebrew/homebrew-core
git config --global --add safe.directory /usr/local/Homebrew/Library/Taps/homebrew/homebrew-cask

# m1/m2
git config --global --add safe.directory /opt/homebrew/Library/Taps/homebrew/homebrew-core
git config --global --add safe.directory /opt/homebrew/Library/Taps/homebrew/homebrew-cask
```

## Startup System Environment
- [ ] brew install zsh
- [ ] brew install tmux
- [ ] brew install fzf
- [ ] brew install bat
- [ ] brew install neovim 
- [ ] brew install node.jus 
- [ ] brew install python3 
- [ ] brew install yarn 


我假设你已经有了iTerm2这样的终端软件，安装好了zsh（Mac OS上已自带），如果没有，通常也是一条命令如apt install zsh或者yum install zsh就可以搞定。

oh-my-zsh
大名鼎鼎的oh-my-zsh是一个高度定制化、插件化的zsh配置，几乎是zsh的标配，安装非常方便。
```
curl -fsSL https://raw.github.com/robbyrussell/oh-my-zsh/master/tools/install.sh > oh-my-zsh.sh

```
安装好之后就可以通过~/.zshrc配置文件来设置theme、plugins了。
```
ssh-keygen -t rsa
cat ~/.ssh/id_rsa.pub
git clone git@github.com:JiaBaoChenT/nvim.git ~/workspace/utils/nvim
cp -r ~/workspace/utils/nvim/zshrc ~/.zshrc
```
autosuggestion
autosuggestion是zsh的一个插件，利用它，可以让你在终端输入命令的时候，自动给出建议，相当高效（酷炫）。
```
git clone https://github.com/zsh-users/zsh-autosuggestions ${ZSH_CUSTOM:-~/.oh-my-zsh/custom}/plugins/zsh-autosuggestions
```
然后将zsh-autosuggestions添加到~/.zshrc的plugins里面。
cp -r ~/workspace/dingxiang/practice/nvim/zshrc ~/.zshrc

syntax-highlight
syntax-highlight是另一个很有用的zsh插件，有了它，你在输入命令的时候如果有拼写错了，马上就能发现。
```
git clone https://github.com/zsh-users/zsh-syntax-highlighting.git ${ZSH_CUSTOM:-~/.oh-my-zsh/custom}/plugins/zsh-syntax-highlighting
```
然后将zsh-syntax-highlighting加入~/.zshrc的plugins里面。

interactive-cd
interactive-cd依赖后面会提到的fzf工具，它的安装很简单，只要把对应的zsh下载到oh-my-zsh的custom目录即可。
```
curl https://raw.githubusercontent.com/changyuheng/zsh-interactive-cd/master/zsh-interactive-cd.plugin.zsh -o ~/.oh-my-zsh/custom/zsh-interactive-cd.plugin.zsh
```
tmux
tmux是一个终端分屏神奇，尤其是对于那种需要在远程机器上开发调试的人来说，它简直是一个福音。当然，即便在本地笔记本上，它的分屏功能也是非常的实用。

通过软件包管理器安装即可，如Mac OS上执行brew install tmux。 安装完成之后，在终端执行tmux，就会开启一个session，你可以执行Ctrl+D从这个session detatch出来，然后再用tmux a -t [session] attach进去，另外你可以把一个终端分成多个window，再分成多个pane。
简约而不简单的fzf
fzf真乃神器，用上它之后，你会马上把什么CtrlP之流抛诸脑后，因为它太方便了。
```
cp ~/workspace/utils/nvim/tmux/tmux.conf ~/.tmux
```

我需要的唯一的一个编辑器neovim
vim/neovim作为我主要的编辑器已经有超过十年的时间了，可能接下来的十年，它仍然是我的主力编辑器，无论是编写代码还是文档，它都足以胜任，并常有惊喜。我用vim编写markdown博客、robotframework case、Python程序、Go、ReactJS写前端等等等等。

在我看来，它的优点有下面这些：

不同于Vs Code、sublime这类图形化的编辑器，vim/neovim在几乎所有的linux发行版上都有，无论在哪个机器上，只要有vim，获取一份配置文件，马上就拥有一个你熟悉的开发环境，那是非常美妙的事情。
快捷键简单、并且专注于编辑器的事情，扩展性非常好，像neovim，你完全可以把它作为一个编辑器内核，在上面创造出一个完整的IDE出来。
只需要一个配置文件，简单æ¸晰。
拥有类似vim-plug这样的插件管理器，和众多的插件贡献者，像vim-go这类插件质量很高。
但同时，如果你经常需要进行单步调试、观察变量这样的事情，那它就不那么合适了，这个时候还是专门的IDE更方便。对我而言，如果工作的方向偏服务端，且有较为完善的单测覆盖，有较好的日志保证，需要调试的情形是极少，甚至可以忽略的。

如果你有兴趣尝试一下在neovim里工作，欢迎参考我的配置：https://github.com/JiaBaoChenT/nvim/nvim/init.vim

## After Installation, You Need To:

- [ ] Install `pynvim` (pip)
- [ ] Install `nodejs`
- [ ] brew install nerdfont
- [ ] brew cask install font-hack-nerd-font

## Config neovim 
```
cp -r ~/workspace/utils/nvim/config ~/.config
cp -r ~/workspace/utils/nvim/vim ~/.vim
```

## After Installation, You Might Want To:

#### First of all
- [ ] Do `:checkhealth`

#### Config `Python` path
- [ ] Well, make sure you have python
- [ ] See `_machine_specific.vim`

#### For Code AutoComplete (coc)
Python:
- [ ] Do `pip3 install flake8` (for linting)

#### For Taglist:
- [ ] Install `ctags` for function/class/variable list

#### For inputing text ASCII art
- [ ] Install `figlet`

大部分系统的软件源里都已经带了这个软件，由于它是golang编写的，安装非常方便，在mac上通过brew install fzf即可安装。

然后执行$(brew --prefix)/opt/fzf/install将其ä¸zsh集成。

如果想在vim中使用，还需要加入下面几行（假设你使用vim-plug管理插件）：

Plug '/usr/local/opt/fzf'
Plug 'junegunn/fzf.vim'

" ...

command! -bang -nargs=* Rg call fzf#vim#grep("rg --column --line-number --no-heading --color=always --smart-case ".shellescape(<q-args>), 1, {'options': '--delimiter : --nth 4..'}, <bang>0)
nmap <C-p> :Files<CR>
nmap <C-e> :Buffers<CR>
nmap <C-g> :Rg<CR>
利用bat提升preview效果
为了提升使用体验，通常我们会对fzf做一些配置，比如用fd替换find等等。 另外，大家可能对上面视频中的交互式git操作印象深刻，它其实利用了fzf的preview功能和bat工具。

bat是一个rust编写的cat命令的替代品，相比cat，它支持：

根据文件类型进行highlight
显示行号
像less命令一样上下翻页
brew install bat安装bat，然后将下面两行加入到~/.zshrc中。

export FZF_DEFAULT_COMMAND="fd --exclude={.git,.idea,.vscode,pkg,node_modules,vendor,bin,build} -H --type f"
export FZF_DEFAULT_OPTS="--height 40% --layout=reverse --bind up:preview-up,down:preview-down --preview '(bat --style=numbers --color=always {} || cat {}) 2> /dev/null | head -500'"
git集成fzf
当git和拥有preview window的fzf集成在一起的时候，世界一下子变得那么美好，我们可以在交互式的界面查看git提交记录，在preview window查看详细的diff信息，交互式的切换branch等等。

你只需要在~/.oh-my-zsh/custom下面创建一个名为fzf-git.zsh的文件，写上你的配置即可。fzf的wiki上有了一份非常棒的配置，我简单修改了一下，避免了和git的zsh插件的函数重名，以及和tmux的按键冲突，内容如下：
```
# GIT heart FZF
# -------------

is_in_git_repo() {
  git rev-parse HEAD > /dev/null 2>&1
}

fzf-down() {
  fzf --height 50% "$@" --border
}

gf_() {
  is_in_git_repo || return
  git -c color.status=always status --short |
  fzf-down -m --ansi --nth 2..,.. \
    --preview '(git diff --color=always -- {-1} | sed 1,4d; bat --color=always {-1}) | head -500' |
  cut -c4- | sed 's/.* -> //'
}

gv_() {
  is_in_git_repo || return
  git branch -a --color=always | rg -v '/HEAD\s' | sort |
  fzf-down --ansi --multi --tac --preview-window right:70% \
    --preview 'git log --oneline --graph --date=short --color=always --pretty="format:%C(auto)%cd %h%d %s" $(sed s/^..// <<< {} | cut -d" " -f1) | head -'$LINES |
  sed 's/^..//' | cut -d' ' -f1 |
  sed 's#^remotes/##'
}

gt_() {
  is_in_git_repo || return
  git tag --sort -version:refname |
  fzf-down --multi --preview-window right:70% \
    --preview 'git show --color=always {} | head -'$LINES
}

gg_() {
  is_in_git_repo || return
  git log --date=short --format="%C(green)%C(bold)%cd %C(auto)%h%d %s (%an)" --graph --color=always |
  fzf-down --ansi --no-sort --reverse --multi --bind 'ctrl-s:toggle-sort' \
    --header 'Press CTRL-S to toggle sort' \
    --preview 'rg -o "\x1b\[m\x1b\[33m[a-f0-9]{7,}" <<< {} | xargs git show --color=always | head -'$LINES |
  rg -w -o "[a-f0-9]{7,}"
}

gr_() {
  is_in_git_repo || return
  git remote -v | awk '{print $1 "\t" $2}' | uniq |
  fzf-down --tac \
    --preview 'git log --oneline --graph --date=short --pretty="format:%C(auto)%cd %h%d %s" {1} | head -200' |
  cut -d$'\t' -f1
}

join-lines() {
  local item
  while read item; do
    echo -n "${(q)item} "
  done
}

bind-git-helper() {
  local c
  for c in $@; do
    eval "fzf-g$c-widget() { local result=\$(g${c}_ | join-lines); zle reset-prompt; LBUFFER+=\$result }"
    eval "zle -N fzf-g$c-widget"
    eval "bindkey '^g^$c' fzf-g$c-widget"
  done
}
bind-git-helper f v t r g
unset -f bind-git-helper
```

在一个git管理的项目里试一下：Ctrl+g Ctrl+f，Ctrl+g Ctrl+v，Ctrl+g Ctrl+t，Ctrl+g Ctrl+r，Ctrl+g Ctrl+g，看看会出现什么吧。 fzf是支持多选的，在选择窗口试着按下[Tab]看看。

集成ripgrep查找内容
ripgrep是一个grep的替代品，它由rust编写比grep性能更高，使用更方便。

通过brew install ripgrep安装。 最简单的使用只需要在要æ¥找的目录下执行rg searchtext，它会自动在当前目录下进行递归查找，并自动跳过.gitignore里面的内容。

