# Claude JSONL Log Viewer

A web-based viewer for Claude Code conversation logs with real-time monitoring and cross-platform support.

![Claude Log Viewer Interface](https://img.shields.io/badge/Platform-Web-blue) ![License](https://img.shields.io/badge/License-MIT-green) ![Browser Support](https://img.shields.io/badge/Browser-Chrome%20%7C%20Edge%20%7C%20Firefox%20%7C%20Safari-orange)

## Features

### 📊 **Rich Log Display**
- **Session Grouping**: Organizes logs by session with metadata display
- **Conversation Threading**: Shows parent-child relationships between messages
- **Token Usage**: Displays input/output tokens, cache statistics, and model information
- **Tool Interactions**: Enhanced display for tool usage and results with visual indicators
- **Message Types**: Supports text, tool_use, and tool_result content with proper formatting
- **Sorted Log Files**: Automatically sorts log files by modification date for easy access

### 🔄 **Real-Time Monitoring**
- **File Watching**: Automatically detects changes to JSONL files
- **Live Updates**: Refreshes content when new log entries are added
- **Auto-Scroll**: Option to automatically scroll to latest messages
- **Status Indicators**: Visual feedback for monitoring state

### 🌐 **Cross-Platform Support**
- **Windows**: `%USERPROFILE%\.claude\projects\`
- **macOS**: `$HOME/.claude/projects/`
- **Linux**: `$HOME/.claude/projects/`
- **Browser Compatibility**: Works with File System Access API (Chrome/Edge) and file picker fallback

### 🎨 **Modern Interface**
- **Responsive Design**: Works on desktop and mobile devices
- **Clean UI**: Modern styling with Tailwind CSS
- **Dark/Light Themes**: Readable color schemes for different content types
- **Smooth Animations**: Polished user experience with transitions

## Getting Started

### Prerequisites
- Modern web browser (Chrome, Edge, Firefox, or Safari)
- Access to Claude Code log files

### Installation
1. Clone or download this repository
2. Open `clog.html` in your web browser
3. No additional setup required!

### Usage

#### Method 1: Project Browser (Recommended)
1. Click "🗂️ Browse for Projects Folder" in the Claude Projects Browser
2. Navigate to your Claude projects directory:
   - **Windows**: `C:\Users\[username]\.claude\projects\`
   - **macOS**: `/Users/[username]/.claude/projects/`
   - **Linux**: `/home/[username]/.claude/projects/`
3. Select a project folder containing JSONL files
4. Choose a log file from the dropdown
5. Click "Load Log File"

#### Method 2: Manual File Selection
1. Click "Choose File" in the header
2. Browse to your JSONL log file manually
3. Select the file to load

#### Real-Time Monitoring
1. Load a file using the Project Browser method
2. Check "Monitor file for changes" to enable real-time updates
3. Check "Auto-scroll to latest" to automatically scroll to new messages
4. Watch live as new log entries appear

## File Structure

```
claude-logs/
├── clog.html              # Main application file
├── README.md              # This file
└── docs/
    └── claude-log-path.md  # Platform-specific path documentation
```

## Supported Log Format

The viewer supports JSONL files with the following structure:

```json
{
  "parentUuid": "string",
  "sessionId": "string", 
  "version": "string",
  "gitBranch": "string",
  "cwd": "string",
  "message": {
    "role": "user|assistant",
    "content": [
      {
        "type": "text|tool_use|tool_result",
        "text": "string",
        "name": "string",
        "input": {},
        "tool_use_id": "string"
      }
    ],
    "usage": {
      "input_tokens": 0,
      "output_tokens": 0,
      "cache_creation_input_tokens": 0,
      "cache_read_input_tokens": 0
    }
  },
  "uuid": "string",
  "timestamp": "ISO-8601",
  "toolUseResult": {}
}
```

## Browser Compatibility

| Feature | Chrome/Edge | Firefox | Safari |
|---------|-------------|---------|--------|
| Basic Viewing | ✅ | ✅ | ✅ |
| File Upload | ✅ | ✅ | ✅ |
| Project Browser | ✅ | ❌ | ❌ |
| File Monitoring | ✅ | ❌ | ❌ |

*File System Access API features require Chrome 86+ or Edge 86+*

## Development

### Technologies Used
- **HTML5**: Semantic markup
- **Tailwind CSS**: Utility-first styling
- **Vanilla JavaScript**: No dependencies
- **File System Access API**: Modern file handling

### Key Functions
- `parseJsonl()`: Parses JSONL content with error handling
- `displayLogs()`: Renders sessions and conversation threads
- `startFileMonitoring()`: Implements real-time file watching
- `autoScrollToBottom()`: Handles automatic scrolling

## Contributing

1. Fork the repository
2. Create a feature branch (`git checkout -b feature/amazing-feature`)
3. Commit your changes (`git commit -m 'Add amazing feature'`)
4. Push to the branch (`git push origin feature/amazing-feature`)
5. Open a Pull Request

## License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.

## Acknowledgments

- Built for the Claude Code community
- Inspired by the need for better log visualization
- Uses Tailwind CSS for styling
- Icons from Heroicons

## Support

If you encounter issues or have suggestions:
1. Check the browser console for error messages
2. Ensure your JSONL files are valid
3. Verify file permissions for monitoring features
4. Open an issue on GitHub for bugs or feature requests

---

Made with ❤️ for the Claude Code community