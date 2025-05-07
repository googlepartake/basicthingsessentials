# 🚀 Basic Thing Essentials

**Basic Thing Essentials** is a **powerful, streamlined admin system** for Roblox designed to be *way better* than the original. Originally created by [r_r], this enhanced version brings clarity, performance, and a modular structure that makes Roblox admin management intuitive and efficient. *Still being made*

> ✨ Clean. 🔐 Secure. ⚙️ Extensible. ⚡ Fast.

---

## 🎯 Features

- ✅ **Command Handler** – Easily add and customize admin commands
- 📊 **Permission System** – Rank-based permissions with full flexibility
- 🧩 **Modular Design** – Plug-and-play architecture for commands and modules
- 💬 **Chat Integration** – Execute commands directly from chat
- 🛡️ **Security Enhancements** – Hardened against abuse and exploits
- 🎮 **User-Friendly Interface** – Smooth UI elements for in-game administration

---

## 📦 Installation

1. Download or clone the repository:
   ```bash
   git clone https://github.com/your-username/basic-thing-essentials.git``

2. Insert the module into ReplicatedStorage or ServerScriptService in your Roblox game.
3. Initialize and configure through your main server script.

## 🛠️ Usage

To get started using **Basic Thing Essentials** in your game:

### 1. **Initialize the System**

In a Script (preferably in `ServerScriptService`), require and start the system:

```lua
local AdminSystem = require(game:GetService("ReplicatedStorage"):WaitForChild("BasicThingEssentials"))
AdminSystem:Init({
    defaultRank = "User", -- Set a default rank for new players
    commandPrefix = "!",  -- Prefix for chat commands
})
```

### 2. **Configure Ranks and Permissions**

Define admin ranks and assign permissions in the config module:

```lua
AdminSystem:SetRanks({
    ["Owner"] = {
        level = 100,
        users = {"PlayerName1", "PlayerName2"},
    },
    ["Moderator"] = {
        level = 50,
        users = {"ModUser"},
    },
    ["User"] = {
        level = 0,
        users = {},
    },
})

AdminSystem:SetPermissions({
    ["kick"] = 50,
    ["ban"] = 100,
    ["fly"] = 50,
    ["teleport"] = 0,
})
```

### 3. **Creating a Custom Command**

You can easily create and register your own commands:

```lua
AdminSystem:RegisterCommand("say", {
    description = "Broadcast a message to all players",
    permissionLevel = 0,
    execute = function(player, args)
        local message = table.concat(args, " ")
        game:GetService("ReplicatedStorage").RemoteEvent:FireAllClients(player.Name .. " says: " .. message)
    end
})
```

### 4. **Using Commands In-Game**

Players with appropriate permissions can use chat commands like:

```
!kick PlayerName
!say Hello everyone!
```

---

## 🧠 Tips

- Modularize your custom commands by putting them in separate modules for better organization.  
- Use `AdminSystem:GetRank(player)` to fetch a player’s rank dynamically.  
- System is updated automatically without breaking any of your scripts! *(Only if user has activated the Roblox Package system)*
- You can also edit the MainModule for custom UI's and other stuff! 

---

## 🧾 License

This project is licensed under the MIT License — see the `LICENSE` file for details.










