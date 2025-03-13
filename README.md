# Development Environment Setup React.js (Next.js)

## 1. Install Prerequisits
### Homebrew (if not installed)
Open a terminal and install __Homebrew__ (if you haven't already):
```sh
/bin/bash -c "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/HEAD/install.sh)"
```
Then, update Homebrew:
```bash
brew update
```
__Node.js & npm__

Next.js requires __Node.js__ (LTS version recommended). Install it using Homebrew:
```bash
brew install node
```
Check versions:
```bash
node -v
npm -v
```
Alternatively, you can install __Node Version Manager (nvm)__ for managing multiple Node versions:
```bash
brew install nvm
mkdir ~/.nvm
echo 'export NVM_DIR="$HOME/.nvm"' >> ~/.zshrc
echo '[ -s "/opt/homebrew/opt/nvm/nvm.sh" ] && \. "/opt/homebrew/opt/nvm/nvm.sh"' >> ~/.zshrc
source ~/.zshrc
```
Then, install Node.js:
```bash
nvm install --lts
nvm use --lts
```
<p>&nbsp;</p>

___



## 2. Create New Next.js Project
Create your root project directory where you will create your projects, then change to that directory:
```bash
mkdir -p ~/code/react
cd ~/code/react
```

Then, create a new Next.js app with TypeScript (optional but recommended):
```bash
npx create-next-app@latest penpal
```

You will be asked a series of questions, answer in the following way:
![npx setup output](https://raw.githubusercontent.com/blwilliams/react_setup/refs/heads/main/images/setup_output_npx.png)


Change into the project directory:
```bash

```
