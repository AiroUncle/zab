# SSH Log Viewer v3.0

A modern, feature-rich Python GUI application for viewing log files on remote servers via SSH connection with enhanced tabbed interface, site management, and advanced file handling capabilities.

## 🎯 Key Features

### Enhanced Tab Management
- **BareTail-Style Interface**: Single "✖ Close Active Tab" button instead of individual tab close buttons
- **Compact Tab Design**: Tabs are designed to be space-efficient with minimal padding and small fonts
- **Clear Active/Inactive States**: Active tabs have blue background with white text, inactive tabs have gray background with black text
- **Persistent Tab Labels**: Tab labels are always visible and never truncated
- **Rolling Log Indicators**: Visual indicators show when logs are actively rolling:
  - 🔄 = Follow tail enabled
  - ● = Actively rolling (new content being added)
- **Tab Navigation**: When window width is reduced, navigation arrows (◀ ▶) appear to scroll through hidden tabs
- **Global Close Option**: "Close All Tabs" option available in the View menu

### Advanced File Handling
- **Full File Loading**: Load complete log files regardless of size
- **Large File Warnings**: Smart warnings for files >100MB with download recommendations
- **Download Functionality**: Download files locally for better performance
- **Memory Monitoring**: Real-time memory usage tracking
- **Local File Support**: Open and monitor local log files (like BareTail)

### Enhanced File Browser
- **Human-Readable File Sizes**: Display sizes in B, KB, MB, GB format
- **File Permissions Display**: Show Unix file permissions in readable format
- **Advanced Sorting**: Sort by name, type, size, permissions, and modification date
- **Enhanced File Type Detection**: Automatic identification of log files

### Real-time Monitoring
- **Follow Tail Mode**: Real-time log monitoring similar to `tail -f`
- **Auto-scroll**: Automatic scrolling to latest entries
- **Connection Status**: Visual indicators for each tab's connection state
- **Improved Search**: Debounced search functionality that prevents application freezing on large files

### Site Management (FileZilla-style)
- **Save SSH Connections**: Store connection details with custom site names
- **Logon Type Options**: Choose between "Normal" (save password) and "Ask for password" authentication
- **Default Log Paths**: Predefined log file paths for each site
- **Quick Connect**: One-time connections without saving
- **Site Organization**: Hierarchical site management

## 🚀 Getting Started

### Prerequisites
- Python 3.7 or higher
- tkinter (usually included with Python)
- paramiko (`pip install paramiko`)
- psutil (optional, for memory monitoring: `pip install psutil`)

### Installation
1. Clone or download the project files
2. Install dependencies:
   ```bash
   pip install -r requirements.txt
   ```
3. Run the application:
   ```bash
   python ssh_log_viewer_v3.py
   ```

## 📁 Project Structure

```
PLV-main/
├── ssh_log_viewer_v3.py      # Main application file
├── site_manager.py           # Site management module
├── log_tab.py               # Enhanced log tab module
├── local_log_tab.py         # Local file log tab module
├── file_browser.py          # File browser with sorting
├── utils.py                 # Utility functions
├── requirements.txt         # Python dependencies
├── sites.json              # Saved site configurations
└── README_v3.md            # This file
```

## 🎨 Interface Layout

### Left Panel (Site Management)
- **Quick Connect**: For one-time connections
- **Saved Sites**: List of configured sites with double-click to connect
- **Site Management**: Access to site manager dialog

### Right Panel (Log Viewer)
- **Tabbed Interface**: Multiple log files from different servers
- **Enhanced Tab Styling**: Clear active/inactive distinction
- **Persistent Close Buttons**: Always visible close buttons
- **Status Indicators**: Connection and follow tail status

## 🔧 Usage Guide

### 1. Site Manager
- Click **File → Site Manager** to open the site management dialog
- Add new sites with connection details and default log paths
- Save frequently used servers for quick access

### 2. Quick Connect
- Use the left panel for one-time connections
- Enter host, username, and password
- Click "Quick Connect" to browse available log files

### 3. Opening Log Files
- Double-click saved sites or use Quick Connect
- Select one or more log files from the enhanced file browser
- Each selected file opens in a new tab with persistent close button

### 4. Enhanced Log Viewing
- **Connect**: Establish SSH connection for the tab (SSH tabs only)
- **Refresh**: Load complete file content
- **Follow Tail**: Enable real-time monitoring (similar to `tail -f`)
- **Download**: Download large files locally for better performance (SSH tabs only)
- **Search**: Find and highlight text in the current tab

### 5. Local File Support
- **Open Local File**: File → Open Local File to select local log files
- **Local File Monitoring**: Follow tail works with local files
- **File Refresh**: Refresh local file content
- **Large File Warnings**: Same warnings apply to local files

### 6. Advanced Tab Management
- **Close Current Tab**: View → Close Current Tab
- **Close All Tabs**: View → Close All Tabs
- **Right-click Context Menu**: Additional tab operations
- **Tab Status Indicators**: Visual feedback for connection and follow tail status

## 🎯 Enhanced Features

### Tab Visibility Improvements
- **Active Tab**: Blue background with white text
- **Inactive Tab**: Gray background with black text
- **Close Button**: Always visible ✖ symbol
- **Status Indicators**: 🔄 for follow tail mode

### File Size Display
- **Human-Readable**: 1.5 KB, 2.3 MB, 1.1 GB
- **Automatic Conversion**: Seamless byte to human-readable conversion
- **Sorting Support**: Proper sorting by actual file size

### File Permissions
- **Readable Format**: rw-r--r-- instead of -rw-r--r--
- **Visual Indicators**: Icons for directories (📁), files (📄), symlinks (🔗)
- **Permission Sorting**: Logical sorting by permission type

### Large File Handling
- **Smart Warnings**: Automatic detection of large files (>100MB)
- **Download Option**: Suggest downloading for better performance
- **Memory Monitoring**: Track memory usage during file operations
- **Progress Indication**: Show download progress for large files

### Enhanced Sorting
- **Multi-column Sorting**: Sort by name, type, size, permissions, date
- **Sort Indicators**: Visual arrows showing sort direction
- **Smart Sorting**: Handle different data types appropriately
- **Persistent Sort**: Maintain sort order during navigation

## 🆕 New Features in v3.0

### Tab Navigation for Reduced Window Width
- **Automatic Detection**: Navigation buttons appear when tabs don't fit in window width
- **Left/Right Navigation**: Use ◀ ▶ buttons to navigate between tabs
- **Smart Visibility**: Buttons only show when needed
- **BareTail-Inspired**: Similar to BareTail's tab navigation system

### Logon Type Options in Site Manager
- **Normal Mode**: Save password with site configuration (default)
- **Ask for Password**: Prompt for password each time you connect
- **Security Flexibility**: Choose authentication method based on security requirements
- **FileZilla-Inspired**: Similar to FileZilla's logon type options

## 🔧 Configuration

### Site Configuration
- **Site Name**: Custom name for easy identification
- **Host**: Server hostname or IP address
- **Port**: SSH port (default: 22)
- **Username/Password**: Authentication credentials
- **Default Log Paths**: Predefined log files for quick access

### File Storage
- Site configurations saved in `sites.json`
- Automatic backup and recovery
- Portable configuration file

## 🛠️ Troubleshooting

### Connection Issues
- Verify SSH credentials and network connectivity
- Check firewall settings and SSH service status
- Ensure SSH key authentication is not required

### Performance Issues
- Use download feature for large files (>100MB)
- Close unused tabs to free resources
- Use Follow Tail for real-time monitoring instead of frequent refreshes

### Memory Issues
- Monitor memory usage with psutil (optional dependency)
- Download large files locally for better performance
- Close unused tabs to free memory

## 🔮 Future Enhancements

- SSH key authentication support
- Syntax highlighting for different log formats
- Log filtering and parsing
- Export functionality
- Bookmark specific log positions
- Multi-server log aggregation
- Dark mode theme
- Plugin system for custom log parsers

## 📝 Changelog

### v3.0 (Latest)
- **Modular Architecture**: Complete refactoring into separate modules for better maintainability
- **Enhanced Tab Visibility**: Improved tab styling with clear active/inactive states
- **Persistent Close Buttons**: Close buttons always visible regardless of window width
- **Full File Loading**: Complete log file loading with large file warnings and download options
- **Improved File Sorting**: Fixed file browser sorting functionality
- **Human-Readable File Sizes**: File sizes displayed in B, KB, MB, GB format
- **File Permissions Display**: Unix-style file permissions shown in file browser
- **Local file support (like BareTail)**: Open and monitor local log files
- **Tab navigation with left/right triangle buttons for reduced window width**
- **Logon Type options (Normal/Ask for password) in Site Manager**
- **Compact Tab Design**: Reduced padding and smaller fonts for better space utilization
- **Rolling Log Indicators**: Visual indicators (🔄●) for actively rolling logs
- **Global Close Button**: "✖ Close All" button to close all tabs at once
- **Tab Text Preservation**: Original labels preserved with indicators and close buttons

### v2.0
- Site Manager functionality
- Tabbed interface
- Real-time log monitoring
- Search functionality

## 🤝 Contributing

This project is designed to be a modern alternative to BareTail with SSH capabilities, inspired by FileZilla's site management approach. Contributions are welcome!

## 📄 License

This project is open source and available under the MIT License.

## 🙏 Acknowledgments

- Inspired by FileZilla's site management approach
- Designed as a modern alternative to BareTail with SSH capabilities
- Built with Python, Tkinter, and Paramiko 