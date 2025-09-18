## 安装
安装 `zsh`。
```sh
apt install zsh
```
## 美化
安装 `oh my zsh`。
```sh
cd
wget https://github.com/robbyrussell/oh-my-zsh/raw/master/tools/install.sh
sh install.sh
rm install.sh
```
安装选项全选 YES。
安装 `zeta` 主题。
```sh
cd
wget https://raw.githubusercontent.com/skylerlee/zeta-zsh-theme/master/scripts/install.sh
bash install.sh
rm install.sh
```
安装 `zsh-autosuggestions`。
```sh
git clone https://github.com/zsh-users/zsh-autosuggestions ${ZSH_CUSTOM:-~/.oh-my-zsh/custom}/plugins/zsh-autosuggestions
```
配置 `~/.zshrc`。
```json
ZSH_THEME="zeta"
plugins=( 
       # other plugins...
       zsh-autosuggestions
)
```

   