# Main-Bot-Backup-System
The Main Bot Backup System is a comprehensive Discord bot extension that allows you to manage multiple backup bots from a single interface. This system provides an easy way to deploy, manage, and control multiple Discord bots simultaneously, making it perfect for server redundancy and load distribution.
> 💡 **Built for the Zygnal Ecosystem — to download and use this extension, you must be part of the Zygnal Ecosystem.**  
> This extension (cog) is part of the **Zygnal Ecosystem** and is only available through its supported platforms.  
> You can use it with:  
> - The **[Discord Bot Framework](https://github.com/TheHolyOneZ/discord-bot-framework)** — ideal for developers who want full control and flexibility *(includes an integrated extension marketplace)*, or  
> - The **[ZygnalBot](https://zygnalbot.de)** — a prebuilt, plug-and-play Discord bot *(also includes an integrated extension marketplace)*.  
>
> Browse and install extensions at [zygnalbot.com/extension](https://zygnalbot.com/extension).  
> For help or community discussions, join us on Discord: [discord.gg/sgZnXca5ts](https://discord.gg/sgZnXca5ts)
# 🤖 Main Bot Backup System Documentation

## Overview

The Main Bot Backup System is a comprehensive Discord bot extension that allows you to manage multiple backup bots from a single interface. This system provides an easy way to deploy, manage, and control multiple Discord bots simultaneously, making it perfect for server redundancy and load distribution.

## Table of Contents

- [Features](#features)
- [Installation](#installation)
- [Quick Start Guide](#quick-start-guide)
- [Commands Reference](#commands-reference)
- [Interactive Panel](#interactive-panel)
- [Bot Management](#bot-management)
- [Security & Whitelisting](#security--whitelisting)
- [Troubleshooting](#troubleshooting)
- [API Reference](#api-reference)

## Features

### 🚀 **Core Features**
- **Multi-Bot Management**: Control dozens of backup bots from one interface
- **Interactive UI**: Modern Discord button-based control panel
- **Bulk Operations**: Start, stop, or manage all bots at once
- **Real-time Status**: Live monitoring of bot connections and server counts
- **Smart Invites**: Auto-generated OAuth2 links with proper permissions

### 🛡️ **Security Features**
- **Anti-Bot Protection**: Built-in warnings and whitelist command generation
- **Permission Management**: Granular permission control for invited bots
- **Safe Token Storage**: Encrypted local storage of bot tokens
- **Administrator Only**: All commands require administrator permissions

### 📊 **Monitoring Features**
- **Connection Status**: Real-time bot online/offline status
- **Server Counts**: Track how many servers each bot has joined
- **Error Logging**: Comprehensive error tracking and reporting
- **Bot IDs Display**: Easy access to bot IDs for whitelisting

## Installation

### Prerequisites
- Python 3.8+
- discord.py library
- Administrator permissions on your Discord server

### Setup Steps

1. **Place the file** in your bot's `Extensions/` directory:
```bash
cp Main_Bot_backup.py /path/to/your/bot/Extensions/
```

2. **Load the extension** in your main bot file:
```python
await bot.load_extension('Extensions.Main_Bot_backup')
```

3. **Create data directory** (auto-created on first run):
```bash
mkdir data
```

4. **Set permissions** - Ensure the bot has write access to the `data/` folder.

## Quick Start Guide

### Step 1: Access the Control Panel
```
!extrabots
```
This opens the interactive management panel with all available options.

### Step 2: Upload Bot Tokens
1. Click **"📤 Upload Bot Tokens"**
2. Enter JSON format:
```json
{
  "Bot1": "your_bot_token_here",
  "Bot2": "another_bot_token_here",
  "BackupBot": "third_bot_token_here"
}
```
3. Submit the modal

### Step 3: Start Your Bots
1. Click **"🚀 Start All Bots"**
2. Wait for connection confirmation
3. Check status with **"📊 Bot Status"**

### Step 4: Generate Invite Links
1. Click **"🔗 Generate Bot Invites"**
2. **IMPORTANT**: Copy whitelist commands first
3. Run whitelist commands on target servers
4. Click invite links to add bots

## Commands Reference

### Primary Commands

#### `!extrabots` / `!backupbots` / `!botmanager`
**Permission Required**: Administrator  
**Description**: Opens the main interactive control panel  
**Usage**: `!extrabots`

#### `!startbots` / `!connectbots`
**Permission Required**: Administrator  
**Description**: Starts all configured backup bots  
**Usage**: `!startbots`

#### `!botinvites` / `!invites`
**Permission Required**: Administrator  
**Description**: Generates invite links with whitelist warnings  
**Usage**: `!botinvites`

#### `!stopbots` / `!disconnectbots`
**Permission Required**: Administrator  
**Description**: Stops all running backup bots  
**Usage**: `!stopbots`

### Management Commands

#### `!addbot <name> <token>`
**Permission Required**: Administrator  
**Description**: Adds a single bot to the system  
**Usage**: `!addbot MyBot MTExNzg5NjE4OTQ4MzQyNzg0MA.GK7...`  
**Note**: Message is auto-deleted for security

#### `!removebot <name>`
**Permission Required**: Administrator  
**Description**: Removes a bot from the system  
**Usage**: `!removebot MyBot`

#### `!listbots`
**Permission Required**: Administrator  
**Description**: Lists all configured bots with their status  
**Usage**: `!listbots`

### Status Commands

#### `!backupstatus` / `!bstatus`
**Permission Required**: Administrator  
**Description**: Shows detailed status of all backup bots  
**Usage**: `!bstatus`

#### `!whitelisthelp` / `!wlhelp`
**Permission Required**: Administrator  
**Description**: Shows comprehensive whitelisting guide  
**Usage**: `!whitelisthelp`

## Interactive Panel

### Button Functions

| Button | Function | Description |
|--------|----------|-------------|
| 📤 **Upload Bot Tokens** | Add multiple bots via JSON | Bulk import bot tokens |
| 🚀 **Start All Bots** | Connect all bots | Activates all configured bots |
| 🔗 **Generate Bot Invites** | Create invite links | OAuth2 links with whitelist warnings |
| 📊 **Bot Status** | View bot status | Real-time connection and server info |
| 🛑 **Stop All Bots** | Disconnect all bots | Safely stops all running bots |
| 🚪 **Leave This Server** | Remove bots from server | Makes all bots leave current server |
| 🗑️ **Clear All Bots** | Remove all bots | Completely clears bot database |

### Panel Features
- **Real-time Updates**: Status updates automatically
- **Error Handling**: Graceful error messages and recovery
- **Ephemeral Responses**: Private responses to avoid spam
- **Timeout Protection**: Auto-expires after 5 minutes

## Bot Management

### Adding Bots

#### Method 1: Interactive Upload (Recommended)
```json
{
  "MainBackup": "MTExNzg5NjE4OTQ4MzQyNzg0MA.GK7...",
  "SecondaryBot": "MTExNzg5NjE4OTQ4MzQyNzg0MB.HL8...",
  "EmergencyBot": "MTExNzg5NjE4OTQ4MzQyNzg0MC.IM9..."
}
```

#### Method 2: Command Line
```
!addbot MainBackup MTExNzg5NjE4OTQ4MzQyNzg0MA.GK7...
```

### Bot Token Requirements
- **Length**: Must be longer than 50 characters
- **Format**: Standard Discord bot token format
- **Validity**: Token must be valid and bot must exist
- **Permissions**: Bot must have necessary OAuth2 permissions

### Connection Process
1. **Token Validation**: Checks token format and length
2. **Client Creation**: Creates Discord client with proper intents
3. **Event Handlers**: Sets up connection monitoring
4. **Connection Attempt**: Attempts to connect to Discord
5. **Status Verification**: Confirms successful connection
6. **ID Retrieval**: Stores bot user ID for invite generation

## Security & Whitelisting

### Anti-Bot Protection Warning System

The system automatically warns users about anti-bot protection and provides:

#### Whitelist Command Generation
```bash
!whitelist_bot 1117896189483427840
!whitelist_bot 1117896189483427841
!whitelist_bot 1117896189483427842
```

#### Common Whitelist Commands
- `!whitelist_bot <bot_id>`
- `!whitelist add <bot_id>`
- `!antibot whitelist <bot_id>`
- `!security whitelist <bot_id>`

#### Step-by-Step Safety Process
1. **First**: Run whitelist commands on target server
2. **Then**: Click invite links
3. **Select**: Choose server from dropdown
4. **Review**: Check permissions before authorizing
5. **Complete**: Finish any required captcha

### Bot Permissions

The system requests these permissions for backup bots:
- ✅ Read Messages
- ✅ Send Messages
- ✅ Embed Links
- ✅ Attach Files
- ✅ Read Message History
- ✅ Use External Emojis
- ✅ Add Reactions
- ✅ Connect (Voice)
- ✅ Speak (Voice)
- ✅ Manage Messages
- ✅ Manage Roles
- ✅ Kick Members
- ✅ Ban Members
- ❌ Administrator (Excluded for security)

## Troubleshooting

### Common Issues

#### Bot Won't Connect
**Symptoms**: Bot shows as offline, connection fails  
**Solutions**:
- Verify token is correct and complete
- Check bot exists in Discord Developer Portal
- Ensure bot is not already running elsewhere
- Check internet connection and Discord API status

#### Invalid Token Error
**Symptoms**: "Invalid token format" message  
**Solutions**:
- Ensure token is complete (usually 70+ characters)
- Copy token directly from Discord Developer Portal
- Check for extra spaces or characters
- Regenerate token if necessary

#### Bot Gets Kicked Immediately
**Symptoms**: Bot joins then leaves instantly  
**Solutions**:
- Run whitelist commands BEFORE inviting
- Check server's anti-bot protection settings
- Contact server administrators
- Try different whitelist command formats

#### Permission Denied
**Symptoms**: Commands don't work, "Permission Denied" error  
**Solutions**:
- Ensure you have Administrator permission
- Check bot has proper role hierarchy
- Verify bot permissions in server settings

### Error Codes

| Error | Meaning | Solution |
|-------|---------|----------|
| `Invalid JSON format` | Malformed JSON in upload | Check JSON syntax |
| `Token too short` | Invalid token length | Use complete bot token |
| `Bot already exists` | Duplicate bot name | Use different name |
| `Connection failed` | Can't connect to Discord | Check token and internet |
| `No bots configured` | No bots in system | Add bots first |

### Debug Information

Enable debug logging by setting:
```python
logging.basicConfig(level=logging.DEBUG)
```

This provides detailed information about:
- Connection attempts
- Token validation
- Guild join/leave events
- Error stack traces

## API Reference

### Classes

#### `BackupBot`
Represents a single backup bot instance.

**Attributes**:
- `token: str` - Bot's Discord token
- `name: str` - Human-readable bot name
- `client: discord.Client` - Discord client instance
- `is_connected: bool` - Connection status
- `guilds: List[discord.Guild]` - List of joined guilds
- `task: asyncio.Task` - Background connection task
- `user_id: int` - Bot's Discord user ID

#### `BotUploadModal`
Discord modal for bulk bot token upload.

**Methods**:
- `on_submit()` - Handles form submission and validation

#### `BackupBotControlView`
Main interactive control panel view.

**Buttons**:
- `upload_tokens()` - Opens upload modal
- `start_all_bots()` - Starts all configured bots
- `generate_invites()` - Creates invite links
- `status_check()` - Shows bot status
- `stop_all_bots()` - Stops all bots
- `leave_server()` - Makes bots leave current server
- `clear_bots()` - Removes all bots

#### `MainBotBackup`
Main cog class containing all functionality.

**Key Methods**:
- `start_backup_bot(backup_bot)` - Starts individual bot
- `save_bot_data()` - Persists bot data to file
- `load_bot_data()` - Loads bot data from file

### Data Storage

#### File Structure
```
data/
└── backup_bots.json
```

#### JSON Format
```json
{
  "BotName1": "bot_token_here",
  "BotName2": "another_token_here"
}
```

### Events

The system monitors these Discord events:
- `on_ready` - Bot connection established
- `on_disconnect` - Bot disconnected
- `on_guild_join` - Bot joined a server
- `on_guild_remove` - Bot left a server

## Best Practices

### Security
- ✅ Never share bot tokens publicly
- ✅ Use the interactive panel for token upload
- ✅ Regularly rotate bot tokens
- ✅ Monitor bot activity logs
- ❌ Don't store tokens in plain text files
- ❌ Don't grant unnecessary permissions

### Management
- ✅ Use descriptive bot names
- ✅ Test bots before mass deployment
- ✅ Monitor connection status regularly
- ✅ Keep backup of working configurations
- ❌ Don't run too many bots simultaneously
- ❌ Don't ignore connection failures

### Performance
- ✅ Start bots gradually to avoid rate limits
- ✅ Monitor memory usage with many bots
- ✅ Use appropriate intents for each bot
- ✅ Clean up disconnected bots regularly

## Support

### Getting Help
1. Check this documentation first
2. Review error messages carefully
3. Enable debug logging for detailed info
4. Check Discord API status
5. Verify bot tokens and permissions

### Common Resources
- [Discord Developer Portal](https://discord.com/developers/applications)
- [Discord.py Documentation](https://discordpy.readthedocs.io/)
- [Discord API Documentation](https://discord.com/developers/docs)

---

**Compatibility**: discord.py 2.0+  
**License**: MIT
