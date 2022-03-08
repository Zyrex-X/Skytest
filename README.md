local DiscordLib = loadstring(game:HttpGet "https://raw.githubusercontent.com/bloodball/-back-ups-for-libs/main/discord")()

local win = DiscordLib:Window("Sky X Hub")

local serv = win:Server("Sky X Hub", "")
local tgls = serv:Channel("Main")

tgls:Toggle("AutoFarmLevel",true, function()
    loadstring(game:HttpGet"https://raw.githubusercontent.com/Zyrex-X/AutoFarmFunc/main/README.md")()

end)

local tgls = serv:Channel("Stats")
tgls:Toggle("Melee",true, function()
    loadstring(game:HttpGet"")
end)

local btns = serv:Channel("Buy Item")

local btns = serv:Channel("Tp")
btns:Button("pink", function()
    local CFrameEnd = CFrame.new(-5419.56641, 1089.33752, -2665.78589, 0.971406102, 1.70427565e-08, 0.237423971, -2.01854462e-08, 1, 1.08056044e-08, -0.237423971, -1.52891388e-08, 0.971406102)
    local time = 3
    local tween = game:GetService("TweenService"):Create(game.Local.LocalPlayers.Character.HumanoidRootPart,tweeninfo.new(Time),{CFrame = CFrameEnd}) tween.play()
end)
btns:Button("Red", function()
    local CFrameEnd = CFrame.new(-5414.27979, 314.237671, -2212.57007, -0.984678745, -4.57075764e-08, 0.174378246, -4.24506084e-08, 1, 2.24074217e-08, -0.174378246, 1.46616497e-08, -0.984678745)
    local time = 3
    local tween = game:GetService("TweenService"):Create(game.Local.LocalPlayers.Character.HumanoidRootPart,tweeninfo.new(Time),{CFrame = CFrameEnd}) tween.play()
end)
btns:Button("White", function()
    local CFrameEnd = CFrame.new(-4972.89502, 335.937714, -3720.4707, -0.738323092, -2.82306036e-08, 0.674447179, 5.20171852e-08, 1, 9.88010598e-08, -0.674447179, 1.08029944e-07, -0.738323092)
    local time = 3
    local tween = game:GetService("TweenService"):Create(game.Local.LocalPlayers.Character.HumanoidRootPart,tweeninfo.new(Time),{CFrame = CFrameEnd}) tween.play()
end)


local btns = serv:Channel("Other Hub")

btns:Button("MukuroHub", function()
    loadstring(game:HttpGet"https://raw.githubusercontent.com/Zyrex-X/MukuroHubAndriond/main/README.md")()
end)
btns:Button("UI Toggles MukuroHub", function()
    loadstring(game:HttpGet"https://raw.githubusercontent.com/Zyrex-X/uitog/main/README.md")()
end)

btns:Button("Some X Hub", function()
    loadstring(game:HttpGet"https://raw.githubusercontent.com/kickTh/SCRIPT-SOME-X-HUB/main/README.md")()
end)

btns:Button("Netna Hub", function()
    loadstring(game:HttpGet"loadstring(game:HttpGet('https://raw.githubusercontent.com/NinoGod/NetnaYay/8d21ce23346c500c93bb8b4a71f7791e4058a70b/startload.lua'))()")()
end)

btns:Button("Maru X Hub", function()
    loadstring(game:HttpGet"https://pastebin.com/raw/mUw5xC3J")()
end)

btns:Button("Dino Hub", function()
    loadstring(game:HttpGet"https://raw.githubusercontent.com/natoppo044/modzcaster/main/dinobf.lua", true)()
end)

btns:Button("Saza Hub", function()
    loadstring(game:HttpGet"https://www.scriptblox.com/raw/SAZA-HUB_496")()
end)

btns:Button("Fusion Hub", function()
    loadstring(game:HttpGet"'https://raw.githubusercontent.com/SHAREHACK/script/main/fusion1")()
end)

btns:Button("Power X Hub", function()
    loadstring(game:HttpGet"https://raw.githubusercontent.com/PowerxCANDYYY/BFFREE/main/POWERX.lua", true)()
end)

btns:Button("Ripper Hub", function()
    loadstring(game:HttpGet"https://raw.githubusercontent.com/hajibeza/RIPPER-HUB/main/BFMobile.lua")()
end)







btns:Seperator()
local lbls = serv:Channel("Labels")




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


local btns = win:Server("Sky X Hub", "http://www.roblox.com/asset/?id=6031075938")

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

