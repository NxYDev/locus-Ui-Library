# UI Library Documentation

## Initialization
```lua
local Library = loadstring(game:HttpGet('https://raw.githubusercontent.com/NxYDev/locus-Ui-Library/refs/heads/main/locus.lua'))()
```

## Window Creation
```lua
local Window = Library:CreateWindow({
    Title = "UI Title", 
    AutoShow = true,
    TabPadding = 5,
    MenuFadeTime = 0.2
})
```

## Tabs
```lua
local Tab = Window:AddTab("Main")
```

## Groupboxes (Sections)
```lua
local LeftGroup = Tab:AddLeftGroupbox("Features")
local RightGroup = Tab:AddRightGroupbox("Options")
```

## Tabboxes (Nested Tabs)
```lua
local NestedTabs = Tab:AddLeftTabbox("Advanced")
local Tab1 = NestedTabs:AddTab("Tab 1")
local Tab2 = NestedTabs:AddTab("Tab 2")
```

## UI Elements

### Button
```lua
LeftGroup:AddButton({
    Text = "Click Me",
    Func = function()
        print("Button clicked!")
    end
})
```

### Toggle
```lua
local MyToggle = LeftGroup:AddToggle({
    Text = "Enable Feature",
    Default = false,
    Callback = function(Value)
        print("Toggle state:", Value)
    end
})
```

### Color Picker
```lua
MyToggle:AddColorPicker({
    Default = Color3.new(1, 0, 0),
    Title = "Select Color"
})
```

### Slider
```lua
LeftGroup:AddSlider({
    Text = "Walk Speed",
    Default = 16,
    Min = 16,
    Max = 100,
    Rounding = 0,
    Callback = function(Value)
        print("Slider value:", Value)
    end
})
```

### Dropdown
```lua
LeftGroup:AddDropdown({
    Values = {"Option 1", "Option 2"},
    Default = "Option 1",
    Callback = function(Value)
        print("Selected:", Value)
    end
})
```

### Keybind
```lua
LeftGroup:AddToggle({
    Text = "Fly Mode"
}):AddKeyPicker({
    Default = "F",
    SyncToggleState = true,
    Mode = "Toggle",
    Callback = function(Value)
        print("Keybind state:", Value)
    end
})
```

### Input Box
```lua
LeftGroup:AddInput({
    Text = "Enter Text",
    Default = "",
    Numeric = false,
    Finished = false,
    Callback = function(Value)
        print("Input:", Value)
    end
})
```

## UI Features

### Watermark
```lua
Library:SetWatermark("UI v1.0 | FPS: 60")
Library:SetWatermarkVisibility(true)
```

### Notifications
```lua
Library:Notify("Action completed!", 5)
```

### Theme Colors
```lua
Library.AccentColor = Color3.fromRGB(255, 0, 0)
Library:UpdateColorsUsingRegistry()
```

## Finalization
```lua
Library:Init()  -- Must be called at end
```

## Destruction
```lua
Library:Destroy()
```

## Complete Example
```lua
local Library = loadstring(game:HttpGet('YOUR_GITHUB_RAW_LINK'))()

local Window = Library:CreateWindow({
    Title = "Example UI",
    AutoShow = true
})

local MainTab = Window:AddTab("Main")
local LeftGroup = MainTab:AddLeftGroupbox("Features")

LeftGroup:AddToggle({
    Text = "Enable ESP",
    Default = false
}):AddColorPicker({
    Default = Color3.new(1, 0, 0)
})

LeftGroup:AddSlider({
    Text = "Walk Speed",
    Min = 16,
    Max = 100,
    Default = 16
})

Library:SetWatermark("UI Loaded")
Library:Init()
```
