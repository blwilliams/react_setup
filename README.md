# Complete Guide for Setting up your Mac for Development
This guide will walk you through setting up your Mac for Development of React. There are many suggestions for you to start with as your base setup. You can always change how you want your environment to be that works best for you. These are my recommendations.

<p>&nbsp;</p>

## Installing ZSH and Oh-My-ZSH for Terminal (optional):
This guide will walk you through installing **Zsh**, setting it as your default shell, and configuring **Oh My Zsh** on macOS. It makes working in the terminal much nicer.

### Step 0: Install Homebrew (if not installed)
Open a terminal and install __Homebrew__ (if you haven't already):
```sh
/bin/bash -c "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/HEAD/install.sh)"
```
Then, update Homebrew:
```sh
brew update
```

### Step 1: Check if Zsh is Installed

macOS comes with **Zsh** pre-installed. To verify, open the terminal and run:

```sh
zsh --version
```

If you see a version number (e.g., `zsh 5.8` or higher), **Zsh is already installed**.

If it's not installed, proceed to the next step.

---

### Step 2: Install Zsh (If Needed)

If Zsh is not installed or you want to update it, install it using **Homebrew**:

```sh
brew install zsh
```

After installation, check the version again:

```sh
zsh --version
```

---

### Step 3: Set Zsh as the Default Shell

To make **Zsh** the default shell, run:

```sh
chsh -s $(which zsh)
```

Then, restart your terminal or log out and log back in.

To confirm that Zsh is now the default shell, run:

```sh
echo $SHELL
```

If it returns `/bin/zsh` (or `/usr/local/bin/zsh` for Homebrew installations), then it’s set correctly.

---

### Step 4: Install Oh My Zsh

Oh My Zsh is a popular Zsh configuration framework that enhances Zsh with themes and plugins.

Install it using:

```sh
sh -c "$(curl -fsSL https://raw.githubusercontent.com/ohmyzsh/ohmyzsh/master/tools/install.sh)"
```

Alternatively, if you prefer **wget**, use:

```sh
sh -c "$(wget -O- https://raw.githubusercontent.com/ohmyzsh/ohmyzsh/master/tools/install.sh)"
```

---

### Step 5: Choose a Theme (Optional)

Oh My Zsh includes multiple themes. The default theme is `robbyrussell`, but you can change it.

1. Open the Zsh configuration file in a text editor:

   ```sh
   nano ~/.zshrc
   ```

2. Locate the line that starts with:

   ```sh
   ZSH_THEME="robbyrussell"
   ```

3. Change `"robbyrussell"` to another theme, such as `"agnoster"` or `"powerlevel10k"` (after installing it).

4. Save the file (`Ctrl + X`, then `Y`, then `Enter`).

5. Apply the changes:

   ```sh
   source ~/.zshrc
   ```

For a list of themes, visit the [Oh My Zsh themes page](https://github.com/ohmyzsh/ohmyzsh/wiki/Themes).

---

### Step 6: Enable Plugins (Optional)

Oh My Zsh has many useful plugins. To enable them:

1. Open the `~/.zshrc` file:

   ```sh
   nano ~/.zshrc
   ```

2. Find the `plugins` section:

   ```sh
   plugins=(git)
   ```

3. Add other plugins, such as:

   ```sh
   plugins=(git zsh-autosuggestions zsh-syntax-highlighting)
   ```

4. Save and apply the changes:

   ```sh
   source ~/.zshrc
   ```

### Install Recommended Plugins:

- **zsh-autosuggestions** (suggests commands as you type):

  ```sh
  git clone https://github.com/zsh-users/zsh-autosuggestions ${ZSH_CUSTOM:-~/.oh-my-zsh/custom}/plugins/zsh-autosuggestions
  ```

- **zsh-syntax-highlighting** (highlights command syntax):

  ```sh
  git clone https://github.com/zsh-users/zsh-syntax-highlighting.git ${ZSH_CUSTOM:-~/.oh-my-zsh/custom}/plugins/zsh-syntax-highlighting
  ```

Then, add them to the `plugins=(...)` section in `~/.zshrc` and run:

```sh
source ~/.zshrc
```

---

### Step 7: Install Powerlevel10k (Optional, but Recommended)

**Powerlevel10k** is a popular, customizable Zsh theme.

1. Install Powerlevel10k:

   ```sh
   git clone --depth=1 https://github.com/romkatv/powerlevel10k.git ${ZSH_CUSTOM:-~/.oh-my-zsh/custom}/themes/powerlevel10k
   ```

2. Set it as your theme in `~/.zshrc`:

   ```sh
   ZSH_THEME="powerlevel10k/powerlevel10k"
   ```

3. Save the file and restart your terminal:

   ```sh
   source ~/.zshrc
   ```

4. Follow the **Powerlevel10k** configuration wizard to customize your prompt.

---

### Step 8: Restart Your Terminal and Enjoy 🎉

Now that Zsh and Oh My Zsh are installed and configured, restart your terminal and enjoy your new shell!

To verify that everything is working:

```sh
echo $SHELL
```

If it returns `/bin/zsh` or `/usr/local/bin/zsh`, you're all set!

For more customizations, visit the [Oh My Zsh documentation](https://ohmyz.sh/).

# Install Prerequisits
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


