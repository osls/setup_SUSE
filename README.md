# setup_SUSE

0. Apps

```sudo zypper in emacs gvim fish golang catfish zsh fish gnuplot openssl openssh-client pandoc wine xchm wget gdb git meld curl aspell fortune geany rustc cargo tmux awesome at gcc-c++```

1. Python
- 从 `https://mirrors.tuna.tsinghua.edu.cn/anaconda/pkgs/main/linux-64/` 下载最新版 `Anaconda` 安装到 `~/anaconda3`
- 添加 `Anaconda Python` 免费仓库的 `TUNA`镜像
```
conda config --add channels https://mirrors.tuna.tsinghua.edu.cn/anaconda/pkgs/free/
conda config --add channels https://mirrors.tuna.tsinghua.edu.cn/anaconda/pkgs/main/
conda config --set show_channel_urls yes
```
- installation
```
~/anaconda3/bin/pip install --upgrade pip

~/anaconda3/bin/pip install msgpack
~/anaconda3/bin/conda install py-xgboost  # conda install -c anaconda py-xgboost
~/anaconda3/bin/conda install lightgbm
~/anaconda3/bin/conda install catboost
~/anaconda3/bin/conda install -c conda-forge fbprophet
~/anaconda3/bin/conda install tensorflow  # conda install -c conda-forge tensorflow 
~/anaconda3/bin/pip install python-xlib   # import Xlib
~/anaconda3/bin/pip install pyautogui
~/anaconda3/bin/pip install EMD-signal
~/anaconda3/bin/pip install pypinyin
~/anaconda3/bin/pip install pytdx

git clone https://github.com/BjmWang/GBDT-PL
cd GBDT-PL/python
~/anaconda3/bin/pip install --user .
```
- startup script
```
mkdir -p ~/.ipython/profile_default/startup
cd ~/.ipython/profile_default/startup
wget https://raw.githubusercontent.com/osls/ipy-rc/master/99_python3_startup.py
cd -
```

- TA-Lib
```
wget https://sourceforge.net/projects/ta-lib/files/ta-lib/0.4.0/ta-lib-0.4.0-src.tar.gz
# Ref: https://github.com/mrjbq7/ta-lib
tar -xzvf ta-lib-0.4.0-src.tar.gz
./configure --prefix=/usr
make
sudo make install

~/anaconda3/bin/pip install TA-Lib
# sudo find / -name libta_lib.so.0
##~/Downloads/ta-lib/src/.libs/libta_lib.so.0
##/usr/lib/libta_lib.so.0

sudo su
echo 'export LD_LIBRARY_PATH=$LD_LIBRARY_PATH:/usr/lib' >> /etc/profile
# tail  /etc/profile

# sudo reboot
```

2. 中文环境 
- `sudo zypper in fcitx kde-l10n-zh_CN  wqy-microhei-fonts wqy-zenhei-fonts`
- 运行 `fcitx configuration` 增加中文输入法
- 英文字体使用 `Hack`

3. 常用软件设置
```
sudo chsh -s /usr/bin/fish mw

cd ~; wget https://raw.githubusercontent.com/osls/code-layout/master/xmodmap/ansi_code.xmodmap -O .Xmodmap

git config --global push.default simple
git config --global user.name BjmWang
git config --global user.email Benjamin.mj.wang@gmail.com

mkdir -p ~/.config/fish/; cd ~/.config/fish/; wget https://raw.githubusercontent.com/osls/shell-rc/master/config.fish; cd -

mkdir -p ~/.emacs.d; cd ~/.emacs.d
wget https://raw.githubusercontent.com/osls/emacs-rc/master/init.el
emacs -nw --batch -l ~/.emacs.d/init.el -f package-refresh-contents
mv ~/.emacs ~/.emacs.d/
cd -

mkdir -p ~/.vim
cd ~/.vim
wget https://raw.githubusercontent.com/osls/vim-rc/master/vimrc
curl -fLo ~/.vim/autoload/plug.vim --create-dirs "https://raw.githubusercontent.com/junegunn/vim-plug/master/plug.vim"
mkdir -p ~/.vim/backup
mkdir -p ~/.vim/tmp
cd -

mkdir -p ~/workshop

#git clone https://github.com/BjmWang/gftd ~/workshop/gftd
```

4. 解码器
```
https://opensuse-guide.ustclug.org/codecs.php
http://opensuse-community.org/
```
One-Click-Installation
