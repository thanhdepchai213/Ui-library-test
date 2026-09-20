local API_URL = "https://rise-evo.xyz"
local KEY_FILE = "riseapi_checkkey.txt"

local UserInputService = game:GetService("UserInputService")
local TweenService = game:GetService("TweenService")
local RunService = game:GetService("RunService")
local CoreGui = game:GetService("CoreGui")
local HttpService = game:GetService("HttpService")
local Debris = game:GetService("Debris")
local StarterGui = game:GetService("StarterGui")
local Players = game:GetService("Players")
local LocalPlayer = Players.LocalPlayer

local function LoadMainScript()

print("\115\116\97\114\116")
if not game:IsLoaded() then game.Loaded:Wait() end
bet = game.PlaceId
SeaPlaceIds = {
    Sea1 = {
        [2753915549] = true,
        [85211729168715] = true
    },
    Sea2 = {
        [4442272183] = true,
        [79091703265657] = true
    },
    Sea3 = {
        [7449423635] = true,
        [100117331123089] = true
    },
    Sea4 = {
        [73902483975735] = true
    }
}

sea1 = SeaPlaceIds.Sea1[bet] == true
sea2 = SeaPlaceIds.Sea2[bet] == true
sea3 = SeaPlaceIds.Sea3[bet] == true
sea4 = SeaPlaceIds.Sea4[bet] == true
DungeonPlaceId = 73902483975735


getgenv().Team = getgenv().Team and (getgenv().Team == "Marines" or getgenv().Team == "Pirates") and getgenv().Team or "Marines"
wait(0.2)
for i, v in pairs(LocalPlayer.PlayerGui:GetChildren()) do
    if v:FindFirstChild("ChooseTeam") then
        local thua = v.ChooseTeam.Container[getgenv().Team].Frame.TextButton
        firesignal(thua.Activated)
    end
end

local lib1 = "https://rise-evo.xyz/apiv3/NotifyLib.lua"
local hopui = "https://rise-evo.xyz/apiv3/HopUi.lua"
local md = "https://rise-evo.xyz/apiv3/module-bf.lua"
local ex1 = "https://rise-evo.xyz/apiv3/lib_1click.lua"
local ex2 = "https://rise-evo.xyz/apiv3/hook-eff.lua"
local ex3 = "https://rise-evo.xyz/apiv3/attack-module.lua"
local netw = "https://rise-evo.xyz/apiv3/module-network.lua"
local boost = "https://rise-evo.xyz/apiv3/fpsboost-module.lua"

function safe_it(bet)
    local gud, saywhat = pcall(game.HttpGet, game, bet)
    if gud then
        local func, idk = loadstring(saywhat)
        if func then return func() end
        print("hello")
    else
        print("ok")
    end
end


safe_it(md)
bf_md = safe_it(md)
notifyrise = safe_it(lib1)
lib2 = safe_it(hopui)
network = safe_it(netw)
hui = safe_it(lib2)
print("bruh")
plr = game.Players
lp = plr.LocalPlayer
pdata = lp.Data
worigin = workspace["_WorldOrigin"]
vim = game:GetService('VirtualInputManager')
cs = game:GetService("CollectionService")
rs = game:GetService("ReplicatedStorage")
runse = game:GetService("RunService")
uis = game:GetService("UserInputService")
wene = workspace.Enemies

print("die")

local MatData = {
    ["Radioactive"] = {mon = {"Factory Staff"}, pos = CFrame.new(-508, 73, -126)},
    ["Mystic Droplet"] = {mon = {"Water Fighter"}, pos = CFrame.new(-3353, 285, -10535)},
    ["Magma Ore"] = {
        [1] = {mon = {"Military Spy"}, pos = CFrame.new(-5850, 77, 8849)},
        [2] = {mon = {"Lava Pirate"}, pos = CFrame.new(-5235, 52, -4732)}
    },
    ["Angel Wings"] = {mon = {"Royal Soldier"}, pos = CFrame.new(-7827, 5607, -1706)},
    ["Leather"] = {
        [1] = {mon = {"Pirate"}, pos = CFrame.new(-1212, 5, 3917)},
        [2] = {mon = {"Marine Captain"}, pos = CFrame.new(-2011, 73, -3327)},
        [3] = {mon = {"Jungle Pirate"}, pos = CFrame.new(-11976, 332, -10620)}
    },
    ["Ectoplasm"] = {mon = {"Ship Deckhand", "Ship Engineer", "Ship Steward", "Ship Officer"}, pos = CFrame.new(911, 126, 33160)},
    ["Scrap Metal"] = {
        [1] = {mon = {"Brute"}, pos = CFrame.new(-1132, 15, 4293)},
        [2] = {mon = {"Mercenary"}, pos = CFrame.new(-972, 73, 1419)},
        [3] = {mon = {"Pirate Millionaire"}, pos = CFrame.new(-290, 44, 5584)}
    },
    ["Conjured Cocoa"] = {mon = {"Chocolate Bar Battler"}, pos = CFrame.new(745, 25, -12638)},
    ["Dragon Scale"] = {mon = {"Dragon Crew Warrior"}, pos = CFrame.new(5824, 51, -1107)},
    ["Gunpowder"] = {mon = {"Pistol Billionaire"}, pos = CFrame.new(-380, 74, 5929)},
    ["Fish Tail"] = {mon = {"Fishman Captain"}, pos = CFrame.new(-10961, 332, -8914)},
    ["Mini Tusk"] = {mon = {"Mithological Pirate"}, pos = CFrame.new(-13516, 470, -6899)}
}
print("aight")

local races_trial_place = {
    ["Human"] = worigin.Locations:FindFirstChild("Trial of Strength"),
    ["Mink"] = worigin.Locations:FindFirstChild("Trial of Speed"),
    ["Fishman"] = worigin.Locations:FindFirstChild("Trial of Water"),
    ["Skypiea"] = worigin.Locations:FindFirstChild("Trial of the King"),
    ["Ghoul"] = worigin.Locations:FindFirstChild("Trial of Carnage"),
    ["Cyborg"] = worigin.Locations:FindFirstChild("Trial of the Machine"),
    ["Draco"] = worigin.Locations:FindFirstChild("Trial of Flames")
}
print("fuck")

local race_abilities = {
    ["Human"] = "Last Resort",
    ["Mink"] = "Agility",
    ["Fishman"] = "Water Body",
    ["Skypiea"] = "Heavenly Blood",
    ["Ghoul"] = "Heightened Senses",
    ["Cyborg"] = "Energy Core",
    ["Draco"] = "Primordial Reign"
}
print("wtf")

local pos_plr_trial = {
    CFrame.new(28692, 14888, -54),
    CFrame.new(28783, 14899, -60),
    CFrame.new(28701, 14888, -154),
    CFrame.new(28796, 14888, -113),
    CFrame.new(28658, 14888, -121),
    CFrame.new(28742, 14888, -18)
}

print("okkkk")

local IslandData = {
    --sea1
    ["WindMill"] = {pos = CFrame.new(980, 17, 1429), sea = 1},
    ["Marine"] = {pos = CFrame.new(-2566, 7, 2045), sea = 1},
    ["Middle Town"] = {pos = CFrame.new(-690, 15, 1582), sea = 1},
    ["Jungle"] = {pos = CFrame.new(-1613, 37, 149), sea = 1},
    ["Pirate Village"] = {pos = CFrame.new(-1181, 5, 3804), sea = 1},
    ["Desert"] = {pos = CFrame.new(944, 21, 4373), sea = 1},
    ["Snow Island"] = {pos = CFrame.new(1348, 105, -1320), sea = 1},
    ["MarineFord"] = {pos = CFrame.new(-4915, 51, 4281), sea = 1},
    ["Colosseum"] = {pos = CFrame.new(-1428, 7, -2793), sea = 1},
    ["Sky Island 1"] = {pos = CFrame.new(-4869, 733, -2667), sea = 1},
    ["Prison"] = {pos = CFrame.new(4875, 6, 735), sea = 1},
    ["Magma Village"] = {pos = CFrame.new(-5248, 13, 8505), sea = 1},
    ["Under Water"] = {pos = CFrame.new(61164, 12, 1820), sea = 1},
    ["Fountain City"] = {pos = CFrame.new(5127, 60, 4105), sea = 1},
    -- sea2
    ["The Cafe"] = {pos = CFrame.new(-380, 77, 256), sea = 2},
    ["Dark Area"] = {pos = CFrame.new(3780, 23, -3499), sea = 2},
    ["Flamingo Mansion"] = {pos = CFrame.new(-484, 332, 595), sea = 2},
    ["Green Zone"] = {pos = CFrame.new(-2449, 73, -3211), sea = 2},
    ["Factory"] = {pos = CFrame.new(424, 211, -428), sea = 2},
    ["Zombie Island"] = {pos = CFrame.new(-5622, 492, -782), sea = 2},
    ["Snow Mountain"] = {pos = CFrame.new(753, 408, -5275), sea = 2},
    ["Cursed Ship"] = {pos = CFrame.new(923, 125, 32886), sea = 2},
    ["Ice Castle"] = {pos = CFrame.new(6148, 294, -6741), sea = 2},
    ["Forgotten Island"] = {pos = CFrame.new(-3033, 318, -10075), sea = 2},
    --sea3
    ["Port Town"] = {pos = CFrame.new(-291, 7, 5344), sea = 3},
    ["Hydra Island"] = {pos = CFrame.new(5747, 668, -274), sea = 3},
    ["Floating Turtle"] = {pos = CFrame.new(-13275, 532, -7579), sea = 3},
    ["Mansion"] = {pos = CFrame.new(-12471, 375, -7552), sea = 3},
    ["Haunted Castle"] = {pos = CFrame.new(-9515, 164, 5786), sea = 3},
    ["Ice Cream Island"] = {pos = CFrame.new(-903, 80, -10989), sea = 3},
    ["Cake Island"] = {pos = CFrame.new(-1885, 19, -11667), sea = 3},
    ["Tiki Outpost"] = {pos = CFrame.new(-16101, 13, 381), sea = 3}
}
local MySea = sea1 and 1 or (sea2 and 2 or 3)
local AvailableIslands = {}
for name, data in pairs(IslandData) do
    if data.sea == MySea then
        table.insert(AvailableIslands, name)
    end
end
table.sort(AvailableIslands)

print("pass")

function say(mo, ok, howlong)
    if notifyrise and notifyrise.Notify then
        notifyrise.Notify(mo or "SYSTEM", ok, howlong or 5)
    else
        print("delete hub pls" .. tostring(ok))
    end
end
say("SYSTEM", "Inlitizing.....", 5)--test

--[[rejoin = function()
    game:GetService("TeleportService"):TeleportToPlaceInstance(game.PlaceId,game.JobId,lp)
end

task.delay(20,function()
  if not lp.Team then
    rejoin()
  end
end)]]

getdis = function (...)
	return bf_md:getdis(...)
end

if not LPH_OBFUSCATED then
	LPH_JIT = (function(...) return ... end)
	LPH_JIT_MAX = (function(...) return ... end)
	LPH_NO_VIRTUALIZE = (function(...) return ... end)
	LPH_NO_UPVALUES = (function(...) return ... end)
end

lp.PlayerScripts["CHECKDMG[DEBUG]"].Disabled = true

function Convert_To_CFrame(value)
	if typeof(value) == "Vector3" then
		return CFrame.new(value)
	elseif typeof(value) == "CFrame" then
		return value
	else
		return nil
	end
end

CommF_ = LPH_JIT_MAX(function(...)
	local ARGS = {...}
	local Data = network:Send("CommF_",...)
	local r,s = pcall(function()
		if ARGS[1] == "requestEntrance" then
			cs:AddTag(lp,"Teleporting")
			task.delay(3,function()
				cs:RemoveTag(lp,"Teleporting")
			end)
			wait(.25)
		end
	end)
	if not r then warn("Remote : "..s) end
	return Data
end)

--[[local HttpService = game:GetService("HttpService")
local Player = game.Players.LocalPlayer
local FolderName = "RisiHub_BloxFruit"
local FileName = FolderName .. "/" .. Player.Name .. ".json"
_G.ConfigData = _G.ConfigData or {}
setmetatable(_G, {
    __newindex = function(t, key, value)
        rawset(t, key, value)
        if type(value) == "boolean" or type(value) == "number" or type(value) == "string" then
            if type(key) == "string" and key ~= "ConfigData" then
                _G.ConfigData[key] = value
            end
        end
    end
})

_G.SaveSetting = function()
    local hasData = false
    for _ in pairs(_G.ConfigData) do hasData = true break end
    if not hasData then 
        warn("data not found") 
        return 
    end
    local success, str = pcall(function()
        if not isfolder(FolderName) then makefolder(FolderName) end
        return HttpService:JSONEncode(_G.ConfigData)
    end)
    if success then
        writefile(FileName, str)
    else
        warn("ecd er" .. tostring(str))
    end
end
_G.LoadSetting = function()
    if isfile(FileName) then
        local success, decoded = pcall(function()
            return HttpService:JSONDecode(readfile(FileName))
        end)
        if success and type(decoded) == "table" then
            for key, value in pairs(decoded) do
                _G.ConfigData[key] = value
                rawset(_G, key, value)
            end
            print("cf loadded f")
        end
    end
end]]

local HttpService = game:GetService("HttpService")
local folderMain = "Rise Evo"
local folderSub = "Rise Evo/lpdata"
local fileName = folderSub .. "/" .. lp.Name .. "_data.json"
if not isfolder(folderMain) then makefolder(folderMain) end
if not isfolder(folderSub) then makefolder(folderSub) end
function read_mastery(meleeName)
    local data = {
        ["Dark Step"] = 0,
        ["Electric"] = 0,
        ["Water Kung Fu"] = 0,
        ["Dragon Breath"] = 0,
        ["Superhuman"] = 0,
        ["Death Step"] = 0,
        ["Sharkman Karate"] = 0,
        ["Electric Claw"] = 0,
        ["Dragon Talon"] = 0
    }
    
    if isfile(fileName) then
        local success, decoded = pcall(function() return HttpService:JSONDecode(readfile(fileName)) end)
        if success then data = decoded end
    end
    
    return data[meleeName] or 0
end

function save_mastery(idk)
    local hellobeach = 0
    local tool = lp.Character:FindFirstChild(idk) or lp.Backpack:FindFirstChild(idk) 
    if tool and tool:FindFirstChild("Level") then
        hellobeach = tool.Level.Value
    end
    local data = {}
    if isfile(fileName) then
        pcall(function() data = HttpService:JSONDecode(readfile(fileName)) end)
    end
    data[idk] = hellobeach
    writefile(fileName, HttpService:JSONEncode(data))
    print("save " .. idk .. ": " .. hellobeach)
end

Is_player_ready = LPH_JIT_MAX(function()
	return lp.Character and lp.Character:FindFirstChild("Humanoid") and lp.Character:FindFirstChild("HumanoidRootPart") and lp.Character:FindFirstChild("Humanoid").Health > 0
end)

Is_raiding = LPH_JIT_MAX(function()
	return lp.PlayerGui.Main.TopHUDList.RaidTimer.Visible or StartingRaid
end)

Check_raid_chip = LPH_JIT_MAX(function()
	local function Has_chip(container)
		for _, item in ipairs(container:GetChildren()) do
			if item:IsA("Tool") and item.Name:lower():find("microchip") then
				return true
			end
		end
		return false
	end
	return Has_chip(lp.Backpack) or Has_chip(lp.Character)
end)

Check_Fruit = LPH_JIT_MAX(function() 
	for i,v in pairs(workspace:GetChildren()) do
		if v.Name:find("Fruit") and v:FindFirstChild("Handle") then
			return true
		end
	end
	return false
end)

Check_fruit_inventory = LPH_JIT_MAX(function()
	local function hasFruit(container)
		for _, item in ipairs(container:GetChildren()) do
			if item:IsA("Tool") and item.Name:lower():find("fruit") then
				return true
			end
		end
		return false
	end
	return hasFruit(lp.Backpack) or hasFruit(lp.Character)
end)

Is_Safe_Zone = LPH_JIT_MAX(function(p)
	for i,v in pairs(worigin.SafeZones:GetChildren()) do
		if v:IsA("Part") then
			if Distance(v.Position, p.HumanoidRootPart.Position, true) <= 1000 then
				return true
			end
		end
	end
	return false
end)

function StopTween()
	if activeTween and activeTween.PlaybackState == Enum.PlaybackState.Playing then
		activeTween:Cancel()
		activeTween = nil
	end
end
local function okeybae(char, state)
    if not char then return end
    for _, p in pairs(char:GetDescendants()) do
        if p:IsA("BasePart") then 
            p.CanCollide = state 
        end
    end
end

function CheckBackpack(v)
	return lp.Backpack:FindFirstChild(v) or lp.Character:FindFirstChild(v)
end

checkmastery = LPH_JIT_MAX(function(Tool,Mastery)
	local Character_Tool = lp.Character:FindFirstChild(Tool)
	if Character_Tool and Character_Tool:IsA('Tool') and Character_Tool:FindFirstChild("Level") and Character_Tool.Level.Value >= Mastery then
		return true
	end
	local Backpack_Tool = lp.Backpack:FindFirstChild(Tool)
	if Backpack_Tool and Backpack_Tool:IsA('Tool') and Backpack_Tool:FindFirstChild("Level") and Backpack_Tool.Level.Value >= Mastery then
		return true
	end
	return false
end)

Distance = LPH_JIT_MAX(function(a, b, noHeight)
	local vector_a = Vector3.new(a.X, not noHeight and a.Y or 0, a.Z)
	local success, result = pcall(function()
		if not b then
			while true do
				local Root = lp.Character and lp.Character:FindFirstChild("HumanoidRootPart")
				if Root and Root.Position then
					b = Root.Position
					break
				end
				wait(.5) 
			end
		end
		local vector_b = Vector3.new(b.X, not noHeight and b.Y or 0, b.Z)
		return (vector_a - vector_b).magnitude
	end)
	if success then
		return result
	else
		warn("Distance Calculation Failed", result)
		return nil
	end
end)

FindNearestLocation = LPH_JIT_MAX(function(Pos, Location)
	local nearest, scale = nil, 0
	if Location then
		if Distance(Pos, Location.Position, true) <= (Location.Mesh.Scale.X / 2) + 500 then
			return Location
		end
	end
	for i, v in pairs(WorldOrigin.Locations:GetChildren()) do
		if Distance(Pos, v.Position, true) <= (v.Mesh.Scale.X / 2) + 500 then
			if scale < v.Mesh.Scale.X then
				scale = v.Mesh.Scale.X
				nearest = v
			end
		end
	end
	return nearest
end)

local TweenService = game:GetService("TweenService")
local lastTPTime, recentlySpawn = tick(), 0
local currentTween = nil

old_tp = LPH_JIT_MAX(function(...)
    local target = Convert_To_CFrame(...)
    if not target or not Is_player_ready() then return end
    local char = lp.Character
    local root = char:FindFirstChild("HumanoidRootPart")
    local hum = char:FindFirstChildOfClass("Humanoid")
    if not root or not hum or hum.Health <= 0 then return end
    
    lastTPTime = tick()
    local currentDist = (target.p - root.Position).Magnitude

    if currentDist >= 1500 and (tick() - recentlySpawn) > 15 and not Is_raiding() then
        local items = {"God's Chalice", "Red Key", "Apple", "Banana", "Pineapple", "Flower 1", "Flower 2", "Flower 3", "Sweet Chalice"}
        if not Check_raid_chip() and not Check_fruit_inventory() and not Check_Inventory(unpack(items)) then
            local worigin = workspace:FindFirstChild("_WorldOrigin") or workspace:FindFirstChild("WorldOrigin")
            local teamSpawns = worigin and worigin:FindFirstChild("PlayerSpawns") and worigin.PlayerSpawns:FindFirstChild(lp.Team.Name)
            if teamSpawns then
                local bDist, bSpawn = math.huge, nil
                for _, v in pairs(teamSpawns:GetChildren()) do
                    local d = (target.p - v:GetPivot().p).Magnitude
                    if d < bDist then bDist, bSpawn = d, v end
                end
                if bSpawn and bDist < 1000 and bDist < currentDist - 500 then
                    local lso = lp:FindFirstChild("LastSpawnPoint") or (lp:FindFirstChild("Data") and lp.Data:FindFirstChild("LastSpawnPoint"))
                    if lso then
                        if currentTween then currentTween:Cancel() end
                        tweenActive = false
                        task.spawn(function()
                            for i = 1, 5 do
                                pcall(function() CommF_("SetLastSpawnPoint", bSpawn.Name) end)
                                if lso.Value == bSpawn.Name then hum.Health = 0 recentlySpawn = tick() break end
                                task.wait(0.2)
                            end
                        end)
                        if lso.Value == bSpawn.Name then return end
                    end
                end
            end
        end
    end

    if lastTweenTarget and (target.p - lastTweenTarget.p).Magnitude < 0.1 and tweenActive then return end
    if currentTween then currentTween:Cancel() end

    if math.abs(root.Position.Y - target.Y) > 1.5 then
        root.CFrame = CFrame.new(root.Position.X, target.Y, root.Position.Z)
    end
    
    local d_final = (target.p - root.Position).Magnitude
    if d_final < 300 then root.CFrame = target return end

    tweenActive = true
    okeybae(char, false)
    local bv = root:FindFirstChild("risefanboi") or Instance.new("BodyVelocity")
    bv.Name, bv.MaxForce, bv.Velocity, bv.Parent = "risefanboi", Vector3.new(1e6, 1e6, 1e6), Vector3.zero, root

    lastTweenTarget = target
    currentTween = TweenService:Create(root, TweenInfo.new(d_final / 350, Enum.EasingStyle.Linear), {CFrame = target})
    currentTween:Play()

    if not _G.CleaningMonitor then
        _G.CleaningMonitor = true
        task.spawn(function()
            while _G.CleaningMonitor do
                if tick() - lastTPTime > 2 or not lp.Character or not lp.Character:FindFirstChild("Humanoid") or lp.Character.Humanoid.Health <= 0 then
                    if currentTween then currentTween:Cancel() end
                    local r = lp.Character and lp.Character:FindFirstChild("HumanoidRootPart")
                    if r and r:FindFirstChild("risefanboi") then r.risefanboi:Destroy() end
                    if lp.Character then okeybae(lp.Character, true) end
                    tweenActive, _G.CleaningMonitor = false, false
                    break
                end
                task.wait(0.5)
            end
        end)
    end
end)

function getdis(a, b)
    local char = lp.Character
    local hrp = char and char:FindFirstChild("HumanoidRootPart")
    if not hrp then return 9e9 end
    b = b or hrp.CFrame.Position
    local _a = Vector3.new(a.X, b.Y, a.Z)
    return (_a - b).Magnitude
end

function Check_Tool_Remote(Name)
            Remote_Inventory = CommF_("getInventory")
            for i, v in pairs(Remote_Inventory) do
                if v.Name == Name then
                    return true
                end
            end
          return false
        end
        
local newdao = CFrame.new(10641.0918, -1953.92981, 9825.07031)
local cframenpc = CFrame.new(-16271.126, 25.5847301, 1371.98755)
TableLocations = {} 

Locations = {
    sea1 = function()
        return {
            ["FishmanSea1"]  = workspace.Map.TeleportSpawn.EntrancePoint.Position,
            ["Island Sky 2"] = workspace.Map.SkyArea2.PathwayHouse.EntrancePoint.Position,
            ["Island Sky 1"] = workspace.Map.SkyArea1.PathwayTemple.ExitPoint.Position,
        }   
    end,
    sea2 = function()
        return {
            ["CaFe"] = Vector3.new(-288, 305, 613),
            ["Swan Room"] = Vector3.new(2284, 15, 897),
            ["Ghost ShipInterior"] = workspace.Map.GhostShipInterior.TeleportSpawn.Position,
            ["OutGhost ShipInterior"] = Vector3.new(-6518, 83, -145),
        }
    end,        
    sea3 = {
        Helm = {
            ["Castle On The Sea"] = Vector3.new(-5058, 314, -3155),
            ["Mansion"] = Vector3.new(-12463, 374, -7523),
        }
    }
}
if sea3 then
    TableLocations = {}
    if Check_Tool_Remote("Valkyrie Helm") then
        if Locations.sea3 and Locations.sea3.Helm then
            for k, v in pairs(Locations.sea3.Helm) do
                TableLocations[k] = v
            end
        end
    end
elseif sea1 then
    TableLocations = Locations.sea1()
else
    TableLocations = Locations.sea2()
end

function GetPortal(x)
    local Max, Choose = math.huge, Vector3.new(0, 0, 0)
    local IslandName
    if TableLocations and next(TableLocations) then
        for k, v in pairs(TableLocations) do
            if (v - x.Position).Magnitude <= Max then
                Max = (v - x.Position).Magnitude
                Choose = v
                IslandName = k
            end
        end
    end
    return Choose, IslandName
end

function TP(pos, ...)
    local targetCf = (typeof(pos) == "CFrame" and pos) or CFrame.new(pos)
    local targetPos = targetCf.Position
    local root = lp.Character and lp.Character:FindFirstChild("HumanoidRootPart")
    if root then
        local dist = (targetPos - root.Position).Magnitude
        if dist < 250 then
            if root:FindFirstChild("risefanboi") then root.risefanboi:Destroy() end
            if currentTween then currentTween:Cancel() end
            if lp.Character then
                for _, p in pairs(lp.Character:GetDescendants()) do
                    if p:IsA("BasePart") then p.CanCollide = true end
                end
            end
            root.CFrame = targetCf
            return
        end
    end
    local Dich, Name = GetPortal(pos)            
    if Dich and Dich ~= Vector3.new(0,0,0) then
        if (Dich - targetPos).Magnitude + 250 <= (targetPos - root.Position).Magnitude and (targetPos - root.Position).Magnitude >= 3000 then
            if currentTween then
                currentTween:Pause() 
                currentTween:Cancel()
            end
            CommF_("requestEntrance", Dich) 
            task.wait(1)
            return 
        end
    end
    if sea3 and newdao and getdis(targetPos, newdao.Position) < 2000 then
        if root and math.abs(newdao.Y - root.CFrame.Y) > 1000 then
            repeat
                task.wait()
                if old_tp then old_tp(cframenpc, function() return true end, true) end               
                if getdis(cframenpc) < 15 then
                    local net = game:GetService("ReplicatedStorage").Modules.Net
                    if net:FindFirstChild("RF/SubmarineWorkerSpeak") then
                        net["RF/SubmarineWorkerSpeak"]:InvokeServer("AskKilledTikiBoss")
                        task.wait(0.5)
                        net["RF/SubmarineWorkerSpeak"]:InvokeServer("TravelToSubmergedIsland")
                    end
                end
            until getdis(targetPos) < 2000
            task.wait(0.6)
            pcall(function() if root:FindFirstChild("BodyClip") then root.BodyClip:Destroy() end end)
        end
    end
    if old_tp then return old_tp(pos, ...) end
end


--[[function TP(pos, ...)
    local Dich, Name = GetPortal(pos)            
    if Dich and Dich ~= Vector3.new(0,0,0) then
        if (Dich - pos.Position).Magnitude + 250 <= (pos.Position - lp.Character.HumanoidRootPart.Position).Magnitude and (pos.Position - lp.Character.HumanoidRootPart.Position).Magnitude >= 3000 then
            if currentTween then
                currentTween:Pause() 
                currentTween:Cancel()
            end
            CommF_("requestEntrance", Dich) 
            task.wait(1)
            return 
        end
    end
    if sea3 and getdis(pos, newdao.Position) < 2000 then
        local hrp = lp.Character and lp.Character:FindFirstChild("HumanoidRootPart")
        if hrp and math.abs(newdao.Y - hrp.CFrame.Y) > 1000 then
            repeat
                task.wait()
                if old_tp then old_tp(cframenpc, function() return true end, true) end               
                if getdis(cframenpc) < 15 then
                    local net = game:GetService("ReplicatedStorage").Modules.Net
                    net["RF/SubmarineWorkerSpeak"]:InvokeServer("AskKilledTikiBoss")
                    task.wait(0.5)
                    net["RF/SubmarineWorkerSpeak"]:InvokeServer("TravelToSubmergedIsland")
                end
            until getdis(pos) < 2000
            task.wait(0.6)
            pcall(function() if hrp:FindFirstChild("BodyClip") then hrp.BodyClip:Destroy() end end)
        end
    end
    if old_tp then return old_tp(pos, ...) end
    return print("fuck")
end]]



Check_Monster = LPH_JIT_MAX(function(Monster)
    local Table_Monster = (type(Monster) == "string") and {Monster} or Monster
    local nearestEnemy = nil
    local shortestDistance = math.huge
    for _, v in pairs(workspace.Enemies:GetChildren()) do
        if table.find(Table_Monster, v.Name) and Check_Alive_Monster(v) then
            local success, dist = pcall(function() return Distance(v.HumanoidRootPart.Position) end)       
            if success and dist < shortestDistance then
                nearestEnemy = v
                shortestDistance = dist
            end
        end
    end
    if not nearestEnemy then
        for _, v in pairs(game:GetService("ReplicatedStorage"):GetChildren()) do
            if table.find(Table_Monster, v.Name) and v:FindFirstChild("HumanoidRootPart") then
                nearestEnemy = v
                break 
            end
        end
    end
    return nearestEnemy
end)
Check_Alive_Monster = LPH_JIT_MAX(function(Mon)
	return Mon and Mon.Parent and Mon:FindFirstChild("Humanoid") and Mon:FindFirstChild("HumanoidRootPart") and Mon:FindFirstChild("Humanoid").Health > 0
end)
local HttpService = game:GetService("HttpService")
local TeleportService = game:GetService("TeleportService")
local Players = game:GetService("Players")
local lp = Players.LocalPlayer
local pi = game.PlaceId

local CFHop = {
    MaxPlayers = 9,
    SortOrder = "Asc"
}
local isHopping = false 
function Server_Hop(Reason)
    if isHopping then return end 
    isHopping = true 
    local function FindAndHop()
        local Cursor = ""
        while isHopping do
            local URL = string.format(
                "https://games.roblox.com/v1/games/%s/servers/Public?sortOrder=%s&limit=100&excludeFullGames=true", 
                pi, CFHop.SortOrder
            )
            if Cursor ~= "" then URL = URL .. "&cursor=" .. Cursor end    
            local Success, Result = pcall(function()
                return HttpService:JSONDecode(game:HttpGet(URL))
            end)
            if Success and Result and Result.data then
                local Candidates = {}
                for _, Server in ipairs(Result.data) do
                    if typeof(Server) == "table" and Server.playing <= CFHop.MaxPlayers and Server.id ~= game.JobId then
                        if Server.ping and Server.ping < 100 then
                            table.insert(Candidates, Server)
                        end
                    end
                end
                if #Candidates == 0 then
                    for _, Server in ipairs(Result.data) do
                        if Server.playing <= CFHop.MaxPlayers and Server.id ~= game.JobId then
                            table.insert(Candidates, Server)
                        end
                    end
                end
                if #Candidates > 0 then
                    table.sort(Candidates, function(a, b) return (a.ping or 999) < (b.ping or 999) end)
                    local Target = Candidates[1]
                    if hui and hui.ServerHop then
                        local pingText = (Target.ping and Target.ping .. "ms") or "N/A"
                        hui.ServerHop("Singapore (" .. pingText .. ")", "Players: " .. Target.playing .. "/" .. Target.maxPlayers)
                    end

                    task.wait(0.5)
                    local s, err = pcall(function()
                        TeleportService:TeleportToPlaceInstance(pi, Target.id, lp)
                    end)
                    if not s then 
                        task.wait(1)
                    end
                else
                    if Result.nextPageCursor then
                        Cursor = Result.nextPageCursor
                    else
                        Cursor = ""
                    end
                end
            end
            task.wait(1)
        end
    end
    task.spawn(function()
        local s, e = pcall(FindAndHop)
        if not s then 
            warn("Hop Error: " .. tostring(e))
            isHopping = false
            task.wait(2)
            Server_Hop("Retrying...") 
        end
    end)
end


--attack func
--[[local _vm3 = 30 
local OrbitDistance = 30 
local OrbitSpeed = 5
local SpeedTween = 315
local OrbitThreshold = 50 
local Target_Mon = nil  
local VeriSign = false  

runse.Heartbeat:Connect(function(dt)
    local char = lp.Character
    local root = char and char:FindFirstChild("HumanoidRootPart")
    local hum = char and char:FindFirstChildOfClass("Humanoid")
    if VeriSign and Target_Mon and Target_Mon:FindFirstChild("HumanoidRootPart") and root and hum then
        local mobPos = Target_Mon.HumanoidRootPart.Position
        local currentPos = root.Position
        local dist = (mobPos - currentPos).Magnitude
        hum.PlatformStand = true 
        hum.AutoRotate = false
        hum:ChangeState(Enum.HumanoidStateType.Physics)
        root.Velocity = Vector3.new(0,0,0)
        root.RotVelocity = Vector3.new(0,0,0)
        local angle = tick() * OrbitSpeed
        local x = math.cos(angle) * OrbitDistance
        local z = math.sin(angle) * OrbitDistance
        local desiredOrbitPos = mobPos + Vector3.new(x, _vm3, z)
        if dist > OrbitThreshold then
            local direction = (desiredOrbitPos - currentPos).Unit
            root.CFrame = CFrame.lookAt(currentPos + (direction * SpeedTween * dt), mobPos)
        else
            local horizontalLook = Vector3.new(mobPos.X, desiredOrbitPos.Y, mobPos.Z)
            local baseCFrame = CFrame.lookAt(desiredOrbitPos, horizontalLook)
            root.CFrame = baseCFrame * CFrame.Angles(math.rad(-45), 0, 0)
        end
        for _, v in pairs(char:GetDescendants()) do
            if v:IsA("BasePart") then v.CanCollide = false end
        end
        local bv = root:FindFirstChild("risefanboi") or Instance.new("BodyVelocity")
        bv.Name = "risefanboi"
        bv.MaxForce = Vector3.new(1e6, 1e6, 1e6)
        bv.Velocity = Vector3.new(0, 0, 0)
        bv.Parent = root
    else
        if hum then
            hum.PlatformStand = false
            hum.AutoRotate = true
            local bv = root and root:FindFirstChild("risefanboi")
            if bv then bv:Destroy() end
        end
    end
end)]]
Check_Inventory = LPH_JIT_MAX(function(...)
   toolsToCheck = {...}
	for _, toolName in pairs(toolsToCheck) do
		if lp.Backpack:FindFirstChild(toolName) or lp.Character:FindFirstChild(toolName) then
			return true
		end
	end
	return false
end)

--[[task.spawn(function()
	local weaponToolTipMap = {
		["Melee"] = "Melee",
		["Sword"] = "Sword",
		["Devil Fruit"] = "Blox Fruit"
	}
	while task.wait(0.5) do
		for _, tool in pairs(lp.Backpack:GetChildren()) do
			local weaponToolTip = weaponToolTipMap[Weapon or "Melee"]
			if weaponToolTip and tool.ToolTip == weaponToolTip and Check_Inventory(tool.Name) then
				Current_Weapon = tool.Name
				break
			end
		end
	end
end)]]

Attack = LPH_JIT_MAX(function(Mon, Statement)
    local Statement = Statement or function() return false end
    local names = type(Mon) == "table" and Mon or {Mon.Name}    
    pcall(function()
        while task.wait() do
            if Statement() then break end       
            local target, dist = nil, math.huge
            for _, v in ipairs(workspace.Enemies:GetChildren()) do
                if table.find(names, v.Name) and v:FindFirstChild("HumanoidRootPart") and v:FindFirstChild("Humanoid") and v.Humanoid.Health > 0 then
                    local d = (v.HumanoidRootPart.Position - lp.Character.HumanoidRootPart.Position).Magnitude
                    if d < dist then
                        dist = d
                        target = v
                    end
                end
            end
            if not target then break end
            repeat task.wait()
                if not Check_Alive_Monster(target) or Statement() then break end
                local mobPos = target.HumanoidRootPart.Position
                local targetCFrame = CFrame.new(mobPos.X, mobPos.Y + 40, mobPos.Z)
                bf_md:eq()
                if bf_md and bf_md.haki then bf_md:haki() end
                TP(targetCFrame)
                local currentDist = (target.HumanoidRootPart.Position - lp.Character.HumanoidRootPart.Position).Magnitude
                if currentDist > 150 then break end
            until not Check_Alive_Monster(target) or Statement()
        end
    end)
end)

--[[Attack = LPH_JIT_MAX(function(Mon, Statement)
    local Statement = Statement or function() return false end
    pcall(function()
        if Check_Alive_Monster(Mon) and Mon:FindFirstChild("HumanoidRootPart") then
            repeat task.wait()
                if not Check_Alive_Monster(Mon) or Statement() then break end                     
                local mobPos = Mon.HumanoidRootPart.Position
                local targetCFrame = CFrame.new(mobPos) * CFrame.new(0,40,0)
                TP(targetCFrame)
                --if Current_Weapon and Check_Inventory(Current_Weapon) then
                    --Equip_Tool(Current_Weapon)
                --end
                if bf_md and bf_md.haki then bf_md:haki() end
            until not Check_Alive_Monster(Mon) or Statement()
        end
    end)
end)]]

safe_it(ex3)

local Players = game:GetService("Players")
local lp = Players.LocalPlayer
local stabilized = {}

local function antiKnockback(hrp)
    if hrp then
        hrp.AssemblyLinearVelocity = Vector3.zero
        hrp.AssemblyAngularVelocity = Vector3.zero
    end
end

local function stabilizeMob(mob)
    if stabilized[mob] then return end
    
    local hrp = mob:FindFirstChild("HumanoidRootPart")
    local hum = mob:FindFirstChild("Humanoid")
    if not hrp or not hum then return end
    
    stabilized[mob] = true
    hum.AutoRotate = false
    hum.PlatformStand = true
    hum.JumpPower = 0
    
    if hum:FindFirstChild("Animator") then
        hum.Animator:Destroy()
    end
    
    for _, part in pairs(mob:GetDescendants()) do
        if part:IsA("BasePart") then
            part.CanCollide = false
            part.Massless = true
            part.Velocity = Vector3.zero
        end
    end
    
    if not hrp:FindFirstChild('Lock') then
        local Lock = Instance.new('BodyVelocity')
        Lock.Name = "Lock"
        Lock.Parent = hrp
        Lock.Velocity = Vector3.zero
        Lock.MaxForce = Vector3.new(9e9, 9e9, 9e9)
    end
    
    if not hrp:FindFirstChild('LockRotation') then
        local LockRot = Instance.new('BodyAngularVelocity')
        LockRot.Name = "LockRotation"
        LockRot.Parent = hrp
        LockRot.AngularVelocity = Vector3.zero
        LockRot.MaxTorque = Vector3.new(9e9, 9e9, 9e9)
    end
end

local function getTargetMobs(mobName, maxCount)
    local list = {}
    for _, v in ipairs(workspace.Enemies:GetChildren()) do
        if #list >= maxCount then break end
        local hum = v:FindFirstChild("Humanoid")
        local hrp = v:FindFirstChild("HumanoidRootPart")
        if v.Name == mobName and hum and hum.Health > 0 and hrp then
            table.insert(list, v)
        end
    end
    return list
end

local function getMidPoint(mobs)
    if #mobs == 0 then return Vector3.zero end
    local total = Vector3.zero
    for _, m in ipairs(mobs) do
        if m:FindFirstChild("HumanoidRootPart") then
            total = total + m.HumanoidRootPart.Position
        end
    end
    return total / #mobs
end

pcall(function()
    sethiddenproperty(lp, "SimulationRadius", math.huge)
end)

local TweenService = game:GetService("TweenService")
local lastBring = tick()
local bringing = true
task.spawn(function()
    while task.wait() do
        if not ename then continue end
        if bringing then
            if tick() - lastBring > 0.5 then
                bringing = false
                lastBring = tick()
            end
        else
            if tick() - lastBring > 2.0 then
                bringing = true
                lastBring = tick()
            end
            continue
        end
        local maxBring = 8
        local mobs = {}
        for _, v in ipairs(workspace.Enemies:GetChildren()) do
            if #mobs >= maxBring then break end
            local hum = v:FindFirstChild("Humanoid")
            local hrp = v:FindFirstChild("HumanoidRootPart")
            if v.Name == ename and hum and hum.Health > 0 and hrp then
                local dist = (hrp.Position - lp.Character.HumanoidRootPart.Position).Magnitude
                if dist <= 300 then
                    table.insert(mobs, v)
                end
            end
        end
        if #mobs <= 0 then continue end
        local mid = getMidPoint(mobs)
        epos = CFrame.new(mid)        
        for i, mob in ipairs(mobs) do
            stabilizeMob(mob)
            local hrp = mob:FindFirstChild("HumanoidRootPart")
            if hrp then
                local tweenInfo = TweenInfo.new(
                    0.2, 
                    Enum.EasingStyle.Linear, 
                    Enum.EasingDirection.Out
                )
                local tween = TweenService:Create(hrp, tweenInfo, {CFrame = CFrame.new(mid)})
                tween:Play()
                antiKnockback(hrp)
            end
        end
    end
end)


task.spawn(function()
    while task.wait() do
        if _G.StartFarm or _G.AutoSummonTyrant or _G.NearbyFarm or _G.AutoRaidCastle or _G.AutoEcto then
            local nearestDist = math.huge
            local nearestMob = nil
            local char = lp.Character           
            if char and char:FindFirstChild("HumanoidRootPart") then
                for _, mob in pairs(workspace.Enemies:GetChildren()) do
                    local hrp = mob:FindFirstChild("HumanoidRootPart")
                    local hum = mob:FindFirstChild("Humanoid")             
                    if hrp and hum and hum.Health > 0 then
                        local dist = (hrp.Position - char.HumanoidRootPart.Position).Magnitude
                        if dist < nearestDist then
                            nearestDist = dist
                            nearestMob = mob
                        end
                    end
                end
                if nearestMob then
                    ename = nearestMob.Name
                end
            end
        end
    end
end)

ReplicatedStorage = game.ReplicatedStorage
            Quests = require(ReplicatedStorage:WaitForChild("Quests"))
            function CreateCacheFolder()
              local AllSpawnPoint = {}
              if not workspace:FindFirstChild("rise") then
                local Folder = Instance.new("Folder", workspace)
                Folder.Name = "rise"
              end
              repeat wait() until workspace:FindFirstChild("rise")
              local MobSpawns = Instance.new("Folder", workspace.rise)
              MobSpawns.Name = "MobSpawns"
              for i, v in next, workspace.rise.MobSpawns:GetChildren() do
                v:Destroy()
              end
              for i, v in next, workspace._WorldOrigin.EnemySpawns:GetChildren() do
                local niger = v:Clone()
                niger.Name = niger.Name:gsub(" %pLv. %d+%p", "")
                niger.Parent = workspace.rise.MobSpawns
              end
              local FarmLevelMob = {}
              for i, v in next, Quests do
                for i1, v1 in next, v do
                  for i2, v2 in next, v1.Task do
                    if v1.Task[i2] > 1 then
                      table.insert(FarmLevelMob, i2)
                    end
                  end
                end  
              end
              for i, v in next, game.workspace.Enemies:GetChildren() do
                if table.find(FarmLevelMob, v.Name) then
                  table.insert(AllSpawnPoint, v)
                end
              end
              for i, v in next, game.ReplicatedStorage:GetChildren() do
                if table.find(FarmLevelMob, v.Name) then
                  table.insert(AllSpawnPoint, v)
                end
              end
              for i, v in next, getnilinstances() do
                pcall(function()
                  if v:FindFirstChild("Humanoid") and table.find(FarmLevelMob, v.Name) then
                    table.insert(AllSpawnPoint, v)
                  end
                end)
              end
              for i, v in next, AllSpawnPoint do
                if v:IsA("Model") and v:FindFirstChild("HumanoidRootPart") then
                  local Part = Instance.new("Part", workspace.rise.MobSpawns)
                  Part.Name = v.Name
                  Part.CanCollide = false
                  Part.Transparency = 1
                  Part.Anchored = true
                  Part.Size = Vector3.new(1, 1, 1)
                  Part.CFrame = v.HumanoidRootPart.CFrame
                elseif v:IsA("Part") then
                  local a = v:Clone()
                  a.Parent = workspace.rise.MobSpawns
                end
              end
            end
            CreateCacheFolder()
          local plr = game.Players.LocalPlayer
          function TweenToMon(Name)
          local Parts = {}
          for _, v in ipairs(workspace.rise.MobSpawns:GetChildren()) do
            if v.Name == Name then
              table.insert(Parts, v)
            end
          end
          if #Parts == 0 then return end
          local hrp = lp.Character and lp.Character:FindFirstChild("HumanoidRootPart")
          if not hrp then return end
          for _, Part in ipairs(Parts) do
            repeat task.wait()
              TP(Part.CFrame * CFrame.new(0, 70, 0))
              task.wait(0.4)
            until (Part.Position - hrp.Position).Magnitude <= 100 or Check_Monster(Name)
            if Check_Monster(Name) then
              return
            end
          end
          task.wait(0.3)
        end


            
function isabletospawncakeprince()
    local thua = game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("CakePrinceSpawner")
    if type(thua) == "string" then
        local numberPart = thua:match("%d+")
        if numberPart then
            return tonumber(numberPart) == 0
        end
    end
    return false
end

local old_getquest = loadstring(game:HttpGet("https://raw.githubusercontent.com/noguchihyuga/idk/refs/heads/main/Quest.lua"))()
function getquest(...)
    local questtext = game.Players.LocalPlayer.PlayerGui.Main.Quest.Container.QuestTitle.Title.Text
    local o,lvl = pcall(function ()
        return game["Players"]["LocalPlayer"]["Data"]["Level"]["Value"]
    end)
    if questtext and string.find(questtext:lower(), "bandit") and o and lvl > 10 then
        rs.Remotes.CommF_:InvokeServer("AbandonQuest")
    end
    return old_getquest(...)
end
local watdsfyck = {"Reborn Skeleton", "Living Zombie", "Demonic Soul", "Posessed Mummy"}
local shitshit = {"Cookie Crafter", "Cake Guard", "Baking Staff", "Head Baker"}
local qGui = lp.PlayerGui.Main.Quest
local function getSpecialQuest(mode)
    local lvl = lp.Data.Level.Value
    local d = {}
    if mode == "cake" then 
        if lvl >= 2275 then d = {Name = "Head Baker", Q = "CakeQuest2", ID = 2, PosQ = CFrame.new(-1927.9, 37.8, -12842.5), PosM = CFrame.new(-2216.2, 82.9, -12869.3)}
        elseif lvl >= 2250 then d = {Name = "Baking Staff", Q = "CakeQuest2", ID = 1, PosQ = CFrame.new(-1927.9, 37.8, -12842.5), PosM = CFrame.new(-1887.8, 77.6, -12998.4)}
        elseif lvl >= 2225 then d = {Name = "Cake Guard", Q = "CakeQuest1", ID = 1, PosQ = CFrame.new(-2021.3, 37.8, -12028.7), PosM = CFrame.new(-1598.3, 43.8, -12244.6)}
        elseif lvl >= 2200 then d = {Name = "Cookie Crafter", Q = "CakeQuest1", ID = 1, PosQ = CFrame.new(-2021.3, 37.8, -12028.7), PosM = CFrame.new(-2374.1, 37.8, -12125.3)} 
        else d = {Name = "Cookie Crafter", Q = "CakeQuest1", ID = 1, PosQ = CFrame.new(-2021.3, 37.8, -12028.7), PosM = CFrame.new(-2374.1, 37.8, -12125.3)} end
    else 
        if lvl >= 2050 then d = {Name = "Posessed Mummy", Q = "HauntedQuest2", ID = 2, PosQ = CFrame.new(-9517, 172, 6078.5), PosM = CFrame.new(-9582, 6, 6205)}
        elseif lvl >= 2025 then d = {Name = "Demonic Soul", Q = "HauntedQuest2", ID = 1, PosQ = CFrame.new(-9517, 172, 6078.5), PosM = CFrame.new(-9505, 172, 6159)}
        elseif lvl >= 2000 then d = {Name = "Living Zombie", Q = "HauntedQuest1", ID = 2, PosQ = CFrame.new(-9479, 141, 5566), PosM = CFrame.new(-10144, 138, 5838)}
        elseif lvl >= 1975 then d = {Name = "Reborn Skeleton", Q = "HauntedQuest1", ID = 1, PosQ = CFrame.new(-9479, 141, 5566), PosM = CFrame.new(-8763, 165, 6159.8)}
        else d = {Name = "Reborn Skeleton", Q = "HauntedQuest1", ID = 1, PosQ = CFrame.new(-9479, 141, 5566), PosM = CFrame.new(-8763, 165, 6159.8)} end
    end
    return d
end

task.spawn(function()
    while task.wait() do
        if not _G.StartFarm then continue end
        local M, Q, ID, NM, PM, PQ
        if SelectMode == "Farm Level" then
            M, Q, ID, NM, PM, PQ = getquest()
        elseif SelectMode == "Farm Bones" then
            local d = getSpecialQuest("bone")
            if d then M, Q, ID, NM, PM, PQ = d.Name, d.Q, d.ID, d.Name, d.PosM, d.PosQ end
        elseif SelectMode == "Farm Katakuri" then
            local d = getSpecialQuest("cake")
            if d then M, Q, ID, NM, PM, PQ = d.Name, d.Q, d.ID, d.Name, d.PosM, d.PosQ end
        end
        if not M then continue end
        local qTitle = qGui.Container.QuestTitle.Title.Text
        if not qGui.Visible or not qTitle:find(NM) then
            if qGui.Visible and not qTitle:find(NM) then CommF_("AbandonQuest") end
            local lvl = lp.Data.Level.Value
            local canGet = (SelectMode == "Farm Bones" and lvl >= 1975) or (SelectMode == "Farm Katakuri" and lvl >= 2200) or (SelectMode == "Farm Level")     
            if canGet then
                TP(PQ)
                if getdis(PQ) < 15 then task.wait(0.2) CommF_("StartQuest", Q, ID) end
            end
            local target = nil
            for _, v in ipairs(workspace.Enemies:GetChildren()) do
                if Check_Alive_Monster(v) then
                    if SelectMode == "Farm Level" and v.Name == M then target = v break
                    elseif SelectMode == "Farm Bones" and table.find(watdsfyck, v.Name) then target = v break
                    elseif SelectMode == "Farm Katakuri" and table.find(shitshit, v.Name) then target = v break end
                end
            end
            if target then
                Attack(target, function() return not _G.StartFarm or qGui.Visible end)
            else
                if SelectMode == "Farm Level" then
                    TweenToMon(M)
                else
                    TP(PM * CFrame.new(0, 75, 0))
                end
            end
        else
            local boss = SelectMode == "Farm Katakuri" and (workspace.Enemies:FindFirstChild("Cake Prince") or workspace.Enemies:FindFirstChild("Dough King"))
            if isabletospawncakeprince and isabletospawncakeprince() then
                CommF_("CakePrinceSpawner", true)
            elseif boss and Check_Alive_Monster(boss) then
                Attack(boss, function() return not _G.StartFarm or SelectMode ~= "Farm Katakuri" end)
            else
                local target = nil
                for _, v in ipairs(workspace.Enemies:GetChildren()) do
                    if Check_Alive_Monster(v) then
                        if SelectMode == "Farm Level" and v.Name == M then target = v break
                        elseif SelectMode == "Farm Bones" and table.find(watdsfyck, v.Name) then target = v break
                        elseif SelectMode == "Farm Katakuri" and table.find(shitshit, v.Name) then target = v break end
                    end
                end
                if target then
                    Attack(target, function() return not _G.StartFarm or not qGui.Visible end)
                else
                    if SelectMode == "Farm Level" then
                        TweenToMon(M)
                    else
                        TP(PM * CFrame.new(0, 75, 0))
                    end
                end
            end
        end
    end
end)

--[[task.spawn(function()
    while task.wait() do
        if not _G.StartFarm then continue end
        local M, Q, ID, NM, PM, PQ
        if SelectMode == "Farm Level" then
            M, Q, ID, NM, PM, PQ = getquest()
        elseif SelectMode == "Farm Bones" then
            local d = getSpecialQuest("bone")
            if d then M, Q, ID, NM, PM, PQ = d.Name, d.Q, d.ID, d.Name, d.PosM, d.PosQ end
        elseif SelectMode == "Farm Katakuri" then
            local d = getSpecialQuest("cake")
            if d then M, Q, ID, NM, PM, PQ = d.Name, d.Q, d.ID, d.Name, d.PosM, d.PosQ end
        end        
        if not M then continue end
        local qTitle = qGui.Container.QuestTitle.Title.Text
        if not qGui.Visible or not qTitle:find(NM) then
            if qGui.Visible and not qTitle:find(NM) then CommF_("AbandonQuest") end
            local lvl = lp.Data.Level.Value
            local canGet = (SelectMode == "Farm Bones" and lvl >= 1975) or (SelectMode == "Farm Katakuri" and lvl >= 2200) or (SelectMode == "Farm Level")     
            if canGet then
                TP(PQ)
                if getdis(PQ) < 15 then task.wait(0.2) CommF_("StartQuest", Q, ID) end
            end
            local target = nil
            for _, v in ipairs(workspace.Enemies:GetChildren()) do
                if Check_Alive_Monster(v) then
                    if SelectMode == "Farm Bones" and table.find(watdsfyck, v.Name) then target = v break
                    elseif SelectMode == "Farm Katakuri" and table.find(shitshit, v.Name) then target = v break end
                end
            end
            if target then
                Attack(target, function() return not _G.StartFarm or qGui.Visible end)
            else
                TP(PM * CFrame.new(0, 75, 0))
            end
        else
            local boss = SelectMode == "Farm Katakuri" and (workspace.Enemies:FindFirstChild("Cake Prince") or workspace.Enemies:FindFirstChild("Dough King"))
            if isabletospawncakeprince and isabletospawncakeprince() then
                CommF_("CakePrinceSpawner", true)
            elseif boss and Check_Alive_Monster(boss) then
                Attack(boss, function() return not _G.StartFarm or SelectMode ~= "Farm Katakuri" end)
            else
                local target = nil
                for _, v in ipairs(workspace.Enemies:GetChildren()) do
                    if Check_Alive_Monster(v) then
                        if SelectMode == "Farm Level" and v.Name == M then target = v break
                        elseif SelectMode == "Farm Bones" and table.find(watdsfyck, v.Name) then target = v break
                        elseif SelectMode == "Farm Katakuri" and table.find(shitshit, v.Name) then target = v break end
                    end
                end
                if target then
                    Attack(target, function() return not _G.StartFarm or not qGui.Visible end)
                else
                    TP(PM * CFrame.new(0, 75, 0))
                end
            end
        end
    end
end)]]

local Players = game:GetService("Players")
local RunService = game:GetService("RunService")
local Workspace = game:GetService("Workspace")
local lp = Players.LocalPlayer
local boat_speed = 350
local min_high_fly = 200
local check_map = 250
local default_high = 300
local lerp_sm = 0.05

local currentTarget = nil
local isMoving = false


local rayParams = RaycastParams.new()
rayParams.FilterType = Enum.RaycastFilterType.Exclude
rayParams.IgnoreWater = false 

local function checkboat()
    if not Workspace:FindFirstChild("Boats") then return end
    for _, v in ipairs(Workspace.Boats:GetChildren()) do
        if v:IsA("Model")
        and v:FindFirstChild("Owner")
        and tostring(v.Owner.Value) == lp.Name
        and v:FindFirstChild("Humanoid")
        and v.Humanoid.Value > 0
        and v:FindFirstChild("VehicleSeat") then
            return v
        end
    end
end

local function noclip(model)
    for _, v in ipairs(model:GetDescendants()) do
        if v:IsA("BasePart") then
            v.CanCollide = false
        end
    end
end

local function bodyLock(part)
    if part:FindFirstChild("FlyVelocity") then return end
    
    local bv = Instance.new("BodyVelocity")
    bv.Name = "FlyVelocity"
    bv.MaxForce = Vector3.new(math.huge, math.huge, math.huge)
    bv.Velocity = Vector3.zero
    bv.Parent = part

    local bg = Instance.new("BodyGyro")
    bg.Name = "FlyGyro"
    bg.MaxTorque = Vector3.new(math.huge, math.huge, math.huge)
    bg.P = 1e5
    bg.CFrame = part.CFrame
    bg.Parent = part
end

local function removeBodyLock(part)
    if part:FindFirstChild("FlyVelocity") then part.FlyVelocity:Destroy() end
    if part:FindFirstChild("FlyGyro") then part.FlyGyro:Destroy() end
end

local function createCover(boat)
    if boat:FindFirstChild("FlyPart") then return boat.FlyPart end

    local cf, size = boat:GetBoundingBox()
    local part = Instance.new("Part")
    part.Name = "FlyPart"
    part.Size = size + Vector3.new(5,5,5)
    part.Transparency = 1 
    part.CanCollide = false
    part.Massless = true
    part.Anchored = false
    part.CFrame = cf
    part.Parent = boat

    local weld = Instance.new("WeldConstraint")
    weld.Part0 = part
    weld.Part1 = boat.VehicleSeat
    weld.Parent = part
    return part
end

local function isSittingOnBoat(char, boat)
    local hum = char:FindFirstChildOfClass("Humanoid")
    if not hum then return false end
    local seat = hum.SeatPart
    if not seat then return false end
    return seat:IsDescendantOf(boat)
end

local function getBestHeight(currentPos, direction)
    local checkDistances = {0, check_map * 0.2, check_map * 0.6, check_map}
    local maxTerrainY = -99999
    local foundGround = false
    for _, dist in ipairs(checkDistances) do
        local checkPos = currentPos + (direction * dist)
        local origin = Vector3.new(checkPos.X, currentPos.Y + 500, checkPos.Z)
        local rayDir = Vector3.new(0, -2000, 0)
        local result = Workspace:Raycast(origin, rayDir, rayParams)
        if result then
            foundGround = true
            if result.Position.Y > maxTerrainY then
                maxTerrainY = result.Position.Y
            end
        end
    end
    if foundGround then
        return maxTerrainY + min_high_fly
    else
        return math.max(currentPos.Y, default_high)
    end
end


getgenv().tweenboat = function(target)
    if typeof(target) == "CFrame" then
        currentTarget = target.Position
    elseif typeof(target) == "Vector3" then
        currentTarget = target
    else
        warn("tweenboat: Invalid argument (must be CFrame or Vector3)")
        return
    end
    isMoving = true
end

getgenv().stopboat = function()
    isMoving = false
    currentTarget = nil
end

task.spawn(function()
    local boat
    repeat task.wait(1) boat = checkboat() until boat
    
    local char = lp.Character or lp.CharacterAdded:Wait()
    local flyPart = createCover(boat)
    
    rayParams.FilterDescendantsInstances = {char, boat, flyPart}
    noclip(boat)
    noclip(char)

    RunService.Heartbeat:Connect(function(dt)
        if not flyPart or not flyPart.Parent or not boat or not boat.Parent then 
            boat = checkboat()
            if boat then 
                flyPart = createCover(boat) 
                rayParams.FilterDescendantsInstances = {char, boat, flyPart}
            end
            return 
        end

        if not isSittingOnBoat(char, boat) then
            removeBodyLock(flyPart)
            return
        end

        if not isMoving or not currentTarget then
            removeBodyLock(flyPart)
            return
        end

        bodyLock(flyPart)
        
        local currentPos = flyPart.Position
        local vecToTarget = Vector3.new(currentTarget.X, currentPos.Y, currentTarget.Z) - currentPos
        
        if vecToTarget.Magnitude < 10 then 
            flyPart.FlyVelocity.Velocity = Vector3.zero
            return 
        end        
        
        local moveDir = vecToTarget.Unit
        
        local targetHeight = getBestHeight(currentPos, moveDir)
        local smoothFactor = (targetHeight > currentPos.Y) and lerp_sm * 2 or lerp_sm     
        
        local newY = currentPos.Y + (targetHeight - currentPos.Y) * smoothFactor
        
        local moveStep = moveDir * boat_speed * dt
        local newCFrame = CFrame.new(
            currentPos.X + moveStep.X,
            newY,
            currentPos.Z + moveStep.Z
        )
        
        flyPart.CFrame = newCFrame * flyPart.CFrame.Rotation
        flyPart.FlyVelocity.Velocity = Vector3.zero 
    end)
end)


task.spawn(function()
    while task.wait(2) do
        pcall(function()
            if _G.EnableV3 then
                game:GetService("ReplicatedStorage").Remotes.CommE:FireServer("ActivateAbility")
               return not _G.EnableV3
            end
        end)
    end
end)

runse.Heartbeat:Connect(function()
    if not _G.EnableV4 then return end
    local char = lp.Character
    if char then
        local raceEnergy = char:FindFirstChild("RaceEnergy")
        local raceTransformed = char:FindFirstChild("RaceTransformed")
        if raceEnergy and raceEnergy.Value >= 1 and raceTransformed and not raceTransformed.Value then
            task.spawn(function()
                vim:SendKeyEvent(true, Enum.KeyCode.Y, false, game)
                task.wait(0.1)
                vim:SendKeyEvent(false, Enum.KeyCode.Y, false, game)
            end)
            task.wait(0.5) 
        end
    end
end)

function EquipTool(v)
	local thua = lp.Backpack:FindFirstChild(v)
	if thua then
		lp.Character.Humanoid:EquipTool(thua)
	end
end

function getgodchalice()
	return lp.Backpack:FindFirstChild("God's Chalice") or lp.Character:FindFirstChild("God's Chalice")
end

function getremainingmob()
    local thua = CommF_("CakePrinceSpawner")
    if type(thua) == "string" then
        local stfu = thua:match("%d+")
        if stfu then
            return tonumber(stfu)
        end
    end
    return 0
end

task.spawn(function()
    if not (sea3 and _G.SpawnDoughKing) then return end
    if getgodchalice() and getremainingmob() < 20 then
        local idkj =  CommF_("SweetChaliceNpc")
        if idkj and string.find(idkj, "Where") then
            CommF_("SweetChaliceNpc")
            return
        end
    end
    local chr = lp.Character
    local bpcheck = lp.Backpack
    local hascha = (bpcheck:FindFirstChild("Sweet Chalice") or (chr and chr:FindFirstChild("Sweet Chalice")))
    if hascha then
        local nge = CommF_("CakePrinceSpawner")
        if nge and string.find(nge, "Do you want to open the portal now?") then
            EquipTool("Sweet Chalice")
            task.wait(0.1)
            CommF_("CakePrinceSpawner")
        end
    end
end)

task.spawn(function()
    while task.wait(0.2) do
        if _G.HideNotify then
            lp.PlayerGui.Notifications.Enabled = false
        else
            lp.PlayerGui.Notifications.Enabled = true
        end
    end
end)

task.spawn(function()
    while task.wait(0.2) do
        if _G.WhiteScreen then
            (game:GetService("RunService")):Set3dRenderingEnabled(false)
        else
            (game:GetService("RunService")):Set3dRenderingEnabled(true)
        end
    end
end)

task.spawn(function()
    while task.wait(0.1) do
        if _G.NearbyFarm then
            local root = lp.Character and lp.Character:FindFirstChild("HumanoidRootPart")
            if root then
                local m = Check_Monster()
                if m and m:FindFirstChild("HumanoidRootPart") then
                    if (root.Position - m.HumanoidRootPart.Position).Magnitude < 1000 then
                        Attack(m, function() return not _G.NearbyFarm end)
                    end
                end
            end
        end
    end
end)

task.spawn(function()
    while task.wait(0.5) do
        if _G.AutoKillTyrant then
            local b = Check_Monster({"Tyrant of the Skies"})
            if b then
                Attack(b, function() return not _G.AutoKillTyrant end)
            end
        end
    end
end)



--[[local function useAllSkill()
    if not _G.AutoSummonTyrant then return end
    local VIM = game:GetService("VirtualInputManager")
    local SkillsGui = game.Players.LocalPlayer.PlayerGui.Main.Skills
    local skillData = {
        ["Melee"] = {"Z", "X", "C"},
        ["Sword"] = {"Z", "X"},
        ["Gun"] = {"Z", "X"}
    }    
    for toolName, keys in pairs(skillData) do
        if not _G.AutoSummonTyrant then return end
        local toolGui = SkillsGui:FindFirstChild(toolName)
        if toolGui then
            EquipTool(toolName)
            for _, key in ipairs(keys) do
                if not _G.AutoSummonTyrant then return end
                local v = toolGui:FindFirstChild(key)
                if v then
                    local cooldown = v:FindFirstChild("Cooldown")
                    local title = v:FindFirstChild("Title")
                    if title and (title.TextColor3 == Color3.new(1,1,1)) and 
                       cooldown and (cooldown.Size.X.Offset <= 0) then
                        VIM:SendKeyEvent(true, key, false, game)
                        task.wait(0.05)
                        VIM:SendKeyEvent(false, key, false, game)
                        task.wait(0.1)
                    end
                end
            end
        end
    end
end]]

local function checkEagleEye()
    local model = workspace.Map.TikiOutpost.IslandModel
    for i = 1, 4 do
        local eye = model:FindFirstChild("Eye"..i)
        if not eye or eye.Transparency ~= 0 then return false end
    end
    return true
end


--[[task.spawn(function()
    while task.wait(0.2) do
        if _G.AutoSummonTyrant then
            local enemies = workspace.Enemies
            if not enemies:FindFirstChild("Tyrant of the Skies") then
                if not checkEagleEye() then
                    for _, v in ipairs(enemies:GetChildren()) do
                        if not _G.AutoSummonTyrant then break end                        
                        if v.Name:match("Serpent Hunter") or v.Name:match("Skull Slayer") or v.Name:match("Isle Champion") or v.Name:match("Sun%-kissed Warrior") then
                            if v:FindFirstChild("Humanoid") and v.Humanoid.Health > 0 then
                                repeat task.wait()
                                    local root = v:FindFirstChild("HumanoidRootPart")
                                    if root then
                                        Attack(v)
                                        useAllSkill()
                                    end
                                until not v.Parent or v.Humanoid.Health <= 0 or checkEagleEye() or not _G.AutoSummonTyrant
                            end
                        end
                    end
                else
                    repeat task.wait()
                        if not _G.AutoSummonTyrant then break end
                        local model = workspace.Map.TikiOutpost.IslandModel
                        for _, child in ipairs(model:GetChildren()) do
                            local arena = child:FindFirstChild("EagleBossArena")
                            if arena and arena:FindFirstChild("Tree") then
                                TP(arena.Tree:GetPivot())
                                useAllSkill()
                            end
                        end
                    until enemies:FindFirstChild("Tyrant of the Skies") or not _G.AutoSummonTyrant
                end
            end
        end
    end
end)]]

task.spawn(function()
    while task.wait(0.5) do
        local p, lvl = CommF_("DressrosaQuestProgress"), lp.Data.Level.Value
        if _G.AutoSea2 and sea1 and lvl >= 700 then
            if p.UsedKey and p.TalkedDetective and p.KilledIceBoss then
                CommF_("TravelDressrosa")
            elseif not p.TalkedDetective then
                TP(CFrame.new(4849, 6, 720)) CommF_("DressrosaQuestProgress", "Detective")
            elseif not p.UsedKey then
                EquipTool("Key") TP(CFrame.new(1348, 37, -1326))
            else
                local b = Check_Monster({"Ice Admiral"})
                if b then Attack(b, function() return not _G.AutoSea2 end) else TP(CFrame.new(1348, 37, -1326)) end
            end
        end
    end
end)

local function hasFruit()
    for _, v in pairs(CommF_("getInventory") or {}) do
        if v.Type == "Blox Fruit" and (v.Price or v.Value or 0) >= 1e6 then return true end
    end
end

task.spawn(function()
    while task.wait(0.5) do
        if _G.AutoSea3 and sea2 then
            local xy, xx, yy = CommF_("BartiloQuestProgress", "Bartilo"), CommF_("GetUnlockables"), CommF_("ZQuestProgress", "Check")
            if yy == 1 then CommF_("TravelZou")
            elseif xy == 3 and xx.FlamingoAccess then
                if yy == 0 then
                    local b = Check_Monster({"rip_indra"})
                    if b then Attack(b, function() return not _G.AutoSea3 end) CommF_("F_", "TravelZou")
                    else CommF_("F_", "ZQuestProgress", "Check") task.wait(0.1) CommF_("F_", "ZQuestProgress", "Begin") end
                else
                    local b = Check_Monster({"Don Swan"})
                    if b then Attack(b, function() return not _G.AutoSea3 end) end
                end
            elseif xy == 0 then
                local qG = lp.PlayerGui.Main.Quest
                if not qG.Visible then TP(CFrame.new(-456, 73, 299))
                elseif qG.Container.QuestTitle.Title.Text:find("Swan Pirates") then
                    local m = Check_Monster({"Swan Pirates"})
                    if m then Attack(m, function() return not _G.AutoSea3 end) else TP(CFrame.new(1058, 138, 1242)) end
                else CommF_("AbandonQuest") end
            elseif xy == 2 or (xy == 1 and Check_Monster({"Jeremy"})) then
                local m = Check_Monster({"Jeremy"})
                if m then Attack(m, function() return not _G.AutoSea3 end) else TP(CFrame.new(2316, 449, 787)) end
            elseif not xx.FlamingoAccess and hasFruit() then
                TP(CFrame.new(-482, 73, 304)) CommF_("GiveItemS", "Trevor", "Fruit")
            end
        end
    end
end)

task.spawn(function()
    while task.wait(0.5) do
        if _G.AutoHaki and not sea1 then
            game:GetService("ReplicatedStorage").Remotes.CommE:FireServer("Ken", true)
            local target = Check_Monster(sea3 and {"Forest Pirate"} or {"Ship Officer"})
            if target then
                local d = lp:GetAttribute("KenDodgesLeft") or 0
                local cf = target.HumanoidRootPart.CFrame
                if d >= 0.5 then TP(cf * CFrame.new(0, 5, 0))
                else 
                    TP(cf * CFrame.new(0, 100, 0))
                    if _G.HakiHop then Server_Hop("Hop Reset Ken")  end
                end
            else
                TP(sea3 and CFrame.new(-13106, 340, -7748) or CFrame.new(1163, 180, 33446))
            end
        end
    end
end)

task.spawn(function()
    while task.wait() do
        if _G.AutoElite then
            local foundElite = nil
            for _, v in pairs(workspace.Enemies:GetChildren()) do
                if v.Name == "Deandre" or v.Name == "Urban" or v.Name == "Diablo" then
                    if v:FindFirstChild("Humanoid") and v.Humanoid.Health > 0 then
                        foundElite = v
                        break
                    end
                end
            end
            if foundElite then
                local questUI = lp.PlayerGui.Main.Quest
                local hasQuest = false            
                if questUI.Visible and questUI.Container.QuestTitle.Title.Text then
                    if string.find(questUI.Container.QuestTitle.Title.Text, foundElite.Name) then
                        hasQuest = true
                    end
                end
                if not hasQuest then
                    CommF_("AbandonQuest")
                    CommF_("EliteHunter")
                    task.wait(0.5)
                else
                    Attack(foundElite, function()
                        return not _G.AutoElite or not foundElite.Parent or foundElite.Humanoid.Health <= 0
                    end)
                end
            else
                TP(CFrame.new(-5419, 313, -2801)) 
            end
        end
    end
end)


local RaidPos = Vector3.new(-5232, 341, -3075)
task.spawn(function()
    while task.wait(0.5) do
        if _G.AutoRaidCastle then
            local target = nil
            for _, v in ipairs(wene:GetChildren()) do
                if v:FindFirstChild("HumanoidRootPart") and v.Humanoid.Health > 0 then
                    if (v.HumanoidRootPart.Position - RaidPos).Magnitude <= 1000 then
                        target = v break
                    end
                end
            end
            if target then
                Attack(target, function() return not _G.AutoRaidCastle end)
            else
                if (lp.Character.HumanoidRootPart.Position - RaidPos).Magnitude > 20 then TP(CFrame.new(RaidPos)) end
            end
        end
    end
end)

task.spawn(function()
    while task.wait(0.1) do
        if _G.AutoFactory and sea2 then
            local m = Check_Monster({"Core"})
            if m then Attack(m, function() return not _G.AutoFactory end) else TP(CFrame.new(-9497, 172, 6151)) end
        end
    end
end)

task.spawn(function()
    while task.wait(0.5) do
        if _G.AutoSaber and lp.Data.Level.Value >= 200 and not Check_Tool_Remote("Saber") then
            local q = CommF_("ProQuestProgress")
            if not q.UsedTorch then TP(CFrame.new(-5215, 12, 8480))
            elseif not q.UsedCup then TP(CFrame.new(1114, -13, -1163))
            elseif not q.KilledMob then
                local m = Check_Monster({"Mob Leader"})
                if m then Attack(m, function() return not _G.AutoSaber end) else TP(CFrame.new(-2850, 6, 5300)) end
            elseif not q.UsedRelic then TP(CFrame.new(-1400, 30, -2770))
            else
                local b = Check_Monster({"Saber Expert"})
                if b then Attack(b, function() return not _G.AutoSaber end) else TP(CFrame.new(-1460, 30, -2770)) end
            end
        end
    end
end)

task.spawn(function()
    while task.wait(0.5) do
        if _G.AutoEcto and sea2 then
            local p = Vector3.new(911, 126, 33160)
            if getdis(p) > 2000 then TP(CFrame.new(-6503, 84, -123))
            else
                local m = Check_Monster({"Ship Deckhand", "Ship Engineer", "Ship Steward", "Ship Officer"})
                if m then Attack(m, function() return not _G.AutoEcto end) else TP(CFrame.new(p)) end
            end
        end
    end
end)

task.spawn(function()
    while task.wait(0.5) do
        if _G.AutoPoleV1 and lp.Data.Level.Value >= 100 and not Check_Inventory("Pole (1st Form)") then
            local b = Check_Monster({"Thunder God"})
            if b then Attack(b, function() return not _G.AutoPoleV1 end) else TP(CFrame.new(-7712, 5602, -1435)) end
        end
    end
end)

local RunService = game:GetService("RunService")
local Players = game:GetService("Players")
local TweenService = game:GetService("TweenService")
local CoreGui = game:GetService("CoreGui")
local lp = Players.LocalPlayer
local RISE_THEME = {
    TextFont = Enum.Font.GothamBold,
    TextColor = Color3.fromRGB(255, 255, 255),
    AccentColor = Color3.fromRGB(0, 255, 215),
    BgColor = Color3.fromRGB(25, 25, 25),
    StrokeColor = Color3.fromRGB(60, 60, 60)
}
local function AddEsp(BoatModel)
    if not BoatModel or not BoatModel.PrimaryPart then return end
    if BoatModel.PrimaryPart:FindFirstChild("RiseESP") then return end
    local hum = BoatModel:FindFirstChild("Humanoid")
    if not hum then return end
    local bg = Instance.new("BillboardGui")
    bg.Name = "RiseESP"
    bg.Adornee = BoatModel.PrimaryPart
    bg.Size = UDim2.new(0, 100, 0, 50)
    bg.StudsOffset = Vector3.new(0, 5, 0)
    bg.AlwaysOnTop = true
    bg.Parent = BoatModel.PrimaryPart
    local container = Instance.new("Frame")
    container.Name = "Container"
    container.Size = UDim2.new(1, 0, 1, 0)
    container.BackgroundColor3 = RISE_THEME.BgColor
    container.BackgroundTransparency = 0.3
    container.Parent = bg
    local uiCorner = Instance.new("UICorner")
    uiCorner.CornerRadius = UDim.new(0, 6)
    uiCorner.Parent = container
    local uiStroke = Instance.new("UIStroke")
    uiStroke.Color = RISE_THEME.StrokeColor
    uiStroke.Thickness = 1.5
    uiStroke.Parent = container
    local strokeGrad = Instance.new("UIGradient")
    strokeGrad.Color = ColorSequence.new{
        ColorSequenceKeypoint.new(0, Color3.fromRGB(0, 255, 215)),
        ColorSequenceKeypoint.new(1, Color3.fromRGB(170, 0, 255))
    }
    strokeGrad.Parent = uiStroke
    local nameLabel = Instance.new("TextLabel")
    nameLabel.Name = "NameLabel"
    nameLabel.Size = UDim2.new(1, 0, 0.4, 0)
    nameLabel.Position = UDim2.new(0, 0, 0, 5)
    nameLabel.BackgroundTransparency = 1
    nameLabel.Text = string.upper(BoatModel.Name)
    nameLabel.TextColor3 = RISE_THEME.TextColor
    nameLabel.Font = RISE_THEME.TextFont
    nameLabel.TextSize = 14
    nameLabel.Parent = container
    local distLabel = Instance.new("TextLabel")
    distLabel.Name = "DistLabel"
    distLabel.Size = UDim2.new(1, 0, 0.3, 0)
    distLabel.Position = UDim2.new(0, 0, 0.4, 0)
    distLabel.BackgroundTransparency = 1
    distLabel.Text = "[ FIND LEVIATHAN ]"
    distLabel.TextColor3 = Color3.fromRGB(200, 200, 200)
    distLabel.Font = Enum.Font.Gotham
    distLabel.TextSize = 12
    distLabel.Parent = container
    local barBg = Instance.new("Frame")
    barBg.Name = "HealthBarBg"
    barBg.Size = UDim2.new(0.8, 0, 0.08, 0)
    barBg.Position = UDim2.new(0.1, 0, 0.8, 0)
    barBg.BackgroundColor3 = Color3.fromRGB(40, 40, 40)
    barBg.BorderSizePixel = 0
    barBg.Parent = container  
    local barCorner = Instance.new("UICorner")
    barCorner.CornerRadius = UDim.new(1, 0)
    barCorner.Parent = barBg
    local barFill = Instance.new("Frame")
    barFill.Name = "HealthFill"
    barFill.Size = UDim2.new(1, 0, 1, 0)
    barFill.BackgroundColor3 = RISE_THEME.AccentColor
    barFill.BorderSizePixel = 0
    barFill.Parent = barBg 
    local fillCorner = Instance.new("UICorner")
    fillCorner.CornerRadius = UDim.new(1, 0)
    fillCorner.Parent = barFill
    local connection
    connection = RunService.RenderStepped:Connect(function()
        if not BoatModel or not BoatModel.Parent or not bg or not bg.Parent then
            if connection then connection:Disconnect() end
            if bg then bg:Destroy() end
            return
        end
        local hp = hum.Health
        local maxHp = hum.MaxHealth
        local percent = math.clamp(hp / maxHp, 0, 1)
        TweenService:Create(barFill, TweenInfo.new(0.3), {Size = UDim2.new(percent, 0, 1, 0)}):Play()
        if percent < 0.3 then
            barFill.BackgroundColor3 = Color3.fromRGB(255, 50, 50)
        else
            barFill.BackgroundColor3 = RISE_THEME.AccentColor
        end
        if lp.Character and lp.Character:FindFirstChild("HumanoidRootPart") then
            local dist = (BoatModel.PrimaryPart.Position - lp.Character.HumanoidRootPart.Position).Magnitude
            distLabel.Text = string.format("[ %d M ]", math.floor(dist))
        end
    end)
end


task.spawn(function()
    while task.wait(0.5) do
        if _G.AutoYama and not Check_Inventory("Yama") then
            local progress = CommF_("EliteHunter", "Progress")
            if tonumber(progress) >= 30 then
                TP(CFrame.new(-5256, 16, 8))
                fireclickdetector(workspace.Map.Waterfall.SealedKatana.Handle.ClickDetector)
            else
                say("SYSTEM", "TOTAL KILL < 30 PLZ FARM ELITE", 1)--test
            end
        end
    end
end)

task.spawn(function()
       lookfuckz = {
        [1] = CFrame.new(-7894, 272, -1202),
        [2] = CFrame.new(-8225, 282, -2019),
        [3] = CFrame.new(-7549, 312, -2253),
        [4] = CFrame.new(-7731, 389, -2534),
        [5] = CFrame.new(-7667, 427, -2134)
    }
    while task.wait(0.5) do
        if _G.AutoTushita and not Check_Inventory("Tushita") then
            local gate = workspace.Map.Turtle.TushitaGate:FindFirstChild("TushitaGate1")
            local hasTorch = CheckBackpack("Holy Torch") or lp.Character:FindFirstChild("Holy Torch")
            if hasTorch then
                for i = 1, 5 do
                    local torch = workspace.Map.Turtle.QuestTorches:FindFirstChild("Torch"..i)
                    if torch and torch.Transparency == 1 then
                        TP(lookfuckz[i])
                        firetouchinterest(lp.Character.HumanoidRootPart, torch, 0)
                        task.wait(0.2)
                        firetouchinterest(lp.Character.HumanoidRootPart, torch, 1)
                    end
                end
            elseif gate and gate.Transparency == 1 then
                TP(CFrame.new(5715, 40, 251))
            elseif Check_Monster({"rip_indra True Form"}) then
                TP(CFrame.new(-1623, 20, -2950))
            end
        end
    end
end)

task.spawn(function()
    while task.wait(0.5) do
        if _G.AutoIndra and sea3 then
            local boss = Check_Monster({"rip_indra True Form"})
            if boss then
                Attack(boss, function() return not _G.AutoIndra end)
            end
        end
    end
end)

task.spawn(function()
    while task.wait(0.5) do
        if _G.AutoDoughKing and sea3 then
            local boss = Check_Monster({"Dough King"})
            if boss then
                Attack(boss, function() return not _G.AutoDoughKing end)
            else
                local hasSweet = CheckBackpack("Sweet Chalice") or lp.Character:FindFirstChild("Sweet Chalice")
                local hasGod = CheckBackpack("God's Chalice") or lp.Character:FindFirstChild("God's Chalice")
                if hasSweet then
                    local msg = CommF_("CakePrinceSpawner")
                    if msg and msg:find("open the portal") then
                        EquipTool("Sweet Chalice")
                        CommF_("CakePrinceSpawner")
                    end
                elseif hasGod then
                    local msg = CommF_("SweetChaliceNpc")
                    if msg and msg:find("Where") and getremainingmob() < 20 then
                        CommF_("SweetChaliceNpc")
                    end
                end
            end
        end
    end
end)

task.spawn(function()
    while task.wait(0.5) do
        if _G.AutoDarkbeard and sea2 then
            local boss = Check_Monster({"Darkbeard"})
            if boss then
                Attack(boss, function() return not _G.AutoDarkbeard end)
            else
                local waitPos = CFrame.new(3692, 13, -3502)
                if (lp.Character.HumanoidRootPart.Position - waitPos.Position).Magnitude > 20 then
                    TP(waitPos)
                end
            end
        end
    end
end)

task.spawn(function()
    while task.wait(0.5) do
        if _G.AutoReaper and sea3 then
            local boss = Check_Monster({"Soul Reaper"})
            if boss then
                Attack(boss, function() return not _G.AutoReaper end)
            else
                local waitPos = CFrame.new(-9515, 164, 5786)
                if (lp.Character.HumanoidRootPart.Position - waitPos.Position).Magnitude > 20 then
                    TP(waitPos)
                end
            end
        end
    end
end)

task.spawn(function()
    while task.wait(0.1) do
        if (_G.AutoChest or _G.AutoChestTP) and lp.Character:FindFirstChild("HumanoidRootPart") then
            if _G.StopItem then
                local stop = false
                for _, name in ipairs({"God's Chalice", "Fist of Darkness", "Sweet Chalice"}) do
                    if lp.Backpack:FindFirstChild(name) or lp.Character:FindFirstChild(name) then
                        _G.AutoChest, _G.AutoChestTP = false, false
                        stop = true break
                    end
                end
                if stop then continue end
            end
            local chests = cs:GetTagged("_ChestTagged")
            local target, closestDist = nil, math.huge
            local myPos = lp.Character.HumanoidRootPart.Position
            for _, chest in ipairs(chests) do
                if chest and not chest:GetAttribute("IsDisabled") then
                    local dist = (chest:GetPivot().Position - myPos).Magnitude
                    if dist < closestDist then
                        closestDist = dist
                        target = chest
                    end
                end
            end
            if target then
                if _G.AutoChestTP then
                    lp.Character.HumanoidRootPart.CFrame = target:GetPivot()
                else
                    TP(target:GetPivot())
                end
                game:GetService("VirtualInputManager"):SendKeyEvent(true, "Q", false, game)
                task.wait(0.05)
                game:GetService("VirtualInputManager"):SendKeyEvent(false, "Q", false, game)
            end
        end
    end
end)

local MaterialList = {}
if sea1 then MaterialList = {"Magma Ore", "Angel Wings", "Leather", "Scrap Metal"}
elseif sea2 then MaterialList = {"Radioactive", "Mystic Droplet", "Magma Ore", "Leather", "Ectoplasm", "Scrap Metal"}
elseif sea3 then MaterialList = {"Leather", "Scrap Metal", "Conjured Cocoa", "Dragon Scale", "Gunpowder", "Fish Tail", "Mini Tusk"} end

task.spawn(function()
    while task.wait(0.5) do
        if _G.StartMetarial and SelectMetarial then
            local data = MatData[SelectMetarial]
            if data[1] then
                local worldIdx = sea1 and 1 or (sea2 and 2 or 3)
                data = data[worldIdx]
            end
            if data then
                local mob = Check_Monster(data.mon)
                if mob then
                    Attack(mob, function() return not _G.StartMetarial end)
                else
                    if SelectMetarial == "Ectoplasm" and getdis(data.pos.Position) > 10000 then
                        CommF_("requestEntrance", Vector3.new(923, 127, 32853))
                    end
                    TP(data.pos)
                end
            end
        end
    end
end)

task.spawn(function()
    while task.wait(0.5) do
        if _G.AutoEnableKen then
            local hasKen = lp.PlayerGui.ScreenGui:FindFirstChild("ImageLabel") 
            if not hasKen then
                game:GetService("ReplicatedStorage").Remotes.CommE:FireServer("Ken", true)
            end
        end
    end
end)

game:GetService("CoreGui").RobloxPromptGui.promptOverlay.ChildAdded:Connect(function(v)
    if _G.AutoRejoin and v.Name == "ErrorPrompt" then
        if v:FindFirstChild("MessageArea") and v.MessageArea:FindFirstChild("ErrorFrame") then
            game:GetService("TeleportService"):Teleport(game.PlaceId, lp)
        end
    end
end)

local StatMap = {
    ["StatMelee"] = "Melee",
    ["StatHealth"] = "Defense",
    ["StatSword"] = "Sword",
    ["StatFruit"] = "Demon Fruit",
    ["StatGun"] = "Gun"
}
task.spawn(function()
    while task.wait(0.3) do
        for toggleName, statName in pairs(StatMap) do
            if _G[toggleName] then
                CommF_("AddPoint", statName, 3)
            end
        end
    end
end)

function GetCountMaterials(MaterialName)
    local inv = CommF_("getInventory")
    for _, v in pairs(inv or {}) do
        if v.Name == MaterialName then return v.Count end
    end
    return 0
end

task.spawn(function()
    while task.wait(1) do
        if _G.RandomFruit then
            CommF_("Cousin", "Buy")
            local btn = lp.PlayerGui:FindFirstChild("SpinnerWindow")
            if btn then
                firesignal(btn.AboveSpinner.Navigation.CloseButton.Activated)
            end
        end
    end
end)

task.spawn(function()
    while task.wait(1) do
        if _G.RandomBones then
            CommF_("Bones", "Buy", 1, 1)
            task.wait(1)
        end
    end
end)


local function CreateESP(parent, name, color, offset)
    if parent:FindFirstChild("nigga") then return parent.nigga.TextLabel end
    local bill = Instance.new("BillboardGui", parent)
    bill.Name = "nigga"
    bill.Size = UDim2.new(0, 200, 0, 50)
    bill.Adornee = parent
    bill.AlwaysOnTop = true
    bill.ExtentsOffset = offset or Vector3.new(0, 2, 0)
    local label = Instance.new("TextLabel", bill)
    label.Size = UDim2.new(1, 0, 1, 0)
    label.BackgroundTransparency = 1
    label.TextColor3 = color
    label.TextStrokeTransparency = 0
    label.Font = Enum.Font.GothamBold
    label.TextSize = 13
    return label
end

task.spawn(function()
    while task.wait(0.5) do
        for _, v in ipairs(game.Players:GetPlayers()) do
            if _G.ESPPlayer and v ~= lp and v.Character and v.Character:FindFirstChild("Head") then
                local label = CreateESP(v.Character.Head, v.Name, v.Team == lp.Team and Color3.new(0,1,0) or Color3.new(1,0,0))
                local dist = math.round((lp.Character.Head.Position - v.Character.Head.Position).Magnitude)
                label.Text = string.format("%s\n[%d HP] - %dm", v.Name, math.round(v.Character.Humanoid.Health), dist)
            elseif v.Character and v.Character.Head:FindFirstChild("nigga") then v.Character.Head.nigga:Destroy() end
        end
        if _G.ESPChest and workspace:FindFirstChild("ChestModels") then
            for _, v in ipairs(workspace.ChestModels:GetChildren()) do
                if v:FindFirstChild("RootPart") then
                    local label = CreateESP(v, v.Name, Color3.new(1, 1, 0))
                    local dist = math.round((lp.Character.Head.Position - v.RootPart.Position).Magnitude)
                    label.Text = v.Name .. "\n" .. dist .. "m"
                end
            end
        else
            for _, v in ipairs(workspace.ChestModels:GetChildren()) do if v:FindFirstChild("nigga") then v.nigga:Destroy() end end
        end
        if _G.ESPFruit then
            for _, v in ipairs(workspace:GetChildren()) do
                if v.Name:find("Fruit") and v:FindFirstChild("Handle") then
                    local label = CreateESP(v.Handle, v.Name, Color3.new(1, 0, 1))
                    label.Text = "Fruit " .. v.Name
                end
            end
        end
        if _G.ESPMirage then
            local mirage = workspace._WorldOrigin.Locations:FindFirstChild("Mirage Island")
            if mirage then 
                local label = CreateESP(mirage, "Mirage Island", Color3.new(0, 1, 1), Vector3.new(0, 10, 0))
                label.Text = "MIRAGE ISLAND"
            end
        end      
        if _G.ESPNpcMirage then
            local npc = workspace.NPCs:FindFirstChild("Advanced Fruit Dealer")
            if npc then
                local label = CreateESP(npc, "Advanced Dealer", Color3.new(1, 0.5, 0))
                label.Text = "ADVANCED DEALER"
            end
        end
    end
end)

function collectchest()
	--if not _G.Config_["CollectChest"] then return false end
	local CS = game:GetService("CollectionService")
	local player = game.Players.LocalPlayer
	local character = player.Character
	if not character or not character:FindFirstChild("HumanoidRootPart") then return end
	local myPos = character.HumanoidRootPart.Position
	local chests = CS:GetTagged("_ChestTagged")
	local closestDist = math.huge
	local target = nil
	for _, chest in pairs(chests) do
		if chest and not chest:GetAttribute("IsDisabled") then
			local dist = (chest:GetPivot().Position - myPos).Magnitude
			if dist < closestDist then
				closestDist = dist
				target = chest
			end
		end
	end
	if target then
		TP(target:GetPivot())
		game:service("VirtualInputManager"):SendKeyEvent(true, "Q", false, game)
		wait()
		game:service("VirtualInputManager"):SendKeyEvent(false, "Q", false, game)
	else
		say("SYSTEM", "Wait Chest Respawn...", 2)
	end
end


task.spawn(function()
    while task.wait(1) do
        if _G.AutoV1V3 then
            local race = lp.Data.Race.Value
            if not race:find("V2") and not race:find("V3") then
                local status = CommF_("Alchemist", "1")
                if status == 0 then CommF_("Alchemist", "2")
                elseif status == 1 then
                    if not Check_Inventory("Flower 1") then
                        if workspace:FindFirstChild("Flower1") then TP(workspace.Flower1.CFrame) end
                    elseif not Check_Inventory("Flower 2") then
                        if workspace:FindFirstChild("Flower2") then TP(workspace.Flower2.CFrame) end
                    elseif not Check_Inventory("Flower 3") then
                        local m = Check_Monster({"Swan Pirates"})
                        if m then Attack(m, function() return not _G.AutoV1V3 end) else TP(CFrame.new(840, 122, 1240)) end
                    end
                elseif status == 2 then CommF_("Alchemist", "3") end
            elseif race:find("V2") then
                local a = CommF_("Wenlocktoad", "1")
                if a == 0 then CommF_("Wenlocktoad", "2")
                elseif a == 2 then CommF_("Wenlocktoad", "3")
                elseif a == 1 then
                    if race:find("Human") then
                        local boss = Check_Monster({"Jeremy", "Fajita", "Diamond"})
                        if boss then Attack(boss, function() return not _G.AutoV1V3 end) end
                    elseif race:find("Mink") then
                        collectchest()
                    elseif race:find("Cyborg") then
                        if not Check_Inventory("Blox Fruit") then
                            say("SYSTEM", "Need any fruit in inventory!", 2)
                        else
                            CommF_("Wenlocktoad", "3")
                        end
                    elseif race:find("Fishman") then
                        local sb = workspace:FindFirstChild("SeaBeast") or workspace.Enemies:FindFirstChild("Sea Beast")
                        if sb then
                            Attack(sb, function() return not _G.AutoV1V3 end)
                        else
                            TP(CFrame.new(-7544, 0, -2458))
                        end
                    end
                end
            end
        end
    end
end)

local function GetBlueGear()
    for _, v in ipairs(workspace:GetDescendants()) do
        if v.Name == "BlueGear" then return v end
    end
end
task.spawn(function()
    while task.wait(0.2) do
        if _G.AutoGetGear and sea3 then
            local mirage = workspace._WorldOrigin.Locations:FindFirstChild("Mirage Island")
            local hasFractal = Check_Inventory("Mirror Fractal")
            local hasValkyrie = Check_Inventory("Valkyrie Helm")
            if not hasFractal or not hasValkyrie then
                say("SYSTEM", "Need Mirror Fractal and Valkyrie Helm!", 2)
            elseif mirage then
                local gear = GetBlueGear()
                if gear and gear.Transparency == 0 then
                    TP(gear.CFrame)
                    say("SYSTEM", "Found Blue Gear! Teleporting...", 2)
                else
                    TP(mirage.CFrame * CFrame.new(0, 400, 0))
                    if game.Lighting.ClockTime < 5 or game.Lighting.ClockTime > 18 then
                        local moonDir = game.Lighting:GetMoonDirection()
                        local lookPos = workspace.CurrentCamera.CFrame.Position + moonDir * 1000
                        workspace.CurrentCamera.CFrame = CFrame.lookAt(workspace.CurrentCamera.CFrame.Position, lookPos)
                        lp.Character.Humanoid.AutoRotate = false
                        lp.Character.HumanoidRootPart.CFrame = CFrame.lookAt(lp.Character.HumanoidRootPart.Position, lookPos)
                        game:GetService("ReplicatedStorage").Remotes.CommE:FireServer("ActivateAbility")
                    else
                        say("SYSTEM", "Waiting for Night to look Moon...", 2)
                    end
                end
            else
                say("SYSTEM", "Waiting for Mirage Island to spawn...", 2)
            end
        else
            if lp.Character and lp.Character:FindFirstChild("Humanoid") then
                lp.Character.Humanoid.AutoRotate = true
            end
        end
    end
end)

task.spawn(function()
    while task.wait(0.5) do
        if _G.GoToMirage and sea3 then
            local mirage = worigin.Locations:FindFirstChild("Mirage Island")
            if mirage then
                TP(mirage.CFrame * CFrame.new(0, 300, 0))
            else
                say("SYSTEM", "Mirage Island not found yet...", 1)
            end
        end
    end
end)

local function AutoStoreFruit()
    for _, v in ipairs(lp.Backpack:GetChildren()) do
        if v:FindFirstChild("Fruit") or v.Name:find("Fruit") then
            local fruitName = v:GetAttribute("OriginalName") or v.Name
            CommF_("StoreFruit", fruitName, v)
        end
    end
end

task.spawn(function()
    while task.wait(0.5) do
        if _G.CollectFruit then
            local fruitFound = false
            for _, v in ipairs(workspace:GetChildren()) do
                if v.Name:find("Fruit") and v:FindFirstChild("Handle") then
                    fruitFound = true
                    repeat task.wait()
                        if v:FindFirstChild("Handle") then
                            TP(v.Handle.CFrame)
                        end
                    until not v.Parent or not _G.CollectFruit
                    if _G.StoreFruit then AutoStoreFruit() end
                end
            end
        end
        if _G.StoreFruit then
            AutoStoreFruit()
        end
    end
end)

task.spawn(function()
    while task.wait(0.3) do
        if _G.AutoTrialV4 and sea3 then
            local myRace = lp.Data.Race.Value
            local trialPart = races_trial_place[myRace]
            if lp.PlayerGui.Main.Timer.Visible then
                if myRace == "Mink" then
                    TP(workspace.Map.MinkTrial.Ceiling.CFrame)
                elseif myRace == "Skypiea" then
                    TP(workspace.Map.SkyTrial.Model.FinishPart.CFrame)
                elseif myRace == "Cyborg" then
                    TP(workspace.Map.CyborgTrial.Floor.CFrame * CFrame.new(0, 500, 0))
                elseif myRace == "Human" or myRace == "Ghoul" or myRace == "Draco" then
                    for _, v in ipairs(workspace.Enemies:GetChildren()) do
                        if v:FindFirstChild("HumanoidRootPart") and v.Humanoid.Health > 0 then
                            if (v.HumanoidRootPart.Position - trialPart.Position).Magnitude < 1500 then
                                Attack(v, function() return not lp.PlayerGui.Main.Timer.Visible end)
                            end
                        end
                    end
                end
            elseif isfullmoon() or isnight() then
                local distToDoor = (lp.Character.HumanoidRootPart.Position - trialPart.Position).Magnitude                
                if distToDoor > 10 then
                    TP(trialPart.CFrame)
                else
                    local ability = race_abilities[myRace]
                    if ability and not lp.Character:FindFirstChild("RaceTransformed") then
                        game:GetService("ReplicatedStorage").Remotes.CommE:FireServer("ActivateAbility")
                    end
                end
            else
                local templeLobby = CFrame.new(28310, 14895, 109)
                if (lp.Character.HumanoidRootPart.Position - templeLobby.Position).Magnitude > 50 then
                    TP(templeLobby)
                end
            end
        end
    end
end)

task.spawn(function()
    while task.wait(0.5) do
        if _G.StartTravel and SelectIsland then
            local data = IslandData[SelectIsland]
            if data then
                if SelectIsland == "Cursed Ship" and getdis(data.pos.Position) > 10000 then
                    CommF_("requestEntrance", Vector3.new(923, 126, 32852))
                end      
                repeat task.wait()
                    TP(data.pos)
                until not _G.StartTravel or getdis(data.pos.Position) < 10
                _G.StartTravel = false
            end
        end
    end
end)

local function GetBestPad()
    local bestPad = nil
    local maxPlayers = -1
    for i = 1, 3 do
        local pad = workspace.Map["Simulation Hub"].Pads:FindFirstChild("DUNGEON_TELEPORTER" .. i)
        if pad then
            local playersOnPad = pad:GetAttribute("NumPlayersOnPad") or 0
            if playersOnPad < 4 and playersOnPad > maxPlayers then
                maxPlayers = playersOnPad
                bestPad = pad
            end
        end
    end
    return bestPad
end

local function GetCurrentZone()
    local nearestZone = nil
    local minDistance = math.huge
    local dungeonFolder = workspace.Map:FindFirstChild("Dungeon")
    if not dungeonFolder then return nil end
    for _, zone in ipairs(dungeonFolder:GetChildren()) do
        local root = zone:FindFirstChild("Root")
        if root and zone:FindFirstChild("ExitTeleporter") then
            local dist = (root.Position - lp.Character.HumanoidRootPart.Position).Magnitude
            if dist < minDistance then
                minDistance = dist
                nearestZone = zone
            end
        end
    end
    return nearestZone
end

local CardPriority = {
    "Overflow", "Lifesteal", "Unbreakable", "Health", "Defense", "Armor", "Melee", "Sword"
}
local function AutoPickCard()
    local playerGui = lp.PlayerGui
    for _, cardName in ipairs(CardPriority) do
        for _, gui in ipairs(playerGui:GetChildren()) do
            if gui.Name == "ScreenGui" and gui:FindFirstChild("1") then
                local cardBtn = gui["1"]:FindFirstChild("2")
                if cardBtn and cardBtn:FindFirstChild("DisplayName") and cardBtn.DisplayName.Text:find(cardName) then
                    firesignal(cardBtn.Activated)
                    return
                end
            end
        end
    end
end

task.spawn(function()
    while task.wait(0.5) do
        if not _G.AutoDungeon then continue end
        if game.PlaceId == DungeonPlaceId then
            if noindungeon then 
                if _G.AutoJoinDungeon then
                    local pad = GetBestPad()
                    if pad then
                        TP(pad.Pad.CFrame * CFrame.new(0, 5, 0))
                        if pad:GetAttribute("NumPlayersOnPad") >= 2 and pad:GetAttribute("Initiator") == lp.UserId then
                            pad.DungeonSettingsChanged:FireServer("Start")
                        end
                    end
                end
            else
                local currentZone = GetCurrentZone()
                if currentZone then
                    local exitRoot = currentZone.ExitTeleporter:FindFirstChild("Root")
                    if exitRoot and exitRoot:FindFirstChild("BBG") then
                        TP(exitRoot.CFrame)
                        task.wait(1)
                    else
                        local enemies = workspace.Enemies:GetChildren()
                        if #enemies > 0 then
                            for _, enemy in ipairs(enemies) do
                                if enemy:FindFirstChild("Humanoid") and enemy.Humanoid.Health > 0 then
                                    if enemy.Name == "PropHitboxPlaceholder" then
                                        enemy.Humanoid.Health = 0
                                    else
                                        Attack(enemy, function() return not _G.AutoDungeon end)
                                    end
                                end
                            end
                        else
                            if _G.AutoPickCard then
                                AutoPickCard()
                            end
                            if exitRoot then TP(exitRoot.CFrame) end
                        end
                    end
                end
            end
        end
    end
end)

local Players = game:GetService("Players")
local ReplicatedStorage = game:GetService("ReplicatedStorage")
local Workspace = game:GetService("Workspace")
local lp = Players.LocalPlayer
local Net = ReplicatedStorage:WaitForChild("Modules"):WaitForChild("Net")
local FishingRequest = ReplicatedStorage:WaitForChild("FishReplicated"):WaitForChild("FishingRequest")
local JobsRF = Net:WaitForChild("RF/JobsRemoteFunction")
local CraftRF = Net:WaitForChild("RF/Craft")
local FishingSettings = {
    SelectedRod = "Fishing Rod",
    SelectedBait = "Basic Bait",
    AutoCraftBait = true,
    LastCastLocation = nil
}
local function LocalEquipTool(toolName)
    local tool = lp.Backpack:FindFirstChild(toolName) or lp.Character:FindFirstChild(toolName)
    if tool then
        lp.Character.Humanoid:EquipTool(tool)
    else
        pcall(function()
            ReplicatedStorage.Remotes.CommF_:InvokeServer("LoadItem", toolName, {"Gear"})
        end)
    end
end

local function GetWaterHeight(pos)
    local success, waterModule = pcall(function() 
        return require(ReplicatedStorage.Util.GetWaterHeightAtLocation)
    end)
    if success then return waterModule(pos) end
    return 0
end

local function StartAutoFishing()
    local character = lp.Character
    local hrp = character and character:FindFirstChild("HumanoidRootPart")
    if not hrp then return end
    local hasRod = lp.Backpack:FindFirstChild(FishingSettings.SelectedRod) or character:FindFirstChild(FishingSettings.SelectedRod)
    if not hasRod then
        JobsRF:InvokeServer("FishingNPC", "FirstTimeFreeRod")
        task.wait(0.5)
    end
    if FishingSettings.AutoCraftBait then
        local currentBait = lp.Data.FishingData:GetAttribute("SelectedBait")
        if not currentBait or currentBait == "None" then
            CraftRF:InvokeServer("Craft", FishingSettings.SelectedBait)
            task.wait(1)
        end
    end
    LocalEquipTool(FishingSettings.SelectedRod)
    local rod = character:FindFirstChild(FishingSettings.SelectedRod)
    if not rod then return end
    local serverState = rod:GetAttribute("ServerState")    
    if serverState == "Biting" then
        FishingRequest:InvokeServer("Catching", true)
        task.wait(0.25)
        FishingRequest:InvokeServer("Catch", 1)
    elseif serverState == "ReeledIn" or serverState == "Idle" or not serverState then
        local config = require(ReplicatedStorage.FishReplicated.FishingClient.Config)
        local lookVec = hrp.CFrame.LookVector
        local castDist = config.Rod.MaxLaunchDistance * 0.6        
        local ray = Ray.new(character.Head.Position, lookVec * castDist)
        local _, hitPos = Workspace:FindPartOnRayWithIgnoreList(ray, {character, Workspace.Characters, Workspace.Enemies})
        local waterY = GetWaterHeight(hitPos)
        local finalPos = Vector3.new(hitPos.X, waterY, hitPos.Z)
        FishingSettings.LastCastLocation = finalPos
        FishingRequest:InvokeServer("StartCasting")
        task.wait(0.5)
        FishingRequest:InvokeServer("CastLineAtLocation", finalPos, 100, true)
    end
end
task.spawn(function()
    while task.wait(0.7) do
        if _G.StartFishsing then
            pcall(StartAutoFishing)
        end
    end
end)


_G.FastAttack = true

if _G.FastAttack then
    local _ENV = (getgenv or getrenv or getfenv)()

    local function SafeWaitForChild(parent, childName)
        local success, result = pcall(function()
            return parent:WaitForChild(childName)
        end)
        if not success or not result then
            warn("noooooo: " .. childName)
        end
        return result
    end

    local function WaitChilds(path, ...)
        local last = path
        for _, child in {...} do
            last = last:FindFirstChild(child) or SafeWaitForChild(last, child)
            if not last then
                break
            end
        end
        return last
    end

    local VirtualInputManager = game:GetService("VirtualInputManager")
    local CollectionService = game:GetService("CollectionService")
    local ReplicatedStorage = game:GetService("ReplicatedStorage")
    local TeleportService = game:GetService("TeleportService")
    local RunService = game:GetService("RunService")
    local Players = game:GetService("Players")
    local Player = Players.LocalPlayer

    if not Player then
        warn(".")
        return
    end

    local Remotes = SafeWaitForChild(ReplicatedStorage, "Remotes")
    if not Remotes then
        return
    end

    local Validator = SafeWaitForChild(Remotes, "Validator")
    local CommF = SafeWaitForChild(Remotes, "CommF_")
    local CommE = SafeWaitForChild(Remotes, "CommE")

    local ChestModels = SafeWaitForChild(workspace, "ChestModels")
    local WorldOrigin = SafeWaitForChild(workspace, "_WorldOrigin")
    local Characters = SafeWaitForChild(workspace, "Characters")
    local Enemies = SafeWaitForChild(workspace, "Enemies")
    local Map = SafeWaitForChild(workspace, "Map")

    local EnemySpawns = SafeWaitForChild(WorldOrigin, "EnemySpawns")
    local Locations = SafeWaitForChild(WorldOrigin, "Locations")

    local RenderStepped = RunService.RenderStepped
    local Heartbeat = RunService.Heartbeat
    local Stepped = RunService.Stepped

    local Modules = SafeWaitForChild(ReplicatedStorage, "Modules")
    local Net = SafeWaitForChild(Modules, "Net")

    local sethiddenproperty = sethiddenproperty or function(...)
        return ...
    end
    local setupvalue = setupvalue or (debug and debug.setupvalue)
    local getupvalue = getupvalue or (debug and debug.getupvalue)

    local Settings = {
        AutoClick = true,
        ClickDelay = 0
    }

    local Module = {}

    Module.FastAttack = (function()
        if _ENV.rz_FastAttack then
            return _ENV.rz_FastAttack
        end

        local FastAttack = {
            Distance = 100,
            attackMobs = true,
            attackPlayers = true,
            Equipped = nil
        }

        local RegisterAttack = SafeWaitForChild(Net, "RE/RegisterAttack")
        local RegisterHit = SafeWaitForChild(Net, "RE/RegisterHit")

        local function IsAlive(character)
            return character and character:FindFirstChild("Humanoid") and character.Humanoid.Health > 0
        end

        local function ProcessEnemies(OthersEnemies, Folder)
            local BasePart = nil
            for _, Enemy in Folder:GetChildren() do
                local Head = Enemy:FindFirstChild("Head")
                if Head and IsAlive(Enemy) and Player:DistanceFromCharacter(Head.Position) < FastAttack.Distance then
                    if Enemy ~= Player.Character then
                        table.insert(OthersEnemies, {Enemy, Head})
                        BasePart = Head
                    end
                end
            end
            return BasePart
        end

        function FastAttack:Attack(BasePart, OthersEnemies)
            if not BasePart or #OthersEnemies == 0 then
                return
            end
            RegisterAttack:FireServer(Settings.ClickDelay or 0)
            RegisterHit:FireServer(BasePart, OthersEnemies)
        end

        function FastAttack:AttackNearest()
            local OthersEnemies = {}
            local Part1 = ProcessEnemies(OthersEnemies, Enemies)
            local Part2 = ProcessEnemies(OthersEnemies, Characters)

            local character = Player.Character
            if not character then
                return
            end
            local equippedWeapon = character:FindFirstChildOfClass("Tool")

            if equippedWeapon and equippedWeapon:FindFirstChild("LeftClickRemote") then
                for _, enemyData in ipairs(OthersEnemies) do
                    local enemy = enemyData[1]
                    local direction = (enemy.HumanoidRootPart.Position - character:GetPivot().Position).Unit
                    pcall(function()
                        equippedWeapon.LeftClickRemote:FireServer(direction, 1)
                    end)
                end
            elseif #OthersEnemies > 0 then
                self:Attack(Part1 or Part2, OthersEnemies)
            else
                task.wait(0)
            end
        end

        function FastAttack:BladeHits()
            local Equipped = IsAlive(Player.Character) and Player.Character:FindFirstChildOfClass("Tool")
            if Equipped and Equipped.ToolTip ~= "Gun" then
                self:AttackNearest()
            else
                task.wait(0)
            end
        end

        task.spawn(function()
            while task.wait(Settings.ClickDelay) do
                if Settings.AutoClick then
                    FastAttack:BladeHits()
                end
            end
        end)

        _ENV.rz_FastAttack = FastAttack
        return FastAttack
    end)()
end
local remote, idremote
for _, v in next, ({game.ReplicatedStorage.Util, game.ReplicatedStorage.Common, game.ReplicatedStorage.Remotes,
                    game.ReplicatedStorage.Assets, game.ReplicatedStorage.FX}) do
    for _, n in next, v:GetChildren() do
        if n:IsA("RemoteEvent") and n:GetAttribute("Id") then
            remote, idremote = n, n:GetAttribute("Id")
        end
    end
    v.ChildAdded:Connect(function(n)
        if n:IsA("RemoteEvent") and n:GetAttribute("Id") then
            remote, idremote = n, n:GetAttribute("Id")
        end
    end)
end
task.spawn(function()
    while task.wait(0.05) do
        local char = game.Players.LocalPlayer.Character
        local root = char and char:FindFirstChild("HumanoidRootPart")
        local parts = {}
        for _, x in ipairs({workspace.Enemies, workspace.Characters}) do
            for _, v in ipairs(x and x:GetChildren() or {}) do
                local hrp = v:FindFirstChild("HumanoidRootPart")
                local hum = v:FindFirstChild("Humanoid")
                if v ~= char and hrp and hum and hum.Health > 0 and (hrp.Position - root.Position).Magnitude <= 60 then
                    for _, _v in ipairs(v:GetChildren()) do
                        if _v:IsA("BasePart") and (hrp.Position - root.Position).Magnitude <= 60 then
                            parts[#parts + 1] = {v, _v}
                        end
                    end
                end
            end
        end
        local tool = char:FindFirstChildOfClass("Tool")
        if #parts > 0 and tool and
            (tool:GetAttribute("WeaponType") == "Melee" or tool:GetAttribute("WeaponType") == "Sword") then
            pcall(function()
                require(game.ReplicatedStorage.Modules.Net):RemoteEvent("RegisterHit", true)
                game.ReplicatedStorage.Modules.Net["RE/RegisterAttack"]:FireServer()
                local head = parts[1][1]:FindFirstChild("Head")
                if not head then
                    return
                end
                game.ReplicatedStorage.Modules.Net["RE/RegisterHit"]:FireServer(head, parts, {}, tostring(
                    game.Players.LocalPlayer.UserId):sub(2, 4) .. tostring(coroutine.running()):sub(11, 15))
                cloneref(remote):FireServer(string.gsub("RE/RegisterHit", ".", function(c)
                    return string.char(
                        bit32.bxor(string.byte(c), math.floor(workspace:GetServerTimeNow() / 10 % 10) + 1))
                end), bit32.bxor(idremote + 909090, game.ReplicatedStorage.Modules.Net.seed:InvokeServer() * 2), head,
                    parts)
            end)
        end
    end
end)


vused = game:GetService("VirtualUser")
lp.Idled:Connect(function()
    vused:CaptureController()
    vused:Button2Down(Vector2.new(0,0), workspace.CurrentCamera.CFrame)
    task.wait(1)
    vused:Button2Up(Vector2.new(0,0), workspace.CurrentCamera.CFrame)
end)

loadstring(game:HttpGet('https://raw.githubusercontent.com/asher-realrise/project/refs/heads/main/stat_inlitizing.lua'))()
wind = loadstring(game:HttpGet("https://github.com/Footagesus/WindUI/releases/latest/download/main.lua"))()
local Window = wind:CreateWindow({
    Title = "Rise Hub | Evo True V2 - by realrise#0 ",
    Icon = "zap",
    Author = "Version: <font color=\"#FFD700\">PREMIUM</font> [ discord.gg/URZ5qcVPwc ]",
    Folder = "bet",
    Size = UDim2.fromOffset(580, 460),
    MinSize = Vector2.new(400, 300),
    MaxSize = Vector2.new(850, 560),
    Transparent = true,
    Theme = "Dark",
    Resizable = true,
    SideBarWidth = 200,
    BackgroundImageTransparency = 0.42,
    HideSearchBar = true,
    ScrollBarEnabled = false,
    User = {
        Enabled = true,
        Anonymous = false,
        Callback = function()
            print("hello " .. game.Players.LocalPlayer.Name)
        end,
    },
})

wind:SetTheme("Dark")
local page2 = Window:Tab({Title = "Shop Tab",Icon = "shopping-basket"})
local page3 = Window:Tab({Title = "Setting Farm",Icon = "cog"})
local page4 = Window:Tab({Title = "Basic Farm",Icon = "sword"})
local page5 = Window:Tab({Title = "Sub Farm",Icon = "swords"})
local mltab = Window:Tab({Title = "Auto Melee",Icon = "hand-fist"})
local page6 = Window:Tab({Title = "Local Player",Icon = "person-standing"})
local pvp = Window:Tab({Title = "PVP Tab",Icon = "speech"})
local raid = Window:Tab({Title = "Raiding",Icon = "heart"})
local page11 = Window:Tab({Title = "Race V4",Icon = "dna"})
local page12 = Window:Tab({Title = "Dungeon",Icon = "rabbit"})
local page13 = Window:Tab({Title = "Traveling",Icon = "plane"})
local page7 = Window:Tab({Title = "Sea Event",Icon = "fish"})
local page8 = Window:Tab({Title = "Volcano",Icon = "mountain-snow", Locked = true})
local page9 = Window:Tab({Title = "Dojo Quest",Icon = "ribbon", Locked = true})
local page10 = Window:Tab({Title = "Leviathan",Icon = "sparkles", Locked = true})
page2:Select()

--local skidder_if = page1:Section({ Title = "Hello World",})
--UI Settings
--
Window:EditOpenButton({
    Title = "Click Here To Open",
    Icon = "sparkles",
    CornerRadius = UDim.new(1),
    StrokeThickness = 2,
    Color = ColorSequence.new(
    Color3.fromHex("#BC13FE"),
    Color3.fromHex("#FFFFFF")
),
    OnlyMobile = false,
    Enabled = true,
    Draggable = false,
})

-- Shop
page2:Button({
    Title = "Buy Cyborg Race",
    Desc = "",
    Locked = false,
    Callback = function()
        CommF_("CyborgTrainer", "Buy")
    end
})

page2:Section({ Title = "Crafting & Scrolls" })

page2:Button({
    Title = "Craft Common Scroll",
    Desc = "",
    Callback = function()
        CommF_("CraftItem", "Craft", "Common Scroll")
    end
})

page2:Button({
    Title = "Craft Mythical Scroll",
    Callback = function()
        CommF_("CraftItem", "Craft", "Mythical Scroll")
    end
})

page2:Button({
    Title = "Craft Leviathan Crown",
    Callback = function()
        CommF_("CraftItem", "Craft", "LeviathanCrown")
    end
})

page2:Button({
    Title = "Craft Beast Hunter",
    Callback = function()
        CommF_("CraftItem", "Craft", "BeastHunter")
    end
})

page2:Section({ Title = "Race & Stats Custom" })

page2:Button({
    Title = "Reroll Race (Fragments)",
    Callback = function()
        CommF_("BlackbeardReward", "Reroll", "1")
        CommF_("BlackbeardReward", "Reroll", "2")
    end
})

page2:Button({
    Title = "Get Ghoul Race",
    Callback = function()
        CommF_("Ectoplasm", "Change", 4)
    end
})

page2:Button({
    Title = "Reset Stats",
    Callback = function()
        CommF_("BlackbeardReward", "Refund", "1")
        CommF_("BlackbeardReward", "Refund", "2")
    end
})

page2:Section({ Title = "Abilities" })

page2:Button({
    Title = "Buy Geppo (Jump)",
    Callback = function()
        CommF_("BuyHaki", "Geppo")
    end
})

page2:Button({
    Title = "Buy Buso (Haki)",
    Callback = function()
        CommF_("BuyHaki", "Buso")
    end
})

page2:Button({
    Title = "Buy Soru",
    Callback = function()
        CommF_("BuyHaki", "Soru")
    end
})

page2:Section({ Title = "Weapons Shop" })

page2:Button({
    Title = "Buy Soul Cane",
    Callback = function()
        CommF_("BuyItem", "Soul Cane")
    end
})

page2:Button({
    Title = "Buy Bisento",
    Callback = function()
        CommF_("BuyItem", "Bisento")
    end
})

page2:Button({
    Title = "Buy Kabucha",
    Callback = function()
        CommF_("BlackbeardReward", "Slingshot", "1")
        CommF_("BlackbeardReward", "Slingshot", "2")
    end
})

-- Setting
page3:Toggle({Title = "Use Sword",Desc = "Change Melee > Sword",
Icon = "play",Type = "Toggle",
Value = false,
Callback = function(x)
_G.USESWORD = x
end})

page3:Toggle({Title = "Use M1",Desc = "Attack M1",
Icon = "play",Type = "Toggle",
Value = false,
Callback = function(x)
_G.USEDF = x
end})

page3:Toggle({Title = "Use Gun",Desc = "dont enable cuz isnt support",
Icon = "play",Type = "Toggle",
Value = false,
Callback = function(x)
_G.UseGun = x
end})

page3:Section({ Title = "Yourself" })

page3:Toggle({Title = "Auto Activate V3",Desc = "",
Icon = "play",Type = "Toggle",
Value = false,
Callback = function(x)
_G.EnableV3 = x
end})

page3:Toggle({Title = "Auto Activate V4",Desc = "",
Icon = "play",Type = "Toggle",
Value = false,
Callback = function(x)
_G.EnableV4 = x
end})

page3:Toggle({Title = "Auto Summon Dough King",Desc = "if have cup, enable it",
Icon = "play",Type = "Toggle",
Value = false,
Callback = function(x)
_G.SpawnDoughKing = x
end})

page3:Toggle({Title = "Walk On Water",Desc = "it may or may not cuz lag depending on ur device power",
Icon = "play",Type = "Toggle",
Value = _G.WalkWt or false,
Callback = function(x)
_G.WalkWt = x
     task.spawn(function()
            local map = workspace:FindFirstChild("Map")
            local water = map and map:FindFirstChild("WaterBase-Plane")
            if water then
                if _G.WalkWt then
                    water.Size = Vector3.new(20000, 112, 20000)
                    water.CanCollide = true
                else
                    water.Size = Vector3.new(1000, 80, 1000)
                    water.CanCollide = false
                end
            end
        end)
end})

page3:Section({ Title = "Your Screen" })

page3:Toggle({Title = "Hide Notification",Desc = "",
Icon = "play",Type = "Toggle",
Value = false,
Callback = function(x)
_G.HideNotify = x
end})

page3:Toggle({Title = "White Screen",Desc = "",
Icon = "play",Type = "Toggle",
Value = false,
Callback = function(x)
_G.WhiteScreen = x
end})

--FARMING

farmmode = page4:Dropdown({
    Title = "Select Farm Mode",
    Desc = "",
    Values = { "Farm Level", "Farm Bones", "Farm Katakuri" },
    Value = "Farm Level",
    Callback = function(x) 
        SelectMode = x
    end
})

page4:Toggle({
    Title = "Start Farm",
    Desc = "",
    Icon = "play",
    Type = "Toggle",
    Value = false,
    Callback = function(x)
        _G.StartFarm = x
    end
})
page4:Section({ Title = "i dont know" })
page4:Toggle({
    Title = "Auto Kill Tyrant Of The Skies",
    Desc = "",
    Icon = "play",
    Type = "Toggle",
    Value = false,
    Callback = function(x)
        _G.AutoKillTyrant = x
    end
})

page4:Toggle({
    Title = "Auto Summon Tyrant",
    Desc = "",
    Icon = "play",
    Type = "Toggle",
    Value = false,
    Callback = function(x)
        _G.AutoSummonTyrant = x
    end
})


page4:Toggle({
    Title = "Aura Farm",
    Desc = "farm nearby mob stud 1000",
    Icon = "play",
    Type = "Toggle",
    Value = false,
    Callback = function(x)
        _G.NearbyFarm = x
    end
})
page4:Section({ Title = "quest sea servicd" })

page4:Toggle({
    Title = "Auto Dressrosa",
    Desc = "make sure u alr reach lv 700",
    Icon = "play",
    Type = "Toggle",
    Value = false,
    Callback = function(x)
        _G.AutoSea2 = x
    end
})

page4:Toggle({
    Title = "Auto Zou",
    Desc = "same dressrosa make sure u alr reach lv 1500",
    Icon = "play",
    Type = "Toggle",
    Value = false,
    Callback = function(x)
        _G.AutoSea3 = x
    end
})

page4:Section({ Title = "money service" })

page4:Toggle({
    Title = "Auto Chest < Tween >",
    Desc = "very safety",
    Value = false,
    Callback = function(x) _G.AutoChest = x end
})

page4:Toggle({
    Title = "Auto Chest < Teleport >",
    Desc = "ultra risk",
    Value = false,
    Callback = function(x) _G.AutoChestTP = x end
})

page4:Toggle({
    Title = "Stop If Have Item",
    Desc = "key darkbeard, cup, etc, idk",
    Value = false,
    Callback = function(x) _G.StopItem = x end
})

page4:Section({ Title = "fruit service" })

page4:Toggle({
    Title = "Tween Collect Fruit",
    Desc = "",
    Value = false,
    Callback = function(x) _G.CollectFruit = x end
})

page4:Toggle({
    Title = "Auto Store Fruit",
    Desc = "Automatically store fruits in inventory",
    Value = false,
    Callback = function(x) _G.StoreFruit = x end
})

page4:Section({ Title = "metarial service" })

page4:Dropdown({
    Title = "Select Metarial",
    Values = MaterialList,
    Callback = function(x) SelectMetarial = x end
})

page4:Toggle({
    Title = "Start Farm Metarial",
    Value = _G.StartMetarial or false,
    Callback = function(x) _G.StartMetarial = x end
})

page4:Section({ Title = "haki" })

page4:Toggle({
    Title = "Auto Observation",
    Desc = "",
    Icon = "play",
    Type = "Toggle",
    Value = false,
    Callback = function(x)
        _G.AutoHaki = x
    end
})

page4:Toggle({
    Title = "HOP for Auto Observation",
    Desc = "",
    Icon = "play",
    Type = "Toggle",
    Value = false,
    Callback = function(x)
        _G.HakiHop = x
    end
})

-- PAGE SUB FARM
elitestat = page5:Section({ Title = "|| Elite Status: Inlitizing ||" })
task.spawn(function()
    local eliti = {"Diablo", "Deandre", "Urban"}  
    while task.wait(1) do
        local checkfl = false
        for _, name in ipairs(eliti) do
            if rs:FindFirstChild(name) or wene:FindFirstChild(name) then
                checkfl = true
                break
            end
        end
        if checkfl then
            elitestat:SetTitle("|| Elite Status: SPAWNED! ||")
        else
            elitestat:SetTitle("|| Elite Status: NOT FOUND! ||")
        end
    end
end)

page5:Section({ Title = "Sea 3 Features" })

page5:Toggle({
    Title = "Auto Elite",
    Desc = "",
    Icon = "play",
    Type = "Toggle",
    Value = false,
    Callback = function(x)
        _G.AutoElite = x
    end
})

page5:Toggle({
    Title = "Auto Yama",
    Value = false,
    Callback = function(x) _G.AutoYama = x end
})

page5:Toggle({
    Title = "Auto Tushita",
    Value = false,
    Callback = function(x) _G.AutoTushita = x end
})

page5:Toggle({
    Title = "Auto Kill Rip Indra",
    Value = false,
    Callback = function(x) _G.AutoIndra = x end
})

page5:Toggle({
    Title = "Auto Dough King",
    Desc = "only enable if you already have a cup",
    Value = false,
    Callback = function(x) _G.AutoDoughKing = x end
})

page5:Toggle({
    Title = "Auto Soul Reaper",
    Value = false,
    Callback = function(x) _G.AutoReaper = x end
})

page5:Toggle({
    Title = "Auto Raid Castle",
    Desc = "",
    Icon = "play",
    Type = "Toggle",
    Value = false,
    Callback = function(x)
        _G.AutoRaidCastle = x
    end
})
page5:Section({ Title = "Sea 2 Features" })
page5:Toggle({
    Title = "Auto Factory",
    Desc = "",
    Icon = "play",
    Type = "Toggle",
    Value = false,
    Callback = function(x)
        _G.AutoFactory = x
    end
})

page5:Toggle({
    Title = "Auto Ectoplasm",
    Value = false,
    Callback = function(x) _G.AutoEcto = x end
})

page5:Toggle({
    Title = "Auto Kill Darkbeard",
    Value = false,
    Callback = function(x) _G.AutoDarkbeard = x end
})
		
page5:Toggle({
    Title = "Auto Rengoku",
    Value = false,
    Callback = function(x) _G.AutoRengoku = x end
})

page5:Section({ Title = "Sea 1 Features" })

page5:Toggle({
    Title = "Auto Pole V1",
    Value = false,
    Callback = function(x) _G.AutoPoleV1 = x end
})

page5:Toggle({
    Title = "Auto Saber",
    Value = false,
    Callback = function(x) _G.AutoSaber = x end
})

page6:Toggle({
    Title = "Auto Enable Observation",
    Desc = "",
    Value = false,
    Callback = function(x) _G.AutoEnableKen = x end
})

page6:Toggle({
    Title = "Auto Rejoin",
    Desc = "Automatically reconnect if disconnected",
    Value = false,
    Callback = function(x) _G.AutoRejoin = x end
})

page6:Section({ Title = "GP Service" })

local SliderWS = page6:Slider({
    Title = "WalkSpeed",
    Desc = "min50 max500",
    Step = 1,
    Value = {
        Min = 20,
        Max = 350,
        Default = 70,
    },
    Callback = function(value)
        _G.WSValue = value
    end
})

page6:Toggle({
    Title = "Enable WalkSpeed",
    Desc = "",
    Value = false,
    Callback = function(x) 
        _G.WalkS = x 
    end
})

local SliderJP = page6:Slider({
    Title = "JumpPower",
    Desc = "min50 max 500",
    Step = 1,
    Value = {
        Min = 50,
        Max = 500,
        Default = 50,
    },
    Callback = function(value)
        _G.JPValue = value
    end
})

page6:Toggle({
    Title = "Enable JumpPower",
    Desc = "",
    Value = false,
    Callback = function(x) 
        _G.JumpP = x 
    end
})

local defaultWS = 20
local defaultJP = 50
task.spawn(function()
    while task.wait() do
        pcall(function()
            local char = game.Players.LocalPlayer.Character
            local hum = char and char:FindFirstChild("Humanoid")            
            if hum then
                if _G.WalkS then
                    hum.WalkSpeed = _G.WSValue or 70
                else
                    if hum.WalkSpeed ~= defaultWS and not _G.WalkS then
                        hum.WalkSpeed = defaultWS
                    end
                end
                if _G.JumpP then
                    hum.UseJumpPower = true
                    hum.JumpPower = _G.JPValue or 50
                else
                    if hum.JumpPower ~= defaultJP and not _G.JumpP then
                        hum.JumpPower = defaultJP
                    end
                end
            end
        end)
    end
end)
mt = getrawmetatable(game)
oldIndex = mt.__index
oldNewIndex = mt.__newindex
setreadonly(mt, false)
mt.__newindex = newcclosure(function(t, k, v)
    if checkcaller() then return oldNewIndex(t, k, v) end
    if _G.WalkS and t:IsA("Humanoid") and k == "WalkSpeed" then
        return
    end
    if _G.JumpP and t:IsA("Humanoid") and k == "JumpPower" then
        return
    end
    return oldNewIndex(t, k, v)
end)
setreadonly(mt, true)

page6:Section({ Title = "HOP Service" })
page6:Button({
    Title = "HOP Server Low",
    Callback = function()
        Server_Hop("niga")
    end
})
page6:Section({ Title = "Gacha Service" })

bonecheck = page6:Section({ Title = "Your Bone: 0" })
task.spawn(function()
    while task.wait(2) do
        local count = GetCountMaterials("Bones")
        bonecheck:SetTitle("Your Bone: " .. tostring(count))
    end
end)

page6:Toggle({
    Title = "Random Fruit",
    Desc = "",
    Value = false,
    Callback = function(x) _G.RandomFruit = x end
})

page6:Toggle({
    Title = "Random Bones",
    Desc = "",
    Value = false,
    Callback = function(x) _G.RandomBones = x end
})

page6:Section({ Title = "ESP Service" })

page6:Toggle({Title = "ESP Fruit", Value = false, Callback = function(x) _G.ESPFruit = x end})
page6:Toggle({Title = "ESP Players", Value = false, Callback = function(x) _G.ESPPlayer = x end})
page6:Toggle({Title = "ESP Chest", Value = false, Callback = function(x) _G.ESPChest = x end})
page6:Toggle({Title = "ESP Mirage", Value = false, Callback = function(x) _G.ESPMirage = x end})
page6:Toggle({Title = "ESP Advanced Fruit Dealer", Value = false, Callback = function(x) _G.ESPNpcMirage = x end})

page6:Section({ Title = "Stats Service" })

page6:Toggle({Title = "Auto Upgrade Melee", Desc = "", Value = false, Callback = function(x) _G.StatMelee = x end})
page6:Toggle({Title = "Auto Upgrade Health", Desc = "", Value = false, Callback = function(x) _G.StatHealth = x end})
page6:Toggle({Title = "Auto Upgrade Sword", Desc = "", Value = false, Callback = function(x) _G.StatSword = x end})
page6:Toggle({Title = "Auto Upgrade Gun", Desc = "", Value = false, Callback = function(x) _G.StatGun = x end})
page6:Toggle({Title = "Auto Upgrade Fruit", Desc = "", Value = false, Callback = function(x) _G.StatFruit = x end})


page11:Toggle({
    Title = "Auto Upgrade V1-V3",
    Desc = "Support: Human, Mink Cyborg\nUnSupport: Fish, Ghoul, Angle",
    Value = false,
    Callback = function(x) _G.AutoV1V3 = x end
})

page11:Section({ Title = "Mirage Service" })

page11:Toggle({
    Title = "Fully Pull Lever < Need Mirage >",
    Desc = "Go To Mirage -> Look Moon -> Get Gear",
    Value = false,
    Callback = function(x) _G.AutoGetGear = x end
})

page11:Toggle({
    Title = "Tween To Mirage",
    Desc = "just tween to mirage",
    Value = false,
    Callback = function(x) _G.GoToMirage = x end
})

page11:Section({ Title = "Trainning Service" })

fullytrial = page11:Toggle({
    Title = "Auto Trial | Buy Gear",
    Desc = "",
    Value = false,
    Callback = function(x) _G.AutoTrialV4 = x end
})

--DUNGEON

page12:Toggle({
    Title = "Auto Dungeon",
    Desc = "Fully Dungeon",
    Value = false,
    Callback = function(x) _G.AutoDungeon = x end
})

page12:Toggle({
    Title = "Auto Join Dungeon",
    Desc = "Auto join in the lobby dungeon\nmake sure u have enough energy",
    Value = false,
    Callback = function(x) _G.AutoJoinDungeon = x end
})

page12:Toggle({
    Title = "Auto Select Cards (Buff)",
    Desc = "Health>Defense>Armor>Melee (or Sword if Use Sword on)",
    Value = false,
    Callback = function(x) _G.AutoPickCard = x end
})

--TRAVEL
page13:Button({
    Title = "Travel Old World",
    Callback = function()
        CommF_("TravelMain")
    end
})

page13:Button({
    Title = "Travel Dressrosa",
    Callback = function()
        CommF_("TravelDressrosa")
    end
})

page13:Button({
    Title = "Travel Zou",
    Callback = function()
        CommF_("TravelZou")
    end
})

page13:Section({ Title = "Travelling Service" })
page13:Dropdown({
    Title = "Select Island",
    Values = AvailableIslands,
    Callback = function(x) SelectIsland = x end
})

page13:Toggle({
    Title = "Start Tween Travel",
    Desc = "",
    Value = false,
    Callback = function(x) _G.StartTravel = x end
})

--Sea Event

local rodstat = page7:Section({ Title = "Fishing Stat: Waiting for rod...." })

task.spawn(function()
    while task.wait(1) do
        local char = lp.Character
        local rodName = FishingSettings.SelectedRod
        if char and rodName then
            local rod = char:FindFirstChild(rodName)
            if rod then
                local state = rod:GetAttribute("ServerState") or "Unknown"
                local loc = FishingSettings.LastCastLocation
                local text = "Rod State: " .. tostring(state)
                if loc then
                    text = text .. "\nPos: " .. math.floor(loc.X) .. ", " .. math.floor(loc.Y) .. ", " .. math.floor(loc.Z)
                end
                rodstat:SetTitle(text)
            else
                rodstat:SetTitle("Rod State: Not Equipped")
            end
        else
            rodstat:SetTitle("Rod State: Waiting for selection...")
        end
    end
end)

page7:Dropdown({
    Title = "Select Rod",
    Values = {"Fishing Rod","Gold Rod","Shark Rod","Shell Rod","Treasure Rod","Shark (Corrupted)","Shell (Celestial)"},
    Callback = function(x) FishingSettings.SelectedRod = x end
})
page7:Dropdown({
    Title = "Select Bait",
    Values = {"Basic Bait","Kelp Bait","Good Bait","Abyssal Bait","Frozen Bait","Epic Bait","Carnivore Bait"},
    Callback = function(x) FishingSettings.SelectedBait = x end
})

page7:Button({
    Title = "Open Fish Index",
    Callback = function()
        lp:WaitForChild("PlayerGui"):SetAttribute("FishIndexVisible", true)
    end})


page7:Toggle({
    Title = "Auto Fishing",
    Desc = "",
    Value = false,
    Callback = function(x) 
        _G.StartFishsing = x 
    end
})

page7:Section({ Title = "Leviathan Service" })
leviastat = page7:Section({ Title = "|| Bribe Status : Inlitizing... ||" })
page7:Button({
    Title = "Leviathan Bribe",
    Callback = function()
        noob = CommF_("InfoLeviathan", "2")
        leviastat:SetTitle(noob)
end})
local inf_levia = CFrame.new(-100000, 31, 37016.25)
local buy_boat_cf = CFrame.new(-16202.62, 9.30, 473.52)
page7:Dropdown({
    Title = "Select Boat [ Leviathan ]",
    Values = {'Dinghy', 'PirateSloop', 'PirateBrigade', 'PirateGrandBrigade', 'MarineSloop', 'MarineBrigade', 'MarineGrandBrigade', 'Beast Hunter','Lantern','Guardian','Grand Brigade','Sloop','The Sentinel'},
    Callback = function(x) 
        _G.SelectBoatLeviathan = x 
    end
})
page7:Toggle({
    Title = "Auto Find Leviathan",
    Desc = "make sure alr enough 5 players\nand its ur boat",
    Value = false,
    Callback = function(x) 
        _G.FindLeviathan = x 
        if not x then stopboat() end
    end
})
page7:Toggle({
    Title = "Tween Frozen Dimension",
    Desc = "make sure island alr spawn",
    Value = false,
    Callback = function(x) 
        TP(worigin.Locations:FindFirstChild("Frozen Dimension").CFrame *CFrame.new(0,250,0))
    end
})
page7:Toggle({
    Title = "ESP Your Boat",
    Value = false,
    Callback = function(x) 
        _G.ESPBoat = x       
        if _G.ESPBoat then
            task.spawn(function()
                while _G.ESPBoat do
                    local myBoat = checkboat()
                    if myBoat then
                        AddEsp(myBoat)
                    end
                    task.wait(1)
                end
            end)
        else
            for _, v in pairs(workspace.Boats:GetDescendants()) do
                if v.Name == "RiseESP" then v:Destroy() end
            end
        end
    end
})

page7:Section({ Title = "Prehistoric Service" })
page7:Toggle({
    Title = "Auto Find Prehistoric",
    Desc = "",
    Value = false,
    Callback = function(x) 
        _G.Prehistoric = x 
        if not x then stopboat() end
    end
})
page7:Toggle({
    Title = "Tween Prehistoric Island",
    Desc = "make sure island alr spawn",
    Value = false,
    Callback = function(x) 
        TP(worigin.Locations:FindFirstChild("Prehistoric Island").CFrame *CFrame.new(0,250,0))
    end
})


page7:Section({ Title = "Azure Ember Service" })
page7:Toggle({
    Title = "Auto Find Kitsune Island",
    Desc = "",
    Value = false,
    Callback = function(x) 
        _G.FindKit = x
    end
})

_G.SetAzureEmber = 10 
page7:Slider({
    Title = "Set Azure Ember",
    Description = "",
    Min = 1,
    Max = 25,
    Default = 10,
    Callback = function(v)
        _G.SetAzureEmber = v
    end
})


page7:Toggle({
    Title = "Collect Azure Ember",
    Desc = "",
    Value = false,
    Callback = function(x) 
        _G.EmberCollect = x
    end
})

page7:Section({ Title = "Mirage Service" })

page7:Toggle({
    Title = "Auto Find Mirage",
    Desc = "",
    Value = false,
    Callback = function(x) 
        _G.FindMirage = x
    end
})

page7:Toggle({
    Title = "Tween Highest Mirage",
    Desc = "",
    Value = false,
    Callback = function(x) 
        _G.HighMirage = x
    end
})

page7:Toggle({
    Title = "Tween Blue Gear",
    Desc = "",
    Value = false,
    Callback = function(x) 
        _G.BlueGear = x
    end
})


local function FindBlueGear()
    local island = workspace.Map:FindFirstChild("MysticIsland")
    if not island then return nil end
    local gear = island:FindFirstChild("Blue Gear", true)
    if gear then return gear end
    for _, v in ipairs(island:GetDescendants()) do
        if v:IsA("MeshPart") and v.Material == Enum.Material.Neon then
            if v.Size.X < 5 then 
                return v
            end
        end
    end
    return nil
end
task.spawn(function()
    while task.wait(0.3) do
        if _G.BlueGear and sea3 then
            pcall(function()
                local gear = FindBlueGear()
                if gear then
                    TP(gear.CFrame)
                end
            end)
        end
    end
end)



local cachedHighestPoint = nil
local function GetHighestPoint()
    local island = workspace.Map:FindFirstChild("MysticIsland")
    if not island then return nil end
    if cachedHighestPoint and cachedHighestPoint.Parent == island then
        return cachedHighestPoint
    end
    for _, v in ipairs(island:GetDescendants()) do
        if v:IsA("MeshPart") and v.MeshId == "rbxassetid://6745037796" then
            cachedHighestPoint = v
            return v
        end
    end
    return nil
end

task.spawn(function()
    while task.wait(0.5) do
        if _G.HighMirage and sea3 then
            pcall(function()
                local island = workspace.Map:FindFirstChild("MysticIsland")
                if island then
                    local highestPart = GetHighestPoint()
                    if highestPart then
                        local targetCFrame = highestPart.CFrame * CFrame.new(0, 212, 0)
                        TP(targetCFrame)
                    end
                else
                    cachedHighestPoint = nil
                end
            end)
        else
            cachedHighestPoint = nil
        end
    end
end)

local function GetMaterialCount(itemName)
    local inv = game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("getInventory")
    if inv then
        for _, item in pairs(inv) do
            if item.Name == itemName then
                return item.Count
            end
        end
    end
    return 0
end
task.spawn(function()
    while task.wait(0.7) do
        if _G.EmberTrade and sea3 then
            pcall(function()
                local currentEmber = GetMaterialCount("Azure Ember")
                local targetCount = _G.SetAzureEmber or 10              
                if currentEmber >= targetCount then
                    local net = game:GetService("ReplicatedStorage").Modules.Net
                    local commF = game:GetService("ReplicatedStorage").Remotes.CommF_
                    if net:FindFirstChild("RF/KitsuneStatuePray") then
                        net["RF/KitsuneStatuePray"]:InvokeServer()
                    end
                    CommF_("KitsuneStatuePray")
                    task.wait(1) 
                end
            end)
        end
    end
end)


task.spawn(function()
    while task.wait() do
        if _G.EmberCollect and sea3 then
            for _, v in pairs(workspace:GetChildren()) do
                if v.Name == "AttachedAzureEmber" then
                    local targetPart = v:FindFirstChild("Part")
                    if targetPart then
                        local dist = (targetPart.Position - lp.Character.HumanoidRootPart.Position).Magnitude
                        if dist > 5 then
                            TP(targetPart.CFrame)
                        end
                        break 
                    end
                end
            end
        end
    end
end)


local function check_kit()
    if worigin.Locations:FindFirstChild('KitsuneIsland') then
        return true
    end
    return false
end

local function check_frozen()
    if worigin.Locations:FindFirstChild('Frozen Dimension') then
        return true
    end
    return false
end

local function check_prehistoric()
    if worigin.Locations:FindFirstChild('Prehistoric Island') then
        return true
    end
    return false
end

local function check_mirage()
    if worigin.Locations:FindFirstChild('MysticIsland') then
        return true
    end
    return false
end

local function SetEventMode(modeName, state)
    local allModes = {"FindLeviathan", "Prehistoric", "FindKit", "FindMirage"}
    if state then
        for _, mode in ipairs(allModes) do
            _G[mode] = (mode == modeName)
        end
        print("[ Rise ApI ] switch " .. modeName)
    else
        _G[modeName] = false
        stopboat()
    end
end

task.spawn(function()
    while task.wait(0.5) do
        local activeCheck = nil
        if _G.FindLeviathan then activeCheck = check_frozen
        elseif _G.Prehistoric then activeCheck = check_prehistoric
        elseif _G.FindKit then activeCheck = check_kit
        elseif _G.FindMirage then activeCheck = check_mirage
        end
        if activeCheck then
            pcall(function()
                if activeCheck() then
                    stopboat()
                else
                    local myBoat = checkboat()
                    if not myBoat then
                        if getdis(buy_boat_cf) > 15 then
                            TP(buy_boat_cf)
                        else
                            CommF_("BuyBoat", _G.SelectBoatLeviathan)
                        end
                    else
                        local char = lp.Character
                        local hum = char and char:FindFirstChild("Humanoid")
                        if hum then
                            if not hum.Sit then
                                if myBoat:FindFirstChild("VehicleSeat") then
                                    TP(myBoat.VehicleSeat.CFrame)
                                end
                            else
                                tweenboat(inf_levia)
                            end
                        end
                    end
                end
            end)
        end
    end
end)







page7:Section({ Title = "Sea Event Service [ Not Working Now ]" })

local SeaSettings = {
    SelectedBoat = "Dinghy",
    SelectZone = "Level 1",
    AutoPrehistoric = false,
    Targets = {},
    Zones = {
        ["Level 1"] = CFrame.new(-21998.375, 30, -682.309),
        ["Level 2"] = CFrame.new(-26779.5215, 30, -822.858),
        ["Level 3"] = CFrame.new(-31171.957, 30, -2256.9377),
        ["Level 4"] = CFrame.new(-34054.6875, 30.2187, -2560.1201),
        ["Level 5"] = CFrame.new(-38887.5547, 30, -2162.9902),
        ["Level 6"] = CFrame.new(-44541.7617, 30, -1244.8584),
        ["Infinite"] = CFrame.new(-100000, 31, 37016.25)
    }
}


page7:Dropdown({
    Title = "Select Boat",
    Values = {'Dinghy', 'PirateSloop', 'PirateBrigade', 'PirateGrandBrigade', 'MarineSloop', 'MarineBrigade', 'MarineGrandBrigade', 'Beast Hunter','Lantern','Guardian','Grand Brigade','Sloop','The Sentinel'},
    Callback = function(x) SeaSettings.SelectedBoat = x end
})

--[[findprr = page7:Toggle({
    Title = "Auto Find Prehistoric",
    Value = false,
    Callback = function(x) print("not work not release") end
})]]

page7:Dropdown({
    Title = "Zone Select",
    Values = {'Level 1', 'Level 2', 'Level 3', 'Level 4', 'Level 5', 'Level 6', 'Infinite'},
    Callback = function(x) SeaSettings.SelectZone = x end
})

page7:Dropdown({
    Title = "Select Entity",
    Values = {"Shark", "Piranha", "Fish Crew Member", "Terrorshark", "FishBoat", "PirateBrigade", "PirateGrandBrigade", "Sea Beast"},
    Multi = true,
    Callback = function(x) SeaSettings.Targets = x end
})

startsea = page7:Toggle({
    Title = "Start Sea Event",
    Value = false,
    Callback = function(x) print("not work not release") end
})

-- PVP
_G.SelectedPlayer = nil
local function GetPlayerList()
    local list = {}
    for _, v in ipairs(game:GetService("Players"):GetPlayers()) do
        if v ~= lp then
            table.insert(list, v.Name)
        end
    end
    return list
end

local selectpl = pvp:Dropdown({
    Title = "Select Player",
    Values = GetPlayerList(),
    Callback = function(x) 
        _G.SelectedPlayer = x 
    end
})

pvp:Button({
    Title = "Refresh Player List",
    Callback = function()
        local newList = GetPlayerList()
        selectpl:Refresh(newList, true)
    end
})

pvp:Toggle({
    Title = "Spectate Player",
    Value = false,
    Callback = function(x)
        _G.SpectatePlayer = x
    end
})

pvp:Toggle({
    Title = "Tween To Player",
    Value = false,
    Callback = function(x)
        _G.TeleportToPlayer = x
    end
})
task.spawn(function()
    while task.wait() do
        pcall(function()
            local camera = workspace.CurrentCamera
            local target = _G.SelectedPlayer and game:GetService("Players"):FindFirstChild(_G.SelectedPlayer)
            if _G.SpectatePlayer and target and target.Character and target.Character:FindFirstChild("Humanoid") then
                camera.CameraSubject = target.Character.Humanoid
            else
                if lp.Character and lp.Character:FindFirstChild("Humanoid") then
                    if camera.CameraSubject ~= lp.Character.Humanoid then
                        camera.CameraSubject = lp.Character.Humanoid
                    end
                end
            end
            if _G.TeleportToPlayer and target and target.Character and target.Character:FindFirstChild("HumanoidRootPart") then
                TP(target.Character.HumanoidRootPart.CFrame)
            end
        end)
    end
end)


-- RAIDING

local function isRaidActive()
    return lp.PlayerGui.Main.TopHUDList.RaidTimer.Visible
end
local function getRaidIsland()
    for i = 5, 1, -1 do
        if workspace.Map.RaidMap:FindFirstChild("RaidIsland"..i) then
            return i
        end
    end
    return 0
end

local Raidslist = {}
local success, RaidsModule = pcall(function() return require(game.ReplicatedStorage.Raids) end)

if success and RaidsModule then
    for _, v in pairs(RaidsModule.raids) do 
        table.insert(Raidslist, tostring(v)) 
    end
    if RaidsModule.advancedRaids then
        for _, v in pairs(RaidsModule.advancedRaids) do 
            table.insert(Raidslist, tostring(v)) 
        end
    end
else
    Raidslist = {"Flame", "Ice", "Quake", "Light", "Dark", "Spider", "Rumble", "Magma", "Buddha", "Sand"} -- Dự phòng nếu require lỗi
end


task.spawn(function()
    while task.wait(1) do
        if _G.UnstoreFruit then
            pcall(function()
                local hasFruit = false
                for _, v in pairs(lp.Backpack:GetChildren()) do if v.Name:find("Fruit") then hasFruit = true break end end
                for _, v in pairs(lp.Character:GetChildren()) do if v.Name:find("Fruit") then hasFruit = true break end end
                if not hasFruit then
                    local fruits = CommF_("getInventoryFruits")
                    for _, v in pairs(fruits) do
                        if v.Price <= _G.SetPriceFruit then
                            CommF_("LoadFruit", v.Name)
                            break
                        end
                    end
                end
            end)
        end
    end
end)

task.spawn(function()
    while task.wait(0.5) do
        if _G.AutoLaw then
            pcall(function()
                local order = workspace.Enemies:FindFirstChild("Order") or game.ReplicatedStorage:FindFirstChild("Order")              
                if not order then
                    if not lp.Backpack:FindFirstChild("Microchip") and not lp.Character:FindFirstChild("Microchip") then
                        CommF_("BlackbeardReward", "Microchip", "1")
                        CommF_("BlackbeardReward", "Microchip", "2")
                    else
                        local button = workspace.Map.CircleIsland.RaidSummon.Button.Main.ClickDetector
                        if button then fireclickdetector(button) end
                    end
                else
                    local boss = workspace.Enemies:FindFirstChild("Order")
                    if boss and boss:FindFirstChild("HumanoidRootPart") then
                        Attack(boss, function()
                            return not _G.AutoLaw or not boss.Parent or boss.Humanoid.Health <= 0
                        end)
                    else
                        TP(CFrame.new(-6217, 28, -5053))
                    end
                end
            end)
        end
    end
end)

task.spawn(function()
    while task.wait(0.5) do
        if _G.StartRaid then
            pcall(function()
                if isRaidActive() then
                    local enemy = nil
                    for _, v in pairs(workspace.Enemies:GetChildren()) do
                        if v:FindFirstChild("Humanoid") and v.Humanoid.Health > 0 then
                            enemy = v
                            break
                        end
                    end
                    if enemy then
                        Attack(enemy, function()
                            return not _G.StartRaid or not isRaidActive() or not enemy.Parent or enemy.Humanoid.Health <= 0
                        end)
                    else
                        local currentIsland = getRaidIsland()
                        if currentIsland > 0 then
                            local islandPart = workspace._WorldOrigin.Locations:FindFirstChild("Island "..currentIsland)
                            if islandPart then
                                TP(islandPart.CFrame * CFrame.new(0, 50, 0))
                            end
                        end
                    end
                else
                    if not lp.Backpack:FindFirstChild("Special Microchip") and not lp.Character:FindFirstChild("Special Microchip") then
                        CommF_("RaidsTrainer", "Verify")
                    else
                        if sea2 then
                            local btn = workspace.Map.CircleIsland.RaidSummon2.Button.Main.ClickDetector
                            if btn then fireclickdetector(btn) end
                        elseif sea3 then
                            CommF_("requestEntrance", Vector3.new(-5083, 314, -3175))
                            task.wait(0.5)
                            local btn = workspace.Map["Boat Castle"].RaidSummon2.Button.Main.ClickDetector
                            if btn then fireclickdetector(btn) end
                        end
                    end
                end
            end)
        end
        if _G.AutoAwakening then
            CommF_("Awakener", "Awaken")
        end
    end
end)

task.spawn(function()
    while task.wait(0.5) do
        pcall(function()
            if isRaidActive() then
                TimeRaidParagraph:SetDesc(lp.PlayerGui.Main.TopHUDList.RaidTimer.Text)
                local currentIsland = getRaidIsland()
                niha1:SetTitle("| Current Island Tracking |\nIsland: " .. (currentIsland > 0 and currentIsland or "Loading"))
            else
                niha:SetTitle("| Raid Timer Tracking |\n| Inlitizing... |")
                niha1:SetTitle("| Current Island Tracking |\n| Idle... |")
            end
        end)
    end
end)


_G.SelectedChip = ""
_G.SetPriceFruit = 25000
_G.UnstoreFruit = false
_G.StartRaid = false
_G.AutoAwakening = false
_G.AutoLaw = false



raid:Toggle({
    Title = "Tween to Lab",
    Desc = "sea2 or 3 same func",
    Value = false,
    Callback = function(x)
        if sea2 then
            TP(CFrame.new(-6438.7, 250.6, -4501.5))
        elseif sea3 then
            TP(CFrame.new(-5017.4, 314.8, -2823.0))
        end
    end
})

niha = raid:Section({ Title = "| Raid Timer Tracking |\n| Inlitizing... |" })
niha1 = raid:Section({ Title = "| Current Island Tracking |\n| Inlitizing... |" })


raid:Dropdown({
    Title = "Select Chip",
    Values = Raidslist,
    Callback = function(x) _G.SelectedChip = x end
})
local nigahhh = raid:Slider({
    Title = "Fruit Price",
    Desc = "",
    Step = 1,
    Value = {
        Min = 1,
        Max = 10000000,
        Default = 25000,
    },
    Callback = function(value)
        _G.SetPriceFruit = value
    end
})

raid:Toggle({
    Title = "Auto Get Fruit",
    Desc = "will get fruit from ur inventory\nmake sure u alr select price",
    Value = false,
    Callback = function(x) _G.UnstoreFruit = x end
})

raid:Toggle({
    Title = "Start Auto Rading",
    Desc = "Killing mob for complete raid\nor idk hehe",
    Value = false,
    Callback = function(x) _G.StartRaid = x end
})

raid:Toggle({
    Title = "Auto Awakening",
    Desc = "this func will auto talk with npc to awakening fruit\nmake sure ure select correct chip",
    Value = false,
    Callback = function(x) _G.AutoAwakening = x end
})

raid:Section({ Title = "Law Service" })

raid:Toggle({
    Title = "Auto Law [ Raid ] ",
    Desc = "this func will auto buy chip\nmake sure ure enough fragment",
    Value = false,
    Callback = function(x) _G.AutoLaw = x end
})


-- Auto Melee

idk = mltab:Toggle({
    Title = "Auto Get SuperHuman",
    Value = false,
    Callback = function(x) _G.AutoSphm = x end
})

idk1 = mltab:Toggle({
    Title = "Auto Get Death Step",
    Value = false,
    Callback = function(x) _G.AutoDeathStep = x end
})

idk2 = mltab:Toggle({
    Title = "Auto Get Sharkman Karate",
    Value = false,
    Callback = function(x) _G.AutoSharkman = x end
})

idk3 = mltab:Toggle({
    Title = "Auto Get Electric Claw",
    Value = false,
    Callback = function(x) _G.ElecClaw = x end
})

idk4 = mltab:Toggle({
    Title = "Auto Get Dragon Talon",
    Value = false,
    Callback = function(x) _G.DraTalon = x end
})

idk5 = mltab:Toggle({
    Title = "Auto Get GodHuman",
    Value = false,
    Callback = function(x) _G.AutoGH = x end
})

--[[spawn(function()
    while task.wait() do
        if _G.OnlyBone then
            local mob = Check_Monster(watdsfyck)
            if mob then
                Attack(mob, function()
                    return not _G.OnlyBone
                end)
            else
                TP(CFrame.new(-9497, 172, 6151))
            end
        end
    end
end)

spawn(function()
    while task.wait() do
        if _G.OnlySea2 then
            local mob = Check_Monster({"Snow Lurker", "Arctic Warrior"})
            if mob then
                Attack(mob, function()
                    return not _G.OnlySea2
                end)
            else
                TP(CFrame.new(-9497, 172, 6151))
            end
        end
    end
end)]]


_G.at = true

local Players = game:GetService("Players")
local ReplicatedStorage = game:GetService("ReplicatedStorage")
local RunService = game:GetService("RunService")

local lp = Players.LocalPlayer

local Net = require(ReplicatedStorage.Modules.Net)
local CombatUtil = require(ReplicatedStorage.Modules.CombatUtil)

local hitRemote = Net:RemoteEvent("RegisterHit")
local attackRemote = ReplicatedStorage.Modules.Net:FindFirstChild("RE/RegisterAttack")

local function getChar()
    return lp.Character or lp.CharacterAdded:Wait()
end

local function FastAttack(target)
    local char = lp.Character
    if not char then return end
    
    local hrp = target:FindFirstChild("HumanoidRootPart")
    local hum = target:FindFirstChild("Humanoid")
    if not hrp or not hum or hum.Health <= 0 then return end

    local tool = char:FindFirstChildOfClass("Tool")
    if not tool then return end 

    pcall(function()
        local weaponName = CombatUtil:GetWeaponName(tool)
        local uuid = tostring(lp.UserId):sub(2, 4) .. tostring(math.random(10000, 99999)) 
        local hitData = {{target, hrp}}
        hitRemote:FireServer(hrp, hitData, nil, nil, uuid)
        CombatUtil:ApplyDamageHighlight(target, char, weaponName, hrp, nil)
    end)
end
local function GetMobsInRange(maxDist)
    local char = lp.Character
    if not char or not char:FindFirstChild("HumanoidRootPart") then return {} end
    local root = char.HumanoidRootPart
    local mobs = {}
    for _, mob in ipairs(workspace.Enemies:GetChildren()) do
        local mHrp = mob:FindFirstChild("HumanoidRootPart")
        local mHum = mob:FindFirstChild("Humanoid")
        if mHrp and mHum and mHum.Health > 0 then
            local dist = (mHrp.Position - root.Position).Magnitude
            if dist <= (maxDist or 60) then
                table.insert(mobs, mob)
            end
        end
    end
    return mobs
end
task.spawn(function()
    while task.wait() do
        if _G.at then
            pcall(function()
                local char = lp.Character
                if char and char:FindFirstChild("Humanoid") and char.Humanoid.Health > 0 then
                    local mobs = GetMobsInRange(60)
                    if #mobs > 0 then
                        if attackRemote then
                            attackRemote:FireServer()
                        end
                        for _, mob in ipairs(mobs) do
                            FastAttack(mob)
                        end
                    end
                end
            end)
        end
    end
end)




			--[[if CommF_("BuyElectro",true) == 1 then
				HasElectro = true
			end
			if CommF_("BuyBlackLeg",true) == 1 then
				HasBlackleg = true
			end
			if CommF_("BuyFishmanKarate",true) == 1 then
				HasFishman = true
			end
			if CommF_("BlackbeardReward","DragonClaw","1") == 1 then
				HasDragonClaw = true
			end
			if CommF_("BuySuperhuman",true) == 1 then
				Hassuperhuman = true
			end
			if CommF_("BuyDeathStep",true) == 1 then
				HasDeathStep = true
			end
			if CommF_("BuySharkmanKarate",true) == 1 then
				HasSharkman = true
			end
			if CommF_("BuyElectricClaw",true) == 1 then
				HasElectricClaw = true
			end
			if CommF_("BuyDragonTalon",true) == 1 then
				HasDragonTalon = true
			end
			if CommF_("BuyGodhuman",true) == 1 then
				HasGodhuman = true
			end            ]]


startsea:Lock()
idk:Lock()
idk1:Lock()
idk2:Lock()
idk3:Lock()
idk4:Lock()
idk5:Lock()
--findprr:Lock()
fullytrial:Lock()
end

local function Notify(msg)
    StarterGui:SetCore("SendNotification", { Title = "Rise Auth", Text = msg, Duration = 3 })
end

local function GetHWID()
    return (gethwid and gethwid()) or LocalPlayer.UserId
end

local function Sha256(str)
    if crypt and crypt.hash then return crypt.hash(str, "sha256") end
    if syn and syn.crypt then return syn.crypt.hash(str) end
    return "" 
end

local function Base64Encode(data)
    if crypt and crypt.base64encode then return crypt.base64encode(data) end
    if syn and syn.crypt then return syn.crypt.base64.encode(data) end
    return HttpService:JSONEncode({data}):sub(2, -2) 
end

local function GenerateSignature(payloadTable, hwid)
    local jsonBody = HttpService:JSONEncode(payloadTable)
    local timestamp = tostring(os.time())
    local placeId = tostring(game.PlaceId)
    local seed = hwid:sub(1, 8) .. placeId .. timestamp:sub(-4)
    local xor_key = Sha256(seed)
    
    local encrypted = {}
    for i = 1, #jsonBody do
        local b = string.byte(jsonBody, i)
        local k = string.byte(xor_key, (i - 1) % #xor_key + 1)
        table.insert(encrypted, string.char(bit32.bxor(b, k)))
    end
    local xor_data = table.concat(encrypted)
    local data_hash = Sha256(xor_data)
    local combined = data_hash .. xor_data
    return Base64Encode(combined), timestamp
end

local function VerifyPremiumKey(key)
    if not key or #key < 5 then return false, "Key Invalid" end
    local hwid = GetHWID()
    local payload = { key = key, hwid = hwid } 
    local sig, timestamp = GenerateSignature(payload, hwid)
    
    local requestUrl = string.format("%s/check_key?key=%s&sig=%s&hwid=%s&game_id=%s&timestamp=%s",
        API_URL, HttpService:UrlEncode(key), HttpService:UrlEncode(sig), HttpService:UrlEncode(hwid), tostring(game.PlaceId), timestamp)
    
    local success, response = pcall(function() return game:HttpGet(requestUrl) end)
    if success then
        local data = HttpService:JSONDecode(response)
        if data.status == "true" then return true, data.type else return false, data.message end
    end
    return false, "Connection Error"
end

local pb_service = 19488
local pb_host = "https://api.platoboost.app"
local function lDigest(s) if crypt and crypt.hash then return crypt.hash(s,"sha256") end return s end

local function VerifyPlatoboost(key)
    local endpoint = pb_host .. "/public/whitelist/" .. tostring(pb_service) .. "?identifier=" .. lDigest(GetHWID()) .. "&key=" .. key
    local s, r = pcall(function() return game:HttpGet(endpoint) end)
    if s then
        local d = HttpService:JSONDecode(r)
        if d.success and d.data.valid then return true end
    end
    return false
end

local function GetLinkPB()
    local url = pb_host .. "/public/start"
    local body = HttpService:JSONEncode({ service = pb_service, identifier = lDigest(GetHWID()) })
    local s, r = pcall(function() 
        return request({Url=url, Method="POST", Body=body, Headers={["Content-Type"]="application/json"}})
    end)
    if s and r.StatusCode == 200 then
        local d = HttpService:JSONDecode(r.Body)
        if d.success then return d.data.url end
    end
    return "Error Getting Link"
end


local function CreateUI()
    if getgenv().RISE_UI_LOADED then return end
    getgenv().RISE_UI_LOADED = true
    local ScreenGui = Instance.new("ScreenGui")
    local MainFrame = Instance.new("Frame")
    local UIStroke_Main = Instance.new("UIStroke")
    local GridEffect = Instance.new("ImageLabel")
    local ParticlesContainer = Instance.new("Frame")
    ScreenGui.Name = "RiseEvoUI"
    if gethui then ScreenGui.Parent = gethui() else ScreenGui.Parent = CoreGui end
    ScreenGui.IgnoreGuiInset = true
    local TARGET_SIZE = UDim2.new(0, 360, 0, 250) 
    MainFrame.Name = "MainFrame"
    MainFrame.Parent = ScreenGui
    MainFrame.AnchorPoint = Vector2.new(0.5, 0.5)
    MainFrame.BackgroundColor3 = Color3.fromRGB(5, 5, 8)
    MainFrame.Position = UDim2.new(0.5, 0, 0.5, 0)
    MainFrame.Size = TARGET_SIZE
    MainFrame.ClipsDescendants = true
    MainFrame.BorderSizePixel = 0
    MainFrame.BackgroundTransparency = 1 
    local MainCorner = Instance.new("UICorner")
    MainCorner.CornerRadius = UDim.new(0, 10)
    MainCorner.Parent = MainFrame
    UIStroke_Main.Parent = MainFrame
    UIStroke_Main.Color = Color3.fromRGB(180, 100, 255)
    UIStroke_Main.Thickness = 1.2
    UIStroke_Main.Transparency = 1
    local CloseBtn = Instance.new("TextButton")
    CloseBtn.Name = "CloseBtn"
    CloseBtn.Parent = MainFrame
    CloseBtn.BackgroundTransparency = 1
    CloseBtn.Position = UDim2.new(1, -35, 0, 10)
    CloseBtn.Size = UDim2.new(0, 25, 0, 25)
    CloseBtn.Font = Enum.Font.Code
    CloseBtn.Text = "★"
    CloseBtn.TextColor3 = Color3.fromRGB(150, 150, 150)
    CloseBtn.TextSize = 24
    CloseBtn.ZIndex = 10
    CloseBtn.MouseEnter:Connect(function() TweenService:Create(CloseBtn, TweenInfo.new(0.3), {TextColor3 = Color3.fromRGB(255, 50, 50)}):Play() end)
    CloseBtn.MouseLeave:Connect(function() TweenService:Create(CloseBtn, TweenInfo.new(0.3), {TextColor3 = Color3.fromRGB(150, 150, 150)}):Play() end)
    CloseBtn.MouseButton1Click:Connect(function()
        TweenService:Create(MainFrame, TweenInfo.new(0.5, Enum.EasingStyle.Quart, Enum.EasingDirection.In), {Size = UDim2.new(0, 360, 0, 0), BackgroundTransparency = 1}):Play()
        task.wait(0.5)
        ScreenGui:Destroy()
        getgenv().RISE_UI_LOADED = false
    end)
    GridEffect.Name = "GridEffect"
    GridEffect.Parent = MainFrame
    GridEffect.BackgroundTransparency = 1
    GridEffect.Position = UDim2.new(0, 0, 0.4, 0)
    GridEffect.Size = UDim2.new(1, 0, 0.6, 0)
    GridEffect.Image = "rbxassetid://10651685382"
    GridEffect.ImageColor3 = Color3.fromRGB(120, 50, 255)
    GridEffect.ImageTransparency = 0.8
    GridEffect.ZIndex = 0
    ParticlesContainer.Name = "Particles"
    ParticlesContainer.Parent = MainFrame
    ParticlesContainer.Size = UDim2.new(1, 0, 1, 0)
    ParticlesContainer.BackgroundTransparency = 1
    ParticlesContainer.ZIndex = 1
    local function CreateParticle()
        if not MainFrame.Parent then return end
        local p = Instance.new("Frame")
        p.Parent = ParticlesContainer
        p.Size = UDim2.new(0, 2, 0, 2)
        p.BackgroundColor3 = Color3.fromRGB(200, 150, 255)
        p.Position = UDim2.new(math.random(), 0, 1, 0)
        Instance.new("UICorner", p).CornerRadius = UDim.new(1, 0) 
        local speed = math.random(3, 6)
        TweenService:Create(p, TweenInfo.new(speed, Enum.EasingStyle.Linear), {
            Position = UDim2.new(p.Position.X.Scale + (math.random(-1, 1)/10), 0, -0.1, 0),
            BackgroundTransparency = 1
        }):Play()
        Debris:AddItem(p, speed)
    end
    task.spawn(function()
        while MainFrame.Parent and task.wait(0.5) do CreateParticle() end
    end)
    local Title = Instance.new("TextLabel")
    Title.Parent = MainFrame
    Title.BackgroundTransparency = 1
    Title.Position = UDim2.new(0, 25, 0, 15)
    Title.Size = UDim2.new(0, 200, 0, 30)
    Title.Font = Enum.Font.Code
    Title.Text = "RISE EVO > AUTHENTICATION"
    Title.TextColor3 = Color3.fromRGB(255, 255, 255)
    Title.TextSize = 18
    Title.TextXAlignment = Enum.TextXAlignment.Left
    Title.ZIndex = 5
    local Divider = Instance.new("Frame")
    Divider.Parent = MainFrame
    Divider.BackgroundColor3 = Color3.fromRGB(180, 100, 255)
    Divider.BorderSizePixel = 0
    Divider.Position = UDim2.new(0, 25, 0, 45)
    Divider.Size = UDim2.new(0, 0, 0, 1)
    Divider.ZIndex = 5
    local InputContainer = Instance.new("Frame")
    InputContainer.Parent = MainFrame
    InputContainer.BackgroundColor3 = Color3.fromRGB(255, 255, 255)
    InputContainer.BackgroundTransparency = 0.96
    InputContainer.Position = UDim2.new(0, 25, 0, 75)
    InputContainer.Size = UDim2.new(0, 310, 0, 45)
    InputContainer.ZIndex = 5
    Instance.new("UICorner", InputContainer).CornerRadius = UDim.new(0, 10)
    local InputStroke = Instance.new("UIStroke")
    InputStroke.Parent = InputContainer
    InputStroke.Color = Color3.fromRGB(60, 60, 80)
    InputStroke.Thickness = 1
    local InputBox = Instance.new("TextBox")
    InputBox.Parent = InputContainer
    InputBox.BackgroundTransparency = 1
    InputBox.Size = UDim2.new(1, -20, 1, 0)
    InputBox.Position = UDim2.new(0, 10, 0, 0)
    InputBox.Font = Enum.Font.Code
    InputBox.Text = ""
    InputBox.TextColor3 = Color3.fromRGB(255, 255, 255)
    InputBox.TextSize = 13
    InputBox.TextXAlignment = Enum.TextXAlignment.Left
    InputBox.ZIndex = 6
    if isfile(KEY_FILE) then InputBox.Text = readfile(KEY_FILE) end
    local Placeholder = Instance.new("TextLabel")
    Placeholder.Parent = InputContainer
    Placeholder.BackgroundTransparency = 1
    Placeholder.Size = UDim2.new(1, -20, 1, 0)
    Placeholder.Position = UDim2.new(0, 10, 0, 0)
    Placeholder.Font = Enum.Font.Code
    Placeholder.Text = "// ENTER KEY (PREMIUM/FREE)"
    Placeholder.TextColor3 = Color3.fromRGB(120, 120, 120)
    Placeholder.TextSize = 13
    Placeholder.TextXAlignment = Enum.TextXAlignment.Left
    Placeholder.ZIndex = 5
    InputBox.Focused:Connect(function()
        TweenService:Create(Placeholder, TweenInfo.new(0.3, Enum.EasingStyle.Quart), {Position = UDim2.new(0, 10, 0, -12), TextSize = 10, TextColor3 = Color3.fromRGB(180, 100, 255)}):Play()
        TweenService:Create(InputStroke, TweenInfo.new(0.3), {Color = Color3.fromRGB(180, 100, 255)}):Play()
    end)
    InputBox.FocusLost:Connect(function()
        if InputBox.Text == "" then
            TweenService:Create(Placeholder, TweenInfo.new(0.3, Enum.EasingStyle.Quart), {Position = UDim2.new(0, 10, 0, 0), TextSize = 13, TextColor3 = Color3.fromRGB(120, 120, 120)}):Play()
            TweenService:Create(InputStroke, TweenInfo.new(0.3), {Color = Color3.fromRGB(60, 60, 80)}):Play()
        else
             TweenService:Create(Placeholder, TweenInfo.new(0.3), {Position = UDim2.new(0, 10, 0, -12), TextSize = 10}):Play()
             TweenService:Create(InputStroke, TweenInfo.new(0.3), {Color = Color3.fromRGB(60, 60, 80)}):Play()
        end
    end)
    if InputBox.Text ~= "" then
        Placeholder.Position = UDim2.new(0, 10, 0, -12)
        Placeholder.TextSize = 10
        Placeholder.TextColor3 = Color3.fromRGB(180, 100, 255)
    end
    local function NewBtn(text, pos, color)
        local b = Instance.new("TextButton")
        b.Parent = MainFrame
        b.Size = UDim2.new(0, 150, 0, 35)
        b.Position = pos
        b.BackgroundColor3 = Color3.fromRGB(255, 255, 255)
        b.BackgroundTransparency = 0.98
        b.Font = Enum.Font.Code
        b.Text = text
        b.TextColor3 = Color3.fromRGB(180, 180, 180)
        b.TextSize = 11
        b.ZIndex = 5
        Instance.new("UICorner", b).CornerRadius = UDim.new(0, 8)
        local bs = Instance.new("UIStroke", b)
        bs.Color = color
        bs.Transparency = 0.6
        b.MouseEnter:Connect(function() TweenService:Create(b, TweenInfo.new(0.3), {BackgroundTransparency = 0.9, TextColor3 = Color3.fromRGB(255, 255, 255)}):Play() TweenService:Create(bs, TweenInfo.new(0.3), {Transparency = 0, Thickness = 1.2}):Play() end)
        b.MouseLeave:Connect(function() TweenService:Create(b, TweenInfo.new(0.3), {BackgroundTransparency = 0.98, TextColor3 = Color3.fromRGB(180, 180, 180)}):Play() TweenService:Create(bs, TweenInfo.new(0.3), {Transparency = 0.6, Thickness = 1}):Play() end)
        return b
    end
    local Discord = NewBtn("DISCORD", UDim2.new(0, 25, 0, 135), Color3.fromRGB(114, 137, 218))
    local GetKey = NewBtn("GET URL", UDim2.new(0, 185, 0, 135), Color3.fromRGB(255, 170, 0))  
    local Verify = Instance.new("TextButton")
    Verify.Parent = MainFrame
    Verify.BackgroundColor3 = Color3.fromRGB(120, 50, 255)
    Verify.Position = UDim2.new(0, 25, 0, 185)
    Verify.Size = UDim2.new(0, 310, 0, 45)
    Verify.Font = Enum.Font.Code
    Verify.Text = "VERIFY IDENTITY"
    Verify.TextColor3 = Color3.fromRGB(255, 255, 255)
    Verify.TextSize = 14
    Verify.ZIndex = 5
    Instance.new("UICorner", Verify).CornerRadius = UDim.new(0, 10)
    Discord.MouseButton1Click:Connect(function()
        setclipboard("https://discord.gg/URZ5qcVPwc")
        Notify("Discord Invite Copied!")
    end)    
    GetKey.MouseButton1Click:Connect(function()
        setclipboard(GetLinkPB())
        Notify("Get Key Copied!")
    end)
    Verify.MouseButton1Click:Connect(function()
        local input = InputBox.Text:gsub(" ", "")
        if #input < 5 then Notify("Please enter key!") return end        
        Verify.Text = "AUTHENTICATING..."
        local isPrem, kType = VerifyPremiumKey(input)
        if isPrem then
            Verify.Text = "GRANTED (PREMIUM)"
            Verify.BackgroundColor3 = Color3.fromRGB(50, 255, 100)
            Notify("Welcome Premium User! ("..tostring(kType)..")")
            writefile(KEY_FILE, input)
            task.wait(1)
            TweenService:Create(MainFrame, TweenInfo.new(0.5, Enum.EasingStyle.Quart, Enum.EasingDirection.In), {Size = UDim2.new(0, 360, 0, 0), BackgroundTransparency = 1}):Play()
            task.wait(0.5)
            ScreenGui:Destroy()
            LoadMainScript()
            return
        end
        local isFree = VerifyPlatoboost(input)
        if isFree then
             Verify.Text = "GRANTED (FREE)"
             Verify.BackgroundColor3 = Color3.fromRGB(50, 255, 100)
             Notify("Welcome Free User!")
             writefile(KEY_FILE, input)
             task.wait(1)
             TweenService:Create(MainFrame, TweenInfo.new(0.5, Enum.EasingStyle.Quart, Enum.EasingDirection.In), {Size = UDim2.new(0, 360, 0, 0), BackgroundTransparency = 1}):Play()
             task.wait(0.5)
             ScreenGui:Destroy()
             LoadMainScript()
             return
        end
        Verify.Text = "ACCESS DENIED"
        Verify.BackgroundColor3 = Color3.fromRGB(255, 50, 50)
        Notify("Invalid Key!")
        task.wait(1)
        Verify.Text = "VERIFY IDENTITY"
        Verify.BackgroundColor3 = Color3.fromRGB(120, 50, 255)
    end)
    local smoothness = 0.15
    RunService.RenderStepped:Connect(function()
        if not MainFrame.Parent then return end
        local mPos = UserInputService:GetMouseLocation()
        local screenSize = workspace.CurrentCamera.ViewportSize
        local center = Vector2.new(screenSize.X/2, screenSize.Y/2)
        local diff = (mPos - center)
        local goalRot = diff.X / 250
        local goalPosX = 0.5 + (diff.X / (screenSize.X * 15))
        local goalPosY = 0.5 + (diff.Y / (screenSize.Y * 15))
        MainFrame.Rotation = MainFrame.Rotation + (goalRot - MainFrame.Rotation) * smoothness
        MainFrame.Position = MainFrame.Position:Lerp(UDim2.new(goalPosX, 0, goalPosY, 0), smoothness)
    end)
    MainFrame.Size = UDim2.new(0, 0, 0, 2)
    MainFrame.BackgroundTransparency = 0
    TweenService:Create(MainFrame, TweenInfo.new(0.8, Enum.EasingStyle.Quart), {Size = UDim2.new(0, 360, 0, 2)}):Play()
    task.wait(0.8)
    TweenService:Create(MainFrame, TweenInfo.new(0.6, Enum.EasingStyle.Quart), {Size = TARGET_SIZE}):Play()
    TweenService:Create(UIStroke_Main, TweenInfo.new(1), {Transparency = 0}):Play()
    task.wait(0.5)
    TweenService:Create(Divider, TweenInfo.new(1), {Size = UDim2.new(0, 310, 0, 1)}):Play()
end
local function Init()
    if getgenv().Key and type(getgenv().Key) == "string" and #getgenv().Key > 5 then
        print("[wl rise] database connectmmmm...")
        Notify("Checking Script Key...")
        local valid, typeK = VerifyPremiumKey(getgenv().Key)
        if valid then
            print("[wl rise] database verify...")
            Notify("Premium Authenticated! ("..tostring(typeK)..")")
            LoadMainScript()
            return
        end
    end
    if isfile(KEY_FILE) then
        local saved = readfile(KEY_FILE)
        if #saved > 5 then
            if VerifyPremiumKey(saved) then Notify("Auto-Login (Premium)") LoadMainScript() return end
            if VerifyPlatoboost(saved) then Notify("Auto-Login (Free)") LoadMainScript() return end
        end
    end
    CreateUI()
end
Init()