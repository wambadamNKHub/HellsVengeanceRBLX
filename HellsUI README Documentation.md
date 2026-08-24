# HellsUI

A simple Roblox UI library inspired by the classic **Hell's Vengeance** menu style.

---

## 📖 Documentation

### Initializing the Library

Load the HellsUI library using:

```lua
local HellsUI = loadstring(game:HttpGet(
    "https://raw.githubusercontent.com/wambadamNKHub/HellsVengeanceRBLX/refs/heads/main/HellsUI"
))()
```

Once loaded, you can create your UI window.

---

## 🪟 Creating a Window

Create the main HellsUI window with:

```lua
local Window = HellsUI:CreateWindow({
    Title = "Hell's Vengeance v1"
})
```

### Window Options

| Option | Description |
|---|---|
| `Title` | The title displayed at the top of the UI |

Example:

```lua
local Window = HellsUI:CreateWindow({
    Title = "My Custom Menu"
})
```

---

# 📄 Pages

Pages are used to organize your buttons and toggles into different sections.

Create a page with:

```lua
local Main = Window:CreatePage("Main")
```

The string `"Main"` is the name of the page.

### Example

```lua
local Main = Window:CreatePage("Main")
local Players = Window:CreatePage("Players")
local Weapons = Window:CreatePage("Weapons")
local Settings = Window:CreatePage("Settings")
```

You can create as many pages as you need.

---

# 🔘 Buttons

Buttons execute a function when clicked.

### Syntax

```lua
Page:CreateButton("Button Name", function()
    -- code
end)
```

### Example

```lua
Main:CreateButton("Test Button", function()
    print("Test button!")
end)
```

When the user clicks **Test Button**, the callback function runs.

### Example With a Function

```lua
Main:CreateButton("Say Hello", function()
    print("Hello!")
end)
```

---

# 🔀 Toggles

Toggles are used for features that can be turned **ON/OFF**.

### Syntax

```lua
Page:CreateToggle("Toggle Name", false, function(enabled)
    -- code
end)
```

The second argument controls the toggle's default state.

- `false` = OFF by default
- `true` = ON by default

### Example

```lua
Main:CreateToggle("Test Toggle", false, function(enabled)
    print("Toggle:", enabled)
end)
```

### Checking the Toggle State

The `enabled` variable tells you whether the toggle is currently enabled.

```lua
Main:CreateToggle("Funny Mode", false, function(enabled)

    if enabled then
        print("Funny Mode enabled!")
    else
        print("Funny Mode disabled!")
    end

end)
```

---

# 📂 Subpages

Pages can also contain their own pages.

For example:

```lua
local Main = Window:CreatePage("Main")

local Fun = Main:CreatePage("Fun")
```

This creates a **Fun** subpage under the **Main** page.

You can then add buttons and toggles to the subpage normally.

```lua
local Fun = Main:CreatePage("Fun")

Fun:CreateButton("Option 1", function()
    print("Option 1")
end)

Fun:CreateToggle("Funny Mode", false, function(enabled)
    print("Funny Mode:", enabled)
end)
```

---

# 🧩 Full Example

Here's a complete basic HellsUI script:

```lua
local HellsUI = loadstring(game:HttpGet(
    "https://raw.githubusercontent.com/wambadamNKHub/HellsVengeanceRBLX/refs/heads/main/HellsUI"
))()


-- Create the window
local Window = HellsUI:CreateWindow({
    Title = "Hell's Vengeance v1"
})


-- Create the Main page
local Main = Window:CreatePage("Main")


-- Create a button
Main:CreateButton("Test Button", function()
    print("Test button!")
end)


-- Create a toggle
Main:CreateToggle("Test Toggle", false, function(enabled)
    print("Toggle:", enabled)
end)


-- Create a subpage
local Fun = Main:CreatePage("Fun")


-- Button inside the subpage
Fun:CreateButton("Option 1", function()
    print("Option 1")
end)


-- Toggle inside the subpage
Fun:CreateToggle("Funny Mode", false, function(enabled)
    print("Funny Mode:", enabled)
end)
```

---

# 📚 Quick Reference

### Library

```lua
local HellsUI = loadstring(game:HttpGet("URL"))()
```

### Window

```lua
local Window = HellsUI:CreateWindow({
    Title = "My Menu"
})
```

### Page

```lua
local Page = Window:CreatePage("Page Name")
```

### Button

```lua
Page:CreateButton("Button Name", function()
    -- code
end)
```

### Toggle

```lua
Page:CreateToggle("Toggle Name", false, function(enabled)
    -- code
end)
```

### Subpage

```lua
local Subpage = Page:CreatePage("Subpage Name")
```

---

## ⚠️ Notes

HellsUI currently provides the basic components documented above:

- Windows
- Pages
- Subpages
- Buttons
- Toggles
- Callbacks

Additional components can be added to the library in future versions.