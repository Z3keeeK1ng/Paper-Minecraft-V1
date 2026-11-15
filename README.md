# PaperMC Server

A high-performance Minecraft server powered by **[PaperMC](https://papermc.io)**, the next-generation Minecraft server compatible with Spigot plugins, offering uncompromising performance and extensive configuration options.

## 📋 Prerequisites

Before setting up the server, ensure you have the following installed:
* **Java 21** (Required for Minecraft 1.20.5 and newer)
* **Git** (For cloning this repository)
* At least **4GB of RAM** recommended for smooth gameplay

## 🚀 Quick Start

1. **Clone the repository:**
   ```bash
   git clone https://github.com
   cd your-repo-name
   ```

2. **Download PaperMC:**
   Download the latest PaperMC `.jar` file from the [official PaperMC downloads page](https://papermc.iodownloads/paper) and place it in the root directory. Rename it to `paper.jar`.

3. **Accept the EULA:**
   Create or edit the `eula.txt` file in the root directory and set:
   ```text
   eula=true
   ```
   *(By changing the setting to `true`, you are indicating your agreement to the [Minecraft EULA](https://aka.ms)).*

4. **Start the Server:**
   Run the server using Aikar's flags for optimal garbage collection and performance:
   ```bash
   java -Xms4G -Xmx4G -XX:+UseG1GC -XX:+ParallelRefProcEnabled -XX:MaxGCPauseMillis=200 -XX:+UnlockExperimentalVMOptions -XX:+DisableExplicitGC -XX:+AlwaysPreTouch -XX:G1NewSizePercent=30 -XX:G1MaxNewSizePercent=40 -XX:G1HeapRegionSize=8M -XX:G1ReservePercent=20 -XX:G1HeapWastePercent=5 -XX:G1MixedGCCountTarget=4 -XX:InitiatingHeapOccupancyPercent=15 -XX:G1MixedGCLiveThresholdPercent=90 -XX:G1RSetUpdatingPauseTimePercent=5 -XX:SurvivorRatio=32 -XX:+PerfDisableSharedMem -XX:MaxTenuringThreshold=1 -Dusing.aikars.flags=https://emc.gs -Daikars.new.flags=true -jar paper.jar --nogui
   ```

## 📁 Directory Structure

```text
├── config/             # Paper global and world-specific configurations
├── plugins/            # Place your Spigot/Paper .jar plugins here
├── world/              # Overworld save data
├── world_nether/       # Nether save data
├── world_the_end/      # End save data
├── bukkit.yml          # Bukkit configuration
├── commands.yml        # Custom command aliases
├── eula.txt            # Minecraft EULA agreement
├── paper.jar           # PaperMC server executable
├── permissions.yml     # Default permissions configuration
├── server.properties   # Core Minecraft server settings
└── spigot.yml          # Spigot configuration
```

## 🔌 Installed Plugins

*(List your server's plugins here so contributors or admins know what is running)*
* **[EssentialsX](https://essentialsx.net)** - Core commands and features
* **[LuckPerms](https://luckperms.net)** - Permissions management
* **[WorldEdit](https://enginehub.org)** - In-game world editing
* **[CoreProtect](https://modrinth.com)** - Block logging and anti-griefing

## ⚙️ Configuration & Optimization

To get the best performance out of PaperMC, consider reviewing the community optimization guide:
* Adjust `view-distance` and `simulation-distance` in `server.properties`.
* Fine-tune entity activation ranges in `spigot.yml`.
* Configure anti-xray and chunk loading settings in `config/paper-world-defaults.yml`.

## 🤝 Contributing

1. Fork the project
2. Create your feature/config branch (`git checkout -b feature/NewPluginConfig`)
3. Commit your changes (`git commit -m 'Add configuration for NewPlugin'`)
4. Push to the branch (`git push origin feature/NewPluginConfig`)
5. Open a Pull Request

## 📄 License

This project configuration is licensed under the MIT License - see the [LICENSE](LICENSE) file for details. PaperMC itself is licensed under the GPLv3 and MIT licenses.
