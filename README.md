# setup_openSUSE

1. Python
- 从 `https://mirrors.tuna.tsinghua.edu.cn/anaconda/pkgs/main/linux-64/` 下载最新版 `Anaconda` 安装
- 添加 `TUNA` 的 `Anaconda Python` 免费仓库镜像
```
conda config --add channels https://mirrors.tuna.tsinghua.edu.cn/anaconda/pkgs/free/
conda config --add channels https://mirrors.tuna.tsinghua.edu.cn/anaconda/pkgs/main/
conda config --set show_channel_urls yes
```
- `conda install py-xgboost`

2. 中文环境 
- `sudo zypper in fcitx kde-l10n-zh_CN  wqy-microhei-fonts wqy-zenhei-fonts`
- 运行 `fcitx configuration` 增加中文输入法
