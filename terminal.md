to install oh-my-zsh

sh -c "$(curl -fsSL https://raw.github.com/ohmyzsh/ohmyzsh/master/tools/inst

Then source it

source ~/.zshrc

Then, install and configure PowerLevel10k

cd ~
mkdir .powerlevel10k
git clone --depth=1 https://github.com/romkatv/powerlevel10k.git ~/.powerlevel10k
echo "source ~/.powerlevel10k/powerlevel10k.zsh-theme" >>! ~/.zshrc

From here: https://github.com/romkatv/powerlevel10k install Meslo LGS Regular font.

After the installation of the above font is complete, set it as your default terminal font by going to
Terminal => Preferences… => Profile => Under Text tap, click on Change button at the font section and set to Meslo Regular with your preferred font size.

relaunching your mac terminal


on ~/.zshrc file add the followings

# plugins
plugins=(
  git
  zsh-autosuggestions
  zsh-syntax-highlighting
)

source $ZSH/oh-my-zsh.sh

# default editor
export EDITOR='code'

# ssh key path
export SSH_KEY_PATH="~/.ssh/rsa_id"


Link: https://v-char.medium.com/now-let-customize-your-native-macos-terminal-with-oh-my-zsh-and-powerlevel10k-b48b9c30d39f

After completeing this run the following command

open ~/.zshrc

then search for text "source $ZSH/oh-my-zsh.sh", usually on the Line number 82, comment out this line.
