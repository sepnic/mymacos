## 安装 brew

- 官网安装：

```
/bin/bash -c "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/master/install.sh)"
```

- 镜像安装：由于国内被墙的原因，很多时候官网安装很慢或者安装不了，可通过国内镜像安装

```
./tools/brew_install.sh  ## 修改 BREW_REPO 为 https://mirrors.ustc.edu.cn/brew.git，已修改好，直接执行安装即可，也可替换其他镜像地址
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

## 安装和配置 oh-my-zsh

```
cp -a tools/terminal/ohmyzsh ~/.oh-my-zsh
tools/terminal/ohmyzsh/tools/install.sh
cp tools/terminal/zshrc ~/.zshrc
```

默认安装已配置主题为 `agnoster`，已使能语法高亮和隐藏用户名主机名。注意：使用 `agnoster` 主题，必须在终端内配置字体为 `Meslo LG M Regular for Powerline.ttf`，否则会显示乱码

## 安装 AndroidStudio

1. 安装 openjdk 8：https://adoptopenjdk.net/ 默认安装在 `/Library/Java/JavaVirtualMachines/adoptopenjdk-8.jdk`
2. 安装 Android Studio 和 NDK
3. 环境变量设置，JAVA/AndroidSDK/NDK 的路径根据实际情况来设置，建议写到 `~/.zshrc`，参考如下：

```
export JAVA_HOME=/Library/Java/JavaVirtualMachines/adoptopenjdk-8.jdk/Contents/Home
export ANDROID_HOME=${HOME}/Documents/Tools/Android/sdk
export ANDROID_NDK=${HOME}/Documents/Tools/Android/sdk/ndk/android-ndk-r19c
export CMAKE=/Applications/CMake.app/Contents/bin
export CLASSPATH=${JAVA_HOME}/bin
export ANDROID_SDK=${ANDROID_HOME}
export ANDROID_SDK_ROOT=${ANDROID_HOME}
export ANDROID_NDK_VERSION=19
export ANDROID_NDK_ROOT=${ANDROID_NDK}
export ANDROID_NDK_TOOLS=${ANDROID_NDK}/toolchains/arm-linux-androideabi-4.9/prebuilt/darwin-x86_64/bin
export PATH=$PATH:$JAVA_HOME:$ANDROID_HOME:$ANDROID_HOME/platform-tools:$ANDROID_HOME/tools/:$ANDROID_NDK:$ANDROID_NDK_TOOLS
export PATH=$PATH:/usr/local/bin:${HOME}/bin:$CMAKE
```

## 安装其他

1. 安装 cmake 工具： 'tools/cmake-3.17.3-Darwin-x86_64.dmg'
2. 安装 SublimeText 代码编辑器：'tools/Sublime Text Build 3211.dmg'
3. 安装 Xcode
