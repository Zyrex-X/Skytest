local DiscordLib = loadstring(game:HttpGet "https://raw.githubusercontent.com/bloodball/-back-ups-for-libs/main/discord")()

local win = DiscordLib:Window("Sky X Hub")

local serv = win:Server("Main", "")
local tgls = serv:Channel("Auto")

tgls:Toggle("Auto Farm Level", _G.AutoFarmLevel, function(vu)
    _G.AutoFarm = vu
	if _G.AutoFarm and SelectToolWeapon == "" then
		DiscordLib:Notification("AutoFarm","SelectWeapon First","Okay")
	else
		Auto_Farm = vu
		SelectMonster = ""
		if vu == false then
			wait(1)
			TP(game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame)
		end
	end
end)



local tgls = serv:Channel("Stats")
tgls:Toggle("Melee",true, function()
    loadstring(game:HttpGet"")
end)

local btns = serv:Channel("Buy Item")

local btns = serv:Channel("Tp")
btns:Button("pink", function()
    local args = {
    [1] = "ActivateColor", 
    [2] = "Winter Sky"
}

game.GetService("ReplicatedStorage").Remotes.CommF_:invokeServer(unpack(args))
local CFrameEnd = CFrame.new(-5419.56641, 1089.33752, -2665.78589, 0.971406102, 1.70427565e-08, 0.237423971, -2.01854462e-08, 1, 1.08056044e-08, -0.237423971, -1.52891388e-08, 0.971406102) --ใส่พิกัดวาร์ปใน()
local Time = 4 --แนะนำ28
local tween = game:GetService("TweenService"):Create(game.Players.LocalPlayer.Character.HumanoidRootPart,
    TweenInfo.new(Time), {CFrame = CFrameEnd}) tween:Play()
end)

btns:Button("Red", function()
    local args = {
    [1] = "ActivateColor", 
    [2] = "Winter Sky"
}

game.GetService("ReplicatedStorage").Remotes.CommF_:invokeServer(unpack(args))
local CFrameEnd = CFrame.new() --ใส่พิกัดวาร์ปใน()
local Time = 5 --แนะนำ28
local tween = game:GetService("TweenService"):Create(game.Players.LocalPlayer.Character.HumanoidRootPart,
    TweenInfo.new(Time), {CFrame = CFrameEnd}) tween:Play()

end)

btns:Button("White", function()
    local args = {
    [1] = "ActivateColor", 
    [2] = "Winter Sky"
}

game.GetService("ReplicatedStorage").Remotes.CommF_:invokeServer(unpack(args))
local CFrameEnd = CFrame.new() --ใส่พิกัดวาร์ปใน()
local Time = 5 --แนะนำ28
local tween = game:GetService("TweenService"):Create(game.Players.LocalPlayer.Character.HumanoidRootPart,
    TweenInfo.new(Time), {CFrame = CFrameEnd}) tween:Play()
end)


local btns = serv:Channel("Other Hub")

btns:Button("MukuroHub", function()
    loadstring(game:HttpGet"https://raw.githubusercontent.com/Zyrex-X/MukuroHubAndriond/main/README.md")()
end)
btns:Button("UI Toggles MukuroHub", function()
    loadstring(game:HttpGet"https://raw.githubusercontent.com/Zyrex-X/uitog/main/README.md")()
end)

btns:Button("Some X Hub", function()
    loadstring(game:HttpGet"https://raw.githubusercontent.com/kickTh/SomeHub/main/New.txt")()
end)

btns:Button("Netna Hub", function()
    loadstring(game:HttpGet"https://raw.githubusercontent.com/NinoGod/NetnaYay/8d21ce23346c500c93bb8b4a71f7791e4058a70b/startload.lua")()
end)

btns:Button("Maru X Hub", function()
    loadstring(game:HttpGet"https://pastebin.com/raw/mUw5xC3J")()
end)

btns:Button("Dino Hub", function()
    loadstring(game:HttpGet"https://raw.githubusercontent.com/natoppo044/modzcaster/main/dinobf.lua")()
end)

btns:Button("Saza Hub", function()
    loadstring(game:HttpGet"https://www.scriptblox.com/raw/SAZA-HUB_496")()
end)

btns:Button("Fusion Hub", function()
    loadstring(game:HttpGet"https://raw.githubusercontent.com/SHAREHACK/script/main/fusion1")()
end)

btns:Button("Power X Hub", function()
    loadstring(game:HttpGet"https://raw.githubusercontent.com/PowerxCANDYYY/BFFREE/main/POWERX.lua")()
end)

btns:Button("Ripper Hub", function()
    loadstring(game:HttpGet"https://raw.githubusercontent.com/hajibeza/RIPPER-HUB/main/BFMobile.lua")()
end)
btns:Button("สคริปเหี้ยไรนี่5555", function()
    loadstring(game:HttpGet"https://raw.githubusercontent.com/Gohan9k/BLACKTRAP/main/GOHANSSJ3")()
end)
btns:Button("Ren Hub", function()
    getgenv().keys = "Ren-IQVHIN-Y9N3MY"
    getgenv().Discordid = "861809193501196309"
    loadstring(game:HttpGet('https://raw.githubusercontent.com/RenHubb/Script/main/scriptmobile.lua'))()
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

local win = SomeLib:Window("Type", _G.Color, _G.Toggle)

local serv = win:Server("Main","")

local AutoFarm = serv:Channel("A", "http://www.roblox.com/asset/?id=7040391851")


Time = Auto:Label("Server Time")

function UpdateTime()
    local GameTime = math.floor(workspace.DistributedGameTime+0.5)
    local Hour = math.floor(GameTime/(60^2))%24
    local Minute = math.floor(GameTime/(60^1))%60
    local Second = math.floor(GameTime/(60^0))%60
    Time:Refresh("Hour : "..Hour.." Minute : "..Minute.." Second : "..Second)
end

spawn(function()
    while true do
        UpdateTime()
        wait()
    end
end)

Client = Auto:Label("FPS Server")

function UpdateClient()
    local Ping = game:GetService("Stats").Network.ServerStatsItem["Data Ping"]:GetValueString()
    local Fps = workspace:GetRealPhysicsFPS()
    Client:Refresh("Fps : "..Fps.." Ping : "..Ping)
end

spawn(function()
    while true do wait(.1)
        UpdateClient()
    end
end)

Auto:Line()


local btns = serv:Channel("Button","")



btns:Button("Button", function()
DiscordLib:Notification("Notification", "Button", "Okay!")
end)


btns:Button("Button", function()
SomeLib:Notification("Notification", "Button", "Okay!")
end)

local tgls = serv:Channel("Toggles","")

tgls:Toggle("Toggles",false, function(bool)
print(bool)
end)

local sldrs = serv:Channel("Sliders","")

local sldr = sldrs:Slider("sldrs", 0, 1000, 400, function(t)
print(t)
end)

sldrs:Button("Button", function()
sldr:Change(50)
end)

local drops = serv:Channel("Dropdowns","")


local drop = drops:Dropdown("drops",{"Option 1","Option 2","Option 3","Option 4","Option 5"}, function(bool)
print(bool)
end)

drops:Button("Button", function()
drop:Clear()
end)

drops:Button("Add Button", function()
drop:Add("Option")
end)

local clrs = serv:Channel("Colorpickers","")

clrs:Colorpicker("ESP Color", Color3.fromRGB(255,1,1), function(t)
print(t)
end)

local textbs = serv:Channel("Textboxes","")

textbs:Textbox("Gun power", "Type here!", true, function(t)
print(t)
end)

local lbls = serv:Channel("Labels","")

lbls:Label("This is just a label.")

local bnds = serv:Channel("Binds","")

bnds:Bind("Kill bind", Enum.KeyCode.RightShift, function()
print("Killed everyone!")
end)
