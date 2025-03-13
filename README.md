# Install Prerequisits
## Homebrew (if not installed)
Open a terminal and install __Homebrew__ (if you haven't already):
```sh
/bin/bash -c "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/HEAD/install.sh)"
```
Then, update Homebrew:
```sh
brew update
```
## Node.js & npm

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

## Installing Visual Studio Code
Follow these steps to install **Visual Studio Code (VS Code)** on your **MacBook**.

### Step 1: Download VS Code

1. Open your web browser and go to the [Visual Studio Code download page](https://code.visualstudio.com/).
2. Click on the **Mac Universal** download option (recommended for Apple Silicon and Intel Macs).
3. Wait for the `.zip` file to download.

### Step 2: Install VS Code

1. Locate the downloaded `.zip` file in your **Downloads** folder.
2. Double-click the `.zip` file to extract the **Visual Studio Code** application.
3. Drag the **Visual Studio Code** app into the **Applications** folder.

### Step 3: Open VS Code

1. Open the **Applications** folder.
2. Double-click **Visual Studio Code** to launch it.
3. If prompted with a security warning, click **Open**.

### Step 4: Add VS Code to PATH (Optional)

To use **VS Code** from the terminal, follow these steps:

1. Open **VS Code**.
2. Press `Cmd + Shift + P` to open the Command Palette.
3. Type `"Shell Command: Install 'code' command in PATH"` and select it.
4. Restart your terminal and type `code` to verify the installation.

### Step 5: Install Extensions (Optional)

- Click on the **Extensions** icon in the sidebar or press `Cmd + Shift + X`.
- Search for useful extensions like:
  - **Python** (for Python development)
  - **ESLint** (for JavaScript linting)
  - **Prettier** (for code formatting)
  - **GitLens** (for enhanced Git integration)

### Step 6: Enable Auto-Updates (Recommended)

VS Code updates automatically, but you can manually check for updates:

1. Click **Code** > **Check for Updates** in the menu bar.
2. Install updates if available.

### Conclusion
For more details, visit the Visual Studio [official documentation](https://code.visualstudio.com/docs).



## Create New Next.js Project
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


