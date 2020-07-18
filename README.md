## 安装 brew

- 官网安装：

```
/bin/bash -c "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/master/install.sh)"
```

- 镜像安装：由于国内被墙的原因，很多时候官网安装很慢或者安装不了，可通过国内镜像安装

```
./tools/brew_install.sh  ## 修改 BREW_REPO 为 https://mirrors.ustc.edu.cn/brew.git
git clone git://mirrors.ustc.edu.cn/homebrew-core.git/ /usr/local/Homebrew/Library/Taps/homebrew/homebrew-core --depth=1

export PATH=$PATH:/usr/local/bin ## brew 命令放在 /usr/local/bin 目录，需要添加该环境变量

cd $(brew --repo)
git remote set-url origin https://mirrors.ustc.edu.cn/brew.git
cd "$(brew --repo)/Library/Taps/homebrew/homebrew-core"
git remote set-url origin https://mirrors.ustc.edu.cn/homebrew-core.git

brew upate
```
