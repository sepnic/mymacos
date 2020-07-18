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

## 安装和配置 iTerm2

1. 解压 tools/terminal/iTerm2-3_3_12.zip 并安装

2. 安装字体：'tools/terminal/Meslo LG M Regular for Powerline.ttf'

3. 打开 iTerm2

4. 在 `Preferences -> Profiles -> Text -> Font` 选择 `Meslo LG M Regular for Powerline` 字体，字体大小调整到 14px

5. 在 `Preferences -> Profiles -> Colors -> Color Presets` 选择 `Tango Dark` 主题

6. 在 `Preferences -> Profiles -> General -> Working Directory` 选择 `Reuse previous session's directory`，这样打开新窗口会继承上一个回话的位置

