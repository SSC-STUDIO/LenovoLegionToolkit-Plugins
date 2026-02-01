# Lenovo Legion Toolkit Plugins

Official plugin repository for Lenovo Legion Toolkit.

## For Users

Download plugins from the [Releases](https://github.com/Crs10259/LenovoLegionToolkit-Plugins/releases) page or install via the Plugin Manager in Lenovo Legion Toolkit.

## For Developers

### Prerequisites

- .NET 8.0 SDK
- Visual Studio 2022 or VS Code

### Building Plugins

1. Clone this repository:
   ```bash
   git clone https://github.com/Crs10259/LenovoLegionToolkit-Plugins.git
   cd LenovoLegionToolkit-Plugins
   ```

2. Build all plugins:
   ```bash
   dotnet build
   ```

3. Build a specific plugin:
   ```bash
   dotnet build ./ViveTool/LenovoLegionToolkit.Plugins.ViveTool.csproj
   ```

4. Create a ZIP package for release:
   ```powershell
   # Windows PowerShell
   Compress-Archive -Path ./ViveTool -DestinationPath ./ViveTool.zip -Force
   ```

### Plugin Structure

```
LenovoLegionToolkit-Plugins/
├── SDK/                          # Plugin SDK (development dependency)
│   └── LenovoLegionToolkit.Plugins.SDK.csproj
├── ViveTool/                     # Example plugin
│   └── LenovoLegionToolkit.Plugins.ViveTool.csproj
├── CustomMouse/
├── NetworkAcceleration/
├── ShellIntegration/
└── store.json                    # Plugin store metadata
```

### Creating a New Plugin

1. Create a new class library project:
   ```bash
   dotnet new classlib -n LenovoLegionToolkit.Plugins.MyPlugin -o ./MyPlugin
   ```

2. Add reference to the SDK:
   ```bash
   dotnet add ./MyPlugin/LenovoLegionToolkit.Plugins.MyPlugin.csproj reference ./SDK/LenovoLegionToolkit.Plugins.SDK.csproj
   ```

3. Implement the `IPlugin` interface from `LenovoLegionToolkit.Lib.Plugins`

4. Build and package your plugin as a ZIP file

## Store URL

Lenovo Legion Toolkit fetches plugins from:
```
https://raw.githubusercontent.com/Crs10259/LenovoLegionToolkit-Plugins/master/store.json
```

## License

MIT License
