# mpvyt

## About

**mpvyt** is a personal script designed to play videos from YouTube and other sites supported by `yt-dlp` in various formats.

## How to Use

### Prerequisites

Before using `mpvyt`, ensure you have the following installed:

- **yt-dlp** (to fetch available formats)
  - For example, on openSUSE, you can install it using:
    ```bash
    sudo zypper install yt-dlp
    ```

- **mpv Player**
  - You can install it via Flatpak:
    ```bash
    flatpak install flathub io.mpv.Mpv
    ```
  - If you have non-free media codecs, you can also install it using your distribution’s package manager.

### Download & Setup the Script

1. **Clone the repository**:
   ```bash
   git clone "https://github.com/rycane/mpvyt"
   ```
2. **Modify the Script for Flatpak (if applicable):**
   - If you are using Flatpak for mpv, you need to uncomment the Flatpak commands in the mpvyt script and comment out the mpv commands.
   Example:
   ```bash
    if [[ "$audio\_only" == "y" ]]; then
        # mpv "$yt\_link" --ytdl-format="bestaudio" --term-osd-bar
        flatpak run io.mpv.Mpv "$yt\_link" --ytdl-format="bestaudio" --term-osd-bar
    else
        # mpv "$yt\_link" --ytdl-format="$format" --hwdec=auto --term-osd-bar
        flatpak run io.mpv.Mpv "$yt\_link" --ytdl-format="$format" --hwdec=auto --term-osd-bar
    fi
    ```
3. **Grant Execute Permission:**
   - Navigate to the script folder and run:
    ```bash
    chmod +x mpvyt
    ```
4. **Add mpvyt to Local /bin:***
  - You can either move the mpvyt file to the .local/bin folder graphically or via the command line:
    ```bash
    mv mpvyt ~/.local/bin
    ```
## Usage

To use the script, simply run:

    ```bash
    mpvyt <YouTube or stream link here>    ```


