## 🧭 TLP Profile Switcher

A simple GNOME Shell extension for switching [TLP](https://linrunner.de/tlp/) power profiles from the top panel.
Switch between performance, balanced, and battery-saving modes with a single click.


### ✨ Features

* 🔋 One-click switching between TLP profiles
* 🔍 Auto-detects `.conf` profiles from `/etc/tlp.d/`
* ✅ Shows current active profile with a checkmark
* 🔐 Uses `pkexec` to apply profiles with root privileges
* 🧼 Minimal, native GNOME UI


### ⚙️ Prerequisites

* TLP must be installed and active
      → e.g. `sudo pacman -S tlp` or `sudo apt install tlp`
* `pkexec` (from PolicyKit)
* GNOME Shell 45, 46, 47, or 48


### 📦 Installation

#### From GNOME Extensions Website

1. Visit: [extensions.gnome.org](https://extensions.gnome.org)
2. Search: **"TLP Profile Switcher"**
3. Click **Install**

#### Manual Installation

1. Download the extension files
2. Copy to: `~/.local/share/gnome-shell/extensions/tlp-switcher@mahaon.dev/`
3. Restart GNOME Shell: press `Alt+F2`, type `r`, hit Enter
4. Enable the extension via GNOME Extensions app


### 🛠 Usage

#### 📁 Creating Profiles

Profiles are now stored in `/etc/tlp.d/` and should have `.conf` extension.
Each profile should contain a full TLP configuration.

> ✅ Profile name = filename (e.g. `battery.conf` → "battery" mode)

**Steps:**

```sh
sudo mkdir -p /etc/tlp.d/
sudo cp /etc/tlp.conf /etc/tlp.d/performance.conf
sudo nano /etc/tlp.d/performance.conf  # modify settings
```

You can create as many as you like:

```
/etc/tlp.d/
├── battery.conf
├── balanced.conf
└── performance.conf
```


#### 🔄 Switching Profiles

1. Click the icon in the top panel
2. Select a profile from the dropdown
3. Grant permission when prompted
4. The selected profile is copied to `/etc/tlp.conf` and applied


### 🧯 Troubleshooting

#### ⛔ No profiles found

* Make sure `/etc/tlp.d/` exists: `sudo mkdir -p /etc/tlp.d/`
* Add at least one valid `.conf` file to that directory

#### 🔄 Switching fails

* Ensure you have sudo access via `pkexec`
* Check if TLP is running: `sudo systemctl status tlp`
* Verify that selected `.conf` files are syntactically valid

#### 🐚 Extension not visible

* Ensure it's enabled in *GNOME Extensions* app
* Restart GNOME Shell if needed (`Alt+F2`, type `r`, press Enter)


### 🤝 Contributing

Bugs, suggestions, or pull requests are welcome at
👉 [github.com/MAHAON26/tlp-switcher](https://github.com/MAHAON26/tlp-switcher)


### 📜 License

GPL-2.0-or-later
