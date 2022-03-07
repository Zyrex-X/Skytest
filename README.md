local DiscordLib = loadstring(game:HttpGet "https://raw.githubusercontent.com/bloodball/-back-ups-for-libs/main/discord")()

local win = DiscordLib:Window("Sky X Hub")

local serv = win:Server("Test", "")

local btns = serv:Channel("Other Hub")

btns:Button("MukuroHub", function()
    loadstring(game:HttpGet"https://raw.githubusercontent.com/Zyrex-X/MukuroHubAndriond/main/README.md")()
end)
btns:Button("UI MukuroHub", function()
    loadstring(game:HttpGet"https://raw.githubusercontent.com/Zyrex-X/uitog/main/README.md")()
end)


btns:Seperator()
local lbls = serv:Channel("Labels")
lbls:Label("Some X Hub")

btns:Button("Some X Hub", function()
    loadstring(game:HttpGet"https://raw.githubusercontent.com/kickTh/SCRIPT-SOME-X-HUB/main/README.md")()
end)

local tgls = serv:Channel("Toggles")

tgls:Toggle("Toggles",false, function(bool)
print(bool)
end)

local sldrs = serv:Channel("Sliders")

local sldr = sldrs:Slider("sldrs", 0, 1000, 400, function(t)
print(t)
end)

sldrs:Button("Button", function()
sldr:Change(50)
end)

local drops = serv:Channel("Dropdowns")


local drop = drops:Dropdown("drops",{"Option 1","Option 2","Option 3","Option 4","Option 5"}, function(bool)
print(bool)
end)

drops:Button("Button", function()
drop:Clear()
end)

drops:Button("Add Button", function()
drop:Add("Option")
end)

local clrs = serv:Channel("Colorpickers")

clrs:Colorpicker("ESP Color", Color3.fromRGB(255,1,1), function(t)
print(t)
end)

local textbs = serv:Channel("Textboxes")

textbs:Textbox("Gun power", "Type here!", true, function(t)
print(t)
end)

local lbls = serv:Channel("Labels")

lbls:Label("This is just a label.")

local bnds = serv:Channel("Binds")

bnds:Bind("Kill bind", Enum.KeyCode.RightShift, function()
print("Killed everyone!")
end)

serv:Channel("Ui")


win:Server("Sky X Hub", "http://www.roblox.com/asset/?id=6031075938")

--Main

local btns = serv:Channel("Main")

lbls:Label("Auto Farm")
btns:Button("AutoFarm Level", function()
    loadstring(game:HttpGet"")()
end)

lbils:Button()

--Stats

--Raid - Esp

--Buy

-- Misc

--Settings

--About

--OtherHub If you Hate Sky x Hub

local btns = serv:Channel("Other Scripts")

lbls:Label("Mukuro Hub")
btns:Button("MukuroHub", function()
    loadstring(game:HttpGet"")()
end)
btns:Button("Button Toggle", function()
    loadstring(game:HttpGet"")()
end)
lbls:Label("Some X Hub")
btns:Button("Some X Hub", function()
    loadstring(game:HttpGet"")()
end)
lbls:Label("Netna Hub")
btns:Button("Netna Hub", function()
    loadstring(game:HttpGet"")()
end)

