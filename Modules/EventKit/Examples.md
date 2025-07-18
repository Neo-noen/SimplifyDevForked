## Requiring the Module
```lua
local ekit = require(<Path>)
```


Note: The code shown in here are examples. More sophisticated implementation is recommended.


## Connecting and Firing Test Events
```lua
-- Uses a BindableEvent under the hood
ekit.connect("TestCategory", "Event1", function(param1, param2)
	print(param1, param2)
end)

ekit.fire("TestCategory", "Event1", 123, 456)
```


## Attaching and Invoking Test Functions
```lua
-- Uses a BindableFunction under the hood
ekit.attach(nil, "DoRandomWait", function()
	print("Started Waiting")
	task.wait((math.random() * 2) + 1)
	print("Wait ended")
end)

ekit.invoke(nil, "DoRandomWait")
print("Passed Function")
```


## Client-Server Communication
#### Server Script:
```lua
ekit.client.attach("Stats", "Request", function(plr: Player)
	return {
		killCount = plr:GetAttribute("")
	}
end)
```
#### Client Script:
```lua
local myStats = ekit.server.invoke("Stats", "Request")
print("Hey, mom, I have " .. myStats.killCount .. " in this game!")
```