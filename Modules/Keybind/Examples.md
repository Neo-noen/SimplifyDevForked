These are not the only functions with this module. If you want to see what else it has, you can do that by [getting the Module](Downloads: https://github.com/IcKon/SimplifyDev/tree/main/Modules/Keybind/Keybind.lua)

## Requiring the Module
```lua
local keybind = require(<Path>)
```


## Adding Binds
```lua
keybind.bind.add("Jump", Enum.KeyCode.Space, Enum.KeyCode.ButtonA)
```


## Connecting Bind Press
```lua
keybind.connect.press.bind("Jump", function(keyUsed: EnumItem)
	print("Jumped using the " .. keyUsed.Name .. " key.")
end)
```


## Force Press
A hacky solution, but it is what is used for my project called Untitled Parkour Game for mobile players.
```lua
-- When mobile button is pressed:
keybind.press.bind("Jump", Enum.UserInputType.Touch)

-- When mobile button released:
keybind.release.bind("Jump", Enum.UserInputType.Touch)
```