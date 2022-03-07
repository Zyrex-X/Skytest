local Library = loadstring(game:HttpGet("https://raw.githubusercontent.com/xHeptc/Kavo-UI-Library/main/source.lua"))()

local Window = Library.CreateLib("Sky X Hub", "Sentinel")

local Tab = Window:NewTab("Main")
local Section = Tab:NewSection("Section Name")

local Tab = Window:NewTab("Auto")

local Tab = Window:NewTab("Stats")

local Tab = Window:NewTab("Buy")

local Tab = Window:NewTab("Misc")

local Tab = Window:NewTab("Settings")

local Tab = Window:NewTab("AboutHub")

--SCRIPT-SOME-X-HUB

local Tab = Window:NewTab("Ohther Hub")
local Section = Tab:NewSection("Other Hub")
Section:NewButton("Some X Hub", "Script For Mobile", function()
    loadstring(game:HttpGet"https://raw.githubusercontent.com/kickTh/SCRIPT-SOME-X-HUB/main/README.md")()
end)
local Section = Tab:NewSection("ฮับอื่นไอ่ควาย5555")
Section:NewButton("NetnaHub", "Script For Mobile", function()
    loadstring(game:HttpGet('https://raw.githubusercontent.com/NinoGod/NetnaYay/8d21ce23346c500c93bb8b4a71f7791e4058a70b/startload.lua'))()
end)
