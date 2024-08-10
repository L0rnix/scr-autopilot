So, hi i tried to make it work and i got it but i need a few help with all coordinate. I made some of them but yeah need help. BTW it works better if you use big siwe GUI in scr settings. I removed some code from the origanal main.py script cuz it makes everything worse so i removed it 

# SCR-Autopilot
Hello,
MaTY-MT/SCR-Autopilot is archived, and I have a couple reasons why:
- I haven't been enjoying the development, the last commit was like last year
- The development of this has been pretty difficult and tedious
- I don't really enjoy playing SCR anymore

This is sadly bad news for some people, but also good news for some.
If you really want to still have the autopilot functionality in SCR, different projects have now appeared, so maybe give them a try! :) 



Here is a step-by-step guide on how to install Tesseract and add the `TESSDATA_PREFIX` environment variable.

# Installing Tesseract

## 1. Install Tesseract on Windows

1. **Download the Tesseract installer**:
   - Go to the [Tesseract GitHub releases page](https://github.com/tesseract-ocr/tesseract/releases).
   - Download the latest stable version of the Windows installer (`.exe` file).

2. **Run the installer**:
   - Double-click the downloaded `.exe` file.
   - Follow the prompts to complete the installation.
   - Make sure to note the installation directory (e.g., `C:\Program Files\Tesseract-OCR`).

3. **Verify the installation**:
   - Open the Command Prompt.
   - Type `tesseract -v` and press Enter. You should see the version information, confirming that Tesseract is installed correctly.

## 2. Install Tesseract on Linux

1. **Update your package list**:
   ```bash
   sudo apt update
   ```

2. **Install Tesseract**:
   ```bash
   sudo apt install tesseract-ocr
   ```

3. **Verify the installation**:
   ```bash
   tesseract -v
   ```

## 3. Install Tesseract on macOS

1. **Install Homebrew** (if you don't have it already):
   ```bash
   /bin/bash -c "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/HEAD/install.sh)"
   ```

2. **Install Tesseract using Homebrew**:
   ```bash
   brew install tesseract
   ```

3. **Verify the installation**:
   ```bash
   tesseract -v
   ```

# Adding the `TESSDATA_PREFIX` Environment Variable

Tesseract needs to know where to find its language data files (`.traineddata` files). This can be done by setting the `TESSDATA_PREFIX` environment variable.

## 1. On Windows

1. **Open the Environment Variables window**:
   - Right-click on `This PC` or `My Computer` and select `Properties`.
   - Click on `Advanced system settings`.
   - In the System Properties window, click on `Environment Variables`.

2. **Add the `TESSDATA_PREFIX` variable**:
   - In the Environment Variables window, click on `New` under the `System variables` or `User variables` section.
   - Enter `TESSDATA_PREFIX` as the variable name.
   - Set the variable value to the directory where the `tessdata` folder is located. For example, if the `tessdata` folder is in `C:\Program Files\Tesseract-OCR\tessdata`, set the value to `C:\Program Files\Tesseract-OCR\`.

3. **Apply and close**:
   - Click `OK` to close all windows.
   - Restart your computer to ensure the changes take effect.

## 2. On Linux and macOS

1. **Open your shell configuration file**:
   - If you're using `bash`, open `~/.bashrc` or `~/.bash_profile`.
   - If you're using `zsh`, open `~/.zshrc`.

2. **Add the `TESSDATA_PREFIX` variable**:
   ```bash
   export TESSDATA_PREFIX=/usr/share/tesseract-ocr/4.00/tessdata/
   ```

   - Modify the path according to where your `tessdata` folder is located.

3. **Save and close the file**.

4. **Apply the changes**:
   ```bash
   source ~/.bashrc   # for bash users
   source ~/.zshrc    # for zsh users
   ```

# Verification

To verify that the `TESSDATA_PREFIX` variable is set correctly, you can print it in the terminal:

```bash
echo $TESSDATA_PREFIX
```

On Windows, you can verify by opening Command Prompt and typing:

```cmd
echo %TESSDATA_PREFIX%
```

If the path to your `tessdata` folder is printed correctly, everything is set up properly!
