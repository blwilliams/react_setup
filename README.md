# Development Environment Setup React.js (Next.js)

## 1. Install Prerequisits
#### Homebrew (if not installed)
Open a terminal and install __Homebrew__ (if you haven't already):
```sh
/bin/bash -c "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/HEAD/install.sh)"
```
Then, update Homebrew:
```sh
brew update
```
#### Node.js & npm

Next.js requires __Node.js__ (LTS version recommended). Install it using Homebrew:
```sh
brew install node
```
Check versions:
```sh
node -v
npm -v
```
Alternatively, you can install __Node Version Manager (nvm)__ for managing multiple Node versions:
```sh
brew install nvm
mkdir ~/.nvm
echo 'export NVM_DIR="$HOME/.nvm"' >> ~/.zshrc
echo '[ -s "/opt/homebrew/opt/nvm/nvm.sh" ] && \. "/opt/homebrew/opt/nvm/nvm.sh"' >> ~/.zshrc
source ~/.zshrc
```
Then, install Node.js:
```sh
nvm install --lts
nvm use --lts
```
<p>&nbsp;</p>


## 2. Create New Next.js Project
Create your root project directory where you will create your projects, then change to that directory:
```sh
mkdir -p ~/code/react
cd ~/code/react
```

Then, create a new Next.js app with TypeScript (optional but recommended):
```sh
npx create-next-app@latest penpal
```

You will be asked a series of questions, answer in the following way:
![npx setup output](https://raw.githubusercontent.com/blwilliams/react_setup/refs/heads/main/images/setup_output_npx.png)


Change into the project directory:
```sh
cd penpal
```


## 3. Install Dependencies
#### Intsall TailswindCSS
```sh
npm install -D tailwindcss postcss autoprefixer
npx tailwindcss init -p
```
Modify `tailwind.config.js`:
```javascript
/** @type {import('tailwindcss').Config} */
module.exports = {
  content: [
    "./pages/**/*.{js,ts,jsx,tsx}",
    "./components/**/*.{js,ts,jsx,tsx}",
    "./app/**/*.{js,ts,jsx,tsx}", // If using Next.js App Router
  ],
  theme: {
    extend: {},
  },
  plugins: [],
};
```

Update `styles/globals.css`:
```css
@tailwind base;
@tailwind components;
@tailwind utilities;
```

####Install Axios
```sh
npm install axios
```


