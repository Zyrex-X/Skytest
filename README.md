local colors = {
    SchemeColor = Color3.fromRGB(0,255,255),
    Background = Color3.fromRGB(51, 255, 255),
    Header = Color3.fromRGB(0, 0, 0),
    TextColor = Color3.fromRGB(0,0,0),
    ElementColor = Color3.fromRGB(20, 20, 20)
}
local Library = loadstring(game:HttpGet("https://raw.githubusercontent.com/kickTh/New-Ui/main/Kavo-UI.txt"))()
local Window = Library.CreateLib("Kavo-UI :  Game", "DarkTheme")
local Tab = Window:NewTab("LUNAR HUB")
local Section = Tab:NewSection("Main")

Section:NewButton("AutoHakipad + summonRipindra", "เสกบอสแอดอัตโนมัติ", function()
        
wait(1)


    local args = {
    [1] = "activateColor", 
    [2] = "Winter Sky"
}
game:GetService("ReplicatedStorage").Remotes.CommF_:invokeServer(unpack(args))

    TP2(CFrame.new(-5419.56641, 1089.33752, -2665.78589, 0.971406102, 1.70427565e-08, 0.237423971, -2.01854462e-08, 1, 1.08056044e-08, -0.237423971, -1.52891388e-08, 0.971406102))
    wait(1)

    local args = {
    [1] = "activateColor", 
    [2] = "Pure Red"
}

game:GetService("ReplicatedStorage").Remotes.CommF_:invokeServer(unpack(args))
    TP2(CFrame.new(-5414.27979, 314.237671, -2212.57007, -0.984678745, -4.57075764e-08, 0.174378246, -4.24506084e-08, 1, 2.24074217e-08, -0.174378246, 1.46616497e-08, -0.984678745))

wait(1)

    local args = {
    [1] = "activateColor", 
    [2] = "Snow White"
}

game:GetService("ReplicatedStorage").Remotes.CommF_:invokeServer(unpack(args))
    TP2(CFrame.new(-4972.89502, 335.937714, -3720.4707, -0.738323092, -2.82306036e-08, 0.674447179, 5.20171852e-08, 1, 9.88010598e-08, -0.674447179, 1.08029944e-07, -0.738323092))

end)
local Section Tab:NewSection("Stats")

local Section Tab:NewSection("Misc")
Section:NewButton("Anti AFK", "", function()
    local vu = game:GetService("VirtualUser")
	game:GetService("Players").LocalPlayer.Idled:connect(function()
		vu:Button2Down(Vector2.new(0,0),workspace.CurrentCamera.CFrame)
		wait(1)
		vu:Button2Up(Vector2.new(0,0),workspace.CurrentCamera.CFrame)
end)
end)

Time = Section:Label("Server Time")

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

Client = Section:Label("Client")

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

Section:Line()

Old_World = false
New_World = false
Three_World = false
local placeId = game.PlaceId
if placeId == 2753915549 then
    Old_World = true
elseif placeId == 4442272183 then
    New_World = true
elseif placeId == 7449423635 then
	Three_World = true
end

Section:Toggle("Auto Farm Level", _G.SectionLevel, function(vu)
    _G.Section = vu
	if _G.Section and SelectToolWeapon == "" then
		DiscordLib:Notification("Section","SelectWeapon First","Okay")
	else
		Auto_Farm = vu
		SelectMonster = ""
		if vu == false then
			wait(1)
			TP(game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame)
		end
	end
end)

Section:Toggle("Auto SetSpawnPoint", false, function(vu)
    AutoSetSpawn = vu
end)

if New_World then
    Section:Toggle("Auto Factory", false, function(vu)
        Factory = vu
		if vu == false then
			wait(1)
			TP(game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame)
		end
    end)
end

if _G.Auto_Elite_Hop then
	_G.AutoElite = true
end

if Three_World then
	Section:Toggle("Auto Elite Hunter", _G.AutoElite, function(vu)
		EliteHunter = vu
		if vu == false then
			wait(1)
			TP(game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame)
		end
	end)

	CheckElite = Section:Label("")

	spawn(function()
		while true do
			local TotalElite = tostring(game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("EliteHunter","Progress"))
			CheckElite:Refresh("Total EliteHunter Progress : "..TotalElite)
			game:GetService("RunService").Heartbeat:wait()
		end
	end)

	Section:Toggle("Auto Enma/Yama", _G.AutoYama, function(vu)
		AutoYama = vu
	end)
	Section:Toggle("Auto Rainbow Haki", false, function(vu)
		AutoRainbow = vu
		if vu == false then
			wait(1)
			TP(game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame)
		end
	end)
end

if Old_World then
	Section:Toggle("Auto New World", _G.AutoNewworld, function(vu)
		Auto_Newworld = vu
		if vu == false then
			wait(1)
			TP(game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame)
		end
	end)
end

if New_World then
	Section:Toggle("Auto Third Sea", _G.AutoThirdSea, function(vu)
        ReadyThirdSea = vu
		TP(game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame)
        if ReadyThirdSea and game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("BartiloQuestProgress","Bartilo") ~= 3 then
            DiscordLib:Notification("Auto Third Sea","u must have\n Finish Bartilo Quest","Ok")
        elseif ReadyThirdSea and game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("ZQuestProgress","Check") ~= 0 then
            DiscordLib:Notification("Auto Third Sea","u must have to Killed Don Swan First","Ok")
        elseif ReadyThirdSea and SelectToolWeapon == "" then
            DiscordLib:Notification("Auto Third Sea","Select Weapon First","Ok")
        else
            AutoThird = vu
        end
    end)
end

Section:Toggle("Auto Superhuman", _G.AutoSuperhuman, function(vu)
    Superhuman = vu
end)

Section:Toggle("Auto Fully Superhuman", _G.FullyAutoSuperhuman, function(vu)
    AutoFullySuperhuman = vu
end)

Section:Toggle("Auto Electric Claw", false, function(vu)
    AutoElectricClaw = vu
	if AutoElectricClaw then
		game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("BuyElectro")
	end
end)

spawn(function()
	while wait(.1) do
		if AutoElectricClaw then
			if game.Players.LocalPlayer.Character:FindFirstChild("Electro") and game.Players.LocalPlayer.Character:FindFirstChild("Electro").Level.Value >= 400 then
				game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("BuyElectricClaw")
			end
			if game.Players.LocalPlayer.Backpack:FindFirstChild("Electro") and game.Players.LocalPlayer.Backpack:FindFirstChild("Electro").Level.Value >= 400 then
				game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("BuyElectricClaw")
			end
			if (game.Players.LocalPlayer.Backpack:FindFirstChild("Electro") and game.Players.LocalPlayer.Backpack:FindFirstChild("Electro").Level.Value <= 399) or (game.Players.LocalPlayer.Character:FindFirstChild("Electro") and game.Players.LocalPlayer.Character:FindFirstChild("Electro").Level.Value <= 399) then
				SelectToolWeapon = "Electro"
			end
			if game.Players.LocalPlayer.Backpack:FindFirstChild("Electric Claw") or game.Players.LocalPlayer.Character:FindFirstChild("Electric Claw") then
				SelectToolWeapon = "Electric Claw"
			end
			if (game.Players.LocalPlayer.Character:FindFirstChild("Electro") and game.Players.LocalPlayer.Character:FindFirstChild("Electro").Level.Value >= 400) or (game.Players.LocalPlayer.Backpack:FindFirstChild("Electro") and game.Players.LocalPlayer.Backpack:FindFirstChild("Electro").Level.Value >= 400) then
				if game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("BuyElectricClaw") == "..." and game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("BuyElectricClaw","Start") == 4 then
					TP(CFrame.new(-12548.998046875, 332.40396118164, -7603.1865234375))
				elseif game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("BuyElectricClaw",true) == 4 then
					Auto_Farm = false
					if (CFrame.new(-10369.7725, 331.654175, -10130.3047, 0.879783928, -1.15147909e-08, 0.475373745, -1.70712194e-10, 1, 2.45385472e-08, -0.475373745, -2.16697718e-08, 0.879783928).Position - game.Players.LocalPlayer.Character.HumanoidRootPart.Position).Magnitude <= 4 then
						wait(1.1)
						game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("BuyElectricClaw","Start")
					else
						TP(CFrame.new(-10369.7725, 331.654175, -10130.3047, 0.879783928, -1.15147909e-08, 0.475373745, -1.70712194e-10, 1, 2.45385472e-08, -0.475373745, -2.16697718e-08, 0.879783928))
					end
				elseif _G.Section then
					Auto_Farm = true
				end
			end
		end
	end
end)

Section:Toggle("Auto Accessories", _G.AutoAccessory, function(Value)
	AutoAccessories = Value 
end)

local SelectWeapon = Section:Dropdown("Select Weapon",Wapon,function(Value)
    SelectToolWeapon = Value
    SelectToolWeaponOld = Value
end)

Section:Button("Refresh Weapon", function()
    SelectWeapon:Clear()
    for i,v in pairs(game.Players.LocalPlayer.Backpack:GetChildren()) do
        if v:IsA("Tool") then
            SelectWeapon:Add(v.Name)
        end
    end
    for i,v in pairs(game.Players.LocalPlayer.Character:GetChildren()) do
        if v:IsA("Tool") then
            SelectWeapon:Add(v.Name)
        end
    end
end)

if not Old_World then
    Section:Line()
end

if _G.AutoLegendary_Hop then
    _G.Auto_Legendary_Sword = true
elseif _G.Auto_Legendary_Sword then
	_G.Auto_Legendary_Sword = true
else
    _G.Auto_Legendary_Sword = false
end

if _G.AutoEnchancement_Hop then
    _G.AutoEnchancement = true
elseif _G.AutoEnchancement then
    _G.AutoEnchancement = true
else
    _G.AutoEnchancement = false
end

if New_World then
    Section:Toggle("Auto Buy Legendary Sword", _G.Auto_Legendary_Sword, function(Value)
        LegebdarySword = Value    
    end)
end
if not Old_World then
    Section:Toggle("Auto Buy Enchancement >= 1500 F", _G.AutoEnchancement, function(Value)
        Enchancement = Value    
    end)
end

Section:Line()

Section:Toggle("Auto Farm Mastery Devil Fruit", false, function(vu)
	SectionMasteryFruit = vu
	if SectionMasteryFruit and WeaponMastery == "" then
		DiscordLib:Notification("Auto Farm Mastery","SelectWeapon First","Okay")
	else
		FarmMasteryFruit = vu
		if vu == false then
			wait(1)
			TP(game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame)
		end
	end
end)

Section:Toggle("Auto Farm Mastery Gun", false, function(vu)
	AutoarmMasteryGun = vu
	if AutoarmMasteryGun and WeaponMastery == "" then
		DiscordLib:Notification("Auto Farm Mastery","SelectWeapon First","Okay")
	else
		FarmMasteryGun = vu
		if vu == false then
			wait(1)
			TP(game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame)
		end
	end
end)

HealthPersen = 100
Section:Slider("Health %", 1,100,HealthPersen, function(Value)
	HealthPersen = Value
end)

Section:Toggle("Auto Farm Mastery Magnet", false, function(vu)
	MasteryMagnet = vu
end)

local SelectWeapon = Section:Dropdown("Select Weapon",Wapon,function(Value)
    WeaponMastery = Value
end)

Section:Button("Refresh Weapon", function()
    SelectWeapon:Clear()
    for i,v in pairs(game.Players.LocalPlayer.Backpack:GetChildren()) do  
        if v:IsA("Tool") then
            SelectWeapon:Add(v.Name)
        end
    end
    for i,v in pairs(game.Players.LocalPlayer.Character:GetChildren()) do  
        if v:IsA("Tool") then
            SelectWeapon:Add(v.Name)
        end
    end
end)

Section:Line()

Section:Toggle("Auto Farm Boss", false, function(vu)
	SectionBoss = vu
	if vu == false then
		wait(1)
		TP(game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame)
	end
end)

Section:Toggle("Auto Farm Boss Quest", true, function(vu)
	BossQuest = vu
end)

local BossName = Section:Dropdown("Select Boss", Boss, function(Value)
    SelectBoss = Value
end)

local SelectWeapon = Section:Dropdown("Select Weapon",Wapon,function(Value)
    SelectWeaponBoss = Value
end)

Section:Button("Refresh Boss", function()
    BossName:Clear()
    for i,v in pairs(game.ReplicatedStorage:GetChildren()) do
        if string.find(v.Name, "Boss") then
            if v.Name == "Ice Admiral [Lv. 700] [Boss]" then
			elseif v.Name == "rip_indra [Lv. 1500] [Boss]" then
			else
                BossName:Add(v.Name)
            end
        end
    end
    for i,v in pairs(game.workspace.Enemies:GetChildren()) do
        if string.find(v.Name, "Boss") then
            if v.Name ~= "Ice Admiral [Lv. 700] [Boss]" or v.Name ~= "rip_indra [Lv. 1500] [Boss]" then
                BossName:Add(v.Name)
            end
        end
    end
end)

Section:Button("Refresh Weapon",function()
    SelectWeapon:Clear()
    for i,v in pairs(game.Players.LocalPlayer.Backpack:GetChildren()) do  
        if v:IsA("Tool") then
            SelectWeapon:Add(v.Name)
        end
    end
    for i,v in pairs(game.Players.LocalPlayer.Character:GetChildren()) do
        if v:IsA("Tool") then
            SelectWeapon:Add(v.Name)
        end
    end
end)

Section:Line()

MiscFarmWeapon = ""
if Old_World then
	tableMon = {"Bandit [Lv. 5]","Monkey [Lv. 14]","Gorilla [Lv. 20]","Pirate [Lv. 35]","Brute [Lv. 45]","Desert Bandit [Lv. 60]","Desert Officer [Lv. 70]","Snow Bandit [Lv. 90]","Snowman [Lv. 100]","Chief Petty Officer [Lv. 120]","Sky Bandit [Lv. 150]","Dark Master [Lv. 175]","Toga Warrior [Lv. 225]","Gladiator [Lv. 275]","Military Soldier [Lv. 300]","Military Spy [Lv. 330]","Fishman Warrior [Lv. 375]","Fishman Commando [Lv. 400]","God's Guard [Lv. 450]","Shanda [Lv. 475]","Royal Squad [Lv. 525]","Royal Soldier [Lv. 550]","Galley Pirate [Lv. 625]","Galley Captain [Lv. 650]"}
elseif New_World then
	tableMon = {"Raider [Lv. 700]","Mercenary [Lv. 725]","Swan Pirate [Lv. 775]","Factory Staff [Lv. 800]","Marine Lieutenant [Lv. 875]","Marine Captain [Lv. 900]","Zombie [Lv. 950]","Vampire [Lv. 975]","Snow Trooper [Lv. 1000]","Winter Warrior [Lv. 1050]","Lab Subordinate [Lv. 1100]","Horned Warrior [Lv. 1125]","Magma Ninja [Lv. 1175]","Lava Pirate [Lv. 1200]","Ship Deckhand [Lv. 1250]","Ship Engineer [Lv. 1275]","Ship Steward [Lv. 1300]","Ship Officer [Lv. 1325]","Arctic Warrior [Lv. 1350]","Snow Lurker [Lv. 1375]","Sea Soldier [Lv. 1425]","Water Fighter [Lv. 1450]"}
elseif Three_World then
	tableMon = {"Pirate Millionaire [Lv. 1500]","Dragon Crew Warrior [Lv. 1575]","Dragon Crew Archer [Lv. 1600]","Female Islander [Lv. 1625]","Giant Islander [Lv. 1650]","Marine Commodore [Lv. 1700]","Marine Rear Admiral [Lv. 1725]","Fishman Raider [Lv. 1775]","Fishman Captain [Lv. 1800]","Forest Pirate [Lv. 1825]","Mythological Pirate [Lv. 1850]","Jungle Pirate [Lv. 1900]","Musketeer Pirate [Lv. 1925]","Reborn Skeleton [Lv. 1975]","Living Zombie [Lv. 2000]","Demonic Soul [Lv. 2025]","Posessed Mummy [Lv. 2050]"}
end

Section:Dropdown("Select Monster", tableMon, function(vu)
	SelectMonster = vu
end)

Section:Toggle("Auto Farm Select Monster", false, function(vu)
	SectionSelectMonster = vu
	if vu == false then
		wait(1)
		TP(game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame)
	end
end)

game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("getInventoryWeapons")

if New_World then
	Section:Toggle("Auto Quest Bartilo", false, function(vu)
		CheckBarto = vu
		if game.Players.LocalPlayer.Backpack:FindFirstChild("Warrior Helmet") then
			Success = true
		elseif game.Players.LocalPlayer.Character:FindFirstChild("Warrior Helmet") then
			Success = true
		end
		if Success and CheckBarto == true then
			DiscordLib:Notification("Auto Quest Bartilo","Successfully","Ok")
		elseif CheckBarto == true and MiscFarmWeapon == "" then
			DiscordLib:Notification("Auto Quest Bartilo","SelectWeapon First","Okay")
		elseif game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("BartiloQuestProgress","Bartilo") == 3 and CheckBarto == true then
			DiscordLib:Notification("Auto Quest Bartilo","Successfully","Ok")
		else
			AutoBartilo = vu
			if vu == false then
				wait(1)
				TP(game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame)
			end
		end
	end)

	Section:Toggle("Auto Evo Race", false, function(vu)
		CheckEvo = vu
		if not game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("BartiloQuestProgress","Bartilo") == 3 and CheckEvo then
			DiscordLib:Notification("Auto Evo Race","You Have To Success Bartilo Quest","Okay")
		elseif CheckEvo == true and MiscFarmWeapon == "" then
			DiscordLib:Notification("Auto Evo Race","SelectWeapon First","Okay")
		elseif game:GetService("Players").LocalPlayer.Data.Race:FindFirstChild("Evolved") and CheckEvo then
			DiscordLib:Notification("Auto Evo Race","Successfully","Ok")
		else
			AutoEvoRace = vu
			if vu == false then
				wait(1)
				TP(game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame)
			end
		end
	end)

	Section:Toggle("Auto Rengoku", false, function(vu)
		AutoRengoku = vu
		if vu == false then
			wait(1)
			TP(game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame)
		end
	end)

	Section:Toggle("Auto Ectoplasm", false, function(vu)
		AutoEcto = vu
		if vu == false then
			wait(1)
			TP(game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame)
		end
	end)
end

if Three_World then
	Section:Toggle("Auto Citizen Quest", false, function(vu)
		CheckCitizen = vu
		TP(game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame)
		if game.Players.LocalPlayer.Backpack:FindFirstChild("Musketeer Hat") then
			CTCH = true
		elseif game.Players.LocalPlayer.Character:FindFirstChild("Musketeer Hat") then
			CTCH = true
		end
		if CTCH and CheckCitizen then
			DiscordLib:Notification("Auto Quest Citizen","Successfully","Ok")
		elseif CheckCitizen and MiscFarmWeapon == "" then
			DiscordLib:Notification("Auto Quest Citizen","SelectWeapon First","Okay")
		elseif game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("CitizenQuestProgress","Citizen") == 3 and CheckCitizen then
			DiscordLib:Notification("Auto Quest Citizen","Successfully","Ok")
		else
			AutoCitizen = vu
			if vu == false then
				wait(1)
				TP(game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame)
			end
		end
	end)
end

local SelectWeapon = Section:Dropdown("Select Weapon",Wapon,function(value)
   	MiscFarmWeapon = value
end)

Section:Button("Refresh Weapon",function()
    SelectWeapon:Clear()
	for i,v in pairs(game.Players.LocalPlayer.Backpack:GetChildren()) do
		if v:IsA("Tool") then
			SelectWeapon:Add(v.Name)
		end
	end
	for i,v in pairs(game.Players.LocalPlayer.Character:GetChildren()) do
		if v:IsA("Tool") then
			SelectWeapon:Add(v.Name)
		end
	end
end)

Section:Line()

Section:Label(""):Refresh("Halloween's Event & Bone Shop")

local Bone = Section:Label("")

spawn(function()
	while game:GetService("RunService").Heartbeat:wait() do
		Bone:Refresh("Total Bone : "..tostring(game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("Bones","Check")))
	end
end)

Section:Button("Buy Reroll race", function()
	game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("Bones","Buy",1,3)
end)

Section:Button("Buy Refund Stats", function()
	game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("Bones","Buy",1,2)
end)

Section:Button("Buy Random Surprise", function()
	game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("Bones","Buy",1,1)
end)

Section:Toggle("Auto Buy Random Surprise", false, function(vu)
	AutoBuySurprise = vu
end)

Section:Toggle("Auto Buy EXP x2 [ Bone ]", false, function(vu)
    AutoBuyEXPBone = vu
end)

if Three_World then

    Section:Toggle("Auto Try Luck [gravestone]", false, function(vu)
        TryLuck = vu
    end)

    Section:Toggle("Auto Pray [gravestone]", false, function(vu)
        Pray = vu
    end)

    Section:Toggle("Auto Farm Bone", false, function(vu)
		Auto_Bone = vu
		if vu == false then
			wait(1)
			TP(game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame)
		end
	end)
    
    local SelectWeaponEvent = Section:Dropdown("Select Weapon",Wapon,function(value)
        EventWeapon = value
    end)
     
    Section:Button("Refresh Weapon",function()
        SelectWeaponEvent:Clear()
        for i,v in pairs(game.Players.LocalPlayer.Backpack:GetChildren()) do
            if v:IsA("Tool") then
               SelectWeaponEvent:Add(v.Name)
            end
        end
        for i,v in pairs(game.Players.LocalPlayer.Character:GetChildren()) do
            if v:IsA("Tool") then
               SelectWeaponEvent:Add(v.Name)
            end
        end
    end)

end

spawn(function()
    pcall(function()
        while wait(.1) do
            if AutoBuyEXPBone then
                if not string.find(game:GetService("Players").LocalPlayer.PlayerGui.Main.Level.Exp.Text, "2x") then
                    game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("Bones","Buy",1,1)
                end
            end
        end
    end)
end)

spawn(function()
	while wait(.1) do
		if AutoBuySurprise then
			game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("Bones","Buy",1,1)
		end
	end
end)

spawn(function()
	while wait(.1) do
		if TryLuck then
			game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("gravestoneEvent",1)
		end
	end
end)

spawn(function()
	while wait(.1) do
		if Pray then
			game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("gravestoneEvent",2)
		end
	end
end)

Section:Line()

Sec = 40
Section:Slider("Time", 1,600,Sec, function(Value)
	Sec = Value
end)

if _G.Section_Ken then
	SectionKen = true
else
	SectionKen = false
end

Section:Toggle("Auto Farm Observation Haki", SectionKen, function(vu)
	SectionObservation = vu
	TP(game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame)
	if SectionObservation then
	   game:GetService("VirtualUser"):CaptureController()
	   game:GetService("VirtualUser"):SetKeyDown('0x65')
	   wait(2)
	   game:GetService("VirtualUser"):SetKeyUp('0x65')
	end
end)

local ObservationLevel = Section:Label("")

spawn(function()
	while game:GetService("RunService").Heartbeat:wait() do
		if game.Players.LocalPlayer.VisionRadius.Value == 3000 then
			Value = "Max"
		else
			Value = math.round(game.Players.LocalPlayer.VisionRadius.Value)
		end
		ObservationLevel:Refresh("Observation Haki Level : "..tostring(Value))
	end
end)


Section:NewSlider("JumpPower", "", 500, 0, function(s) -- 500 (MaxValue) | 0 (MinValue)
    game.Players.LocalPlayer.Character.Humanoid.JumpPower = s
end)
Section:NewSlider("WalkSpeed", "", 500, 0, function(s) -- 500 (MaxValue) | 0 (MinValue)
     game.Players.LocalPlayer.Character.Humanoid.WalkSpeed = s
end)
local Tab = Window:NewTab("Setting")
local Section = Tab:NewSection("Keybund")
Section:NewKeybind("KeybindText", "KeybindInfo", Enum.KeyCode.RightControl, function()
	Library:ToggleUI()
end)
local Section = Tab:NewSection("Theme")
for theme, color in pairs(colors) do
    Section:NewColorPicker(theme, "DarkTheme"..theme, color, function(color3)
        Library:ChangeColor(theme, color3)
    end)
end
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
