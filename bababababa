getgenv().username = 'petpetgem2001'
repeat wait() until game.Players
repeat wait() until game.Players.LocalPlayer
repeat wait() until game.ReplicatedStorage
repeat wait() until game:GetService("Players").LocalPlayer:FindFirstChild("PlayerGui")
repeat wait() until game:GetService("Players").LocalPlayer.PlayerGui:FindFirstChild("Main")
local vu = game:GetService("VirtualUser")
local plr = game.Players.LocalPlayer
local shotmodule = getsenv(game:GetService("Players").LocalPlayer.PlayerScripts.Scripts.Game.Misc.Slingshot)
local UTS = game.UserInputService
local camera = game.Workspace.CurrentCamera
local plr = game.Players.LocalPlayer
local Client = require(game.ReplicatedStorage.Library.Client)

repeat task.wait() until game:IsLoaded()
if not game:IsLoaded() then game:IsLoaded():Wait(5) end
local UserInputService = game:GetService("UserInputService")
local RunService = game:GetService("RunService")

local WindowFocusReleasedFunction = function()
    RunService:Set3dRenderingEnabled(false)
    setfpscap(15)
    return
end

local WindowFocusedFunction = function()
    RunService:Set3dRenderingEnabled(true)
    setfpscap(15)
    return
end

local Initialize = function()
    UserInputService.WindowFocusReleased:Connect(WindowFocusReleasedFunction)
    UserInputService.WindowFocused:Connect(WindowFocusedFunction)
    return
end
Initialize()
UserSettings():GetService("UserGameSettings").MasterVolume = 0
local decalsyeeted = true
local g = game
local w = g.Workspace
local l = g.Lighting
local t = w.Terrain
sethiddenproperty(l,"Technology",2)
sethiddenproperty(t,"Decoration",false)
t.WaterWaveSize = 0
t.WaterWaveSpeed = 0
t.WaterReflectance = 0
t.WaterTransparency = 1
l.GlobalShadows = 0
l.FogEnd = 9e9
l.Brightness = 0
settings().Rendering.QualityLevel = "Level01"
for i, v in pairs(w:GetDescendants()) do
    if v:IsA("BasePart") and not v:IsA("MeshPart") then
        v.Material = "Plastic"
        v.Transparency = 1
        v.Reflectance = 0
    elseif (v:IsA("Decal") or v:IsA("Texture")) and decalsyeeted then
        v.Transparency = 1
    elseif v:IsA("ParticleEmitter") or v:IsA("Trail") then
        v.Lifetime = NumberRange.new(0)
    elseif v:IsA("Explosion") then
        v.BlastPressure = 1
        v.BlastRadius = 1
    elseif v:IsA("Fire") or v:IsA("SpotLight") or v:IsA("Smoke") or v:IsA("Sparkles") then
        v.Enabled = false
    elseif v:IsA("MeshPart") and decalsyeeted then
        v.Material = "Plastic"
        v.Transparency = 1
        v.Reflectance = 0
        v.TextureID = 0
    elseif v:IsA("SpecialMesh") and decalsyeeted  then
        v.TextureId=0
    elseif v:IsA("ShirtGraphic") and decalsyeeted then
        v.Graphic=1
    elseif (v:IsA("Shirt") or v:IsA("Pants")) and decalsyeeted then
        v[v.ClassName.."Template"]=1
    end
end
for i = 1,#l:GetChildren() do
    e=l:GetChildren()[i]
    if e:IsA("BlurEffect") or e:IsA("SunRaysEffect") or e:IsA("ColorCorrectionEffect") or e:IsA("BloomEffect") or e:IsA("DepthOfFieldEffect") then
        e.Enabled = false
    end
end
w.DescendantAdded:Connect(function(v)
    pcall(function()
        if v:IsA("BasePart") and not v:IsA("MeshPart") then
            v.Material = "Plastic"
            v.Reflectance = 0
            v.Transparency = 1
        elseif v:IsA("Decal") or v:IsA("Texture") and decalsyeeted then
            v.Transparency = 1
        elseif v:IsA("ParticleEmitter") or v:IsA("Trail") then
            v.Lifetime = NumberRange.new(0)
        elseif v:IsA("Explosion") then
            v.BlastPressure = 1
            v.BlastRadius = 1
        elseif v:IsA("Fire") or v:IsA("SpotLight") or v:IsA("Smoke") or v:IsA("Sparkles") then
            v.Enabled = false
        elseif v:IsA("MeshPart") and decalsyeeted then
            v.Material = "Plastic"
            v.Reflectance = 0
            v.TextureID = 0
            v.Transparency = 1
        elseif v:IsA("SpecialMesh") and decalsyeeted then
            v.TextureId=0
        elseif v:IsA("ShirtGraphic") and decalsyeeted then
            v.ShirtGraphic=1
        elseif (v:IsA("Shirt") or v:IsA("Pants")) and decalsyeeted then
            v[v.ClassName.."Template"]=1
        end
    end)
end)

function dectectballon(pos)
    for i,v in pairs(game:GetService("Workspace")["__THINGS"].BalloonGifts:GetChildren()) do
        if v:FindFirstChild('Giftbox') then
            if (getgenv().getonebloon.Position - v.Giftbox.Position).Magnitude < 10 then
                return v
            end
        end
    end
    return false
end

getgenv().ballon = nil

local oldballon
oldballon = hookmetamethod(game, "__namecall", function(self, ...)
    local args = {...}    
    if self.Name == "BalloonGifts_BalloonPopped" then
        getgenv().ballon = args[1]
    end
    return oldballon(self, ...)
end);

-- print('ere')
-- repeat wait() until game:GetService("ReplicatedStorage").Network:FindFirstChild('BalloonGifts_BalloonPopped')
-- print('asdasd')
-- game:GetService("ReplicatedStorage").Network["BalloonGifts_BalloonPopped"].OnClientEvent:Connect(function(...) 
--     local a,b = ...
--     getgenv().ballon = a
-- end)

function getchest()
    for i,v in pairs(getgenv().data) do
        if v.Id == getgenv().ballon then
            return v.LandPosition
        end
    end
    return false
end

function onehitspeed()
    local Library = require(game:GetService("ReplicatedStorage").Library)
    local Network = Library.Network
    local Balancing = Library.Balancing
    local Zones = Library.Directory.Zones
    local pets = Library.Save.Get().Inventory.Pet	
    Library.PlayerPet.CalculateSpeedMultiplier = function(...)
        return 999999999
    end
end

onehitspeed()

-- hop sv
---

function attack()
    pcall(function()
        local a = {}
        for i,v in pairs(game:GetService("Workspace")["__THINGS"].Breakables:GetChildren()) do
            for i1,v1 in pairs(v:GetChildren()) do
                if (v1.Position - game.Players.LocalPlayer.Character.HumanoidRootPart.Position).Magnitude <= 5 then
                    return v.Name
                end
            end
        end
    end)
end

game:GetService("RunService").Heartbeat:Connect(function()
	game:GetService("ReplicatedStorage").Network.Breakables_PlayerDealDamage:FireServer(attack())
end)

getgenv().getonebloon = nil

function get1on100()
    getgenv().data = game:GetService("ReplicatedStorage").Network["BalloonGifts_GetActiveBalloons"]:InvokeServer()
    if not getgenv().data[getgenv().getonebloon] then
        getgenv().getonebloon = nil
    end
    for i,v in pairs(getgenv().data) do
        if getgenv().getonebloon == nil then
            getgenv().getonebloon = v
            return
        else
            return
        end
    end
    return false
end

function havegiftbag()
    for i,v in pairs(Client.InventoryCmds.State().container._store._byType.Misc._byUID) do
        if v._data.id == 'Gift Bag' then
            if v._data._am > 500 then
                return {v._data._am, i}
            end
        end
    end
    return false
end

function havegiftbag2()
    for i,v in pairs(Client.InventoryCmds.State().container._store._byType.Misc._byUID) do
        if v._data.id == 'Large Gift Bag' then
            if v._data._am > 500 then
                return {v._data._am, i}
            end
        end
    end
    return false
end

function havegiftbag3()
    for i,v in pairs(Client.InventoryCmds.State().container._store._byType.Misc._byUID) do
        if v._data.id == 'Mini Chest' then
            if v._data._am > 50 then
                return {v._data._am, i}
            end
        end
    end
    return false
end

function getcoin()
    local a = Client.Save.Get()
    for i,v in pairs(a.Inventory.Currency) do
        if type(v) == "table" and v.id == "Diamonds" and v._am ~= nil then
            return {v._am,i}
        end
    end
    return 0
end

function collectgem()
    if havegiftbag() ~= false and getcoin()[1] > 10000 then
        getgenv().busy = true
        wait(5)
        game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame = CFrame.new(147.03858947753906, 23.593482971191406, -349.0108337402344)
        wait(2)
        local args = {
            [1] = getgenv().username,
            [2] = "quanhsendgemne",
            [3] = "Misc",
            [4] = havegiftbag()[2],
            [5] = havegiftbag()[1]
        }
        game:GetService("ReplicatedStorage").Network:FindFirstChild("Mailbox: Send"):InvokeServer(unpack(args))      
        return
    end
    if havegiftbag2() ~= false and getcoin()[1] > 10000 then
        getgenv().busy = true
        wait(5)
        game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame = CFrame.new(147.03858947753906, 23.593482971191406, -349.0108337402344)
        wait(2)
        local args = {
            [1] = getgenv().username,
            [2] = "quanhsendgemne",
            [3] = "Misc",
            [4] = havegiftbag2()[2],
            [5] = havegiftbag2()[1]
        }
        game:GetService("ReplicatedStorage").Network:FindFirstChild("Mailbox: Send"):InvokeServer(unpack(args))      
        return
    end
    if havegiftbag3() ~= false and getcoin()[1] > 10000 then
        getgenv().busy = true
        wait(5)
        game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame = CFrame.new(147.03858947753906, 23.593482971191406, -349.0108337402344)
        wait(2)
        local args = {
            [1] = getgenv().username,
            [2] = "quanhsendgemne",
            [3] = "Misc",
            [4] = havegiftbag3()[2],
            [5] = havegiftbag3()[1]
        }
        game:GetService("ReplicatedStorage").Network:FindFirstChild("Mailbox: Send"):InvokeServer(unpack(args))      
        return
    end
    getgenv().busy = false
end

function autoballon()
    if getgenv().busy == false then
        local toiuu1 = dectectballon(get1on100())
        if toiuu1 ~= false and getgenv().ballon == nil then
            game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame = CFrame.new(toiuu1.Balloon.Position) * CFrame.new(0,20,0)
            print(getgenv().getonebloon.Id)
            local args = {
                [1] = getgenv().getonebloon.Id
            }
        
            game:GetService("ReplicatedStorage").Network.BalloonGifts_BalloonHit:FireServer(unpack(args))
            local args = {
                [1] = getgenv().getonebloon.Position,
                [2] = 1.1334461712289494,
                [3] = 0.7074524422595941,
                [4] = 200
            }
            
            game:GetService("ReplicatedStorage").Network.Slingshot_FireProjectile:InvokeServer(unpack(args))
        end
        if getgenv().data[getgenv().ballon] then
            print('erere')
            game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame = CFrame.new(getgenv().data[getgenv().ballon].LandPosition)
            wait(5)
        else
            getgenv().ballon = nil
            getgenv().getonebloon = nil
            if toiuu1 == false then
            end
        end
    end
end

function dbuoi()
    for i,v in pairs(game:GetService("Workspace")["__THINGS"].Orbs:GetChildren()) do
        v.CanCollide = false
        v.CFrame = game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame + Vector3.new(0,0,0)
    end
    for i,v in pairs(game:GetService("Workspace")["__THINGS"].Lootbags:GetDescendants()) do
        if v:IsA("MeshPart") then
            v.CanCollide = false
            v.CFrame = game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame + Vector3.new(0,0,0)
        end
    end
end

function jump()
    game:GetService("VirtualInputManager"):SendKeyEvent(true, 32, false, game)
    wait(1)
    game:GetService("VirtualInputManager"):SendKeyEvent(false, 32, false, game)
end

spawn(function()
    while true do wait()
        pcall(function()
            local tickm = tick()
            repeat wait()
            until tick() - tickm >= 30
            jump()
        end)
    end
end)

spawn(function()
    while true do wait()
        local a,b = pcall(collectgem)
        print(a,b)
    end
end)

spawn(function()
    while true do wait()
        pcall(dbuoi)
        if game:GetService("Players").LocalPlayer.PlayerGui["_MISC"].Slingshot.Enabled == false then
            game:GetService("ReplicatedStorage").Network.Slingshot_Toggle:InvokeServer()
        end
    end
end)

spawn(function()
    while true do wait(60)
        if game:GetService("Players").LocalPlayer.PlayerGui["_MISC"].Slingshot.Enabled == true then
            game:GetService("ReplicatedStorage").Network.Slingshot_Toggle:InvokeServer()
        end
    end
end)

spawn(function()
    while true do wait()
        pcall(function()
            local Client = require(game.ReplicatedStorage.Library.Client)
            local a = Client.Save.Get()
            for i,v in pairs(a.HiddenPresents) do
                local args = {
                    [1] = v.ID
                }
                
                game:GetService("ReplicatedStorage").Network:FindFirstChild("Hidden Presents: Found"):InvokeServer(unpack(args))
                wait(2)
            end
        end)
    end
end)

while true do task.wait()
    local a,b = pcall(autoballon)
end
