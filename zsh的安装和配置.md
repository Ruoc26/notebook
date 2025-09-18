# zsh 的安装和配置

1. 安装 zsh。

   ```sh
   apt install zsh
   ```

2. 安装 oh my zsh。

   ```sh
   cd
   wget https://github.com/robbyrussell/oh-my-zsh/raw/master/tools/install.sh
   sh install.sh
   rm install.sh
   ```

   选项全 YES。

3. 安装 zeta 主题。

   ```sh
   cd
   wget https://raw.githubusercontent.com/skylerlee/zeta-zsh-theme/master/scripts/install.sh
   bash install.sh
   rm install.sh
   ```

4. 安装 zsh-autosuggestions。

   ```sh
   git clone https://github.com/zsh-users/zsh-autosuggestions ${ZSH_CUSTOM:-~/.oh-my-zsh/custom}/plugins/zsh-autosuggestions
   ```

5. 配置 `~/.zshrc`。

   ```json
   ZSH_THEME="zeta"
   
   plugins=( 
       # other plugins...
       zsh-autosuggestions
   )
   ```

   