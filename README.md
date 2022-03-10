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
    TP2(CFrame.new(-5419.56641, 1089.33752, -2665.78589, 0.971406102, 1.70427565e-08, 0.237423971, -2.01854462e-08, 1, 1.08056044e-08, -0.237423971, -1.52891388e-08, 0.971406102))
    
    local args = {
    [1] = "ActivateColor", 
    [2] = "Winter Sky"
}
game.GetService("ReplicatedStorage").Remotes.CommF_:invokeServer(unpack(args))

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

function TP(P1)
    Distance = (P1.Position - game.Players.LocalPlayer.Character.HumanoidRootPart.Position).Magnitude
    if Distance < 250 then
        Speed = 600
    elseif Distance < 500 then
        Speed = 400
    elseif Distance < 1000 then
        Speed = 350
    elseif Distance >= 1000 then
        Speed = 200
    end
    game:GetService("TweenService"):Create(
        game.Players.LocalPlayer.Character.HumanoidRootPart,
        TweenInfo.new(Distance/Speed, Enum.EasingStyle.Linear),
        {CFrame = P1}
    ):Play()
end

function TP2(P1)
	Distance = (P1.Position - game.Players.LocalPlayer.Character.HumanoidRootPart.Position).Magnitude
	if Distance < 1000 then
		Speed = 400
	elseif Distance >= 1000 then
		Speed = 250
	end
    game:GetService("TweenService"):Create(
        game.Players.LocalPlayer.Character.HumanoidRootPart,
        TweenInfo.new(Distance/Speed, Enum.EasingStyle.Linear),
        {CFrame = P1}
    ):Play()
    Clip = true
    wait(Distance/Speed)
    Clip = false
end

tgls:Toggle("Ctrl + Click to TP", false, function(vu)
	CTRL = vu
end)

btns:Button("Stop Tween", function()
    Clip = false
    TP(game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame)
end)

if Old_World then

    btns:Button("Teleport To Second Sea", function()
        game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("TravelDressrosa")
    end)

	btns:Button("Teleport To Third Sea", function()
        game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("TravelZou")
    end)

    btns:Line()

    btns:Button("Wild Mill", function()
        TP2(CFrame.new(1042.1501464844, 16.299360275269, 1444.3442382813))
    end)

    btns:Button("Marine 1st", function()
        TP2(CFrame.new(-2599.6655273438, 6.9146227836609, 2062.2216796875))
    end)

    btns:Button("Marine 2sd", function()
        TP2(CFrame.new(-5081.3452148438, 85.221641540527, 4257.3588867188))
    end)

    btns:Button("Midle Town", function()
        TP2(CFrame.new(-655.97088623047, 7.878026008606, 1573.7612304688))
    end)

    btns:Button("Jungle", function()
        TP2(CFrame.new(-1499.9877929688, 22.877912521362, 353.87060546875))
    end)

    btns:Button("Pirate Village", function()
        TP2(CFrame.new(-1163.3889160156, 44.777843475342, 3842.8276367188))
    end)

    btns:Button("Desert", function()
        TP2(CFrame.new(954.02056884766, 6.6275520324707, 4262.611328125))
    end)

    btns:Button("Frozen Village", function()
        TP2(CFrame.new(1144.5270996094, 7.3292083740234, -1164.7322998047))
    end)

    btns:Button("Colosseum", function()
        TP2(CFrame.new(-1667.5869140625, 39.385631561279, -3135.5817871094))
    end)

    btns:Button("Prison", function()
        TP2(CFrame.new(4857.6982421875, 5.6780304908752, 732.75750732422))
    end)

    btns:Button("Mob Leader", function()
        TP2(CFrame.new(-2841.9604492188, 7.3560485839844, 5318.1040039063))
    end)

    btns:Button("Magma Village", function()
        TP2(CFrame.new(-5328.8740234375, 8.6164798736572, 8427.3994140625))
    end)

    btns:Button("UnderWater Gate", function()
        TP2(CFrame.new(3893.953125, 5.3989524841309, -1893.4851074219))
    end)

    btns:Button("UnderWater City", function()
        TP2(CFrame.new(61191.12109375, 18.497436523438, 1561.8873291016))
    end)

    btns:Button("Fountain City", function()
        TP2(CFrame.new(5244.7133789063, 38.526943206787, 4073.4987792969))
    end)

    btns:Button("Sky 1st", function()
        TP2(CFrame.new(-4878.0415039063, 717.71246337891, -2637.7294921875))
    end)

    btns:Button("Sky 2sd", function()
        TP2(CFrame.new(-7899.6157226563, 5545.6030273438, -422.21798706055))
    end)

    btns:Button("Sky 3th", function()
        TP2(CFrame.new(-7868.5288085938, 5638.205078125, -1482.5548095703))
    end)
    
elseif New_World then
        
    btns:Button("Teleport To First Sea", function()
        game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("TravelMain")
    end)

	btns:Button("Teleport To Third Sea", function()
        game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("TravelZou")
    end)

    btns:Line()

    btns:Button("Dock", function()
        TP2(CFrame.new(-12.519311904907, 19.302536010742, 2827.853515625))
    end)

    Tp:Button("Mansion", function()
        TP2(CFrame.new(-390.34829711914, 321.89730834961, 869.00506591797))
    end)

    Tp:Button("Kingdom Of Rose", function()
        TP2(CFrame.new(-388.29895019531, 138.35575866699, 1132.1662597656))
    end)

    Tp:Button("Cafe", function()
        TP2(CFrame.new(-379.70889282227, 73.0458984375, 304.84692382813))
    end)

    Tp:Button("Sunflower Field", function()
        TP2(CFrame.new(-1576.7171630859, 198.61849975586, 13.725157737732))
    end)

    Tp:Button("Jeramy Mountain", function()
        TP2(CFrame.new(1986.3519287109, 448.95678710938, 796.70239257813))
    end)

    Tp:Button("Colossuem", function()
        TP2(CFrame.new(-1871.8974609375, 45.820514678955, 1359.6843261719))
    end)

    Tp:Button("Factory", function()
        TP2(CFrame.new(349.53750610352, 74.446998596191, -355.62420654297))
    end)

    Tp:Button("The Bridge", function()
        TP2(CFrame.new(-1860.6354980469, 88.384948730469, -1859.1593017578))
    end)

    Tp:Button("Green Bit", function()
        TP2(CFrame.new(-2202.3706054688, 73.097663879395, -2819.2687988281))
    end)

    Tp:Button("Graveyard", function()
        TP2(CFrame.new(-5617.5927734375, 492.22183227539, -778.3017578125))
    end)

    Tp:Button("Dark Area", function()
        TP2(CFrame.new(3464.7700195313, 13.375151634216, -3368.90234375))
    end)

    Tp:Button("Snow Mountain", function()
        TP2(CFrame.new(561.23834228516, 401.44781494141, -5297.14453125))
    end)

    Tp:Button("Hot Island", function()
        TP2(CFrame.new(-5505.9633789063, 15.977565765381, -5366.6123046875))
    end)

    Tp:Button("Cold Island", function()
        TP2(CFrame.new(-5924.716796875, 15.977565765381, -4996.427734375))
    end)

    Tp:Button("Ice Castle", function()
        TP2(CFrame.new(6111.7109375, 294.41259765625, -6716.4829101563))
    end)

    Tp:Button("Usopp's Island", function()
        TP2(CFrame.new(4760.4985351563, 8.3444719314575, 2849.2426757813))
    end)

    Tp:Button("inscription Island", function()
        TP2(CFrame.new(-5099.01171875, 98.241539001465, 2424.4035644531))
    end)

    Tp:Button("Forgotten Island", function()
        TP2(CFrame.new(-3051.9514160156, 238.87203979492, -10250.807617188))
    end)

    Tp:Button("Ghost Ship", function()
        game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("requestEntrance",Vector3.new(923.21252441406, 126.9760055542, 32852.83203125))
    end)

    Tp:Button("Mini Sky", function()
        TP2(CFrame.new(-262.11901855469, 49325.69140625, -35272.49609375))
    end)

elseif Three_World then

	Tp:Button("Teleport to First Sea", function()
		game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("TravelMain")
	end)

	Tp:Button("Teleport to Second Sea", function()
		game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("TravelDressrosa")
	end)

	Tp:Line()

	btns:Button("Port Town", function()
        TP2(CFrame.new(-275.21615600586, 43.755737304688, 5451.0659179688))
    end)

	btns:Button("Hydra Island", function()
		TP2(CFrame.new(5541.2685546875, 668.30456542969, 195.48069763184))
	end)
	
	btns:Button("Gaint Tree", function()
		TP2(CFrame.new(2276.0859375, 25.87850189209, -6493.03125))
	end)
	
	btns:Button("Zou Island", function()
		TP2(CFrame.new(-10034.40234375, 331.78845214844, -8319.6923828125))
	end)
	
	btns:Button("PineApple Village", function()
		TP2(CFrame.new(-11172.950195313, 331.8049621582, -10151.033203125))
	end)
	
	btns:Button("Mansion", function()
		TP2(CFrame.new(-12548.998046875, 332.40396118164, -7603.1865234375))
	end)

	btns:Button("Castle on the Sea", function()
		TP2(CFrame.new(-5498.0458984375, 313.79473876953, -2860.6022949219))
	end)

    btns:Button("Graveyard Island", function()
        TP2(CFrame.new(-9515.07324, 142.130615, 5537.58398))
    end)

	btns:Button("Raid Lab", function()
		TP2(CFrame.new(-5057.146484375, 314.54132080078, -2934.7995605469))
	end)

	btns:Button("Mini Sky", function()
		TP2(CFrame.new(-263.66668701172, 49325.49609375, -35260))
	end)
end



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
