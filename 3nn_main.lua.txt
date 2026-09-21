if getgenv().__BF_LOADED then
	return getgenv().__BF_RESULT
end

Settings = {}
HttpService = game:GetService("HttpService")
FolderName = "Banana Cat Hub"
SaveFileNameGame = "-BloxFruitBNNC.json"
SaveFileName = game.Players.LocalPlayer.Name .. SaveFileNameGame
function SaveSettings(b, t, A)
	if A ~= nil then
		Settings[b] = Settings[b] or {}
		Settings[b][t] = A
	elseif b ~= nil then
		Settings[b] = t
	end
	if not isfolder(FolderName) then
		makefolder(FolderName)
	end
	writefile(FolderName .. "/" .. SaveFileName, HttpService:JSONEncode(Settings))
end
if getgenv().Config then
	Settings = getgenv().Config
	SaveSettings()
end
function ReadSetting()
	local b, t = pcall(function()
		if not isfolder(FolderName) then
			makefolder(FolderName)
		end
		return HttpService:JSONDecode(readfile(FolderName .. "/" .. SaveFileName))
	end)
	if b then
		return t
	else
		SaveSettings()
		return ReadSetting()
	end
end
Settings = ReadSetting()
getgenv().Settings = Settings
function PrepareMultiSelectList(b, t, A)
	local a = {}
	for s in pairs(b) do
		local b = t and t[s]
		if b == nil then
			a[s] = A and true or false
		else
			a[s] = b
		end
	end
	return a
end
function EnsureAllTrueDefaults(b, t)
	if type(Settings[b]) ~= "table" then
		Settings[b] = {}
	end
	local A = false
	for a, a in ipairs(t) do
		if Settings[b][a] == nil then
			Settings[b][a] = true
			A = true
		end
	end
	if A then
		for t, A in pairs(Settings[b]) do
			SaveSettings(b, t, A)
		end
	end
end
repeat
	wait()
until game:FindFirstChild("CoreGui")
repeat
	wait()
until not game:GetService("Players").LocalPlayer.PlayerGui:FindFirstChild("LoadingScreen")
repeat
	wait()
until game:IsLoaded() and (game.Players.LocalPlayer:FindFirstChild("DataLoaded"))
function FireButton(b)
	b.Selectable = true
	game:GetService("GuiService").SelectedObject = b
	game:GetService("VirtualInputManager"):SendKeyEvent(true, "Return", false, b)
	game:GetService("VirtualInputManager"):SendKeyEvent(false, "Return", false, b)
	b.Activated:Connect(function()
		game:GetService("GuiService").SelectedObject = nil
	end)
end
repeat
	wait()
until game:GetService("Players").LocalPlayer.PlayerGui:FindFirstChild("Main (minimal)")
	or (game:GetService("Players").LocalPlayer.PlayerGui:FindFirstChild("Main"))
local b = game:GetService("Players").LocalPlayer.PlayerGui:FindFirstChild("Main (minimal)")
	or (game:GetService("Players").LocalPlayer.PlayerGui:FindFirstChild("Main"))
repeat
	wait()
until b:FindFirstChild("ChooseTeam")
repeat
	task.wait()
	pcall(function()
		if Settings["Select Team"] == "Pirate" then
			FireButton(
				game:GetService("Players").LocalPlayer.PlayerGui["Main (minimal)"].ChooseTeam.Container.Pirates.Frame.TextButton
			)
			wait(1)
		else
			FireButton(
				game:GetService("Players").LocalPlayer.PlayerGui["Main (minimal)"].ChooseTeam.Container.Marines.Frame.TextButton
			)
			wait(1)
		end
	end)
until game:GetService("Players").LocalPlayer.PlayerGui:FindFirstChild("Main (minimal)")
		and (game:GetService("Players").LocalPlayer.PlayerGui["Main (minimal)"]:FindFirstChild("ChooseTeam"))
		and not game:GetService("Players").LocalPlayer.PlayerGui["Main (minimal)"]:WaitForChild("ChooseTeam").Visible
	or game:GetService("Players").LocalPlayer.PlayerGui:FindFirstChild("Main")
		and (game:GetService("Players").LocalPlayer.PlayerGui.Main:FindFirstChild("ChooseTeam"))
		and not game:GetService("Players").LocalPlayer.PlayerGui.Main:WaitForChild("ChooseTeam").Visible
game:GetService("GuiService").SelectedObject = nil
repeat
	wait()
until game:IsLoaded() and game.Players.LocalPlayer
repeat
	wait()
until game:FindFirstChild("CoreGui")
getgenv().ExploitReq = syn and syn.request
	or identifyexecutor() == "Fluxus" and request
	or http_request
	or http.request
	or requests
if getgenv().LoadScript then
	return print("Double UI")
end
getgenv().CheckPlaceId = game.PlaceId == 100117331123089 and 100117331123089 or 7449423635
getgenv().CheckPlaceId2 = game.PlaceId == 4442272183 and 4442272183 or 79091703265657
getgenv().CheckPlaceId3 = game.PlaceId == 2753915549 and 2753915549 or 85211729168715
getgenv().LoadScript = true
local t = game.Players.LocalPlayer
getgenv().getupvalue = debug.getupvalue
getgenv().getupvalues = debug.getupvalues
wOrigin = game.workspace._WorldOrigin
CommF = game.ReplicatedStorage.Remotes.CommF_
vu = game:GetService("VirtualUser")
game:GetService("Players").LocalPlayer.Idled:connect(function()
	vu:Button2Down(Vector2.new(0, 0), workspace.CurrentCamera.CFrame)
	wait(1)
	vu:Button2Up(Vector2.new(0, 0), workspace.CurrentCamera.CFrame)
end)
local A =
	loadstring(game:HttpGet("https://raw.githubusercontent.com/obiiyeuem/vthangsitink/refs/heads/main/zzzz.lua"))()
Main = A.CreateMain({ Title = "Blox Fruit", Desc = " - Blox Fruit" })
PageShop = Main.CreatePage({ Page_Name = "Shop", Page_Title = "Shop" })
getgenv().Options = A.Options
SectionShopMisc = PageShop.CreateSection("Misc Shop")
function Remote(a, s, X)
	if not a and X then
		game.ReplicatedStorage.Remotes.CommF_:InvokeServer(s, true)
	else
		game.ReplicatedStorage.Remotes.CommF_:InvokeServer(a, s, X)
	end
end
getgenv().tablefruitausea3 = {}
whitelistedfruit = {}
TableDevilFruit = {}
local a, s, X = next, game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("GetFruits", false)
for g, g in a, s, X do
	if g.Price >= 1000000 then
		table.insert(whitelistedfruit, string.split(g.Name, "-")[1] .. " Fruit")
		getgenv().tablefruitausea3[g.Name] = g.Price
	end
	TableDevilFruit[g.Name] = false
end
getgenv().tablefruitausea3["Dragon (East)-Dragon (East)"] = 15000000
getgenv().tablefruitausea3["Dragon (West)-Dragon (West)"] = 15000000
ItemId = require(game.ReplicatedStorage.Economy.ItemId)
function CheckFruitReal(g)
	local G, f, K = next, game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("GetFruits", false)
	for R, R in G, f, K do
		if R.Name == g then
			return R
		end
	end
end
SkinFruit = {}
-- spawn(function()
--     for g, g in next, require(game:GetService("ReplicatedStorage").Modules.SkinUtil.FruitSkins).Grouped do
--         for G, G in next, g do
--             getgenv().tablefruitausea3[g.StorageName] = CheckFruitReal(G.Item).Price
--             table.insert(whitelistedfruit, G.StorageName .. " Fruit")
--             SkinFruit[G.StorageName .. " Fruit"] = true
--         end
--     end
-- end)
NameWorldMaterials = {
	Ectoplasm = { [getgenv().CheckPlaceId2] = "TravelDressrosa" },
	["Magma Ore"] = { [getgenv().CheckPlaceId2] = "TravelDressrosa" },
	Leather = { [getgenv().CheckPlaceId] = "TravelZou" },
	["Scrap Metal"] = { [getgenv().CheckPlaceId] = "TravelZou" },
	["Angel Wings"] = { [getgenv().CheckPlaceId3] = "TravelMain" },
	["Fish Tail"] = { [getgenv().CheckPlaceId] = "TravelZou" },
	["Radioactive Material"] = { [getgenv().CheckPlaceId2] = "TravelDressrosa" },
	["Vampire Fang"] = { [getgenv().CheckPlaceId2] = "TravelDressrosa" },
	["Mystic Droplet"] = { [getgenv().CheckPlaceId2] = "TravelDressrosa" },
	["Mini Tusk"] = { [getgenv().CheckPlaceId] = "TravelZou" },
	Gunpowder = { [getgenv().CheckPlaceId] = "TravelZou" },
	["Demonic Wisp"] = { [getgenv().CheckPlaceId] = "TravelZou" },
	["Dragon Scale"] = { [getgenv().CheckPlaceId] = "TravelZou" },
	["Conjured Cocoa"] = { [getgenv().CheckPlaceId] = "TravelZou" },
	Bones = { [getgenv().CheckPlaceId] = "TravelZou" },
}
NameMaterials = {
	Ectoplasm = { "Ship Deckhand", "Ship Engineer", "Ship Steward", "Ship Officer", "Cursed Captain" },
	["Magma Ore"] = { "Lava Pirate", "Magma Ninja" },
	Leather = { "Jungle Pirate", "Musketeer Pirate" },
	["Scrap Metal"] = { "Jungle Pirate" },
	["Angel Wings"] = { "God's Guard", "Shanda", "Royal Squad", "Royal Soldier" },
	["Fish Tail"] = { "Fishman Raider", "Fishman Captain" },
	["Radioactive Material"] = { "Factory Staff" },
	["Vampire Fang"] = { "Vampire" },
	["Mystic Droplet"] = { "Sea Soldier", "Water Fighter" },
	["Mini Tusk"] = { "Mythological Pirate" },
	Gunpowder = { "Pistol Billionaire" },
	["Demonic Wisp"] = { "Demonic Soul" },
	["Dragon Scale"] = { "Dragon Crew Archer", "Dragon Crew Warrior" },
	["Conjured Cocoa"] = { "Cocoa Warrior", "Chocolate Bar Battler" },
	Bones = { "Reborn Skeleton", "Demonic Soul", "Living Zombie", "Posessed Mummy" },
}
TableMaterials = {}
for g, G in next, NameMaterials, nil do
	table.insert(TableMaterials, g)
end
REDEEM_CODES = {
	"EASTEREXP",
	"BANEXPLOIT",
	"NOMOREHACKS",
	"WildDares",
	"BossBuild",
	"GetPranked",
	"EARN_FRUITS",
	"Sub2UncleKizaru",
	"FIGHT4FRUIT",
	"kittgaming",
	"TRIPLEABUSE",
	"Sub2CaptainMaui",
	"Sub2Fer999",
	"Enyu_is_Pro",
	"Magicbus",
	"JCWK",
	"Starcodeheo",
	"Bluxxy",
	"SUB2GAMERROBOT_EXP1",
	"Sub2NoobMaster123",
	"Sub2Daigrock",
	"Axiore",
	"TantaiGaming",
	"StrawHatMaine",
	"Sub2OfficialNoobie",
	"TheGreatAce",
	"SEATROLLIN",
	"24NOADMIN",
	"ADMIN_TROLL",
	"NEWTROLL",
	"SECRET_ADMIN",
	"staffbattle",
	"NOEXPLOIT",
	"NOOB2ADMIN",
	"CODESLIDE",
	"fruitconcepts",
}
SectionShopMisc.CreateButton({ Title = "Redeem Code" }, function()
	LPH_ATTRIBUTES(VM(NONE))
	for _, v in REDEEM_CODES do
		game.ReplicatedStorage.Remotes.Redeem:InvokeServer(v)
	end
end)

SectionShopMisc.CreateButton({ Title = "Teleport Old World" }, function()
	game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer(unpack({ [1] = "TravelMain" }))
end)

SectionShopMisc.CreateButton({ Title = "Teleport New World" }, function()
	game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer(unpack({ [1] = "TravelDressrosa" }))
end)

SectionShopMisc.CreateButton({ Title = "Teleport Thid Sea" }, function()
	game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer(unpack({ [1] = "TravelZou" }))
end)

SectionShopMisc.CreateButton({ Title = "Buy Dual Flintlock" }, function()
	game.ReplicatedStorage.Remotes.CommF_:InvokeServer("BuyItem", "Dual Flintlock")
end)

SectionShopMisc.CreateButton({ Title = "Reroll Race" }, function()
	game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("BlackbeardReward", "Reroll", "2")
end)

SectionShopMisc.CreateButton({ Title = "Reset Stats" }, function()
	game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("BlackbeardReward", "Refund", "1")
	game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("BlackbeardReward", "Refund", "2")
end)

SectionShopMisc.CreateButton({ Title = "Buy Race Cyborg" }, function()
	game.ReplicatedStorage.Remotes.CommF_:InvokeServer("CyborgTrainer", "Buy")
end)

SectionShopMisc.CreateButton({ Title = "Buy Race Ghoul" }, function()
	game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("Ectoplasm", "BuyCheck", 4)
	game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("Ectoplasm", "Change", 4)
end)

SectionShopFighting = PageShop.CreateSection("Fighting Shop")
local g = {}
getgenv().notsave = g
local G = {
	BuyBlackLeg = "Dark Step Teacher",
	BuySuperhuman = "Martial Arts Master",
	BuySharkmanKarate = "Sharkman Teacher",
	DragonClaw = "Sabi",
	BuyDragonTalon = "Uzoth",
	BuyElectro = "Mad Scientist",
	BuyFishmanKarate = "Water Kung-fu Teacher",
	BuyDeathStep = "Phoeyu, the Reformed",
	BuyGodhuman = "Ancient Monk",
	BuyElectricClaw = "Previous Hero",
	BuySanguineArt = "Shafi",
}
NPCManager = require(game:GetService("ReplicatedStorage").NPCManager)
function DetectNpc(f)
	local K = t.Character and (t.Character:FindFirstChild("HumanoidRootPart"))
	if not K then
		return
	end
	local R, m, E, l = next, { workspace.NPCs, game:GetService("ReplicatedStorage").NPCs }, 1 / 0
	for Q, Q in R, m, nil do
		local R, m, S = next, Q:GetChildren()
		for Q, L in R, m, S do
			if
				L:GetAttribute("NPCLoaded")
				and (L:GetAttribute("NPCReady"))
				and L.Name == f
				and (L:FindFirstChild("HumanoidRootPart"))
			then
				Q = (K.Position - L.HumanoidRootPart.Position).Magnitude
				if Q < E then
					E, l = Q, L
				end
			end
		end
	end
	if not l then
		return NPCManager.getNPCsByName(f)[1]._modelState._instance
	end
	return l, E
end

SectionShopFighting.CreateToggle({ Title = "Black Leg", Desc = nil, Default = false }, function(f)
	if f then
		spawn(function()
			while g["Black Leg"] and (task.wait()) do
				local K, K = pcall(function()
					local R = DetectNpc(G.BuyBlackLeg)
					if t:DistanceFromCharacter(R.HumanoidRootPart.Position) < 8 then
						game.ReplicatedStorage.Remotes.CommF_:InvokeServer("BuyBlackLeg")
					end
					getgenv().BackupTween(R.HumanoidRootPart.CFrame * CFrame.new(0, 4, 4))
				end)
				if K then
					print(K)
				end
			end
		end)
	end
	g["Black Leg"] = f
end)

SectionShopFighting.CreateToggle({ Title = "Fishman Karate", Desc = nil, Default = false }, function(f)
	if f then
		spawn(function()
			while g["Fishman Karate"] and (task.wait()) do
				local K, K = pcall(function()
					local R = DetectNpc(G.BuyFishmanKarate)
					if t:DistanceFromCharacter(R.HumanoidRootPart.Position) < 8 then
						game.ReplicatedStorage.Remotes.CommF_:InvokeServer("BuyFishmanKarate")
					end
					getgenv().BackupTween(R.HumanoidRootPart.CFrame * CFrame.new(0, 4, 4))
				end)
				if K then
					print(K)
				end
			end
		end)
	end
	g["Fishman Karate"] = f
end)

SectionShopFighting.CreateToggle({ Title = "Electro", Desc = nil, Default = false }, function(f)
	if f then
		spawn(function()
			while g.Electro and (task.wait()) do
				pcall(function()
					local K = DetectNpc(G.BuyElectro)
					if t:DistanceFromCharacter(K.HumanoidRootPart.Position) < 8 then
						game.ReplicatedStorage.Remotes.CommF_:InvokeServer("BuyElectro")
					end
					getgenv().BackupTween(K.HumanoidRootPart.CFrame * CFrame.new(0, 4, 4))
				end)
			end
		end)
	end
	g.Electro = f
end)

SectionShopFighting.CreateToggle({ Title = "Dragon Breath", Desc = nil, Default = false }, function(f)
	if f then
		spawn(function()
			while g.DragonClaw and (task.wait()) do
				pcall(function()
					local K = DetectNpc(G.DragonClaw)
					if t:DistanceFromCharacter(K.HumanoidRootPart.Position) < 8 then
						game.ReplicatedStorage.Remotes.CommF_:InvokeServer("BlackbeardReward", "DragonClaw", "1")
						game.ReplicatedStorage.Remotes.CommF_:InvokeServer("BlackbeardReward", "DragonClaw", "2")
					end
					getgenv().BackupTween(K.HumanoidRootPart.CFrame * CFrame.new(0, 4, 4))
				end)
			end
		end)
	end
	g.DragonClaw = f
end)

SectionShopFighting.CreateToggle({ Title = "SuperHuman", Desc = nil, Default = false }, function(f)
	if f then
		spawn(function()
			while g.SuperHuman and (task.wait()) do
				pcall(function()
					local K = DetectNpc(G.BuySuperhuman)
					if t:DistanceFromCharacter(K.HumanoidRootPart.Position) < 8 then
						Remote("BuySuperhuman")
					end
					getgenv().BackupTween(K.HumanoidRootPart.CFrame * CFrame.new(0, 4, 4))
				end)
			end
		end)
	end
	g.SuperHuman = f
end)

SectionShopFighting.CreateToggle({ Title = "Death Step", Desc = nil, Default = false }, function(f)
	if f then
		spawn(function()
			while g["Death Step"] and (task.wait()) do
				pcall(function()
					local K = DetectNpc(G.BuyDeathStep)
					if t:DistanceFromCharacter(K.HumanoidRootPart.Position) < 8 then
						Remote("BuyDeathStep")
					end
					getgenv().BackupTween(K.HumanoidRootPart.CFrame * CFrame.new(0, 4, 4))
				end)
			end
		end)
	end
	g["Death Step"] = f
end)

SectionShopFighting.CreateToggle({ Title = "Sharkman Karate", Desc = nil, Default = false }, function(f)
	if f then
		spawn(function()
			while g["Sharkman Karate"] and (task.wait()) do
				pcall(function()
					local K = DetectNpc(G.BuySharkmanKarate)
					if t:DistanceFromCharacter(K.HumanoidRootPart.Position) < 8 then
						Remote("BuySharkmanKarate")
					end
					getgenv().BackupTween(K.HumanoidRootPart.CFrame * CFrame.new(0, 4, 4))
				end)
			end
		end)
	end
	g["Sharkman Karate"] = f
end)

SectionShopFighting.CreateToggle({ Title = "Electric Claw", Desc = nil, Default = false }, function(f)
	if f then
		spawn(function()
			while g["Electric Claw"] and (task.wait()) do
				pcall(function()
					local K = DetectNpc(G.BuyElectricClaw)
					if t:DistanceFromCharacter(K.HumanoidRootPart.Position) < 8 then
						Remote("BuyElectricClaw")
					end
					getgenv().BackupTween(K.HumanoidRootPart.CFrame * CFrame.new(0, 4, 4))
				end)
			end
		end)
	end
	g["Electric Claw"] = f
end)

SectionShopFighting.CreateToggle({ Title = "Dragon Talon", Desc = nil, Default = false }, function(f)
	if f then
		spawn(function()
			while g["Dragon Talon"] and (task.wait()) do
				pcall(function()
					local K = DetectNpc(G.BuyDragonTalon)
					if t:DistanceFromCharacter(K.HumanoidRootPart.Position) < 8 then
						Remote("BuyDragonTalon")
					end
					getgenv().BackupTween(K.HumanoidRootPart.CFrame * CFrame.new(0, 4, 4))
				end)
			end
		end)
	end
	g["Dragon Talon"] = f
end)
SectionShopFighting.CreateToggle({ Title = "God Human", Desc = nil, Default = false }, function(f)
	if f then
		spawn(function()
			while g["God Human"] and (task.wait()) do
				pcall(function()
					local K = DetectNpc(G.BuyGodhuman)
					if t:DistanceFromCharacter(K.HumanoidRootPart.Position) < 8 then
						Remote("BuyGodhuman")
					end
					getgenv().BackupTween(K.HumanoidRootPart.CFrame * CFrame.new(0, 4, 4))
				end)
			end
		end)
	end
	g["God Human"] = f
end)
SectionShopFighting.CreateToggle({ Title = "Sanguine Art", Desc = nil, Default = false }, function(f)
	if f then
		spawn(function()
			while g["Sanguine Art"] and (task.wait()) do
				pcall(function()
					local K = DetectNpc(G.BuySanguineArt)
					if t:DistanceFromCharacter(K.HumanoidRootPart.Position) < 8 then
						Remote("BuySanguineArt")
					end
					getgenv().BackupTween(K.HumanoidRootPart.CFrame * CFrame.new(0, 4, 4))
				end)
			end
		end)
	end
	g["Sanguine Art"] = f
end)
SectionShopAbilities = PageShop.CreateSection("Abilities Shop")
SectionShopAbilities.CreateButton({ Title = "Skyjump [ $10,000 Beli ]" }, function()
	game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("BuyHaki", "Geppo")
end)
SectionShopAbilities.CreateButton({ Title = "Buso Haki [ $25,000 Beli ]" }, function()
	game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("BuyHaki", "Buso")
end)
SectionShopAbilities.CreateButton({ Title = "Observation haki [ $750,000 Beli ]" }, function()
	game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("KenTalk", "Buy")
end)
SectionShopAbilities.CreateButton({ Title = "Soru [ $100,000 Beli ]" }, function()
	game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("BuyHaki", "Soru")
end)
PageStatusAndServer = Main.CreatePage({ Page_Name = "Status And Server", Page_Title = "Status And Server" })
SectionStatus = PageStatusAndServer.CreateSection("Status")
TimerLabel = SectionStatus.CreateLabel({ Title = "Timer" })
TimerServerLabel = SectionStatus.CreateLabel({ Title = "Timer Server" })
NextTimerServerLabel = SectionStatus.CreateLabel({ Title = "Next Time Spawn Fist of Darkness or God's Chalice" })
StatusEliteHunter = SectionStatus.CreateLabel({ Title = "Elite" })
StatusTyrant = SectionStatus.CreateLabel({ Title = "Eyes Summon Tyrant" })
StatusKatakuri = SectionStatus.CreateLabel({ Title = "Summon Katakuri" })
Statusspy = SectionStatus.CreateLabel({ Title = "Status SPY" })
StatusMirage = SectionStatus.CreateLabel({ Title = "Mirage" })
StatusPrehistoricIsland = SectionStatus.CreateLabel({ Title = "Prehistoric Island" })
StatusFrozenDimension = SectionStatus.CreateLabel({ Title = "Frozen Dimension" })
StatusMoon = SectionStatus.CreateLabel({ Title = "Moon" })
StatusGear = SectionStatus.CreateLabel({ Title = "Acient One Status" })
SectionServer = PageStatusAndServer.CreateSection("Server")
SectionServer.CreateButton({ Title = "Open Gui Server Browser (Low Player and Ping)" }, function()
	local G = game:GetService("HttpService")
	game:GetService("TeleportService")
	local f, K = game:GetService("Players"), game:GetService("TweenService")
	local R, R, m = f.LocalPlayer, game.PlaceId, syn and syn.request or http_request or request
	if not m then
		warn("[ServerBrowser] Executor does not support http_request")
		return
	end
	if game.CoreGui:FindFirstChild("SB_UI") then
		game.CoreGui.SB_UI:Destroy()
	end
	local E, l, Q =
		{ servers = {}, cursor = nil, finished = false, lastUpdate = 0, pages = 0 },
		{
			CACHE_TIME = 60,
			MAX_SHOW = 50,
			PAGE_DELAY = 5,
			RETRY_MAX = 4,
			RETRY_BASE = 2,
			RETRY_JITTER = 5,
			RATE_COOLDOWN = 30,
		},
		{
			BG = Color3.fromRGB(10, 11, 16),
			SURFACE = Color3.fromRGB(13, 14, 20),
			ROW = Color3.fromRGB(16, 17, 26),
			ROW_HOVER = Color3.fromRGB(20, 22, 35),
			ROW_TOP = Color3.fromRGB(10, 22, 34),
			BORDER = Color3.fromRGB(28, 31, 48),
			BORDER_HOV = Color3.fromRGB(0, 80, 120),
			CYAN = Color3.fromRGB(0, 212, 255),
			CYAN_DIM = Color3.fromRGB(0, 80, 120),
			GREEN = Color3.fromRGB(0, 204, 102),
			GREEN_GLOW = Color3.fromRGB(0, 255, 136),
			AMBER = Color3.fromRGB(255, 170, 0),
			RED = Color3.fromRGB(255, 68, 85),
			TEXT_PRI = Color3.fromRGB(232, 234, 240),
			TEXT_SEC = Color3.fromRGB(80, 90, 120),
			TEXT_DIM = Color3.fromRGB(45, 52, 82),
		}
	local function S(L, d, I)
		local _ = Instance.new(L)
		for L, o in pairs(d or {}) do
			_[L] = o
		end
		if I then
			_.Parent = I
		end
		return _
	end
	local function L(d, I)
		return S("UICorner", { CornerRadius = UDim.new(0, d) }, I)
	end
	local function d(I, _, o, V)
		return S("UIStroke", { Thickness = I, Color = _, Transparency = o or 0 }, V)
	end
	local function I(_, o, V, N, y)
		K:Create(_, TweenInfo.new(V or 0.15, N or Enum.EasingStyle.Quad, y or Enum.EasingDirection.Out), o):Play()
	end
	local function K(_, o, V)
		_.MouseEnter:Connect(function()
			I(_, { BackgroundColor3 = V })
		end)
		_.MouseLeave:Connect(function()
			I(_, { BackgroundColor3 = o })
		end)
	end
	local function _()
		return math.random() * l.RETRY_JITTER
	end
	local o = S(
		"ScreenGui",
		{ Name = "SB_UI", ResetOnSpawn = false, ZIndexBehavior = Enum.ZIndexBehavior.Sibling, IgnoreGuiInset = true },
		game.CoreGui
	)
	local V = S(
		"Frame",
		{
			Name = "Window",
			Size = UDim2.new(0, 580, 0, 500),
			Position = UDim2.new(0.5, -290, 0.5, -250),
			BackgroundColor3 = Q.SURFACE,
			BorderSizePixel = 0,
			ClipsDescendants = true,
		},
		o
	)
	L(4, V)
	d(1, Q.BORDER, 0, V)
	do
		local N, y, x
		V.InputBegan:Connect(function(k)
			if k.UserInputType == Enum.UserInputType.MouseButton1 then
				N = true
				y = k.Position
				x = V.Position
			end
		end)
		V.InputEnded:Connect(function(k)
			local P, e = k.UserInputType, Enum.UserInputType.MouseButton1
			if P == e then
				N = false
			end
		end)
		game:GetService("UserInputService").InputChanged:Connect(function(k)
			if N and k.UserInputType == Enum.UserInputType.MouseMovement then
				local N = k.Position - y
				V.Position = UDim2.new(x.X.Scale, x.X.Offset + N.X, x.Y.Scale, x.Y.Offset + N.Y)
			end
		end)
	end
	f = S("Frame", { Size = UDim2.new(1, 0, 0, 52), BackgroundColor3 = Q.BG, BorderSizePixel = 0 }, V)
	S(
		"TextLabel",
		{
			Size = UDim2.new(0, 300, 0, 18),
			Position = UDim2.new(0, 18, 0, 9),
			BackgroundTransparency = 1,
			Text = "SERVER BROWSER",
			TextColor3 = Q.TEXT_PRI,
			Font = Enum.Font.GothamBold,
			TextSize = 13,
			TextXAlignment = Enum.TextXAlignment.Left,
		},
		f
	)
	S(
		"TextLabel",
		{
			Size = UDim2.new(0, 360, 0, 14),
			Position = UDim2.new(0, 18, 0, 30),
			BackgroundTransparency = 1,
			Text = "CACHE PAGE \194\183 LOAD MORE \194\183 LOWEST PLAYER / PING",
			TextColor3 = Q.TEXT_DIM,
			Font = Enum.Font.Gotham,
			TextSize = 10,
			TextXAlignment = Enum.TextXAlignment.Left,
		},
		f
	)
	local N = S(
		"TextButton",
		{
			Size = UDim2.new(0, 28, 0, 28),
			Position = UDim2.new(1, -42, 0, 12),
			BackgroundColor3 = Color3.fromRGB(26, 13, 13),
			BorderSizePixel = 0,
			Text = "X",
			TextColor3 = Q.RED,
			Font = Enum.Font.GothamBold,
			TextSize = 11,
		},
		f
	)
	L(3, N)
	K(N, Color3.fromRGB(26, 13, 13), Color3.fromRGB(60, 20, 20))
	N.MouseButton1Click:Connect(function()
		o:Destroy()
	end)
	f = S(
		"Frame",
		{
			Size = UDim2.new(1, 0, 0, 42),
			Position = UDim2.new(0, 0, 0, 52),
			BackgroundColor3 = Color3.fromRGB(11, 12, 17),
			BorderSizePixel = 0,
		},
		V
	)
	local o = S(
		"Frame",
		{
			Size = UDim2.new(0, 6, 0, 6),
			Position = UDim2.new(0, 14, 0.5, -3),
			BackgroundColor3 = Q.TEXT_DIM,
			BorderSizePixel = 0,
		},
		f
	)
	L(99, o)
	local N, y =
		S(
			"TextLabel",
			{
				Size = UDim2.new(1, -300, 1, 0),
				Position = UDim2.new(0, 26, 0, 0),
				BackgroundTransparency = 1,
				Text = "READY",
				TextColor3 = Q.TEXT_SEC,
				Font = Enum.Font.Gotham,
				TextSize = 11,
				TextXAlignment = Enum.TextXAlignment.Left,
			},
			f
		),
		S(
			"TextButton",
			{
				Size = UDim2.new(0, 82, 0, 26),
				Position = UDim2.new(1, -270, 0.5, -13),
				BackgroundColor3 = Color3.fromRGB(14, 22, 40),
				BorderSizePixel = 0,
				Text = "REFRESH",
				TextColor3 = Color3.fromRGB(100, 140, 200),
				Font = Enum.Font.GothamBold,
				TextSize = 10,
			},
			f
		)
	L(3, y)
	K(y, Color3.fromRGB(14, 22, 40), Color3.fromRGB(10, 30, 55))
	local x = S(
		"TextButton",
		{
			Size = UDim2.new(0, 82, 0, 26),
			Position = UDim2.new(1, -182, 0.5, -13),
			BackgroundColor3 = Color3.fromRGB(16, 32, 24),
			BorderSizePixel = 0,
			Text = "LOAD MORE",
			TextColor3 = Q.GREEN,
			Font = Enum.Font.GothamBold,
			TextSize = 10,
		},
		f
	)
	L(3, x)
	K(x, Color3.fromRGB(16, 32, 24), Color3.fromRGB(10, 48, 28))
	local k = S(
		"TextButton",
		{
			Size = UDim2.new(0, 82, 0, 26),
			Position = UDim2.new(1, -94, 0.5, -13),
			BackgroundColor3 = Color3.fromRGB(38, 18, 18),
			BorderSizePixel = 0,
			Text = "RESET",
			TextColor3 = Q.RED,
			Font = Enum.Font.GothamBold,
			TextSize = 10,
		},
		f
	)
	L(3, k)
	K(k, Color3.fromRGB(38, 18, 18), Color3.fromRGB(60, 20, 20))
	local P = S(
		"Frame",
		{
			Size = UDim2.new(1, 0, 0, 24),
			Position = UDim2.new(0, 0, 0, 94),
			BackgroundColor3 = Color3.fromRGB(11, 12, 17),
			BorderSizePixel = 0,
		},
		V
	)
	local function e(Y, H, B)
		S(
			"TextLabel",
			{
				Size = UDim2.new(0, B, 1, 0),
				Position = UDim2.new(0, H, 0, 0),
				BackgroundTransparency = 1,
				Text = Y,
				TextColor3 = Q.TEXT_DIM,
				Font = Enum.Font.GothamBold,
				TextSize = 9,
				TextXAlignment = Enum.TextXAlignment.Left,
			},
			P
		)
	end
	e("#", 14, 28)
	e("JOB ID", 42, 170)
	e("PLAYERS", 220, 80)
	e("PING", 310, 60)
	local P = S(
		"ScrollingFrame",
		{
			Size = UDim2.new(1, -8, 1, -172),
			Position = UDim2.new(0, 4, 0, 118),
			BackgroundTransparency = 1,
			BorderSizePixel = 0,
			ScrollBarThickness = 3,
			ScrollBarImageColor3 = Q.CYAN_DIM,
			CanvasSize = UDim2.new(0, 0, 0, 0),
		},
		V
	)
	local e = S("UIListLayout", { Padding = UDim.new(0, 3), SortOrder = Enum.SortOrder.LayoutOrder }, P)
	S(
		"UIPadding",
		{
			PaddingTop = UDim.new(0, 6),
			PaddingLeft = UDim.new(0, 4),
			PaddingRight = UDim.new(0, 4),
			PaddingBottom = UDim.new(0, 6),
		},
		P
	)
	f = S(
		"Frame",
		{
			Size = UDim2.new(1, 0, 0, 30),
			Position = UDim2.new(0, 0, 1, -30),
			BackgroundColor3 = Color3.fromRGB(10, 11, 15),
			BorderSizePixel = 0,
		},
		V
	)
	local Y, H, B =
		S(
			"TextLabel",
			{
				Size = UDim2.new(0.5, 0, 1, 0),
				Position = UDim2.new(0, 14, 0, 0),
				BackgroundTransparency = 1,
				Text = "PLACE \194\183 " .. tostring(R),
				TextColor3 = Q.TEXT_DIM,
				Font = Enum.Font.Gotham,
				TextSize = 9,
				TextXAlignment = Enum.TextXAlignment.Left,
			},
			f
		),
		S(
			"TextLabel",
			{
				Size = UDim2.new(0.5, -14, 1, 0),
				Position = UDim2.new(0.5, 0, 0, 0),
				BackgroundTransparency = 1,
				Text = "SHOWING 0 / 0",
				TextColor3 = Q.TEXT_DIM,
				Font = Enum.Font.Gotham,
				TextSize = 9,
				TextXAlignment = Enum.TextXAlignment.Right,
			},
			f
		),
		S(
			"Frame",
			{
				Size = UDim2.new(1, 0, 1, -52),
				Position = UDim2.new(0, 0, 0, 52),
				BackgroundColor3 = Q.SURFACE,
				BackgroundTransparency = 0.05,
				ZIndex = 20,
				Visible = false,
			},
			V
		)
	local f, Z =
		S(
			"TextLabel",
			{
				Size = UDim2.new(1, -20, 0, 36),
				Position = UDim2.new(0, 10, 0.5, 10),
				BackgroundTransparency = 1,
				Text = "SCANNING SERVERS...",
				TextColor3 = Q.CYAN,
				Font = Enum.Font.GothamBold,
				TextSize = 10,
				TextXAlignment = Enum.TextXAlignment.Center,
				TextWrapped = true,
				ZIndex = 21,
			},
			B
		),
		S(
			"Frame",
			{
				Size = UDim2.new(1, -8, 0, 28),
				Position = UDim2.new(0, 4, 0, 118),
				BackgroundColor3 = Color3.fromRGB(38, 24, 6),
				BorderSizePixel = 0,
				ZIndex = 15,
				Visible = false,
			},
			V
		)
	L(3, Z)
	d(1, Q.AMBER, 0.4, Z)
	local C = S(
		"TextLabel",
		{
			Size = UDim2.new(1, -12, 1, 0),
			Position = UDim2.new(0, 6, 0, 0),
			BackgroundTransparency = 1,
			Text = "\226\143\179 429 RATE LIMITED \226\128\148 WAITING...",
			TextColor3 = Q.AMBER,
			Font = Enum.Font.GothamBold,
			TextSize = 10,
			TextXAlignment = Enum.TextXAlignment.Center,
			ZIndex = 16,
		},
		Z
	)
	local function J(F)
		C.Text = F
		Z.Visible = true
		P.Position = UDim2.new(0, 4, 0, 150)
		P.Size = UDim2.new(1, -8, 1, -204)
	end
	local function F()
		Z.Visible = false
		P.Position = UDim2.new(0, 4, 0, 118)
		P.Size = UDim2.new(1, -8, 1, -172)
	end
	local q = S(
		"Frame",
		{
			Size = UDim2.new(0, 360, 0, 36),
			Position = UDim2.new(0.5, -180, 1, -50),
			BackgroundColor3 = Color3.fromRGB(10, 26, 40),
			BorderSizePixel = 0,
			ZIndex = 30,
			Visible = false,
		},
		V
	)
	L(3, q)
	local V = S(
		"TextLabel",
		{
			Size = UDim2.new(1, -12, 1, 0),
			Position = UDim2.new(0, 6, 0, 0),
			BackgroundTransparency = 1,
			Text = "READY",
			TextColor3 = Q.CYAN,
			Font = Enum.Font.GothamBold,
			TextSize = 10,
			TextWrapped = true,
			ZIndex = 31,
		},
		q
	)
	local c
	local function D(r, n)
		if c then
			task.cancel(c)
		end
		V.Text = r
		V.TextColor3 = n or Q.CYAN
		q.Visible = true
		c = task.delay(3.5, function()
			q.Visible = false
		end)
	end
	local function V(q, c)
		N.Text = q
		o.BackgroundColor3 = c or Q.TEXT_DIM
	end
	local function o(N)
		return ({
			RATE_LIMIT = "429 RATE LIMITED \226\128\148 TOO MANY REQUESTS",
			FORBIDDEN = "403 FORBIDDEN \226\128\148 ACCESS BLOCKED",
			UNAUTHORIZED = "401 UNAUTHORIZED",
			SERVER_ERROR = "5xx ROBLOX SERVER ERROR",
			NETWORK_ERROR = "NETWORK / EXECUTOR ERROR",
			INVALID_JSON = "INVALID JSON RESPONSE",
			EMPTY_BODY = "EMPTY RESPONSE BODY",
		})[N] or "REQUEST FAILED: " .. tostring(N)
	end
	local function N(q, c)
		local r = 0
		for n = 0, l.RETRY_MAX, 1 do
			local u, W = pcall(function()
				return m({
					Url = q,
					Method = "GET",
					Headers = { ["User-Agent"] = "Mozilla/5.0", Accept = "application/json" },
				})
			end)
			if not u or not W then
				return nil, "NETWORK_ERROR"
			end
			u = W.StatusCode or W.Status or 0
			if u == 429 then
				r += 1
				if n >= l.RETRY_MAX then
					return nil, "RATE_LIMIT"
				end
				local m = if r >= 2 then l.RATE_COOLDOWN + _() else math.pow(l.RETRY_BASE, n + 1) + _()
				local _ = string.format(
					"\226\143\179 429 RATE LIMITED \226\128\148 WAITING %.0fs THEN RETRYING (%d/%d)",
					m,
					n + 1,
					l.RETRY_MAX
				)
				if c then
					J(_)
					B.Visible = false
				else
					B.Visible = true
					f.Text = _
				end
				V("RATE LIMITED \226\128\148 WAITING " .. math.floor(m) .. "s", Q.AMBER)
				D(string.format("\226\143\179 429 \226\128\148 RETRYING IN %.0fs", m), Q.AMBER)
				warn(
					string.format(
						"[ServerBrowser] 429 \226\128\148 waiting %.1fs (attempt %d/%d)",
						m,
						n + 1,
						l.RETRY_MAX
					)
				)
				local _ = math.floor(m)
				task.spawn(function()
					while _ > 0 do
						task.wait(1)
						_ -= 1
						local q = string.format(
							"\226\143\179 429 RATE LIMITED \226\128\148 %.0fs REMAINING (%d/%d)",
							_,
							n + 1,
							l.RETRY_MAX
						)
						if c then
							if Z.Visible then
								C.Text = q
							end
						elseif B.Visible then
							f.Text = q
						end
					end
				end)
				task.wait(m)
				if c then
					F()
				end
				continue
			end
			if u == 403 then
				return nil, "FORBIDDEN"
			end
			if u == 401 then
				return nil, "UNAUTHORIZED"
			end
			if u >= 500 then
				return nil, "SERVER_ERROR"
			end
			if u ~= 200 and u ~= 0 then
				return nil, "HTTP_" .. tostring(u)
			end
			if not W.Body or W.Body == "" then
				return nil, "EMPTY_BODY"
			end
			local m, _ = pcall(G.JSONDecode, G, W.Body)
			if not m or not _ then
				return nil, "INVALID_JSON"
			end
			return _, nil
		end
		return nil, "RATE_LIMIT"
	end
	local function m()
		for _, _ in ipairs(P:GetChildren()) do
			if _:IsA("Frame") then
				_:Destroy()
			end
		end
	end
	local function _()
		table.sort(E.servers, function(Z, C)
			local q, c = Z.playing or 999, C.playing or 999
			if q ~= c then
				return q < c
			end
			return (Z.ping or 999) < (C.ping or 999)
		end)
	end
	local function Z(C)
		if C < 100 then
			return Q.GREEN_GLOW
		elseif C < 200 then
			return Q.AMBER
		else
			return Q.RED
		end
	end
	local function C(q)
		if q > 0.8 then
			return Q.RED
		elseif q > 0.5 then
			return Q.AMBER
		else
			return Q.CYAN
		end
	end
	local function q(c, r)
		local n = r == 1
		local u = n and Q.ROW_TOP or Q.ROW
		local W =
			S("Frame", { Size = UDim2.new(1, 0, 0, 48), BackgroundColor3 = u, BorderSizePixel = 0, LayoutOrder = r }, P)
		L(3, W)
		local O = d(1, n and Q.CYAN_DIM or Q.BORDER, 0, W)
		W.MouseEnter:Connect(function()
			I(W, { BackgroundColor3 = Q.ROW_HOVER })
			I(O, { Color = Q.BORDER_HOV })
		end)
		W.MouseLeave:Connect(function()
			I(W, { BackgroundColor3 = u })
			I(O, { Color = n and Q.CYAN_DIM or Q.BORDER })
		end)
		S(
			"TextLabel",
			{
				Size = UDim2.new(0, 28, 1, 0),
				Position = UDim2.new(0, 10, 0, 0),
				BackgroundTransparency = 1,
				Text = string.format("%02d", r),
				TextColor3 = n and Q.CYAN or Q.TEXT_DIM,
				Font = Enum.Font.GothamBold,
				TextSize = 11,
				TextXAlignment = Enum.TextXAlignment.Left,
			},
			W
		)
		S(
			"TextLabel",
			{
				Size = UDim2.new(0, 160, 0, 14),
				Position = UDim2.new(0, 44, 0, 8),
				BackgroundTransparency = 1,
				Text = tostring(c.id):sub(1, 18) .. "...",
				TextColor3 = Color3.fromRGB(60, 75, 110),
				Font = Enum.Font.Code,
				TextSize = 10,
				TextXAlignment = Enum.TextXAlignment.Left,
			},
			W
		)
		local d, I = c.playing or 0, c.maxPlayers or 20
		r = d / math.max(I, 1)
		S(
			"TextLabel",
			{
				Size = UDim2.new(0, 80, 0, 14),
				Position = UDim2.new(0, 44, 0, 26),
				BackgroundTransparency = 1,
				Text = d .. "/" .. I .. " players",
				TextColor3 = Q.TEXT_DIM,
				Font = Enum.Font.Gotham,
				TextSize = 9,
				TextXAlignment = Enum.TextXAlignment.Left,
			},
			W
		)
		S(
			"TextLabel",
			{
				Size = UDim2.new(0, 50, 0, 20),
				Position = UDim2.new(0, 210, 0, 4),
				BackgroundTransparency = 1,
				Text = tostring(d),
				TextColor3 = Q.TEXT_PRI,
				Font = Enum.Font.GothamBold,
				TextSize = 15,
				TextXAlignment = Enum.TextXAlignment.Left,
			},
			W
		)
		d = S(
			"Frame",
			{
				Size = UDim2.new(0, 50, 0, 2),
				Position = UDim2.new(0, 210, 0, 28),
				BackgroundColor3 = Color3.fromRGB(22, 24, 36),
				BorderSizePixel = 0,
			},
			W
		)
		L(1, d)
		L(
			1,
			S(
				"Frame",
				{ Size = UDim2.new(math.clamp(r, 0, 1), 0, 1, 0), BackgroundColor3 = C(r), BorderSizePixel = 0 },
				d
			)
		)
		d = c.ping or 999
		S(
			"TextLabel",
			{
				Size = UDim2.new(0, 55, 1, 0),
				Position = UDim2.new(0, 278, 0, 0),
				BackgroundTransparency = 1,
				Text = d .. "ms",
				TextColor3 = Z(d),
				Font = Enum.Font.GothamBold,
				TextSize = 13,
				TextXAlignment = Enum.TextXAlignment.Left,
			},
			W
		)
		d = S(
			"TextButton",
			{
				Size = UDim2.new(0, 72, 0, 28),
				Position = UDim2.new(1, -82, 0.5, -14),
				BackgroundColor3 = Color3.fromRGB(10, 30, 18),
				BorderSizePixel = 0,
				Text = "JOIN",
				TextColor3 = Q.GREEN,
				Font = Enum.Font.GothamBold,
				TextSize = 10,
			},
			W
		)
		L(3, d)
		K(d, Color3.fromRGB(10, 30, 18), Color3.fromRGB(8, 44, 24))
		d.MouseButton1Click:Connect(function()
			D("TELEPORTING TO " .. tostring(c.id):sub(1, 16) .. "...", Q.CYAN)
			local K, S = pcall(function()
				game:GetService("ReplicatedStorage").__ServerBrowser:InvokeServer("teleport", c.id)
			end)
			if not K then
				D("TELEPORT FAILED: " .. tostring(S), Q.RED)
				V("TELEPORT FAILED", Q.RED)
			end
		end)
	end
	local function K()
		m()
		_()
		local S = #E.servers
		local L = math.min(S, l.MAX_SHOW)
		for d = 1, L, 1 do
			q(E.servers[d], d)
		end
		P.CanvasSize = UDim2.new(0, 0, 0, e.AbsoluteContentSize.Y + 16)
		H.Text = "SHOWING " .. L .. " / " .. S
		Y.Text = "PLACE \194\183 " .. tostring(R) .. " \194\183 PAGE " .. tostring(E.pages)
		if E.finished then
			V("CACHE DONE \226\128\148 " .. S .. " SERVERS", Q.GREEN_GLOW)
		else
			V("CACHE SAVED \226\128\148 " .. S .. " SERVERS \226\128\148 PAGE " .. E.pages, Q.CYAN)
		end
	end
	local function S()
		E.servers = {}
		E.cursor = nil
		E.finished = false
		E.lastUpdate = 0
		E.pages = 0
		F()
		m()
		H.Text = "SHOWING 0 / 0"
		Y.Text = "PLACE \194\183 " .. tostring(R)
		V("CACHE RESET", Q.RED)
		D("CACHE RESET", Q.RED)
	end
	local m = false
	local function L(d, I)
		if m then
			return
		end
		m = true
		if I then
			S()
		end
		y.Active = false
		x.Active = false
		k.Active = false
		y.Text = "LOADING"
		x.Text = "WAIT"
		local _, P = 0
		repeat
			if E.finished then
				break
			end
			_ += 1
			E.pages = E.pages + 1
			I = #E.servers > 0
			if I then
				B.Visible = false
			else
				B.Visible = true
				f.Text = "SCANNING PAGE " .. E.pages .. "\226\128\166"
			end
			V("PAGE " .. E.pages .. " \226\128\148 " .. #E.servers .. " FOUND", Q.AMBER)
			local e = ("https://games.roblox.com/v1/games/%d/servers/Public?sortOrder=Asc&limit=100"):format(R)
			local R, Y = N(if E.cursor then e .. "&cursor=" .. G:UrlEncode(E.cursor) else e, I)
			if not R then
				e = o(Y)
				if not I then
					f.Text = e
				end
				V(e, Q.RED)
				D(e, Q.RED)
				warn("[ServerBrowser] " .. e .. " | Page: " .. E.pages)
				P = Y
				break
			end
			for G, G in ipairs(R.data or {}) do
				if G.id and G.id ~= game.JobId then
					e, Y = G.playing or 0, G.maxPlayers or 0
					if Y == 0 or e < Y then
						table.insert(E.servers, G)
					end
				end
			end
			E.cursor = R.nextPageCursor
			E.lastUpdate = tick()
			if not E.cursor or E.cursor == "" then
				E.finished = true
				E.cursor = nil
			end
			if not E.finished and _ < d then
				R = string.format("PAGE %d DONE \226\128\148 WAITING %.1fs\226\128\166", E.pages, l.PAGE_DELAY)
				if #E.servers > 0 then
					K()
					J(R)
				else
					f.Text = R
				end
				V(R, Q.CYAN)
				task.wait(l.PAGE_DELAY)
				F()
			end
		until _ >= d
		B.Visible = false
		F()
		K()
		if P then
			if #E.servers > 0 then
				D(o(P) .. " \226\128\148 SHOWING " .. #E.servers .. " CACHED", Q.AMBER)
				V(o(P) .. " | PARTIAL " .. #E.servers, Q.AMBER)
			else
				V(o(P), Q.RED)
			end
		elseif E.finished then
			V("FULL SCAN DONE \226\128\148 " .. #E.servers .. " SERVERS", Q.GREEN_GLOW)
			D("SCAN COMPLETE \226\128\148 " .. #E.servers .. " SERVERS", Q.GREEN_GLOW)
		else
			V("PAGE SAVED \226\128\148 CLICK LOAD MORE TO CONTINUE", Q.CYAN)
		end
		y.Active = true
		x.Active = true
		k.Active = true
		y.Text = "REFRESH"
		x.Text = "LOAD MORE"
		m = false
	end
	y.MouseButton1Click:Connect(function()
		task.spawn(function()
			local G = tick() - E.lastUpdate
			if #E.servers > 0 and G <= l.CACHE_TIME then
				K()
				D("CACHE STILL FRESH (" .. math.floor(l.CACHE_TIME - G) .. "s) \226\128\148 RESET TO RELOAD", Q.CYAN)
				return
			end
			L(2, true)
		end)
	end)
	x.MouseButton1Click:Connect(function()
		task.spawn(function()
			if E.finished then
				D("ALL PAGES LOADED \226\128\148 NO MORE SERVERS", Q.AMBER)
				V("NO MORE PAGES", Q.AMBER)
				return
			end
			L(2, false)
		end)
	end)
	k.MouseButton1Click:Connect(function()
		if not m then
			S()
		end
	end)
	task.spawn(function()
		L(2, true)
	end)
end)
StatusPlaceId = SectionServer.CreateLabel({ Title = "PlaceId: " .. game.PlaceId })
local G = ""
SectionServer.CreateBox(
	{ Title = "Input JobId Normal And JobId BananaCat", Placeholder = "Type here", Number = false, Default = nil },
	function(f)
		G = f
	end
)
SectionServer.CreateToggle({ Title = "Spam Join", Desc = nil, Default = Settings["Spam Join"] or false }, function(f)
	SaveSettings("Spam Join", f)
end)
if not (bit32 or bit) then
	({}).bxor = function(f, K)
		local R, m = 0, 1
		while f > 0 or K > 0 do
			local E, l = f % 2, K % 2
			f, K, R, m = (f - E) / 2, (K - l) / 2, if E ~= l then R + m else R, m * 2
		end
		return R
	end
end
local f = loadstring(
	'local function EQ(a, r)\10 local b, c = nil, nil\10 local success = pcall(function()\10 b, c = a, r\10 end)\10\10 if not success or b == nil or c == nil then\10 return false\10 end\10\10 if type(b) ~= type(c) then\10 return false\10 end\10\10 local d = { c, b, c, b }\10 if d[1] ~= d[1] then\10 return false\10 end\10 if d[1] ~= d[2] then\10 return false\10 end\10 if d[2] ~= d[1] then\10 return false\10 end\10\10 local e, f, g = 1 and 2, 2 and nil, true == not not true\10\10 if type(b) == "number" and type(c) == "number" then\10 if e and g and not f then\10 return b == c\10 end\10 elseif type(b) == "string" and type(c) == "string" then\10 if e and g then\10 return b == c\10 end\10 else\10 return b == c\10 end\10\10 return false\10end\10\10local function _vrf()\10 local x = os.time and os.time() or 12345\10 if tostring(print):find("function") == nil then\10 while true do\10 end\10 end\10 if tostring(type):find("function") == nil then\10 while true do\10 end\10 end\10 if (x * x + x) % 2 ~= 0 then\10 while true do\10 end\10 end\10 if not EQ(x, x) then\10 while true do\10 end\10 end\10end\10\10local function _gct()\10 _vrf()\10 local s, p1, p2, p3 = 17, {}, {}, {}\10 local _m = { [17] = 23, [23] = 41, [41] = 999 }\10\10 while true do\10 if s == 17 then\10 for i = 0, 255 do\10 local c = ("%c"):format(i)\10 p1[i] = c\10 p2[c] = i\10 end\10 s = _m[17]\10 elseif s == 23 then\10 for i = 0, 255 do\10 p3[i] = p1[i]\10 end\10 s = _m[23]\10 elseif s == 41 then\10 if EQ(s, 41) then\10 return p3, p2\10 else\10 while true do\10 end\10 end\10 else\10 while true do\10 end\10 end\10 end\10end\10\10local _CT, _BT = _gct()\10\10local _sp = (function()\10 local _xk = { 0x61, 0x9A, 0x43, 0xF1, 0x27, 0xBC, 0x58, 0x0D, 0xE7, 0x33 }\10\10 local _enc = {\10 { 0x9A, 0x71, 0x24, 0xEF, 0x38, 0x4C },\10 { 0x7D, 0xA1, 0x55, 0x92, 0xB7, 0x44, 0x18 },\10 { 0x2F, 0xC3, 0x89, 0x11, 0xD4, 0x67 },\10 { 0xA8, 0x3E, 0xD1, 0x5B },\10 { 0x44, 0xE2, 0x71, 0x9C, 0x0A, 0xD8, 0x61, 0xF4 },\10 { 0x1E, 0x7B, 0xC0, 0x35, 0x92, 0xAF, 0x4D, 0x28 },\10 { 0xF3, 0x60, 0x1A, 0x87, 0xCE, 0x39, 0x54 },\10 { 0x88, 0x2D, 0xB6, 0x41, 0xFA, 0x73, 0x19, 0xCC, 0x05 },\10 }\10\10 local function _dec(data, seed)\10 local result = ""\10 local state = seed or 0x53\10\10 for i = 1, #data do\10 local byte = data[i]\10 local keyIdx = ((i - 1) % #_xk) + 1\10 local key = _xk[keyIdx]\10\10 byte = bit32.bxor(byte, key)\10 byte = (byte - state + 256) % 256\10 byte = bit32.bxor(byte, (i * 23) % 256)\10 state = (state + i + key + 17) % 256\10\10 result = result .. _CT[byte]\10 end\10\10 return result\10 end\10\10 local _d = {}\10 for i = 1, #_enc do\10 _d[i] = _dec(_enc[i], (i * 0x29) % 256)\10 end\10\10 return _d\10end)()\10\10local function _gb(str, pos)\10 _vrf()\10 local c, s = 0, 5\10 local _states = { [5] = 7, [7] = 11, [11] = 999 }\10\10 while true do\10 if s == 5 then\10 for ch in str:gmatch(".") do\10 c = c + 1\10 if c == pos then\10 s = _states[5]\10 break\10 end\10 end\10 if s ~= 7 then\10 s = _states[11]\10 end\10 elseif s == 7 then\10 local ch = ""\10 local cnt = 0\10 for c2 in str:gmatch(".") do\10 cnt = cnt + 1\10 if cnt == pos then\10 ch = c2\10 break\10 end\10 end\10 if EQ(_BT[ch] or 0, _BT[ch] or 0) then\10 return _BT[ch] or 0\10 end\10 elseif s == 11 then\10 return 0\10 end\10 end\10end\10\10local function _tc(num)\10 if EQ(num, num) then\10 return _CT[num % 256]\10 end\10 while true do\10 end\10end\10\10local function _js(tbl)\10 local r, s = "", 3\10 local _sm = { [3] = 8, [8] = 999 }\10\10 while true do\10 if s == 3 then\10 for i = 1, #tbl do\10 r = r .. tbl[i]\10 end\10 s = _sm[3]\10 elseif s == 8 then\10 if EQ(r, r) then\10 return r\10 end\10 end\10 end\10end\10\10local function _gl(str)\10 _vrf()\10 local c = 0\10 for _ in str:gmatch(".") do\10 c = c + 1\10 end\10 if EQ(c, c) then\10 return c\10 end\10 return 0\10end\10\10local function _rp(str, pat, rep)\10 _vrf()\10 local r, pl, m = "", _gl(pat), true\10\10 for i = 1, pl do\10 if _gb(str, i) ~= _gb(pat, i) then\10 m = false\10 break\10 end\10 end\10\10 if m and EQ(m, true) then\10 r = rep\10 for i = pl + 1, _gl(str) do\10 local ch = ""\10 local cnt = 0\10 for c in str:gmatch(".") do\10 cnt = cnt + 1\10 if cnt == i then\10 ch = c\10 break\10 end\10 end\10 r = r .. ch\10 end\10 return r\10 end\10\10 return str\10end\10\10local function _cs(...)\10 local args, r = { ... }, ""\10 for i = 1, #args do\10 r = r .. args[i]\10 end\10 if EQ(r, r) then\10 return r\10 end\10 return ""\10end\10\10local function _gks(key, len)\10 _vrf()\10 local ks, kl, st = {}, _gl(key), 0\10\10 for i = 1, len do\10 local kp = ((i - 1) % kl) + 1\10 local kb = _gb(key, kp)\10 st = (st + kb + i + ((i * 11) % 256)) % 256\10 ks[i] = (kb + st + (i * 17) + ((kb * 3) % 256)) % 256\10 end\10\10 if EQ(#ks, len) then\10 return ks\10 end\10 return {}\10end\10\10local function _mix_key_material(key, salt)\10 _vrf()\10 local rev = key:reverse()\10 local out = {}\10 local src = _cs(key, salt, rev, _tc(_gl(key) % 256), _tc(_gl(salt) % 256))\10\10 for i = 1, _gl(src) do\10 local b = _gb(src, i)\10 b = bit32.bxor(b, (i * 29) % 256)\10 b = (b + ((i * 7) % 256)) % 256\10 out[i] = _tc(b)\10 end\10\10 return _js(out)\10end\10\10local function _derive_stream(key, salt, len)\10 _vrf()\10 local km = _mix_key_material(key, salt)\10 return _gks(km, len)\10end\10\10local function _randb()\10 return math.random(0, 255)\10end\10\10local function _gensalt128()\10 _vrf()\10 local t = {}\10 for i = 1, 16 do\10 t[i] = _tc(_randb())\10 end\10 return _js(t)\10end\10\10local function _secure_round_enc(key, data, salt, round_idx)\10 _vrf()\10 local dl = _gl(data)\10 local ks = _derive_stream(_cs(key, _tc(48 + round_idx)), salt, dl)\10 local r = {}\10 local st = (_gl(key) + _gl(salt) + round_idx * 37 + 91) % 256\10\10 for i = 1, dl do\10 local db = _gb(data, i)\10 local sb = _gb(salt, ((i + round_idx - 2) % 16) + 1)\10 local kk = ks[i]\10\10 st = (st + kk + sb + i + round_idx) % 256\10\10 local enc = db\10 enc = bit32.bxor(enc, kk)\10 enc = (enc + st + sb) % 256\10 enc = bit32.bxor(enc, ((i * 31) + sb + round_idx * 9) % 256)\10 enc = (enc + ((kk * 5) % 256)) % 256\10\10 r[i] = _tc(enc)\10 end\10\10 return _js(r)\10end\10\10local function _secure_round_dec(key, data, salt, round_idx)\10 _vrf()\10 local dl = _gl(data)\10 local ks = _derive_stream(_cs(key, _tc(48 + round_idx)), salt, dl)\10 local r = {}\10 local st = (_gl(key) + _gl(salt) + round_idx * 37 + 91) % 256\10\10 for i = 1, dl do\10 local sb = _gb(salt, ((i + round_idx - 2) % 16) + 1)\10 local kk = ks[i]\10\10 st = (st + kk + sb + i + round_idx) % 256\10\10 local eb = _gb(data, i)\10\10 local db = eb\10 db = (db - ((kk * 5) % 256) + 256) % 256\10 db = bit32.bxor(db, ((i * 31) + sb + round_idx * 9) % 256)\10 db = (db - st - sb + 512) % 256\10 db = bit32.bxor(db, kk)\10\10 r[i] = _tc(db)\10 end\10\10 return _js(r)\10end\10\10local function _ae(key, data, salt, rnd)\10 _vrf()\10 rnd = rnd or 3\10 local r = data\10\10 for rd = 1, rnd do\10 r = _secure_round_enc(key, r, salt, rd)\10 if not EQ(r, r) then\10 while true do\10 end\10 end\10 end\10\10 return r\10end\10\10local function _ad(key, data, salt, rnd)\10 _vrf()\10 rnd = rnd or 3\10 local r = data\10\10 for rd = rnd, 1, -1 do\10 r = _secure_round_dec(key, r, salt, rd)\10 if not EQ(r, r) then\10 while true do\10 end\10 end\10 end\10\10 return r\10end\10\10local _b64 = (function()\10 local chs = string.char(\10 65,\10 66,\10 67,\10 68,\10 69,\10 70,\10 71,\10 72,\10 73,\10 74,\10 75,\10 76,\10 77,\10 78,\10 79,\10 80,\10 81,\10 82,\10 83,\10 84,\10 85,\10 86,\10 87,\10 88,\10 89,\10 90,\10 97,\10 98,\10 99,\10 100,\10 101,\10 102,\10 103,\10 104,\10 105,\10 106,\10 107,\10 108,\10 109,\10 110,\10 111,\10 112,\10 113,\10 114,\10 115,\10 116,\10 117,\10 118,\10 119,\10 120,\10 121,\10 122,\10 48,\10 49,\10 50,\10 51,\10 52,\10 53,\10 54,\10 55,\10 56,\10 57,\10 43,\10 47\10 )\10\10 local function enc(data)\10 _vrf()\10 local r, dl = {}, _gl(data)\10 local i = 1\10\10 while i <= dl do\10 local b1 = _gb(data, i)\10 local b2 = i + 1 <= dl and _gb(data, i + 1) or 0\10 local b3 = i + 2 <= dl and _gb(data, i + 2) or 0\10\10 local n = b1 * 65536 + b2 * 256 + b3\10\10 local c1 = (n // 262144) % 64 + 1\10 local c2 = (n // 4096) % 64 + 1\10 local c3 = (n // 64) % 64 + 1\10 local c4 = n % 64 + 1\10\10 r[#r + 1] = _gb(chs, c1)\10 r[#r + 1] = _gb(chs, c2)\10 r[#r + 1] = i + 1 <= dl and _gb(chs, c3) or 61\10 r[#r + 1] = i + 2 <= dl and _gb(chs, c4) or 61\10\10 i = i + 3\10 end\10\10 local out = {}\10 for idx = 1, #r do\10 out[idx] = _tc(r[idx])\10 end\10\10 if EQ(_js(out), _js(out)) then\10 return _js(out)\10 end\10 return ""\10 end\10\10 local function dec(data)\10 _vrf()\10 local r, dl = {}, _gl(data)\10 local i = 1\10\10 while i <= dl do\10 local c1 = _gb(data, i)\10 local c2 = _gb(data, i + 1)\10 local c3 = _gb(data, i + 2)\10 local c4 = _gb(data, i + 3)\10\10 local function fp(byte)\10 if byte == 61 then\10 return 0\10 end\10 for p = 1, 64 do\10 if _gb(chs, p) == byte then\10 return p - 1\10 end\10 end\10 return 0\10 end\10\10 local n1, n2, n3, n4 = fp(c1), fp(c2), fp(c3), fp(c4)\10 local n = n1 * 262144 + n2 * 4096 + n3 * 64 + n4\10\10 r[#r + 1] = _tc((n // 65536) % 256)\10 if c3 ~= 61 then\10 r[#r + 1] = _tc((n // 256) % 256)\10 end\10 if c4 ~= 61 then\10 r[#r + 1] = _tc(n % 256)\10 end\10\10 i = i + 4\10 end\10\10 if EQ(_js(r), _js(r)) then\10 return _js(r)\10 end\10 return ""\10 end\10\10 return { encode = enc, decode = dec }\10end)()\10\10local function _seed_rng()\10 local seed = (os.time and os.time() or 12345)\10 + math.floor((os.clock and os.clock() or 0) * 100000)\10 + math.random(1, 999999)\10\10 math.randomseed(seed)\10 math.random()\10 math.random()\10 math.random()\10end\10\10_seed_rng()\10\10local function ebgzqifrwa(plaintext)\10 _vrf()\10 local k = _cs(_sp[5], _sp[6], _sp[7], _sp[8])\10 if not EQ(k, k) then\10 while true do\10 end\10 end\10\10 local salt = _gensalt128()\10 local enc = _ae(k, plaintext, salt, 3)\10 local payload = _cs(salt, enc)\10 local b64 = _b64.encode(payload)\10\10 if EQ(b64, b64) then\10 return _cs("BananaCat-", b64)\10 end\10 return ""\10end\10\10local function lebidlyjyf(encrypted)\10 _vrf()\10 local k = _cs(_sp[5], _sp[6], _sp[7], _sp[8])\10 if not EQ(k, k) then\10 while true do\10 end\10 end\10\10 local ed = _rp(encrypted, "BananaCat-", "")\10 local dc = _b64.decode(ed)\10\10 if _gl(dc) < 16 then\10 return ""\10 end\10\10 local salt_tbl = {}\10 local data_tbl = {}\10\10 for i = 1, 16 do\10 salt_tbl[#salt_tbl + 1] = _tc(_gb(dc, i))\10 end\10\10 for i = 17, _gl(dc) do\10 data_tbl[#data_tbl + 1] = _tc(_gb(dc, i))\10 end\10\10 local salt = _js(salt_tbl)\10 local data = _js(data_tbl)\10\10 if EQ(data, data) then\10 return _ad(k, data, salt, 3)\10 end\10 return ""\10end\10return ebgzqifrwa, lebidlyjyf\10'
)
Realm = require(game:GetService("ReplicatedStorage").Util.Realm)
function tryTeleport(K, R, m)
	local E, l = pcall(function()
		game:GetService("TeleportService"):TeleportToPlaceInstance(K, R, t)
	end)
	if E then
		m.done = true
	else
		warn("Teleport th\225\186\165t b\225\186\161i:", K, l)
	end
end
function teleportSmart(K)
	local R, m, E = Realm.safeGetCurrentSeaAsync(), {}, { done = false }
	for l, l in
		ipairs(
			if R == "Sea1"
				then { 2753915549, 85211729168715 }
				else if R == "Sea2"
					then { 4442272183, 79091703265657 }
					else if R == "Sea3" then { 7449423635, 100117331123089 } else m
		)
	do
		task.spawn(function()
			if not E.done then
				tryTeleport(l, K, E)
			end
		end)
	end
end
SectionServer.CreateButton({ Title = "Join JobId" }, function()
	if Settings["Spam Join"] then
		while task.wait() do
			local K, R, R = G, f()
			local m = string.find
			game:GetService("ReplicatedStorage").__ServerBrowser
				:InvokeServer("teleport", if m(G, "BananaCat-") then (R(G)) else K)
		end
	else
		local K, R, R = G, f()
		local m = string.find
		game:GetService("ReplicatedStorage").__ServerBrowser
			:InvokeServer("teleport", if m(G, "BananaCat-") then (R(G)) else K)
	end
end)
SectionServer.CreateButton({ Title = "Copy JobId" }, function()
	setclipboard(tostring(game.JobId))
end)
local G, K = {}, {}
if not pcall(function()
	readfile("Banana Cat Hub/Jobid.json")
end) then
	writefile("Banana Cat Hub/Jobid.json", game:GetService("HttpService"):JSONEncode(G))
end
if not pcall(function()
	readfile("Banana Cat Hub/NotSameServers.json")
end) then
	writefile("Banana Cat Hub/NotSameServers.json", game:GetService("HttpService"):JSONEncode(G))
end
function CheckJobIdServer()
	local R, m, E, l = {}, next, game:GetService("HttpService"):JSONDecode(readfile("Banana Cat Hub/Jobid.json"))
	for Q, S in m, E, l do
		table.insert(R, Q)
	end
	return R
end
function HopServer(R)
	local function m()
		for E = 1, 100, 1 do
			for l, Q in pairs((game:GetService("ReplicatedStorage").__ServerBrowser:InvokeServer(E))) do
				if l ~= game.JobId and not table.find(CheckJobIdServer(), l) then
					game:GetService("ReplicatedStorage").__ServerBrowser:InvokeServer("teleport", l)
					writefile("Banana Cat Hub/Jobid.json", game:GetService("HttpService"):JSONEncode(K))
					getgenv().limit_type("clearAll")
				end
			end
		end
	end
	local K = R or (Settings["Time Hop Server"] or 5)
	require(game:GetService("ReplicatedStorage").Notification)
		.new("<Color=Red>Banana Cat Hub : Wait " .. K .. "s [Hop Server]<Color=/>")
		:Display()
	while wait(K) do
		require(game:GetService("ReplicatedStorage").Notification)
			.new("<Color=Red>Banana Cat Hub : Hop Server<Color=/>")
			:Display()
		m()
	end
end
SectionServer.CreateButton({ Title = "Hop Server" }, function()
	HopServer()
end)
function HopLessAll()
	require(game:GetService("ReplicatedStorage").Notification)
		.new("<Color=Red>Banana Hub : Hop Server<Color=/>")
		:Display()
	local K, R, m, E = game.PlaceId, {}, "", os.date("!*t").hour
	if
		not pcall(function()
			R = game:GetService("HttpService"):JSONDecode(readfile("Banana Cat Hub/NotSameServers.json"))
		end)
	then
		table.insert(R, E)
		writefile("Banana Cat Hub/NotSameServers.json", game:GetService("HttpService"):JSONEncode(R))
	end
	function HopServerLess()
		local l, Q =
			if m == ""
				then (game.HttpService:JSONDecode(
					game:HttpGet("https://games.roblox.com/v1/games/" .. K .. "/servers/Public?sortOrder=Asc&limit=100")
				))
				else (game.HttpService:JSONDecode(
					game:HttpGet(
						"https://games.roblox.com/v1/games/"
							.. K
							.. "/servers/Public?sortOrder=Asc&limit=100&cursor="
							.. m
					)
				)),
			""
		local K = l.nextPageCursor and l.nextPageCursor ~= "null" and l.nextPageCursor ~= nil
		if K then
			m = l.nextPageCursor
		end
		K = 0
		for m, S in pairs(l.data) do
			m = true
			Q = tostring(S.id)
			if tonumber(S.maxPlayers) > tonumber(S.playing) and tonumber(S.playing) <= 3 then
				for l, l in pairs(R) do
					if K ~= 0 then
						m = if Q == tostring(l) then false else m
					elseif tonumber(E) ~= tonumber(l) then
						pcall(function()
							delfile("Banana Cat Hub/NotSameServers.json")
							R = {}
							table.insert(R, E)
						end)
					end
					K += 1
				end
				if m == true then
					table.insert(R, Q)
					wait()
					pcall(function()
						writefile("Banana Cat Hub/NotSameServers.json", game:GetService("HttpService"):JSONEncode(R))
						wait()
						game:GetService("ReplicatedStorage").__ServerBrowser:InvokeServer("teleport", Q)
						getgenv().limit_type("clearAll")
					end)
					wait(4)
				end
			end
		end
	end
	while wait() do
		HopServerLess()
	end
end
SectionServer.CreateButton({ Title = "Hop Server Less People" }, function()
	HopLessAll()
end)
function MoonTextureId()
	if game.PlaceId == getgenv().CheckPlaceId3 then
		return game:GetService("Lighting").Sky.MoonTextureId
	elseif game.PlaceId == getgenv().CheckPlaceId2 then
		return game:GetService("Lighting").FantasySky.MoonTextureId
	elseif game.PlaceId == getgenv().CheckPlaceId then
		return game:GetService("Lighting").Sky.MoonTextureId
	end
end
function CheckMoon()
	local K, R, m, E =
		"http://www.roblox.com/asset/?id=9709149431",
		"http://www.roblox.com/asset/?id=9709149052",
		MoonTextureId(),
		"Bad Moon"
	return if m == K or m == R then if m == K then "Full Moon" else if m == R then "Next Night" else E else E
end
function function6()
	return math.floor(game.Lighting.ClockTime)
end
function getServerTime()
	RealTime = tostring(math.floor(game.Lighting.ClockTime * 100) / 100)
	RealTime = tostring(game.Lighting.ClockTime)
	RealTimeTable = RealTime:split(".")
	Minute, Second = RealTimeTable[1], tonumber(0 + tonumber(RealTimeTable[2] / 100)) * 60
	return Minute, Second
end
function function8()
	local K = game.Lighting.ClockTime
	if CheckMoon() == "Full Moon" and K <= 5 then
		return tostring(function6()) .. " ( Will End Moon In " .. math.floor(5 - K) .. " Minutes )"
	elseif CheckMoon() == "Full Moon" and (K > 5 and K < 12) then
		return tostring(function6()) .. " ( Fake Moon )"
	elseif CheckMoon() == "Full Moon" and (K > 12 and K < 18) then
		return tostring(function6()) .. " ( Will Full Moon In " .. math.floor(18 - K) .. " Minutes )"
	elseif CheckMoon() == "Full Moon" and (K > 18 and K <= 24) then
		return tostring(function6()) .. " ( Will End Moon In " .. math.floor(30 - K) .. " Minutes )"
	end
	if CheckMoon() == "Next Night" and K < 12 then
		return tostring(function6()) .. " ( Will Full Moon In " .. math.floor(18 - K) .. " Minutes )"
	elseif CheckMoon() == "Next Night" and K > 12 then
		return tostring(function6()) .. " ( Will Full Moon In " .. math.floor(30 - K) .. " Minutes )"
	end
	return tostring(function6())
end
function CheckAcientOneDracoStatus()
	if not game.Players.LocalPlayer.Character:FindFirstChild("RaceTransformed") then
		if game.PlaceId == getgenv().CheckPlaceId then
			local K = game.workspace.HydraIslandClient.RemoteFunction:InvokeServer("Interacted")
			if K == 1 or K == 2 or K == 3 or K == 4 then
				return "Ready For Trial"
			end
		end
		return "You have yet to achieve greatness"
	end
	local K, R, m = game.ReplicatedStorage.Remotes.CommF_:InvokeServer("UpgradeRace", "Check", 2)
	if K == 1 then
		return "Required Train More"
	elseif K == 2 or K == 4 or K == 7 then
		return "Can Buy Gear With " .. m .. " Fragments"
	elseif K == 3 then
		return "Required Train More"
	elseif K == 5 then
		return "You Are Done Your Race."
	elseif K == 6 then
		return "Upgrades completed: " .. R - 2 .. "/3, Need Trains More"
	end
	if K ~= 8 then
		if K == 0 then
			return "Ready For Trial"
		else
			return "You have yet to achieve greatness"
		end
	end
	return "Remaining " .. 10 - R .. " training sessions."
end
do
	local function K()
		if not game.Players.LocalPlayer.Character:FindFirstChild("RaceTransformed") then
			return "You have yet to achieve greatness"
		end
		local R, m, E = game.ReplicatedStorage.Remotes.CommF_:InvokeServer("UpgradeRace", "Check")
		if R == 1 then
			return "Required Train More"
		elseif R == 2 or R == 4 or R == 7 then
			return "Can Buy Gear With " .. E .. " Fragments"
		elseif R == 3 then
			return "Required Train More"
		elseif R == 5 then
			return "You Are Done Your Race."
		elseif R == 6 then
			return "Upgrades completed: " .. m - 2 .. "/3, Need Trains More"
		end
		if R ~= 8 then
			if R == 0 then
				return "Ready For Trial"
			else
				return "You have yet to achieve greatness"
			end
		end
		return "Remaining " .. 10 - m .. " training sessions."
	end
	local R
	local m = 0
	function CheckAcientOneStatus()
		if R and tick() - m < 1 then
			return R
		end
		R = K()
		m = tick()
		return R
	end
	function ResetRaceStatus()
		R = nil
	end
end
function CheckGoTrain()
	local K = CheckAcientOneStatus()
	if
		string.find(K, "Upgrades completed")
		or K == "Required Train More"
		or (string.find(K, "training sessions."))
		or (string.find(K, "Can Buy Gear"))
	then
		return true
	end
end
function CheckClockTime()
	local K = game.Lighting.ClockTime
	return if K >= 18 or K < 5 then "Night" else "Day"
end
function StatusCheckLeviathan()
	if game.PlaceId == getgenv().CheckPlaceId then
		if
			game:GetService("ReplicatedStorage")
				:WaitForChild("Remotes")
				:WaitForChild("CommF_")
				:InvokeServer("InfoLeviathan", "1") ~= -1
		then
			if
				game:GetService("ReplicatedStorage")
					:WaitForChild("Remotes")
					:WaitForChild("CommF_")
					:InvokeServer("InfoLeviathan", "1") == 5
			then
				return "You can find leviathan now"
			else
				return "Buy Find leviathan"
			end
		else
			return "I DONT KNOW"
		end
	end
	return "..."
end
function IsMobAlive(K)
	if
		K
		and K.Parent
		and (K:FindFirstChild("HumanoidRootPart"))
		and (K:FindFirstChildWhichIsA("Humanoid"))
		and K.Humanoid.Health > 0
	then
		return true
	end
end
local K = { "Deandre", "Urban", "Diablo" }
function DetectEliteHunter()
	local R, m, E = next, game:GetService("ReplicatedStorage"):GetChildren()
	for l, l in R, m, E do
		if l:IsA("Model") and (table.find(K, l.Name)) and (IsMobAlive(l)) then
			return l
		end
	end
	E, m, R = next, game:GetService("Workspace").Enemies:GetChildren()
	for l, l in E, m, R do
		if l:IsA("Model") and (table.find(K, l.Name)) and (IsMobAlive(l)) then
			return l
		end
	end
end
local K = 0
lastCheckTime = tick()
function GetOldestLocation()
	local R, m = 1 / 0
	for E, l in ipairs(workspace._WorldOrigin.Locations:GetChildren()) do
		E = l:GetAttribute("TimeIn")
		if E and E < R then
			R, m = E, l
		end
	end
	return m
end
spawn(function()
	while wait(0.25) do
		local R, R = pcall(function()
			local m = game.workspace.DistributedGameTime
			local E, l, Q = m % 60, math.floor(m / 60 % 60), math.floor(m / 3600)
			TimerLabel.SetText(string.format("Timer: %.0fh %.0fm %.0fs", Q, l, E))
			l = GetOldestLocation()
			if l then
				Q = l:GetAttribute("TimeIn")
				E, m = tick() - 25200 - Q, 14400
				math.floor(E / m)
				local S = m - E % m
				local m, L, d, I, _, o =
					math.floor(S / 3600),
					math.floor(S % 3600 / 60),
					math.floor(S % 60),
					math.floor(E / 3600),
					math.floor(E % 3600 / 60),
					math.floor(E % 60)
				TimerServerLabel.SetText(string.format("Server Timer: %.0fh %.0fm %.0fs", I, _, o))
				NextTimerServerLabel.SetText(
					string.format("Next Time Spawn Fist of Darkness or God's Chalice: %.0fh %.0fm %.0fs", m, L, d)
				)
				if tonumber(m) == 0 and tonumber(L) == 0 and tonumber(d) <= 5 then
					getgenv().GoCollectChest = true
				end
			end
			if DetectEliteHunter() then
				StatusEliteHunter.SetText("Elite Hunter: \226\156\133")
			else
				StatusEliteHunter.SetText("Elite Hunter: \226\157\140")
			end
			if game.PlaceId == getgenv().CheckPlaceId then
				K = 0
				Q = workspace.Map:FindFirstChild("TikiOutpost") and workspace.Map.TikiOutpost.IslandModel
				if Q then
					l = {}
					for m = 1, 4, 1 do
						E = Q:FindFirstChild("Eye" .. m, true)
						if E then
							table.insert(l, E)
						end
					end
					for m, Q in ipairs(l) do
						m = Q.Transparency == 1 and K < 4
						if m then
							K += 1
						end
					end
				end
			end
			StatusTyrant.SetText("Tyrant Eyes: " .. tostring(K) .. " Eyes")
			E = game.ReplicatedStorage.Remotes.CommF_:InvokeServer("CakePrinceSpawner", true) or ""
			if E and (E:find("open the portal now")) then
				game.ReplicatedStorage.Remotes.CommF_:InvokeServer("CakePrinceSpawner")
			end
			StatusKatakuri.SetText("Cake Prince: " .. string.gsub(E, "%D", "") .. " Mobs")
			Statusspy.SetText("Leviathan: " .. StatusCheckLeviathan())
			if workspace.Map:FindFirstChild("MysticIsland") then
				StatusMirage.SetText("Mirage Island: \226\156\133")
			else
				StatusMirage.SetText("Mirage Island: \226\157\140")
			end
			if not workspace.Map:FindFirstChild("PrehistoricIsland") then
				StatusPrehistoricIsland.SetText("Prehistoric Island: \226\157\140")
			else
				StatusPrehistoricIsland.SetText("Prehistoric Island: \226\156\133")
			end
			if not workspace._WorldOrigin.Locations:FindFirstChild("Frozen Dimension") then
				StatusFrozenDimension.SetText("Frozen Dimension: \226\157\140")
			else
				StatusFrozenDimension.SetText("Frozen Dimension: \226\156\133")
			end
			StatusGear.SetText("Ancient One: " .. CheckAcientOneStatus())
			if getgenv().StatusGearDraco then
				getgenv().StatusGearDraco.SetText("Draco: " .. CheckAcientOneDracoStatus())
			end
			StatusMoon.SetText("Moon Phase: " .. CheckMoon() .. " | " .. function8())
		end)
		if R then
			print(R)
		end
	end
end)
LocalPlayerMain = Main.CreatePage({ Page_Name = "LocalPlayer", Page_Title = "LocalPlayer" })
SectionLocalPlayerMain = LocalPlayerMain.CreateSection("Local Player")
SectionLocalPlayerMain.CreateToggle(
	{
		Title = "Auto Translate",
		Desc = "It may take a bit longer to translate the first time.",
		Default = Settings["Auto Translate"] or false,
	},
	function(K)
		SaveSettings("Auto Translate", K)
	end
)
SectionLocalPlayerMain.CreateButton({ Title = "Stop Tween" }, function()
	getgenv().noclip = false
	TweenManager.CancelCurrent()
end)
SectionLocalPlayerMain.CreateButton({ Title = "Fix UI Button Game" }, function()
	require(game:GetService("ReplicatedStorage").Modules.LastInput).IsMobile = function()
		return true
	end
	wait(0.5)
	t.Character.Humanoid.Health = 0
end)
SectionLocalPlayerMain.CreateButton({ Title = "Load config in Web" }, function()
	local K = game:GetService("HttpService")
	game:GetService("RunService")
	local R, m, E = "https://cfg.banana-hub.xyz", getgenv().Key, game.Players.LocalPlayer.Name
	function ApplyConfigFromWeb(l)
		for Q, S in pairs(l) do
			if not S.name then
				continue
			end
			Q = Options[S.name]
			if Q and S then
				if S.value ~= nil and Q.type ~= "slider_dropdown" and Q.type ~= "priority_dropdown" then
					if Q.FunctionCreate and Q.FunctionCreate.SetValue then
						if Q.type == "box" then
							Q.FunctionCreate.SetValue(tostring(S.value))
						elseif Q.type == "dropdown" then
							Q.FunctionCreate.SetValue(S.value)
						elseif Q.type == "slider" then
							Q.FunctionCreate.SetValue(S.value)
						else
							Q.FunctionCreate:SetValue(S.value)
						end
					elseif Q.FunctionCreate and Q.FunctionCreate.SetStage then
						Q.FunctionCreate.SetStage(S.value)
					end
				end
				if Q.type == "priority_dropdown" and S.selected then
					if Q.FunctionCreate and Q.FunctionCreate.SetValue then
						Q.FunctionCreate.SetValue(S.selected)
					end
				end
				if Q.type == "slider_dropdown" and S.values then
					for l, L in pairs(S.values) do
						if Q.FunctionCreate and Q.FunctionCreate.SetSubValue then
							Q.FunctionCreate:SetSubValue(l, L)
						end
					end
				end
			end
		end
	end
	local l, Q = pcall(function()
		return request({
			Url = string.format("%s/config/get?authId=%s&userId=%s&roblox=true", R, K:UrlEncode(m), K:UrlEncode(E)),
			Method = "GET",
		})
	end)
	if l and Q.StatusCode == 200 then
		ApplyConfigFromWeb((K:JSONDecode(Q.Body)))
	end
end)
SectionLocalPlayerMain.CreateButton(
	{ Title = "Push Data To Web ( just push when join game,if push again plz rejoin )" },
	function()
		local K, R = game:GetService("HttpService"), "https://cfg.banana-hub.xyz"
		function BuildSchema()
			local m, E = {}, 1
			for l, Q in pairs(Options) do
				local S, L, d = Q.Page_Name or "Default Page", Q.Section_Name or "Default Section", tostring(E)
				if Q.type == "toggle" then
					m[d] = { name = l, type = "toggle", value = Q.value, page = S, section = L }
				elseif Q.type == "button" then
					m[d] = { name = l, type = "button", value = l, text = l, page = S, section = L }
				elseif Q.type == "textlabel" then
					local I = Q.FunctionCreate and Q.FunctionCreate.GetText and (Q.FunctionCreate.GetText())
						or Q.text
						or l
					m[d] = {
						name = l,
						type = "label",
						value = I,
						text = I,
						color = Q.color or "#B8B8B8",
						size = Q.size or "14px",
						bold = Q.bold or false,
						page = S,
						section = L,
					}
				elseif Q.type == "box" then
					m[d] = { name = l, type = "box", value = Q.value or "", page = S, section = L }
				elseif Q.type == "slider" then
					m[d] = {
						name = l,
						type = "slider",
						min = Q.min or 0,
						max = Q.max or 100,
						step = Q.step or 1,
						value = Q.value or Q.min or 0,
						page = S,
						section = L,
					}
				elseif Q.type == "dropdown" then
					m[d] = {
						name = l,
						type = "dropdown",
						options = table.clone(Q.list or {}),
						value = Q.value or Q.list and Q.list[1] or "",
						page = S,
						section = L,
					}
				elseif Q.type == "priority_dropdown" then
					local I = table.clone(Q.value or {})
					m[d] = {
						name = l,
						type = "priority_dropdown",
						options = table.clone(Q.list or {}),
						selected = I,
						value = I,
						page = S,
						section = L,
					}
				elseif Q.type == "multi_toggle" then
					m[d] = {
						name = l,
						type = "multi_toggle",
						options = table.clone(Q.list or {}),
						value = table.clone(Q.value or {}),
						page = S,
						section = L,
					}
				elseif Q.type == "slider_dropdown" then
					local I, _ = {}, {}
					for o, V in pairs(Q.list or {}) do
						I[o] = { min = V.min or 0, max = V.max or 100, step = V.step or 1 }
						_[o] = Q.value and Q.value[o] or V.Default or V.min or 0
					end
					m[d] = { name = l, type = "slider_dropdown", sliders = I, values = _, page = S, section = L }
				end
				E += 1
			end
			return m
		end
		function UploadSchemaToWeb(m, E)
			if not m or not E then
				warn("\226\157\140 Missing authId or userId for schema upload")
				return false
			end
			local l = BuildSchema()
			local Q, S = pcall(function()
				return request({
					Url = string.format("%s/schema/init?authId=%s&userId=%s", R, K:UrlEncode(m), K:UrlEncode(E)),
					Method = "POST",
					Headers = { ["Content-Type"] = "application/json" },
					Body = K:JSONEncode(l),
				})
			end)
			if Q and S.StatusCode == 200 then
				print("\226\156\133 Schema initialized (first time)")
				return true
			end
			if Q and S.StatusCode == 409 then
				print("\226\132\185\239\184\143 Schema already exists, skipping upload")
				return true
			end
			warn("\226\157\140 Schema upload failed")
			if Q then
				warn("Status:", S.StatusCode)
				warn("Body:", S.Body)
			end
			return false
		end
		function PushSchemaToWebupdate(m, E)
			if not m or not E then
				return
			end
			local l = BuildSchema()
			local Q, S = pcall(function()
				return request({
					Url = string.format("%s/schema/update?authId=%s&userId=%s", R, K:UrlEncode(m), K:UrlEncode(E)),
					Method = "POST",
					Headers = { ["Content-Type"] = "application/json" },
					Body = K:JSONEncode(l),
				})
			end)
			if Q and S.StatusCode == 200 then
				print("\226\156\133 Schema UPDATED \226\134\146 web will reload")
			else
				warn("\226\157\140 Push schema failed")
				if Q then
					warn("Status:", S.StatusCode)
					warn("Body:", S.Body)
				end
			end
		end
		local m, E = getgenv().Key, game.Players.LocalPlayer.Name
		request({
			Url = "https://cfg.banana-hub.xyz/config/get?authId=" .. m .. "&userId=" .. E .. "&roblox=true",
			Method = "GET",
		})
		function ForceResetSchema(l, Q)
			pcall(function()
				request({
					Url = string.format("%s/schema/delete?authId=%s&userId=%s", R, K:UrlEncode(l), K:UrlEncode(Q)),
					Method = "DELETE",
				})
			end)
			wait(0.5)
			return UploadSchemaToWeb(l, Q)
		end
		ForceResetSchema(m, E)
	end
)
local K = require(game.ReplicatedStorage:WaitForChild("Controllers"):WaitForChild("UI"):WaitForChild("Inventory"))
SectionLocalPlayerMain.CreateButton({ Title = "Show Item" }, function()
	if not game:GetService("CoreGui").ExperienceChat.bubbleChat:FindFirstChild("Right") then
		local R, m, E = game.Players.LocalPlayer, game:GetService("CoreGui"), game:GetService("ReplicatedStorage")
		if not K.IsOpen then
			K:Open()
			task.wait(2)
		end
		local l, Q, S = R.PlayerGui.Inventory.Frame.Main.PageContent.Inner.TileGrid.Inner.Container, {}, {}
		t.PlayerGui:WaitForChild("Inventory"):WaitForChild("Frame")
		l.CanvasPosition = Vector2.new(0, 0)
		local L, d = l.CanvasSize.Y.Offset - l.AbsoluteWindowSize.Y, 0
		while l.CanvasPosition.Y < L and (task.wait(0.1)) do
			l.CanvasPosition = Vector2.new(0, d)
			for I, _ in pairs(l:GetChildren()) do
				if _:FindFirstChild("Details") and (_.Details:FindFirstChild("Line-1")) then
					I = _.Details["Line-1"].ContentText
						.. (_.Details:FindFirstChild("Line-2") and _.Details["Line-2"].ContentText or "")
					if not Q[I] then
						Q[I] = true
						table.insert(S, _:Clone())
					end
				end
			end
			d += 20
		end
		Q = { "Left", "Right" }
		for I, I in ipairs(Q) do
			l = m.ExperienceChat.bubbleChat:FindFirstChild(I)
			if l then
				l:Destroy()
			end
		end
		L = Instance.new("Frame", m.ExperienceChat.bubbleChat)
		L.Name = "Left"
		L.BackgroundTransparency = 1
		L.Size = UDim2.new(0.5, 0, 1, 0)
		Q = Instance.new("Frame", m.ExperienceChat.bubbleChat)
		Q.Name = "Right"
		Q.BackgroundTransparency = 1
		Q.Position = UDim2.new(0.5, 0, 0, 0)
		Q.Size = UDim2.new(0.5, 0, 1, 0)
		local function I(_)
			local o = Instance.new("UIListLayout", _)
			o.FillDirection = Enum.FillDirection.Vertical
			o.HorizontalAlignment = Enum.HorizontalAlignment.Center
			o.SortOrder = Enum.SortOrder.LayoutOrder
			o.Padding = UDim.new(0, 10)
			return o
		end
		I(L)
		I(Q)
		local function _(o)
			local V = Instance.new("UIGridLayout", o)
			V.CellPadding = UDim2.new(0, 8, 0, 8)
			V.CellSize = UDim2.new(0, 70, 0, 70)
			V.FillDirectionMaxCells = 8
			V.FillDirection = Enum.FillDirection.Horizontal
			V.SortOrder = Enum.SortOrder.LayoutOrder
			return V
		end
		l = Instance.new("Frame", L)
		l.BackgroundTransparency = 1
		l.Size = UDim2.new(1, 0, 0, 0)
		l.AutomaticSize = Enum.AutomaticSize.Y
		l.LayoutOrder = 1
		_(l)
		L = Instance.new("Frame", Q)
		L.BackgroundTransparency = 1
		L.Size = UDim2.new(1, 0, 0, 0)
		L.AutomaticSize = Enum.AutomaticSize.Y
		L.LayoutOrder = 1
		_(L)
		d = { Vector2.new(218, 225), Vector2.new(436, 225) }
		for o, o in ipairs(S) do
			I = o.Details.Category.ContentText
			if I == "Blox Fruit" and (table.find(d, o.ImageRectOffset)) then
				o.Parent = L
			elseif I ~= "Blox Fruit" then
				o.Parent = l
			end
		end
		S = Instance.new("Frame", Q)
		S.BackgroundTransparency = 1
		S.Size = UDim2.new(1, 0, 0, 0)
		S.AutomaticSize = Enum.AutomaticSize.Y
		S.LayoutOrder = 100
		_(S)
		local L, d, I =
			{
				Superhuman = Vector2.new(3, 2),
				DeathStep = Vector2.new(4, 3),
				ElectricClaw = Vector2.new(2, 0),
				SharkmanKarate = Vector2.new(0, 0),
				DragonTalon = Vector2.new(1, 5),
				Godhuman = "rbxassetid://10338473987",
			},
			{},
			{}
		for o, V in pairs(L) do
			if E.Remotes.CommF_:InvokeServer("Buy" .. o, true) == 1 then
				l = Instance.new("ImageLabel", S)
				l.BackgroundTransparency = 1
				if type(V) == "string" then
					l.Image = V
				else
					l.Image = "rbxassetid://9945562382"
					l.ImageRectSize = Vector2.new(100, 100)
					l.ImageRectOffset = V * 100
				end
				I[o] = l
				table.insert(d, o)
			end
		end
		local function S()
			local L = Instance.new("TextLabel")
			L.BackgroundTransparency = 1
			L.Size = UDim2.new(0.5, 0, 0.5, 0)
			L.Position = UDim2.new(0.5, 0, 0.5, 0)
			L.Font = Enum.Font.GothamBold
			L.TextColor3 = Color3.fromRGB(255, 255, 255)
			L.TextSize = 10
			L.TextXAlignment = Enum.TextXAlignment.Right
			L.TextYAlignment = Enum.TextYAlignment.Bottom
			L.ZIndex = 5
			return L
		end
		local function L(o)
			for V, V in pairs(R.Backpack:GetChildren()) do
				if V.Name:gsub(" ", "") == o then
					return V
				end
			end
		end
		spawn(function()
			local o, V = #d, 0
			while V < o do
				for d, o in pairs(I) do
					if not o:FindFirstChild("Ditme") then
						E.Remotes.CommF_:InvokeServer("Buy" .. d)
						task.wait(0.1)
						local E = L(d)
						if E then
							E:WaitForChild("Level")
							local L = S()
							L.Name = "Ditme"
							L.Text = E.Level.Value
							L.Parent = o
							V += 1
						end
					end
				end
				task.wait()
			end
		end)
		task.wait(2)
		R.PlayerGui.Main.AwakeningToggler.Visible = true
		l = R.PlayerGui.Main.AwakeningToggler:Clone()
		l.LayoutOrder = 101
		R.PlayerGui.Main.AwakeningToggler.Visible = false
		l.Parent = Q
		l.Size = UDim2.new(1, 0, 0.3, 0)
		local function E(l)
			return tostring(l):reverse():gsub("%d%d%d", "%1,"):reverse():gsub("^,", "")
		end
		_ = R.PlayerGui.Main.Fragments:Clone()
		_.Parent = m.ExperienceChat.bubbleChat
		_.Position = UDim2.new(0, 6, 0.85799, 0)
		_.Text = "\198\146" .. E(R.Data.Fragments.Value)
		wait(2)
		pcall(function()
			game:GetService("Players").LocalPlayer.PlayerGui.Main.MenuButton.Visible = false
		end)
		pcall(function()
			game:GetService("Players").LocalPlayer.PlayerGui.Main.HP.Visible = false
		end)
		pcall(function()
			game:GetService("Players").LocalPlayer.PlayerGui.Main.Energy.Visible = false
		end)
		for R, R in pairs(game:GetService("Players").LocalPlayer.PlayerGui.Main:GetChildren()) do
			if R:IsA("ImageButton") then
				R.Visible = false
			end
		end
		pcall(function()
			game:GetService("Players").LocalPlayer.PlayerGui.Main.Compass.Visible = false
		end)
		K:Close()
	else
		pcall(function()
			game:GetService("Players").LocalPlayer.PlayerGui.Main.MenuButton.Visible = true
		end)
		pcall(function()
			game:GetService("Players").LocalPlayer.PlayerGui.Main.HP.Visible = true
		end)
		pcall(function()
			game:GetService("Players").LocalPlayer.PlayerGui.Main.Energy.Visible = true
		end)
		for K, K in pairs(game:GetService("Players").LocalPlayer.PlayerGui.Main:GetChildren()) do
			if K:IsA("ImageButton") then
				K.Visible = true
			end
		end
		pcall(function()
			game:GetService("Players").LocalPlayer.PlayerGui.Main.Compass.Visible = true
		end)
		for K, K in pairs(game:GetService("CoreGui").ExperienceChat.bubbleChat:GetChildren()) do
			if K.Name == "Left" or K.Name == "Right" or K.Name == "Fragments" then
				K:Destroy()
			end
		end
	end
end)
SectionLocalPlayerMain.CreateButton({ Title = "Open Devil Fruit Shop" }, function()
	local K = require(game.ReplicatedStorage.Controllers.UI.FruitShop)
	K.init()
	K:Open()
end)
SectionLocalPlayerMain.CreateButton({ Title = "Open Devil Fruit Shop Mirage" }, function()
	local K = require(game.ReplicatedStorage.Controllers.UI.FruitShop)
	K.init()
	K:Open("AdvancedFruitDealer")
end)
SectionLocalPlayerMain.CreateButton({ Title = "Open Title" }, function()
	game:GetService("Players").LocalPlayer.PlayerGui.Main.Titles.Visible = true
end)
SectionLocalPlayerMain.CreateButton({ Title = "Open Color" }, function()
	game:GetService("Players").LocalPlayer.PlayerGui.Main.Colors.Visible = true
end)
SectionLocalPlayerMain.CreateDropdown(
	{
		Title = "Select Stats",
		List = PrepareMultiSelectList(
			{ Melee = false, Defense = false, Sword = false, Gun = false, ["Demon Fruit"] = false },
			Settings["Select Stats"]
		),
		Search = true,
		Selected = true,
		Default = Settings["Select Stats"] or nil,
	},
	function(K, R)
		SaveSettings("Select Stats", K, R)
	end
)
SectionLocalPlayerMain.CreateToggle(
	{ Title = "Auto Stats", Desc = nil, Default = Settings["Auto Stats"] or false },
	function(K)
		spawn(function()
			while Settings["Auto Stats"] and (task.wait(0.3)) do
				pcall(function()
					for R, m in next, Settings["Select Stats"], nil do
						if
							m
							and game.Players.localPlayer.Data.Points.Value > 0
							and game:GetService("Players").LocalPlayer.Data.Stats[R].Level.Value < 2800
						then
							game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("AddPoint", R, 9999)
							wait(3)
						end
					end
				end)
			end
		end)
		SaveSettings("Auto Stats", K)
	end
)
SectionLocalPlayerMain.CreateDropdown(
	{
		Title = "Select Team",
		List = { "Pirate", "Marine" },
		Search = true,
		Selected = false,
		Default = Settings["Select Team"] or nil,
	},
	function(K)
		SaveSettings("Select Team", K)
	end
)
SectionLocalPlayerMain.CreateDropdown(
	{ Title = "Change Team", List = { "Pirates", "Marines" }, Search = true, Selected = false, Default = nil },
	function(K)
		if K then
			game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer(unpack({ [1] = "SetTeam", [2] = K }))
		end
	end
)
SectionLocalPlayerMain.CreateToggle({ Title = "Noclip", Desc = nil, Default = Settings.Noclip or false }, function(K)
	SaveSettings("Noclip", K)
end)
local K
function SetRobloxGUI(R)
	game.CoreGui.RobloxGui.Enabled = R
end
spawn(function()
	local R = tick()
	repeat
		wait(1)
		if tick() - R > 179 then
			game:Shutdown()
			wait(10)
		end
	until game:FindFirstChild("CoreGui") and game.Players.LocalPlayer and game.Players.LocalPlayer.Character
	R = tick()
	repeat
		wait(1)
		if tick() - R > 169 then
			game:Shutdown()
			wait(10)
		end
	until game.Players.LocalPlayer:FindFirstChild("Backpack") and (game.Players.LocalPlayer:GetMouse())
	R = Instance.new("ScreenGui")
	R.Parent = game:GetService("Players").LocalPlayer.PlayerGui
	R.ResetOnSpawn = false
	getgenv().SCGUI = R
	repeat
		wait(1)
	until SCGUI
	K = Instance.new("ImageLabel", SCGUI)
	K.BackgroundColor3 = Color3.fromRGB(0, 0, 0)
	K.Position = UDim2.new(0, 0, 0, -50)
	K.Size = UDim2.new(1, 0, 1, 50)
	K.Visible = false
	K.Name = "Black Screen"
	getgenv().BS_Text = Instance.new("TextLabel", K)
	BS_Text.TextSize = 30
	BS_Text.TextColor3 = Color3.fromRGB(255, 255, 255)
	BS_Text.AnchorPoint = Vector2.new(0.5, 0)
	BS_Text.Position = UDim2.new(0.5, 0, 0.6, 0)
	BS_Text.Font = Enum.Font.SourceSansBold
	BS_Text.RichText = true
	BS_Default = '\10<font color="rgb(45, 45, 45)"><font size="20">Black Screen</font></font>'
	getgenv().UpdateBlackScreenText = function(R)
		BS_Text.Text = R .. BS_Default
	end
	UpdateBlackScreenText("")
	getgenv().DisableBlackScreen = false
end)
local R, m = {}, {}
for E, E in pairs(game:GetService("Workspace").NPCs:GetChildren()) do
	if not string.find(E.Name, "Boat") and not string.find(E.Name, "Set Home") then
		table.insert(R, E.Name)
		table.insert(m, E)
	end
end
for E, E in pairs(game:GetService("ReplicatedStorage").NPCs:GetChildren()) do
	if not string.find(E.Name, "Boat") and not string.find(E.Name, "Set Home") then
		table.insert(R, E.Name)
		table.insert(m, E)
	end
end
local E = {}
if game.PlaceId == getgenv().CheckPlaceId3 then
	E = {
		["Start Island"] = CFrame.new(1071.2832, 16.3085976, 1426.86792),
		["Marine Start"] = CFrame.new(-2573.3374, 6.88881969, 2046.99817),
		["Middle Town"] = CFrame.new(-655.824158, 7.88708115, 1436.67908),
		Jungle = CFrame.new(-1249.77222, 11.8870859, 341.356476),
		["Pirate Village"] = CFrame.new(-1122.34998, 4.78708982, 3855.91992),
		Desert = CFrame.new(1094.14587, 6.47350502, 4192.88721),
		["Frozen Village"] = CFrame.new(1198.00928, 27.0074959, -1211.73376),
		MarineFord = CFrame.new(-4505.375, 20.687294, 4260.55908),
		Colosseum = CFrame.new(-1428.35474, 7.38933945, -3014.37305),
		["Sky 1st Floor"] = CFrame.new(-4970.21875, 717.707275, -2622.35449),
		["Sky 2st Floor"] = CFrame.new(-4813.0249, 903.708557, -1912.69055),
		["Sky 3st Floor"] = CFrame.new(-7952.31006, 5545.52832, -320.704956),
		Prison = CFrame.new(4854.16455, 5.68742752, 740.194641),
		["Magma Village"] = CFrame.new(-5231.75879, 8.61593437, 8467.87695),
		["UndeyWater City"] = CFrame.new(61163.8516, 11.7796879, 1819.78418),
		["Fountain City"] = CFrame.new(5132.7124, 4.53632832, 4037.8562),
		["House Cyborg's"] = CFrame.new(6262.72559, 71.3003616, 3998.23047),
		["Shank's Room"] = CFrame.new(-1442.16553, 29.8788261, -28.3547478),
		["Mob Island"] = CFrame.new(-2850.20068, 7.39224768, 5354.99268),
	}
elseif game.PlaceId == getgenv().CheckPlaceId2 then
	E = {
		["First Spot"] = CFrame.new(82.9490662, 18.0710983, 2834.98779),
		["Kingdom of Rose"] = game.Workspace._WorldOrigin.Locations["Kingdom of Rose"].CFrame,
		["Dark Ares"] = game.Workspace._WorldOrigin.Locations["Dark Arena"].CFrame,
		["Flamingo Mansion"] = CFrame.new(-390.096313, 331.886475, 673.464966),
		["Flamingo Room"] = CFrame.new(2302.19019, 15.1778421, 663.811035),
		["Green bit"] = CFrame.new(-2372.14697, 72.9919434, -3166.51416),
		Cafe = CFrame.new(-385.250916, 73.0458984, 297.388397),
		Factroy = CFrame.new(430.42569, 210.019623, -432.504791),
		Colosseum = CFrame.new(-1836.58191, 44.5890656, 1360.30652),
		["Ghost Island"] = CFrame.new(-5571.84424, 195.182297, -795.432922),
		["Ghost Island 2nd"] = CFrame.new(-5931.77979, 5.19706631, -1189.6908),
		["Snow Mountain"] = CFrame.new(1384.68298, 453.569031, -4990.09766),
		["Hot and Cold"] = CFrame.new(-6026.96484, 14.7461271, -5071.96338),
		["Magma Side"] = CFrame.new(-5478.39209, 15.9775667, -5246.9126),
		["Cursed Ship"] = CFrame.new(902.059143, 124.752518, 33071.8125),
		["Frosted Island"] = CFrame.new(5400.40381, 28.21698, -6236.99219),
		["Forgotten Island"] = CFrame.new(-3043.31543, 238.881271, -10191.5791),
		["Usoapp Island"] = CFrame.new(4748.78857, 8.35370827, 2849.57959),
		["Raids Low"] = CFrame.new(-5554.95313, 329.075623, -5930.31396),
		Minisky = CFrame.new(-260.358917, 49325.7031, -35259.3008),
	}
elseif game.PlaceId == getgenv().CheckPlaceId then
	E = {
		["Port Town"] = CFrame.new(-287, 30, 5388),
		["Hydar Island"] = CFrame.new(
			3399.32227,
			72.4142914,
			1572.99963,
			-0.809679806,
			-4.48284467E-8,
			0.586871922,
			2.42332163E-8,
			1,
			1.09818842E-7,
			-0.586871922,
			1.0313989E-7,
			-0.809679806
		),
		["Room Enma/Yama & Secret Temple"] = CFrame.new(5247, 7, 1097),
		["House Hydar Island"] = CFrame.new(5245, 602, 251),
		["Great Tree"] = CFrame.new(2443, 36, -6573),
		["Castle on the sea"] = CFrame.new(-5500, 314, -2855),
		Mansion = CFrame.new(-12548, 337, -7481),
		["Floating Turtle"] = CFrame.new(-10016, 332, -8326),
		["Haunted Castle"] = CFrame.new(-9509.34961, 142.130661, 5535.16309),
		["Peanut Island"] = CFrame.new(-2131, 38, -10106),
		["Ice Cream Island"] = CFrame.new(-950, 59, -10907),
		CakeLoaf = CFrame.new(-1762, 38, -11878),
		Tiki = CFrame.new(-16204.0810546875, 9.0863618850708, 479.2259521484375),
	}
end
b = {}
for l, Q in next, E, nil do
	table.insert(b, l)
end
SectionLocalPlayerMain.CreateDropdown(
	{ Title = "Select Npc", List = R, Search = true, Selected = false, Default = nil },
	function(l)
		g["Select Npc"] = l
	end
)
SectionLocalPlayerMain.CreateToggle({ Title = "Teleport To Npc", Desc = nil, Default = false }, function(l)
	g["Teleport To Npc"] = l
end)
SectionLocalPlayerMain.CreateDropdown(
	{ Title = "Select Island", List = b, Search = true, Selected = false, Default = nil },
	function(l)
		g["Select Island"] = l
	end
)
SectionLocalPlayerMain.CreateToggle({ Title = "Teleport To Island", Desc = nil, Default = false }, function(l)
	g["Teleport To Island"] = l
end)
SectionLocalPlayerMain.CreateToggle({ Title = "Teleport Mirage", Desc = nil, Default = false }, function(l)
	g["Teleport Mirage"] = l
end)
SectionLocalPlayerMain.CreateToggle({ Title = "Teleport Prehistoric Island", Desc = nil, Default = false }, function(l)
	g["Teleport Prehistoric Island"] = l
end)
function DetectPrehistoricIsland()
	local l, Q, S = next, workspace._WorldOrigin.Locations:GetChildren()
	for L, L in l, Q, S do
		if L.Name == "Prehistoric Island" and (L:GetAttribute("CFrame")) then
			return L
		end
	end
end
function SetNoClip(l)
	getgenv().noclip = l
	local Q = t.Character
	if not Q then
		return
	end
	local S, L = Q:FindFirstChild("HumanoidRootPart"), Q:FindFirstChildOfClass("Humanoid")
	if not l then
		for l, l in ipairs(Q:GetDescendants()) do
			if l:IsA("BasePart") then
				l.CanCollide = true
			end
		end
		if L then
			L.PlatformStand = false
		end
		if S and (S:FindFirstChild("FloatForce")) and not ToggleNoclip() then
			S.FloatForce:Destroy()
		end
	end
end
function ToggleNoclip()
	if
		Settings["Start Farm"]
		or Settings["Auto Present Event"]
		or Settings["Auto Celestial Soldier"]
		or Settings["Auto Rip Commander"]
		or Settings["Auto Event Halloween"]
		or Settings["Auto Attack Dungeon"]
		or Settings["Auto Fishing"]
		or Settings["Teleport To Fruit"]
		or Settings["Auto Factory"]
		or Settings["Auto Pirate Raid"]
		or Settings["Auto Elite Hunter"]
		or Settings["Auto Touch Pad Haki"]
		or Settings["Auto Summon Rip Indra"]
		or Settings["Attack Rip Indra"]
		or Settings["Attack Soul Reaper"]
		or Settings["Attack Dough King"]
		or Settings["Attack Darkbeard"]
		or Settings["Auto Raid"]
		or Settings["Auto Sea Event"]
		or Settings["Auto Shipwright"]
		or Settings["Teleport Acient Clock"]
		or Settings["Auto Upgrade Race V2-V3"]
		or Settings["Auto Trial"]
		or Settings["Auto Get Ghoul"]
		or Settings["Auto Get Cyborg"]
		or Settings["Auto Pull Lever"]
		or g["Teleport Mirage"]
		or g["Teleport To Island"]
		or g["Teleport To Npc"]
		or g["Teleport Prehistoric Island"]
		or g["Sanguine Art"]
		or g["God Human"]
		or g["Dragon Talon"]
		or g["Electric Claw"]
		or g["Sharkman Karate"]
		or g["Death Step"]
		or g.SuperHuman
		or g.DragonClaw
		or g.Electro
		or g["Fishman Karate"]
		or g["Black Leg"]
		or Settings["Teleport To Kitsune Island"]
		or Settings["Auto Spawn Kitsune Island"]
		or Settings["Auto Collect Soul Ember"]
		or Settings["Auto Summon Soul Ember"]
		or Settings["Auto Attack Leviathan"]
		or Settings["Auto Soul Guitar"]
		or Settings["Auto CDK"]
		or Settings["Auto Yama"]
		or Settings["Auto Tushita"]
		or Settings["Auto Upgrade Sword Inventory"]
		or Settings["Teleport Player"]
		or Settings["Auto Chest"]
		or Settings["Farm Observation"]
		or Settings["Auto Upgrade Gun Inventory"]
		or Settings["Kill Boss"]
		or Settings["Kill Mob"]
		or Settings["Auto UP Observation V2"]
		or Settings["Auto New World"]
		or Settings["Auto Third World"]
		or Settings["Tween Safe if have Items"]
		or Settings["Teleport Frozen Dimension"]
		or Settings["Auto Yoru Mini"]
		or Settings["Auto Quest Dojo Trainer"]
		or Settings["Auto Quest Dragon Hunter"]
		or Settings["Auto Crafting Volcanic Magnet"]
		or Settings["Auto Find Prehistoric Island"]
		or Settings["Auto Find Mirage"]
		or Settings["Auto Event Prehistoric Island"]
		or Settings["Auto Collect Bone"]
		or Settings["Auto Collect Berry"]
		or Settings["Auto Upgrade Race V2-V3 Draco"]
		or Settings["Auto Trial Draco"]
		or Settings["Auto Get Rainbow Haki"]
		or Settings["Follow Player Select"]
		or Settings["Auto Tween To Prehistoric Island"]
		or Settings["Auto Kill Golem"]
		or Settings["Auto Fix Volcano"]
		or Settings["Multi Find Leviathan"]
		or Settings["Fully Event Prehistoric Island"]
		or Settings["Auto Multi Raid"]
		or Settings["Auto Fire Shoot Heart Leviathan"]
		or Settings["Auto Buy Chip and Attack Law"]
		or Settings["Fully Trial Draco"]
		or Settings["Auto Finish Train Quest"]
		or Settings["Auto Destroy IDK"]
		or Settings["Auto Finish Train Draco Quest"]
		or Settings["Auto TTK"]
		or Settings["Auto Attack All Mob and Boss"]
		or Settings["Auto Collect Egg"]
		or Settings["Collect Chest When Server Spawn God's Chalice or Fist of Darkness"]
	then
		return true
	end
end
local l = game:GetService("TweenService")
getgenv().TweenManager = {
	currentTween = nil,
	currentPart = nil,
	currentGoal = nil,
	TweenRunning = false,
	CancelTweenOnly = function()
		local Q, S = TweenManager.currentTween, getgenv().Tween
		if Q then
			pcall(function()
				Q:Cancel()
				Q:Destroy()
			end)
		end
		if S and S ~= Q then
			pcall(function()
				S:Cancel()
				S:Destroy()
			end)
		end
		TweenManager.currentTween = nil
		TweenManager.currentPart = nil
		TweenManager.currentGoal = nil
		TweenManager.TweenRunning = false
		getgenv().Tween = nil
	end,
	PlayTween = function(Q, S, L, d)
		if not Q or not S or not L or not L.CFrame then
			return
		end
		local I = (d or {}).TargetEpsilon or 12
		if
			TweenManager.currentTween
			and TweenManager.currentPart == Q
			and TweenManager.currentGoal
			and I >= (TweenManager.currentGoal.Position - L.CFrame.Position).Magnitude
		then
			return TweenManager.currentTween
		end
		TweenManager.CancelTweenOnly()
		local d = l:Create(Q, S, L)
		TweenManager.currentTween = d
		TweenManager.currentPart = Q
		TweenManager.currentGoal = L.CFrame
		TweenManager.TweenRunning = true
		getgenv().Tween = d
		d.Completed:Connect(function()
			if TweenManager.currentTween == d then
				TweenManager.currentTween = nil
				TweenManager.currentPart = nil
				TweenManager.currentGoal = nil
				TweenManager.TweenRunning = false
				getgenv().Tween = nil
				pcall(function()
					d:Destroy()
				end)
			end
		end)
		d:Play()
		return d
	end,
	CancelCurrent = function()
		local l = t.Character
		local Q = l and (l:FindFirstChild("HumanoidRootPart"))
		if TweenManager.currentTween or getgenv().Tween or Q and (Q:FindFirstChild("FloatForce")) then
			TweenManager.CancelTweenOnly()
			pcall(function()
				if not l then
					return
				end
				for S, S in ipairs(l:GetDescendants()) do
					if S:IsA("BasePart") then
						S.CanCollide = true
					end
				end
				local S = l:FindFirstChildOfClass("Humanoid")
				if S then
					S.PlatformStand = false
				end
				if Q and (Q:FindFirstChild("FloatForce")) then
					Q.FloatForce:Destroy()
				end
			end)
		end
	end,
}
TweenManager = getgenv().TweenManager
local l, Q, S, L, d =
	{
		Sea1 = {
			Colosseum = Vector3.new(-2143.41333, 152.074326, -3025.54614),
			Desert = Vector3.new(1330.68298, 103.55368, 4489.30615),
			Fountain = Vector3.new(5420.33643, 431.04068, 4396.38721),
			Jungle = Vector3.new(-1340.21948, 136.020538, -101.374214),
			["Marine Fortress"] = Vector3.new(-5180.23828, 281.343445, 4383.03174),
			["Middle Town"] = Vector3.new(-703.16748, 9.55188751, 1575.1864),
			["Pirate Village"] = Vector3.new(-807.662109, 27.8020515, 4119.30127),
			Prison = Vector3.new(5270.56934, 163.508469, 844.72821),
			Sky = Vector3.new(-4808.76904, 721.326355, -2668.81787),
			Snow = Vector3.new(1394.46399, 39.0448875, -1321.63904),
			["Starter Island"] = Vector3.new(1038.29968, 112.1365051, 1287.83447),
			["Starter Marine"] = Vector3.new(-3096.51929, 231.443558, 2087.51929),
			Underwater = Vector3.new(61147.9766, 20.5708408, 1366.09839),
			["Upper Sky"] = Vector3.new(-7950.03662, 5815.68457, -1968.3374),
			Volcano = Vector3.new(-5513.97852, 64.4943161, 8577.40039),
		},
		Sea2 = {
			Cafe = Vector3.new(-382, 74, 356),
			Colosseum = Vector3.new(-1836, 46, 1642),
			["Dark Arena"] = Vector3.new(3948, 13, -3479),
			["Docks 1"] = Vector3.new(-923, 8, 1810),
			["Docks 2"] = Vector3.new(-13, 39, 2708),
			["Docks 3"] = Vector3.new(-1944, 9, -2594),
			["Docks 4"] = Vector3.new(-5798, 1, -5021),
			Doghouse = Vector3.new(-1984, 125, -82),
			Graveyard = Vector3.new(-5710, 126, -775),
			["Haunted Ship"] = Vector3.new(937, 125, 32879),
			Lab = Vector3.new(-5542, 335, -5924),
			Lava = Vector3.new(-5280, 7, -5618),
			Mansion = Vector3.new(-494, 339, 593),
			Raid = Vector3.new(-6503, 251, -4495),
			Remote = Vector3.new(4766, 8, 2911),
			Skull = Vector3.new(-2956.24341, 123.399323, -9981.06934),
			Snow = Vector3.new(1210, 429, -4663),
			["Winter Castle"] = Vector3.new(5544.71777, 60.1393852, -6359.08887),
		},
		Sea3 = {
			["Cake Land"] = Vector3.new(-2098.970458984375, 76.39494323730469, -12128.359375),
			["Chocolate Land"] = Vector3.new(379.1396179199219, 130.20599365234375, -12720.83984375),
			["Great Tree"] = Vector3.new(4345.09375, 575.0524291992188, -6159.00439453125),
			["Haunted Castle"] = Vector3.new(-9515.0009765625, 149.18876647949, 5534.0502929688),
			["Hydra Arena"] = Vector3.new(5020.94580078125, 174.08645629882812, -2011.18505859375),
			["Hydra Town"] = Vector3.new(5288.62158203125, 1011.6527709960938, 392.4296875),
			["Ice Cream Land"] = Vector3.new(-917.54852294922, 63.364143371582, -10858.696289062),
			["Peanut Land"] = Vector3.new(-2037.8001708984, 13.651118278503, -9948.2021484375),
			Port = Vector3.new(-342.4343566894531, 23.8315486907959, 5547.345703125),
			["Sea Castle"] = Vector3.new(-5502.1787109375, 323.6708984375, -2863.4616699219),
			["Tiki Outpost"] = Vector3.new(-16456.4629, 530.251953, 436.231812),
			["Turtle Center"] = Vector3.new(-12007.979492188, 339.15548706055, -9178.580078125),
			["Turtle Entrance"] = Vector3.new(-10163.96484375, 340.29028320313, -8320.767578125),
			["Turtle Mansion"] = Vector3.new(-12538.421875, 339.39358520508, -7817.0708007813),
			["Turtle Mountain"] = Vector3.new(-12856.61328125, 852.75360107422, -10715.23046875),
		},
	},
	{},
	game:GetService("CollectionService"),
	0,
	false
local function I()
	L = tick() + 1.5
	if not S:HasTag(t, "Teleporting") then
		S:AddTag(t, "Teleporting")
		d = true
	end
end
task.spawn(function()
	while task.wait(0.1) do
		if d and tick() >= L then
			S:RemoveTag(t, "Teleporting")
			d = false
		end
	end
end)
spawn(function()
	local S = (game.ReplicatedStorage.Remotes.CommF_:InvokeServer("GetUnlockables"))
	repeat
		task.wait()
		S = (game.ReplicatedStorage.Remotes.CommF_:InvokeServer("GetUnlockables"))
	until S
	if S.DefeatedIndraTrueForm and game.PlaceId == getgenv().CheckPlaceId then
		Q["Caslte On The Sea"] = Vector3.new(-4967.6826171875, 314.88238525390625, -3157.098388671875)
		Q.Hydra = Vector3.new(5661.5302734375, 1013.4113159179688, -334.9619140625)
		Q.Mansion = Vector3.new(-12463.8740234375, 374.9144592285156, -7523.77392578125)
	end
	if game.PlaceId == getgenv().CheckPlaceId then
		Q["Temple Clock"] = Vector3.new(28282.5703125, 14896.8505859375, 105.1042709350586)
	end
	if game.PlaceId == getgenv().CheckPlaceId2 then
		Q["122"] = Vector3.new(923.21252441406, 126.9760055542, 32852.83203125)
		Q["3032"] = Vector3.new(-6508.5581054688, 89.034996032715, -132.83953857422)
	end
	if S.FlamingoAccess and game.PlaceId == getgenv().CheckPlaceId2 then
		Q.Mansion = Vector3.new(-288.46246337890625, 306.130615234375, 597.9988403320312)
		Q.Flamingo = Vector3.new(2284.912109375, 15.152046203613281, 905.48291015625)
	end
	local S, L = game.PlaceId, getgenv().CheckPlaceId3
	if S == L then
		Q = {
			["1"] = Vector3.new(-7894.6201171875, 5545.49169921875, -380.2467346191406),
			["2"] = Vector3.new(-4607.82275390625, 872.5422973632812, -1667.556884765625),
			["3"] = Vector3.new(61163.8515625, 11.759522438049316, 1819.7841796875),
			["4"] = Vector3.new(3876.280517578125, 35.10614013671875, -1939.3201904296875),
		}
	end
end)
local S, L, d = game:GetService("Players"), game:GetService("ReplicatedStorage"), game:GetService("VirtualInputManager")
local function _()
	local o = t.Data:FindFirstChild("DevilFruit")
	if not o or o.Value ~= "Portal-Portal" then
		return false
	end
	local V = t.PlayerGui.Main.Skills:FindFirstChild(o.Value)
	o = V and (V:FindFirstChild("C"))
	if not o or not o:IsA("Frame") then
		V = t.Character:FindFirstChild("Portal-Portal") or (t.Backpack:FindFirstChild("Portal-Portal"))
		if not V then
			return false
		end
		t.Character:FindFirstChildOfClass("Humanoid"):EquipTool(V)
		return false
	end
	V = o:FindFirstChild("Cooldown")
	return o.Title.TextColor3 == Color3.new(1, 1, 1)
		and (V.Size == UDim2.new(0, 0, 1, -1) or V.Size == UDim2.new(1, 0, 1, -1))
end
local function o(V)
	local N = t.Character:FindFirstChild("Portal-Portal") or (t.Backpack:FindFirstChild("Portal-Portal"))
	if not N then
		return false
	end
	t.Character:FindFirstChildOfClass("Humanoid"):EquipTool(N)
	N = t.PlayerGui.Main:FindFirstChild("Gateway")
	if not N then
		return false
	end
	d:SendKeyEvent(true, "C", false, game)
	d:SendKeyEvent(false, "C", false, game)
	local y = tick() + 3
	repeat
		task.wait(0.1)
	until N.Visible or tick() > y
	if not N.Visible then
		return false
	end
	y = N:FindFirstChild("MainContent")
	if not y then
		return false
	end
	N = y.ScrollingFrame:FindFirstChild(tostring(V))
	if N and N.MouseButton1Click then
		for V, V in pairs(getconnections(N.MouseButton1Click)) do
			pcall(function()
				V.Function()
			end)
		end
		return true
	end
	return false
end
G = {
	[Vector3.new(-16455.29, 527.75, 436.11)] = Vector3.new(-4967.68, 314.88, -3157.1),
	[Vector3.new(-9513.47, 142.1, 5528.84)] = Vector3.new(-4967.68, 314.88, -3157.1),
	[Vector3.new(-340.89, 20.6, 5549.8)] = Vector3.new(5661.53, 1013.41, -334.96),
	[Vector3.new(-2100.75, 69.98, -12128.27)] = Vector3.new(28282.57, 14896.85, 105.1),
	[Vector3.new(380.74, 126.58, -12726.16)] = Vector3.new(28282.57, 14896.85, 105.1),
	[Vector3.new(-916.08, 56.24, -10858.4)] = Vector3.new(28282.57, 14896.85, 105.1),
	[Vector3.new(-2039.6, 9.67, -9947.76)] = Vector3.new(28282.57, 14896.85, 105.1),
}
do
	local G = Vector3.new(28282.5703125, 14896.8505859375, 105.1042709350586)
	local function V()
		local N = t.Character and (t.Character:FindFirstChild("HumanoidRootPart"))
		return N ~= nil and (N.Position - G).Magnitude < 1000
	end
	function BorrowTempleOfTime()
		local G = game.ReplicatedStorage.MapStash:FindFirstChild("Temple of Time")
		if not G then
			return
		end
		G:SetAttribute("ClientBorrowed", true)
		G.Parent = workspace.Map
		task.spawn(function()
			local N = tick() + 30
			repeat
				task.wait(0.25)
			until G.Parent ~= workspace.Map or (V()) or tick() > N
			G:SetAttribute("ClientBorrowed", nil)
			if not V() and G.Parent == workspace.Map then
				G.Parent = game.ReplicatedStorage.MapStash
			end
		end)
	end
	function GetTempleOfTime()
		local G = workspace.Map:FindFirstChild("Temple of Time")
		if G and not G:GetAttribute("ClientBorrowed") then
			return G
		end
	end
end
local G = false
getgenv().IsPlayerDead = function()
	if not t.Character or not t.Character:FindFirstChild("Humanoid") or t.Character.Humanoid.Health == 0 then
		return true
	end
end
CS = game:GetService("CollectionService")
cam = workspace.CurrentCamera
function LoadIslandByFakePoint(V)
	local N = Instance.new("Part")
	N.Transparency = 1
	N.CanCollide = false
	N.Anchored = true
	N.Size = Vector3.new(0, 0, 0)
	N.CFrame = CFrame.new(V:GetPivot().Position)
	CS:AddTag(N, "LoDPosition")
	N.Parent = cam
	return N
end
spawn(function()
	pcall(function()
		for V, V in ipairs(workspace:GetChildren()) do
			if V:IsA("Model") and (V:GetAttribute("LevelOfDetailDiameter")) then
				LoadIslandByFakePoint(V)
			end
		end
		for V, V in ipairs(workspace.Map:GetChildren()) do
			if V:IsA("Model") then
				LoadIslandByFakePoint(V)
			end
		end
		for V, V in ipairs(game:GetService("ReplicatedStorage").FakeIslands:GetChildren()) do
			if V:IsA("Model") then
				LoadIslandByFakePoint(V)
			end
		end
	end)
end)
getgenv().TweenGuidePart = nil
getgenv().TweenConnection = nil
getgenv().TweenInProgress = false
getgenv().lastTarget = nil
local function V(N)
	local y, x
	for k, P in ipairs(workspace._WorldOrigin.Locations:GetChildren()) do
		if P:IsA("BasePart") and not P:GetAttribute("IgnoreInTracking") then
			k = (P.Position - N).Magnitude
			if not y or k < y then
				y, x = k, P
			end
		end
	end
	return x
end
local function N(y)
	local x = V(y)
	if not x then
		return nil
	end
	local k = x:FindFirstChild("Mesh")
	if k then
		if k.Scale.X / 2 >= (x.Position - y).Magnitude then
			return x
		else
			return nil
		end
	end
	return x
end
function DetectNpcOni()
	local y = t.Character and (t.Character:FindFirstChild("HumanoidRootPart"))
	if not y then
		return
	end
	local x, k, P, e = next, { workspace.NPCs, game:GetService("ReplicatedStorage").NPCs }, 1 / 0
	for Y, H in x, k, nil do
		local x, k, B = next, H:GetChildren()
		for H, H in x, k, B do
			if
				H:GetAttribute("NPCLoaded")
				and (H:GetAttribute("NPCReady"))
				and H:GetAttribute("DisplayName") == "Celestial Member"
				and (H:FindFirstChild("HumanoidRootPart"))
			then
				Y = (y.Position - H.HumanoidRootPart.Position).Magnitude
				if Y < P then
					P, e = Y, H
				end
			end
		end
	end
	return e, P
end
CelestialDomainController =
	require(game:GetService("ReplicatedStorage").Controllers.MapServices.CelestialDomainController)
LocalPlayer = t
L = game:GetService("ReplicatedStorage")
WorldOrigin = workspace:WaitForChild("_WorldOrigin", 10)
travelFunctions = {}
PlayerSpawnsLot = {}
BypassTpLocation = {}
PlrData = game:GetService("Players").LocalPlayer.Data
localPlayerFunctions = {}
function localPlayerFunctions.IsAlive()
	local y = LocalPlayer.Character
	if not y then
		return false
	end
	local x = y:FindFirstChildOfClass("Humanoid")
	if not x then
		return false
	end
	return x.Health > 0
end
function getHRP()
	local y = LocalPlayer.Character
	if not y then
		return nil
	end
	return y:FindFirstChild("HumanoidRootPart") or (y:FindFirstChild("UpperTorso")) or (y:FindFirstChild("Torso"))
end
function travelFunctions.GetDistance(y, x)
	if not localPlayerFunctions.IsAlive() then
		return 1 / 0
	end
	if not x then
		local k = getHRP()
		if not k then
			return 1 / 0
		end
		x = k.Position
	end
	return (y - x).Magnitude
end
function travelFunctions.LoadBypassTPLocation()
	table.clear(PlayerSpawnsLot)
	table.clear(BypassTpLocation)
	local y, x = WorldOrigin:FindFirstChild("PlayerSpawns"), WorldOrigin:FindFirstChild("Locations")
	if not y or not x then
		return
	end
	for k, k in ipairs(y:GetChildren()) do
		for y, y in ipairs(k:GetChildren()) do
			if y:IsA("Model") then
				table.insert(PlayerSpawnsLot, { y.Name, y:GetModelCFrame() })
			end
		end
		k.ChildAdded:Connect(function(y)
			task.wait()
			if y:IsA("Model") then
				table.insert(PlayerSpawnsLot, { y.Name, y:GetModelCFrame() })
			end
		end)
	end
	local function y(k)
		if not k:IsA("BasePart") then
			return
		end
		BypassTpLocation[k.Name] = {}
		local P = k:FindFirstChildWhichIsA("SpecialMesh")
		local e = P and P.Scale.X or 1
		P = k.Size.X * e / 2
		for e, e in ipairs(PlayerSpawnsLot) do
			if (e[2].Position - k.Position).Magnitude <= P then
				table.insert(BypassTpLocation[k.Name], e)
			end
		end
	end
	for k, k in ipairs(x:GetChildren()) do
		y(k)
	end
	x.ChildAdded:Connect(function(x)
		task.wait(3)
		y(x)
	end)
end
function travelFunctions.GetTPLocation(y)
	local x = WorldOrigin:FindFirstChild("Locations")
	if not x then
		return nil
	end
	local k, P = 1 / 0
	for e, Y in ipairs(x:GetChildren()) do
		e = BypassTpLocation[Y.Name]
		if e then
			local x = Y:FindFirstChildWhichIsA("SpecialMesh")
			local H = x and x.Scale.X or 1
			if Y.Size.X * H / 2 >= travelFunctions.GetDistance(y, Y.Position) then
				for x, Y in ipairs(e) do
					x = travelFunctions.GetDistance(y, Y[2].Position)
					if x < k then
						k, P = x, Y[1]
					end
				end
			end
		end
	end
	return P
end
function travelFunctions.TweenBypass(y, x)
	x = x or 0
	if x >= 5 then
		return
	end
	local k, P = pcall(function()
		if not y then
			return
		end
		if not next(BypassTpLocation) then
			travelFunctions.LoadBypassTPLocation()
		end
		local e = LocalPlayer.Character
		if not e then
			return
		end
		if not getHRP() then
			return
		end
		local Y = {}
		for H, H in pairs(BypassTpLocation) do
			for B, B in ipairs(H) do
				if not table.find(Y, B[2]) then
					table.insert(Y, B[2])
				end
			end
		end
		if #Y == 0 then
			return
		end
		table.sort(Y, function(H, B)
			return travelFunctions.GetDistance(H.Position, y.Position)
				< travelFunctions.GetDistance(B.Position, y.Position)
		end)
		local H = e:FindFirstChild("LastSpawnPoint")
		if H then
			H.Disabled = true
		end
		task.wait()
		for B, Z in ipairs(Y) do
			B = travelFunctions.GetTPLocation(Z.Position)
			if B then
				local Y = travelFunctions.GetDistance(Z.Position, y.Position)
				if
					travelFunctions.GetDistance(y.Position) > Y + 500
					and travelFunctions.GetDistance(Z.Position) >= 1000
				then
					CommF:InvokeServer("SetLastSpawnPoint", B)
					if PlrData.LastSpawnPoint.Value == B then
						e.Humanoid.Health = 0
						repeat
							task.wait()
						until localPlayerFunctions.IsAlive()
						if H then
							H.Disabled = false
						end
						travelFunctions.TweenBypass(y, x + 1)
						return true
					end
				end
			end
		end
		if H then
			H.Disabled = false
		end
	end)
	if not k then
		warn("[TweenBypass ERROR]:", P)
	end
	return false
end
function ShouldResetTeleportSmart(y)
	if not Settings["Reset Teleport"] then
		return false
	end
	if G or ReadyToDodge then
		return false
	end
	local x = getHRP()
	if not x then
		return false
	end
	local k, P = N(y.Position), N(x.Position)
	if not k then
		return true
	end
	if P and k and P.Name == k.Name then
		return false
	end
	return true
end
task.spawn(function()
	travelFunctions.LoadBypassTPLocation()
end)
BypassTp = travelFunctions
local function y(x)
	if x:FindFirstChild("FloatForce") then
		return
	end
	local k = Instance.new("BodyVelocity")
	k.Name = "FloatForce"
	k.Velocity = Vector3.new(0.0, 0.0, 0.0)
	k.MaxForce = Vector3.new(100000, 100000, 100000)
	k.P = 10000
	k.Parent = x
end
local x, k, P, e, Y =
	game:GetService("RunService"), { LastTP = 0, LastCF = nil, ActiveConnection = nil, LastCall = 0 }, 18, 120, 40
local function H()
	local B = getgenv().CharSpeed
	if not B then
		B = { cap = 1000, nextRaise = 0 }
		getgenv().CharSpeed = B
	end
	return B
end
local function B(Z, C, J, F)
	if not Z or typeof(C) ~= "CFrame" then
		return
	end
	local q = t.Character
	local c = q and (q:FindFirstChildOfClass("Humanoid"))
	if not q or Z.Parent ~= q or not c or c.Health <= 0 then
		return
	end
	if tick() - k.LastTP < 1 and C == k.LastCF then
		return
	end
	TweenManager.CancelTweenOnly()
	if k.ActiveConnection and coroutine.status(k.ActiveConnection) == "suspended" then
		pcall(coroutine.close, k.ActiveConnection)
	end
	J = math.max(tonumber(J) or 350, 1)
	F = tonumber(F) or 2.5
	k.LastTP = tick()
	k.LastCF = C
	local c, D = false
	local r = {}
	local function n()
		if k.ActiveConnection == D then
			k.ActiveConnection = nil
		end
		if TweenManager.currentTween == r then
			TweenManager.currentTween = nil
			TweenManager.currentPart = nil
			TweenManager.currentGoal = nil
			TweenManager.TweenRunning = false
		end
		if getgenv().Tween == r then
			getgenv().Tween = nil
		end
	end
	r.Pause = function(u)
		c = true
		if D and coroutine.status(D) == "suspended" then
			pcall(coroutine.close, D)
		end
	end
	r.Cancel = function(u)
		u:Pause()
		n()
	end
	r.Destroy = function(u)
		u:Cancel()
	end
	D = coroutine.create(function()
		local u, W = Z.Position, C.Position
		local O, z, U, h, p, w = (W - u).Magnitude, 1 / 0, (tick()), true
		while not c do
			local M = t.Character
			local j = M and (M:FindFirstChildOfClass("Humanoid"))
			if M ~= q or Z.Parent ~= M or not j or j.Health <= 0 or Z.Anchored or O <= F then
				break
			end
			local q, v0, T0 = x.Heartbeat:Wait(), H(), Z.Position
			M = (W - T0).Magnitude
			if M < z - 5 then
				z, U = M, (tick())
			else
				h = if tick() - U > 2.5 then false else h
			end
			if h and p and w and M > w + Y then
				v0.cap = math.max(v0.cap * 0.7, e)
				v0.nextRaise = tick() + 3
				u = T0
			else
				u = if h and p and (T0 - p).Magnitude > Y then T0 else u
			end
			j = W - u
			local e, Y = j.Magnitude, math.min(math.min(J, v0.cap) * q, P)
			if e > Y and tick() >= v0.nextRaise then
				v0.cap = math.min(v0.cap * 1.08, J)
				v0.nextRaise = tick() + 1.5
			end
			u = if e <= Y or e <= 0.05 then W else u + j / e * Y
			O = (W - u).Magnitude
			I()
			getgenv().noclip = true
			Z.CFrame = CFrame.new(u)
			Z.AssemblyLinearVelocity = Vector3.new(0.0, 0.0, 0.0)
			Z.AssemblyAngularVelocity = Vector3.new(0.0, 0.0, 0.0)
			p, w = u, M
		end
		if not c and Z.Parent == t.Character and (W - Z.Position).Magnitude <= F then
			Z.CFrame = C
			Z.AssemblyLinearVelocity = Vector3.new(0.0, 0.0, 0.0)
			Z.AssemblyAngularVelocity = Vector3.new(0.0, 0.0, 0.0)
		end
		n()
	end)
	k.ActiveConnection = D
	TweenManager.currentTween = r
	TweenManager.currentPart = Z
	TweenManager.currentGoal = C
	TweenManager.TweenRunning = true
	getgenv().Tween = r
	if not coroutine.resume(D) then
		r:Cancel()
		return
	end
	return r
end

function toTarget(P, e)
	LPH_ATTRIBUTES(VM(NONE))
	if typeof(P) ~= "CFrame" then
		return
	end
	local Y = t.Character
	if not Y or not Y:FindFirstChild("HumanoidRootPart") then
		return
	end
	local H, Z = Y.HumanoidRootPart, Y:FindFirstChildOfClass("Humanoid")
	if not Z then
		return
	end
	k.LastCall = tick()
	if Z and Z.Sit then
		TweenManager.CancelCurrent()
		task.wait(0.1)
		getgenv().noclip = false
		d:SendKeyEvent(true, "Space", false, game)
		task.wait()
		d:SendKeyEvent(false, "Space", false, game)
		task.wait(0.1)
		if H:FindFirstChild("EffectsSY") then
			H.EffectsSY:Destroy()
		end
		Z.Jump = true
		task.wait(0.1)
		H.CFrame = H.CFrame * CFrame.new(0, 10, 0)
		return
	end
	if not H:FindFirstChild("FloatForce") then
		y(H)
	end
	Y = (P.Position - H.Position).Magnitude
	if Settings["Teleport Y"] then
		local d, y = Settings["% Health Player"] or 40, Z.Health / Z.MaxHealth
		local C = d / 100
		if y < C then
			G = true
		else
			d = Z.Health / Z.MaxHealth
			if d > 0.8 then
				G = false
			end
		end
	end
	if Y < (e and 8 or 150) and not G and not ReadyToDodge then
		TweenManager.CancelTweenOnly()
		I()
		H.CFrame = P
		return
	end
	if game.PlaceId ~= 122478697296975 then
		e = CFrame.new(28609.392578125, 14896.533203125, 106.4216537475586)
		if
			game.PlaceId == getgenv().CheckPlaceId
			and (P.Position - e.Position).Magnitude > 3000
			and (e.Position - H.Position).Magnitude <= 3000
		then
			B(H, e, 400, 8)
			if (e.Position - H.Position).Magnitude < 8 then
				game:GetService("ReplicatedStorage")
					:WaitForChild("Remotes")
					:WaitForChild("CommF_")
					:InvokeServer("RaceV4Progress", "Check")
				game:GetService("ReplicatedStorage")
					:WaitForChild("Remotes")
					:WaitForChild("CommF_")
					:InvokeServer("RaceV4Progress", "TeleportBack")
				TweenManager.CancelCurrent()
			end
			return
		end
		Z = Vector3.new(11538.599609375, -2154.7021484375, 9827.3125)
		if
			game.PlaceId == getgenv().CheckPlaceId
			and (P.Position - Z).Magnitude <= 3000
			and (Z - H.Position).Magnitude > 3000
		then
			local d = CFrame.new(
				-16269.4082,
				23.9799957,
				1371.66235,
				-0.999388933,
				0,
				-0.0349550731,
				0,
				1,
				0,
				0.0349550731,
				0,
				-0.999388933
			)
			B(H, d, 350, 8)
			if (d.Position - H.Position).Magnitude < 8 then
				game:GetService("ReplicatedStorage").Modules.Net
					:FindFirstChild("RF/SubmarineWorkerSpeak")
					:InvokeServer(unpack({ [1] = "TravelToSubmergedIsland" }))
				game:GetService("ReplicatedStorage").Remotes.CommF_
					:InvokeServer(unpack({ [1] = "SetLastSpawnPoint", [2] = "SubmergedIsland" }))
				TweenManager.CancelCurrent()
			end
			return
		end
		if
			game.PlaceId == getgenv().CheckPlaceId
			and (P.Position - Z).Magnitude > 3000
			and (Z - H.Position).Magnitude <= 3000
		then
			local d = CFrame.new(
				11427.9189,
				-2156.36401,
				9726.24023,
				-0.929097056,
				-7.17796156E-34,
				0.369835705,
				-7.17796156E-34,
				1,
				1.37611875E-34,
				-0.369835705,
				-1.37611875E-34,
				-0.929097056
			)
			B(H, d, 350, 8)
			if (d.Position - H.Position).Magnitude < 8 then
				game:GetService("ReplicatedStorage").Modules.Net
					:FindFirstChild("RF/SubmarineTransportation")
					:InvokeServer(unpack({ [1] = "GetAvailableLocations" }))
				game:GetService("ReplicatedStorage").Modules.Net
					:FindFirstChild("RF/SubmarineTransportation")
					:InvokeServer(unpack({ [1] = "InitiateTeleport", [2] = "Tiki Outpost" }))
				TweenManager.CancelCurrent()
			end
			return
		end
		if Settings["Use Portal Teleport"] then
			local d = t.Character:FindFirstChild("Portal-Portal") or (t.Backpack:FindFirstChild("Portal-Portal"))
			if d and d.Level.Value > 200 and (_()) then
				for d, _ in pairs(l[game.Workspace:GetAttribute("MAP")] or {}) do
					if (P.Position - _).Magnitude <= 3000 and Y >= 3000 then
						getgenv().noclip = true
						if o(d) then
							local l = tick() + 5
							repeat
								task.wait(0.2)
							until t.Character and (t.Character.HumanoidRootPart.Position - _).Magnitude < 500
								or tick() > l
							return
						end
					end
				end
			end
		end
		local l, d, _
		if Y >= 3000 then
			for o, y in pairs(Q) do
				local Q = (P.Position - y).Magnitude
				if Q <= 3000 and (not _ or Q < _) then
					_, l, d = Q, o, y
				end
			end
		end
		if d then
			getgenv().noclip = true
			if l == "Temple Clock" then
				BorrowTempleOfTime()
			end
			I()
			game.ReplicatedStorage.Remotes.CommF_:InvokeServer("requestEntrance", d)
			task.wait(0.1)
			return
		end
		local Q, I, o, y = N(H.Position), N(P.Position), V(P.Position), V(H.Position)
		if I and I.Name == "Celestial Domain" and (not Q or Q.Name ~= "Celestial Domain") then
			d = DetectNpcOni()
			if not d or not d:FindFirstChild("HumanoidRootPart") then
				return
			end
			_ = d.HumanoidRootPart.CFrame * CFrame.new(0, 0, 20)
			B(H, _, 350, 12)
			if (_.Position - H.Position).Magnitude < 300 then
				game:GetService("ReplicatedStorage").Modules.Net
					:WaitForChild("RF/CelestialDomainTransportation")
					:InvokeServer("InitiateTeleportToTemple")
				CelestialDomainController:LoadMap()
				TweenManager.CancelCurrent()
				task.wait(1)
			end
			return
		end
		if o and (o.Name == "Celestial Domain (Interior)" or o.Name == "Celestial Domain <Interior>") then
			if Q and Q.Name == "Celestial Domain" then
				game:GetService("ReplicatedStorage").Modules.Net
					:WaitForChild("RF/CelestialDomainTransportation")
					:InvokeServer("InitiateTeleportToInterior")
				TweenManager.CancelCurrent()
				task.wait(1)
				return
			end
			l = y and (y.Name == "Celestial Domain (Interior)" or y.Name == "Celestial Domain <Interior>")
			if not Q or Q.Name ~= "Celestial Domain" and not l then
				_ = DetectNpcOni()
				if not _ or not _:FindFirstChild("HumanoidRootPart") then
					return
				end
				d = _.HumanoidRootPart.CFrame * CFrame.new(0, 0, 20)
				B(H, d, 350, 12)
				if (d.Position - H.Position).Magnitude < 300 then
					game:GetService("ReplicatedStorage").Modules.Net
						:WaitForChild("RF/CelestialDomainTransportation")
						:InvokeServer("InitiateTeleportToTemple")
					CelestialDomainController:LoadMap()
					TweenManager.CancelCurrent()
					task.wait(1)
					game:GetService("ReplicatedStorage").Modules.Net
						:WaitForChild("RF/CelestialDomainTransportation")
						:InvokeServer("InitiateTeleportToInterior")
				end
				return
			end
		end
		if
			y
			and (y.Name == "Celestial Domain (Interior)" or y.Name == "Celestial Domain <Interior>")
			and (not o or o.Name ~= "Celestial Domain (Interior)" and o.Name ~= "Celestial Domain <Interior>")
		then
			game:GetService("ReplicatedStorage").Modules.Net
				:WaitForChild("RF/CelestialDomainTransportation")
				:InvokeServer("Leave")
			TweenManager.CancelCurrent()
			task.wait(1)
			return
		end
		if Q and Q.Name == "Celestial Domain" and (not I or I.Name ~= "Celestial Domain") then
			game:GetService("ReplicatedStorage").Modules.Net
				:WaitForChild("RF/CelestialDomainTransportation")
				:InvokeServer("Leave")
			TweenManager.CancelCurrent()
			return
		end
		if
			game.PlaceId == getgenv().CheckPlaceId
			and (workspace.Map:FindFirstChild("CakeLoaf"))
			and (workspace.Map.CakeLoaf:FindFirstChild("BigMirror"))
			and (workspace.Map.CakeLoaf.BigMirror:FindFirstChild("Main"))
			and (Vector3.new(-1990.67, 4532.97, -14973.67) - P.Position).Magnitude <= 1000
			and (Vector3.new(-1990.67, 4532.97, -14973.67) - H.Position).Magnitude > 1000
		then
			B(H, workspace.Map.CakeLoaf.BigMirror.Main.CFrame, 400, 8)
			return
		end
	end
	if ShouldResetTeleportSmart(P) then
		if BypassTp.TweenBypass(P) then
			return
		end
	end
	if H.Position.Y < -60 and H.Position.Y > -100 then
		H.CFrame = H.CFrame * CFrame.new(0, 20, 0)
	end
	Z = CFrame.new()
	Z = if ReadyToDodge
		then (CFrame.new(0, 200, 0))
		else if G then (CFrame.new(0, Settings["Distance Teleport Y"] or 800, 0)) else Z
	Y, e = Settings["Speed Tween "] or 300, P * Z
	if (e.Position - H.Position).Magnitude < 3 and not ReadyToDodge and not G then
		TweenManager.CancelTweenOnly()
		H.CFrame = e
		return
	end
	B(H, e, Y)
end
getgenv().BackupTween = toTarget
spawn(function()
	while wait(0.25) do
		local G, G = pcall(function()
			if g["Teleport To Island"] then
				for l, Q in next, E, nil do
					if l == g["Select Island"] then
						toTarget(Q)
					end
				end
			end
			if g["Teleport To Npc"] then
				for E, E in next, m, nil do
					if E.Name == g["Select Npc"] then
						toTarget(E.HumanoidRootPart.CFrame)
					end
				end
			end
			if g["Teleport Mirage"] then
				if game:GetService("Workspace").Map:FindFirstChild("MysticIsland") then
					local m = DetectNpc("Advanced Fruit Dealer")
					if m then
						toTarget(m.HumanoidRootPart.CFrame)
						return
					end
				end
			end
			if g["Teleport Prehistoric Island"] then
				if game:GetService("Workspace").Map:FindFirstChild("PrehistoricIsland") then
					local g = DetectNpc("Fossil Expert")
					if g then
						toTarget(g.HumanoidRootPart.CFrame)
						return
					end
				end
			end
			if Settings["Auto rejoin Disconnect"] then
				if
					not string.find(
						game:GetService("CoreGui").RobloxPromptGui.promptOverlay.ErrorPrompt.MessageArea.ErrorFrame.ErrorMessage.Text,
						"Teleport"
					)
				then
					game:GetService("TeleportService")
						:TeleportToPlaceInstance(game.PlaceId, game.JobId, game.Players.LocalPlayer)
				end
			end
		end)
		if G then
			print(G)
		end
	end
end)
function equiptool(g)
	if g and (t:FindFirstChild("Backpack")) and (t.Backpack:FindFirstChild(g)) and not t.Character.Humanoid.Sit then
		t.Character.Humanoid:EquipTool(t.Backpack:FindFirstChild(g))
	end
end
function NameWeapon(g, G)
	local function m(E)
		local l, Q, d = next, E:GetChildren()
		for E, E in l, Q, d do
			if E:IsA("Tool") and E.ToolTip == g then
				return G and E or E.Name
			end
		end
	end
	return m(t.Backpack) or (m(t.Character))
end
local g, G, m, E =
	require(game:GetService("ReplicatedStorage").Mouse),
	require(game:GetService("ReplicatedStorage").Modules.CombatUtil),
	require(game:GetService("ReplicatedStorage").Modules.Net),
	game:GetService("ReplicatedStorage").Modules.Net:WaitForChild("RE/RegisterAttack")
local l = m:RemoteEvent("RegisterHit", true)
local function m(Q, d, I)
	local _ = {}
	for o, o in pairs(Q:GetChildren()) do
		if o:IsA("BasePart") and (o.Position - d).Magnitude <= I then
			table.insert(_, o)
		end
	end
	return _
end
local function Q(d)
	local I = {}
	for _, _ in pairs(game:GetService("Workspace"):WaitForChild("Enemies"):GetChildren()) do
		table.insert(I, _)
	end
	if d then
		for d, d in pairs(game:GetService("Workspace"):WaitForChild("Characters"):GetChildren()) do
			table.insert(I, d)
		end
	end
	return I
end
getgenv().getBladeHits = function(d, I, _, o)
	local V = {}
	for N, y in pairs(Q(o)) do
		if y:IsDescendantOf(Workspace) and y ~= d and (y:FindFirstChild("HumanoidRootPart")) then
			local Q, d = y.HumanoidRootPart, S:GetPlayerFromCharacter(y) and _ / 1.5 or _
			N = { Q.Position }
			if Q.Size.Y > 5 then
				table.insert(N, (Q.CFrame * CFrame.new(0, -Q.Size.Y * 1.5 + 3, 0)).Position)
			end
			for _, _ in pairs(N) do
				if (_ - I[1].Position).Magnitude < 10 + d + Q.Size.X / 2 then
					for _, _ in pairs(m(y, I[1].Position, d + Q.Size.X / 2)) do
						table.insert(V, _)
					end
					break
				end
			end
		end
	end
	return V
end
local m = {
	RightUpperArm = true,
	RightLowerArm = true,
	RightHand = true,
	RightUpperLeg = true,
	RightLowerLeg = true,
	RightFoot = true,
	LeftUpperArm = true,
	LeftLowerArm = true,
	LeftHand = true,
	LeftUpperLeg = true,
	LeftLowerLeg = true,
	LeftFoot = true,
	UpperTorso = true,
	LowerTorso = true,
	Head = true,
}
function AttackAOE(Q, d)
	local I, _, o, V, N = {}, {}, getgenv().getBladeHits, t.Character, { t.Character.HumanoidRootPart }
	for y, P in o(V, N, Q or 80, d) do
		y = G:GetRigOfHitPart(P)
		if y and not _[y] and m[P.Name] and (G:IsVulnerable(y)) then
			local m, Q = y:FindFirstChild("Summoner"), t.Character:FindFirstChild("Summoner")
			if
				y ~= t.Character
				and (not Q or y ~= Q.Value.Character)
				and (
					not S:GetPlayerFromCharacter(t.Character)
					or not m
					or m.Value ~= S:GetPlayerFromCharacter(t.Character)
				)
			then
				table.insert(I, { y, P })
				_[y] = true
			end
		end
	end
	return #I > 0 and I or nil
end
v_u_27 = 0
v_u_28 = false
v_u_33 = false
v_u_31 = nil
v_u_32 = 0
v_u_21 = 0
v_u_16 = 1
CameraShakerMain = require(game:GetService("ReplicatedStorage").Util.CameraShaker.Main)
CameraShaker = require(game:GetService("ReplicatedStorage").Util.CameraShaker)
function attackMelee(m)
	local Q = game.Players.LocalPlayer.Character:FindFirstChildOfClass("Tool")
	if not Q then
		return
	end
	local d = AttackAOE(m, false)
	if not d then
		return
	end
	m = game.Players.LocalPlayer.Character.Humanoid
	local I = m and m.RootPart
	I = I and I.Parent
	local _ = G:GetMovesetAnimCache(m)
	if _ then
		m = G:GetWeaponName(Q)
		local Q = G:GetWeaponData(m)
		local o, V = Q.WeaponType, Q.Moveset
		if G:CanAttack(I, o) then
			v_u_33 = true
			v_u_32 = 5
			v_u_21 = os.clock()
			v_u_27 += 1
			if v_u_27 > #V.Basic then
				v_u_27 = 1
			end
			Q = _[G:GetPureWeaponName(m) .. "-basic" .. v_u_27]
			E:FireServer(Q.Length / (Q:GetAttribute("SpeedMult") or 1))
			l:FireServer(table.remove(d, 1)[2], d)
			Q:Play(0.100000001, 1, 1 * (Q:GetAttribute("SpeedMult") or 1))
			v_u_28 = true
			task.delay(Q.Length / (Q:GetAttribute("SpeedMult") or 1) * v_u_16, function()
				v_u_28 = false
			end)
			v_u_31 = Q
			table.clear(d)
		end
	end
end
AttackFunction = function(G)
	LPH_ATTRIBUTES(VM(NONE))
	if t.Character.Stun.Value ~= 0 then
		return
	end
	if not Settings["Attack No Animation "] then
		attackMelee(G)
	else
		local m = AttackAOE(G, false)
		if not m then
			return
		end
		E:FireServer(0)
		l:FireServer(table.remove(m, 1)[2], m)
		table.clear(m)
	end
end
getgenv().AttackFunctionnhungSuperTrial = function()
	LPH_ATTRIBUTES(VM(NONE))
	if t.Character.Stun.Value ~= 0 then
		return
	end
	local G = AttackAOE(80, true)
	if not G then
		return
	end
	E:FireServer(0)
	l:FireServer(table.remove(G, 1)[2], G)
	table.clear(G)
end
getgenv().AttackFunctionnhungSuper = getgenv().AttackFunctionnhungSuperTrial
local G = require(game:GetService("ReplicatedStorage").Mouse)
v_u_50 = nil
v_u_51 = 1
v_u_52 = time
v_u_53 = v_u_52()
local function m(E, l, Q)
	local d = t.Character
	local I = d and (d.PrimaryPart or (d:FindFirstChild("HumanoidRootPart")))
	if not I or not E then
		return false
	end
	local _ = Q and E.Position or E.PrimaryPart and E.PrimaryPart.Position
	if not _ then
		return false
	end
	local o, V, N =
		(_ - I.Position).Unit, ((g.Hit.Position - I.Position) * Vector3.new(1, 0, 1)).Unit, NameWeapon("Blox Fruit")
	I = N and (d:FindFirstChild(N))
	if not I then
		return false
	end
	d, E, Q = I:FindFirstChild("LeftClickRemote"), I:FindFirstChild("RemoteFunction"), I:FindFirstChild("RemoteEvent")
	if not d and E then
		if Q then
			Q:FireServer(_)
		end
		E:InvokeServer("TAP")
		return true
	end
	if d and N == "Mammoth-Mammoth" then
		d:FireServer(_)
		return true
	end
	if d then
		v_u_51 += 1
		if v_u_51 > 5 then
			v_u_51 = 1
		end
		d:FireServer(o, v_u_51)
		if l then
			d:FireServer(V, v_u_51)
		end
		return true
	end
	return false
end
getgenv().UseFruitM1 = function(g, E)
	return m(g, E, false)
end
getgenv().UseFruitM1Boat = function(g, E)
	return m(g, E, true)
end
getgenv().PathClickM1 = {}
local function g(m)
	m.ChildAdded:Connect(function(m)
		if m:IsA("Tool") then
			task.wait(0.5)
			local E = m:FindFirstChild("RemoteFunction")
			if E then
				getgenv().PathClickM1[m.Name] = E
			end
		end
	end)
end
if t.Character then
	g(t.Character)
end
t.CharacterAdded:Connect(g)
local function m(E)
	return t.Character
		and (t.Character:FindFirstChild("HumanoidRootPart"))
		and E
		and (E:FindFirstChild("HumanoidRootPart"))
		and E.Humanoid.Health > 0
		and (t.Character.HumanoidRootPart.Position - E.HumanoidRootPart.Position).Magnitude < 70
end
getgenv().ClickM1 = function(E, l)
	if not m(E) then
		return
	end
	if Settings["Select Weapon"] == "Blox Fruit" then
		if getgenv().UseFruitM1(E) then
			return
		end
	end
	AttackFunction(l and 80 or 30)
end
getgenv().ClickM1Dungeon = function(E, l)
	if not m(E) then
		return
	end
	if Settings["Select Weapon Dungeon"] == "Blox Fruit" then
		if getgenv().UseFruitM1(E) then
			return
		end
	end
	AttackFunction(l and 80 or 30)
end
getgenv().ClickM1Volcano = function(E, l)
	if not m(E) then
		return
	end
	if Settings["Select Weapon Kill Golem"] and Settings["Select Weapon Kill Golem"] == "Blox Fruit" then
		if getgenv().UseFruitM1(E) then
			return
		end
	end
	AttackFunction(l and 80 or 30)
end
local m = L:WaitForChild("Modules")
getgenv().SpamGunDragonStorm = function(E)
	local l, Q = require(m.CombatUtil), t.Character
	local d = Q and (Q:FindFirstChild("Dragonstorm"))
	if not d or (l:IsGunReloading(d)) then
		return
	end
	l = getupvalues(require(L.Controllers.CombatController).Attack)[9]
	local I, _, o, V, N, y, P =
		debug.getupvalue(l, 15),
		debug.getupvalue(l, 13),
		debug.getupvalue(l, 16),
		debug.getupvalue(l, 17),
		debug.getupvalue(l, 14),
		debug.getupvalue(l, 12),
		debug.getupvalue(l, 18)
	Q = y * _
	d = ((N * _ + y * I) % o * o + Q) % V
	N = math.floor(d / o)
	y = d - N * o
	P += 1
	debug.setupvalue(l, 15, I)
	debug.setupvalue(l, 13, _)
	debug.setupvalue(l, 16, o)
	debug.setupvalue(l, 17, V)
	debug.setupvalue(l, 14, N)
	debug.setupvalue(l, 12, y)
	debug.setupvalue(l, 18, P)
	L.Remotes.Validator2:FireServer(math.floor(d / V * 16777215), P)
	m.Net:FindFirstChild("RE/ShootGunEvent"):FireServer(E.Position, { E })
end
function ShootM1(E)
	spawn(function()
		if
			not require(game:GetService("ReplicatedStorage").Modules.CombatUtil):IsGunReloading(
				t.Character[NameWeapon("Gun")]
			)
		then
			if NameWeapon("Gun") ~= "Skull Guitar" then
				local l =
					getupvalues(require(game:GetService("ReplicatedStorage").Controllers.CombatController).Attack)[9]
				local Q, d, I, _, o, V, N =
					debug.getupvalue(l, 15),
					debug.getupvalue(l, 13),
					debug.getupvalue(l, 16),
					debug.getupvalue(l, 17),
					debug.getupvalue(l, 14),
					debug.getupvalue(l, 12),
					debug.getupvalue(l, 18)
				local y = V * d
				local P = ((o * d + V * Q) % I * I + y) % _
				o = math.floor(P / I)
				V = P - o * I
				N += 1
				debug.setupvalue(l, 15, Q)
				debug.setupvalue(l, 13, d)
				debug.setupvalue(l, 16, I)
				debug.setupvalue(l, 17, _)
				debug.setupvalue(l, 14, o)
				debug.setupvalue(l, 12, V)
				debug.setupvalue(l, 18, N)
				game.ReplicatedStorage.Remotes.Validator2:FireServer(math.floor(P / _ * 16777215), N)
				if NameWeapon("Gun") == "Cannon" then
					game:GetService("ReplicatedStorage").Modules.Net
						:FindFirstChild("RE/ShootGunEvent")
						:FireServer(unpack({ [1] = E }))
				else
					_ = { [1] = E.HumanoidRootPart.Position, [2] = { [1] = E.HumanoidRootPart } }
					game:GetService("ReplicatedStorage").Modules.Net
						:FindFirstChild("RE/ShootGunEvent")
						:FireServer(unpack(_))
				end
				task.wait(t.Character[NameWeapon("Gun")].Cooldown.Value)
			else
				local l = { [1] = "TAP", [2] = E.HumanoidRootPart.Position }
				game:GetService("Players").LocalPlayer.Character
					:FindFirstChild("Skull Guitar").RemoteEvent
					:FireServer(unpack(l))
				task.wait(t.Character[NameWeapon("Gun")].Cooldown.Value)
			end
		end
	end)
end
getgenv().SpamGunSkullGuitar = function(E)
	local l, Q = require(m.CombatUtil), t.Character
	local m = Q and (Q:FindFirstChild("Skull Guitar"))
	if not m or (l:IsGunReloading(m)) then
		return
	end
	m.RemoteEvent:FireServer("TAP", E.Position)
end
local function m(E, l)
	local Q, d, I, _, o, V, N =
		require(game:GetService("ReplicatedStorage").Modules.CombatUtil),
		getgenv().getBladeHits,
		E.Character,
		{ E.Character.HumanoidRootPart },
		1 / 0
	for y, P in d(I, _, l, true) do
		y = Q:GetRigOfHitPart(P)
		if y and (Q:IsVulnerable(y)) then
			local l = (E.Character.HumanoidRootPart.Position - P.Position).Magnitude
			if l < o then
				o, V, N = l, y, P
			end
		end
	end
	if V and N then
		return { V, N }
	end
	return nil
end
function DetectItemPlr(E)
	if t.Character:FindFirstChild(E) or (t.Backpack:FindFirstChild(E)) then
		return true
	end
end
function sizepart(E)
	AttackingMob = E
	if not E or not E.Parent or not E:FindFirstChild("HumanoidRootPart") then
		return
	end
	if t:DistanceFromCharacter(E.HumanoidRootPart.Position) <= 50 then
		local l, Q, d = next, E:GetDescendants()
		for E, E in l, Q, d do
			if (E:IsA("Part") or (E:IsA("MeshPart"))) and E.CanCollide then
				E.CanCollide = false
			end
		end
	end
end
local E, l
function DeleteIgnoredMob()
	for Q, Q in pairs(game:GetService("Workspace").Enemies:GetChildren()) do
		if Q:IsA("Model") and (Q:FindFirstChild("Ignored")) then
			Q.Ignored:Destroy()
		end
	end
end
function DetectMob(Q)
	local d, I = 1 / 0
	for _, o in pairs(game.Workspace.Enemies:GetChildren()) do
		if (typeof(Q) == "table" and (table.find(Q, o.Name)) or o.Name == Q) and (IsMobAlive(o)) then
			_ = (
				o.HumanoidRootPart.Position - game:GetService("Players").LocalPlayer.Character.HumanoidRootPart.Position
			).magnitude
			if _ < d then
				d, I = _, o
			end
		end
	end
	return I
end
function CheckNameBoss(Q)
	local d, I, _ = next, game.ReplicatedStorage:GetChildren()
	for o, o in d, I, _ do
		if (typeof(Q) == "table" and (table.find(Q, o.Name)) or o.Name == Q) and (IsMobAlive(o)) then
			return o
		end
	end
	d, _, I = next, game.Workspace.Enemies:GetChildren()
	for o, o in d, _, I do
		if (typeof(Q) == "table" and (table.find(Q, o.Name)) or o.Name == Q) and (IsMobAlive(o)) then
			return o
		end
	end
end
getgenv().TableMobSpawn = {}
spawn(function()
	for Q, Q in pairs(getnilinstances()) do
		if
			if Q:GetAttribute("DisplayName") and (string.find(Q:GetAttribute("DisplayName"), "Lv."))
				then (Q:GetAttribute("DisplayName"):gsub(" %pLv. %d+%p", ""))
				else nil
		then
			table.insert(TableMobSpawn, Q)
		end
	end
	for Q, Q in pairs(game:GetService("Workspace")._WorldOrigin.EnemySpawns:GetChildren()) do
		if
			if Q:GetAttribute("DisplayName") and (string.find(Q:GetAttribute("DisplayName"), "Lv."))
				then (Q:GetAttribute("DisplayName"):gsub(" %pLv. %d+%p", ""))
				else nil
		then
			table.insert(TableMobSpawn, Q)
		end
	end
end)
function getcenter(Q)
	if string.find(Q, "Lv.") then
		name1 = Q:gsub(" %pLv. %d+%p", "")
	end
	local d
	local I = 0
	for _, o in pairs(TableMobSpawn) do
		_ = if string.find(o.Name, "Lv.") then (o.Name:gsub(" %pLv. %d+%p", "")) else nil
		if o:IsA("Part") and (_ and _ == Q or Q == o.Name or name1 and o.Name == name1) then
			if d == nil then
				d, I = o.Position, I + 1
			else
				d, I = d + o.Position, I + 1
			end
		end
	end
	d /= I
	return CFrame.new(d)
end
function DetectPartMobBring(Q, d, I, _)
	local o, V = {}, if string.find(Q, "Lv.") then (Q:gsub(" %pLv. %d+%p", "")) else nil
	for N, y in pairs(TableMobSpawn) do
		N = if string.find(y.Name, "Lv.") then (y.Name:gsub(" %pLv. %d+%p", "")) else nil
		if y:IsA("Part") and (N and N == Q or Q == y.Name or V and y.Name == V) then
			table.insert(o, y)
		end
	end
	if I then
		Q, V = 1 / 0
		for I, N in next, o, nil do
			I = (d.HumanoidRootPart.Position - N.Position).Magnitude
			if Q > I then
				Q, V = I, N
			end
		end
		return V
	else
		local Q = {}
		for d, d in next, o, nil do
			if (_.Position - d.Position).Magnitude <= 200 then
				table.insert(Q, d)
			end
		end
		if #Q < #o then
			return true
		end
	end
end
function isnetworkowner2(Q)
	local d, I, _ = next, game.Workspace.Characters:GetChildren()
	for o, o in d, I, _ do
		if
			o.Name ~= t.Name
			and (o:FindFirstChild("HumanoidRootPart"))
			and (o.HumanoidRootPart.Position - Q.Position).Magnitude <= 300
		then
			return false
		end
	end
	return true
end
function BringMob(Q)
	if not Settings["Bring Mob"] then
		return
	end
	if Q and E ~= Q then
		E = Q
		l = DetectPartMobBring(Q.Name, Q, true).CFrame
		local d = game:GetService("Players").LocalPlayer.Data.Race.Value == "Cyborg"
			and (t.Character:FindFirstChild("RaceTransformed"))
			and t.Character.RaceTransformed.Value
		if d then
			l = getcenter(Q.Name)
		end
		DeleteIgnoredMob()
	end
	if DaBringMob then
		delay(0.1, function()
			getgenv().DaBringMob = false
		end)
		return
	end
	local d = {}
	if not Q:FindFirstChild("Ignored") then
		table.insert(d, Q)
	end
	local I = Settings["Bring Mob Count"] or 2
	local _, o = if I > 2 then 350 else 200
	if
		game:GetService("Players").LocalPlayer.Data.Race.Value == "Cyborg"
		and (t.Character:FindFirstChild("RaceTransformed"))
		and t.Character.RaceTransformed.Value
	then
		_, o = 300, 6
	else
		o = I
	end
	for I, I in pairs(workspace.Enemies:GetChildren()) do
		if
			I ~= Q
			and I.Name == Q.Name
			and not I:FindFirstChild("Ignored")
			and (IsMobAlive(I))
			and (isnetworkowner2(I.HumanoidRootPart))
		then
			if (I.HumanoidRootPart.Position - l.Position).Magnitude <= _ and #d < o then
				table.insert(d, I)
			end
		end
	end
	if
		l
		and (t.Character.HumanoidRootPart.Position - Q.HumanoidRootPart.Position).Magnitude <= 50
		and (isnetworkowner2(t.Character.HumanoidRootPart))
		and #d >= 2
	then
		for Q, Q in pairs(d) do
			sizepart(Q)
			if not isnetworkowner2(Q.HumanoidRootPart) then
				Q.HumanoidRootPart.CFrame = Q.WorldPivot
				Instance.new("IntValue", Q).Name = "Ignored"
				task.wait(0.3)
			else
				Q.HumanoidRootPart.CFrame = l * CFrame.new(0, math.random(0, 2), math.random(0, 2))
				task.spawn(function()
					local d = Q.Humanoid.Health
					task.wait(2.2)
					if Q.Humanoid.Health == d and not Q:FindFirstChild("Ignored") then
						Q.HumanoidRootPart.CFrame = Q.WorldPivot
						Instance.new("IntValue", Q).Name = "Ignored"
						task.wait(0.3)
					end
				end)
			end
			getgenv().DaBringMob = true
		end
	end
end
task.wait(1)
SettingFarmMain = Main.CreatePage({ Page_Name = "Setting Farm", Page_Title = "Setting Farm" })
SettingFarmMainSection = SettingFarmMain.CreateSection("Setting Farm")
local Q, d =
	false,
	SettingFarmMainSection.CreateDropdown(
		{
			Title = "Select Weapon",
			List = { "Melee", "Sword", "Blox Fruit" },
			Search = true,
			Selected = false,
			Default = Settings["Select Weapon"] or nil,
		},
		function(I)
			SaveSettings("Select Weapon", I)
		end
	)
SettingFarmMainSection.CreateToggle(
	{ Title = "Attack No Animation ", Desc = nil, Default = Settings["Attack No Animation "] or true },
	function(I)
		SaveSettings("Attack No Animation ", I)
	end
)
SettingFarmMainSection.CreateToggle(
	{
		Title = "Kill Aura Only Raid And Volcano",
		Desc = nil,
		Default = Settings["Kill Aura Only Raid And Volcano"] or false,
	},
	function(I)
		SaveSettings("Kill Aura Only Raid And Volcano", I)
	end
)
SettingFarmMainSection.CreateSlider(
	{ Title = "Time Delay Kill", Min = 0, Max = 5, Default = Settings["Time Delay Kill"] or 5, Precise = true },
	function(I)
		SaveSettings("Time Delay Kill", I)
	end
)
SettingFarmMainSection.CreateToggle(
	{ Title = "Auto Click", Desc = nil, Default = Settings["Auto Click"] or false },
	function(I)
		if I then
			spawn(function()
				while Settings["Auto Click"] and (task.wait()) do
					local _, _ = pcall(function()
						local o = NameWeapon("Blox Fruit")
						if o and (t.Character:FindFirstChild(o)) then
							local o = AttackAOE(80, true)
							if not o then
								return
							end
							getgenv().UseFruitM1(o[1][1])
						else
							getgenv().AttackFunctionnhungSuperTrial()
						end
					end)
					if _ then
						print(_)
					end
				end
			end)
		end
		SaveSettings("Auto Click", I)
	end
)
SettingFarmMainSection.CreateToggle(
	{ Title = "Kill Aura With DragonStorm", Desc = nil, Default = Settings["Kill Aura With DragonStorm"] or false },
	function(I)
		if I then
			spawn(function()
				while Settings["Kill Aura With DragonStorm"] and (wait()) do
					pcall(function()
						if t.Character:FindFirstChild("Dragonstorm") and getgenv().SpamGunDragonStorm then
							local _ = m(game.Players.LocalPlayer, 150)
							if _ then
								local m, o = _[1], _[2]
								SpamGunDragonStorm(m.PrimaryPart)
							end
						end
					end)
				end
			end)
		end
		SaveSettings("Kill Aura With DragonStorm", I)
	end
)
function FFCMatch(m, I)
	for _, _ in pairs(m:GetChildren()) do
		if string.match(_.Name, I) then
			return _
		end
	end
	return nil
end
SettingFarmMainSection.CreateToggle(
	{ Title = "Auto Turn On Buso", Desc = nil, Default = Settings["Auto Turn On Buso"] or true },
	function(m)
		if m then
			spawn(function()
				while Settings["Auto Turn On Buso"] and (wait(1)) do
					pcall(function()
						if not FFCMatch(t.Character, "_BusoLayer1") and not t.Character:FindFirstChild("HasBuso") then
							CommF:InvokeServer("Buso")
							task.wait(2)
						end
					end)
				end
			end)
		end
		SaveSettings("Auto Turn On Buso", m)
	end
)
SettingFarmMainSection.CreateToggle(
	{ Title = "Auto Turn On Observation", Desc = nil, Default = Settings["Auto Turn On Observation"] or false },
	function(m)
		if m then
			spawn(function()
				while Settings["Auto Turn On Observation"] and (wait(1)) do
					pcall(function()
						if not game:GetService("Lighting").Blur.Enabled then
							game:GetService("VirtualInputManager"):SendKeyEvent(true, "E", false, game)
							wait()
							game:GetService("VirtualInputManager"):SendKeyEvent(false, "E", false, game)
							wait(3)
						end
					end)
				end
			end)
		end
		SaveSettings("Auto Turn On Observation", m)
	end
)
function TurnOnV4()
	local m = t.Character
	local I, _ = m and (m:FindFirstChild("RaceEnergy")), m and (m:FindFirstChild("RaceTransformed"))
	if not I or I.Value < 1 or not _ or _.Value then
		return
	end
	_ = t.Backpack:FindFirstChild("Awakening") or (m:FindFirstChild("Awakening"))
	if _ then
		_.RemoteFunction:InvokeServer(true)
	end
end
local m = SettingFarmMainSection.CreateToggle(
	{ Title = "Auto Turn On V4", Desc = nil, Default = Settings["Auto Turn On V4"] or false },
	function(I)
		if I then
			spawn(function()
				while Settings["Auto Turn On V4"] and (task.wait(1)) do
					pcall(TurnOnV4)
				end
			end)
		end
		SaveSettings("Auto Turn On V4", I)
	end
)
SettingFarmMainSection.CreateToggle(
	{ Title = "Auto Turn On V3", Desc = nil, Default = Settings["Auto Turn On V3"] or false },
	function(I)
		if I then
			spawn(function()
				while Settings["Auto Turn On V3"] and (task.wait(1)) do
					game:GetService("ReplicatedStorage").Remotes.CommE:FireServer("ActivateAbility")
					wait(2)
				end
			end)
		end
		SaveSettings("Auto Turn On V3", I)
	end
)
SettingFarmMainSection.CreateToggle(
	{ Title = "Auto Dodge Skill Mobs", Desc = nil, Default = Settings["Auto Dodge Skill Mobs"] or false },
	function(I)
		SaveSettings("Auto Dodge Skill Mobs", I)
	end
)
local I
game:GetService("Workspace").Enemies.DescendantAdded:Connect(function(_)
	if
		Settings["Auto Dodge Skill Mobs"]
		and I
		and I.Parent
		and not Doding
		and (_.Name == "BodyGyro" or _.Name == "BodyPosition" or _.Name == "KiBlastFireShort")
		and _.Parent.Parent.Name == I.Name
	then
		getgenv().Doding = true
		getgenv().ReadyToDodge = true
		local I = tick()
		repeat
			wait()
		until not _ or not _.Parent or tick() - I > 14
		if tick() - I < 2 then
			wait(0.5)
		end
		getgenv().Doding = false
		getgenv().ReadyToDodge = false
	end
end)
SettingFarmMainSection.CreateToggle(
	{ Title = "Teleport Y if low health", Desc = nil, Default = Settings["Teleport Y"] or false },
	function(I)
		SaveSettings("Teleport Y", I)
	end
)
SettingFarmMainSection.CreateSlider(
	{ Title = "% Health Player", Min = 0, Max = 100, Default = Settings["% Health Player"] or 40, Precise = true },
	function(I)
		SaveSettings("% Health Player", I)
	end
)
SettingFarmMainSection.CreateSlider(
	{
		Title = "Distance Teleport Y",
		Min = 0,
		Max = 10000,
		Default = Settings["Distance Teleport Y"] or 800,
		Precise = true,
	},
	function(I)
		SaveSettings("Distance Teleport Y", I)
	end
)
SettingFarmMainSection.CreateToggle(
	{ Title = "Tween Safe if have Items", Desc = nil, Default = Settings["Tween Safe if have Items"] or false },
	function(I)
		if I then
			spawn(function()
				while Settings["Tween Safe if have Items"] and (wait(0.25)) do
					pcall(function()
						if CheckNameBoss("Darkbeard") and Settings["Attack Darkbeard"] then
							return
						end
						if DetectItemPlr("Fist of Darkness") and Settings["Summon Darkbeard"] then
							return
						end
						if
							(DetectItemPlr("Fist of Darkness") or (DetectItemPlr("God's Chalice")))
							and Settings["Tween Safe if have Items"]
						then
							if game.PlaceId == getgenv().CheckPlaceId2 then
								toTarget(CFrame.new(-385.250916, 73.0458984, 297.388397))
							else
								toTarget(CFrame.new(-12463, 374, -7523))
							end
						end
					end)
				end
			end)
		end
		SaveSettings("Tween Safe if have Items", I)
	end
)
SettingFarmMainSection.CreateSlider(
	{ Title = "Time Hop Server", Min = 0, Max = 60, Default = Settings["Time Hop Server"] or 10, Precise = true },
	function(I)
		SaveSettings("Time Hop Server", I)
	end
)
SettingFarmMainSection.CreateToggle(
	{ Title = "Use Portal Teleport", Desc = nil, Default = Settings["Use Portal Teleport"] or false },
	function(I)
		SaveSettings("Use Portal Teleport", I)
	end
)
SettingFarmMainSection.CreateSlider(
	{ Title = "Bring Mob Count", Min = 2, Max = 6, Default = Settings["Bring Mob Count"] or 2, Precise = true },
	function(I)
		SaveSettings("Bring Mob Count", I)
	end
)
SettingFarmMainSection.CreateToggle(
	{ Title = "Bring Mob", Desc = nil, Default = Settings["Bring Mob"] or true },
	function(I)
		SaveSettings("Bring Mob", I)
	end
)
SettingFarmMainSection.CreateToggle(
	{ Title = "Reset Teleport [ Beta ]", Desc = nil, Default = Settings["Reset Teleport"] or false },
	function(I)
		SaveSettings("Reset Teleport", I)
	end
)
SettingFarmMainSection.CreateSlider(
	{ Title = "Speed Tween ", Min = 0, Max = 1000, Default = Settings["Speed Tween "] or 300, Precise = true },
	function(I)
		SaveSettings("Speed Tween ", I)
	end
)
SettingFarmMainSection.CreateLabel({
	Title = "Recommended: 350. If you\226\128\153re farming spots close to each other, use a higher speed",
})
SettingSkillMain =
	Main.CreatePage({ Page_Name = "Hold and Select Skill", Page_Title = "Setting Hold and Select Skill" })
SelectSkillsSection = SettingSkillMain.CreateSection("Select Skills")
local function I(_, o)
	local V, N = "Select Skills " .. _, {}
	for y, y in ipairs(o) do
		N[y] = false
	end
	EnsureAllTrueDefaults(V, o)
	_ = PrepareMultiSelectList(N, Settings[V], true)
	SelectSkillsSection.CreateDropdown(
		{ Title = V, List = _, Search = true, Selected = true, Default = Settings[V] or nil },
		function(_, o)
			SaveSettings(V, _, o)
		end
	)
end
I("Melee", { "Z", "X", "C" })
I("Sword", { "Z", "X" })
I("Gun", { "Z", "X" })
I("Blox Fruit", { "Z", "X", "C", "V", "F" })
HoldSkillsSection = SettingSkillMain.CreateSection("Hold Skills")
local function _(o, V)
	local N = {}
	for y, y in ipairs(V) do
		N[y] = {
			Title = y,
			KeyName = y,
			Min = 0,
			Max = 5,
			Default = Settings["Skill " .. y .. " " .. o] or 0.5,
			Precise = true,
		}
	end
	HoldSkillsSection.CreateDropdown({ Title = "Set Delay " .. o, List = N, Slider = true }, function(V, V)
		if V and V.KeyName then
			SaveSettings("Skill " .. V.KeyName .. " " .. o, V.Default)
		end
	end)
end
HoldSkillsSection.CreateToggle(
	{ Title = "Use skill fast dont hold", Desc = nil, Default = Settings["Use skill fast dont hold"] or false },
	function(o)
		SaveSettings("Use skill fast dont hold", o)
	end
)
_("Melee", { "Z", "X", "C" })
_("Sword", { "Z", "X" })
_("Gun", { "Z", "X" })
_("Blox Fruit", { "Z", "X", "C", "V", "F" })
FarmMain = Main.CreatePage({ Page_Name = "Farming", Page_Title = "Farming" })
SettingAutoFarmSection = FarmMain.CreateSection("Setting Farm")
SettingAutoFarmSection.CreateDropdown(
	{
		Title = "Select Method Farm",
		List = { "Level Farm", "Farm Bones", "Farm Katakuri", "Farm Tyrant of the Skies", "Aura Farm" },
		Search = false,
		Selected = false,
		Default = Settings["Select Method Farm"] or nil,
	},
	function(o)
		SaveSettings("Select Method Farm", o)
	end
)
SettingAutoFarmSection.CreateSlider(
	{
		Title = "Distance Farm Aura",
		Min = 0,
		Max = 1000,
		Default = Settings["Distance Farm Aura"] or 300,
		Precise = true,
	},
	function(o)
		SaveSettings("Distance Farm Aura", o)
	end
)
SettingAutoFarmSection.CreateToggle(
	{ Title = "Ignore Attack Katakuri", Desc = nil, Default = Settings["Ignore Attack Katakuri"] or false },
	function(o)
		SaveSettings("Ignore Attack Katakuri", o)
	end
)
SettingAutoFarmSection.CreateToggle(
	{ Title = "Hop Find Katakuri", Desc = nil, Default = Settings["Hop Find Katakuri"] or false },
	function(o)
		SaveSettings("Hop Find Katakuri", o)
	end
)
SettingAutoFarmSection.CreateToggle(
	{
		Title = "Auto Quest [Katakuri/Bone/Tyrant]",
		Desc = nil,
		Default = Settings["Auto Quest [Katakuri/Bone/Tyrant]"] or false,
	},
	function(o)
		SaveSettings("Auto Quest [Katakuri/Bone/Tyrant]", o)
	end
)
local o = SettingAutoFarmSection.CreateToggle(
	{ Title = "Start Farm", Desc = nil, Default = Settings["Start Farm"] or false },
	function(V)
		SaveSettings("Start Farm", V)
	end
)
MasteryFarmSection = FarmMain.CreateSection("Mastery Farm")
MasteryFarmSection.CreateDropdown(
	{
		Title = "Select Method Farm Mastery",
		List = { "Blox Fruit", "Gun" },
		Search = true,
		Selected = false,
		Default = Settings["Select Method Farm Mastery"] or nil,
	},
	function(V)
		SaveSettings("Select Method Farm Mastery", V)
	end
)
MasteryFarmSection.CreateSlider(
	{ Title = "Health %", Min = 0, Max = 100, Default = Settings["Health %"] or 40, Precise = true },
	function(V)
		SaveSettings("Health %", V)
	end
)
MasteryFarmSection.CreateToggle(
	{ Title = "Farm Mastery", Desc = nil, Default = Settings["Farm Mastery"] or false },
	function(V)
		SaveSettings("Farm Mastery", V)
		if V and not Settings["Start Farm"] then
			A.CreateNoti({ Title = "Banana Cat Hub", Desc = "Turn On Start Farm Plz", ShowTime = 5 })
		end
	end
)
FarmingMaterialSection = FarmMain.CreateSection("Farming Material")
FarmingMaterialSection.CreateDropdown(
	{
		Title = "Select Material",
		List = TableMaterials,
		Search = true,
		Selected = false,
		Default = Settings["Select Material"] or nil,
	},
	function(V)
		SaveSettings("Select Material", V)
	end
)
FarmingMaterialSection.CreateToggle(
	{ Title = "Farm Material", Desc = nil, Default = Settings["Farm Material"] or false },
	function(V)
		SaveSettings("Farm Material", V)
		if V and not Settings["Start Farm"] then
			A.CreateNoti({ Title = "Banana Cat Hub", Desc = "Turn On Start Farm Plz", ShowTime = 5 })
		end
	end
)
local V, N, y, P, e, Y =
	{ "BartiloQuest", "Trainees", "MarineQuest", "CitizenQuest" },
	{},
	{ "Baking Staff", "Head Baker", "Cake Guard", "Cookie Crafter" },
	{ "Cocoa Warrior", "Chocolate Bar Battler", "Candy Rebel", "Sweet Thief" },
	{ "Reborn Skeleton", "Demonic Soul", "Living Zombie", "Posessed Mummy" },
	{ "Isle Champion", "Serpent Hunter", "Skull Slayer", "Sun-kissed Warrior" }
getgenv().NameMobQuest = ""
getgenv().NameQuest = ""
getgenv().IDQuest = 0
getgenv().questpoint = {}
local H = require(game.ReplicatedStorage.Quests)
local function B()
	local Z, C = t.Data.Level.Value, 0
	if Z >= 1450 and game.PlaceId == getgenv().CheckPlaceId2 then
		getgenv().NameMobQuest = "Water Fighter"
		getgenv().NameQuest = "ForgottenQuest"
		getgenv().IDQuest = 2
	elseif Z >= 700 and game.PlaceId == getgenv().CheckPlaceId3 then
		getgenv().NameMobQuest = "Galley Captain"
		getgenv().NameQuest = "FountainQuest"
		getgenv().IDQuest = 2
	else
		for J, F in pairs(H) do
			for q, c in pairs(F) do
				if not table.find(V, J) then
					local F = c.LevelReq
					for D, r in pairs(c.Task) do
						if Z >= F and F >= C and r > 1 then
							getgenv().NameMobQuest = D
							getgenv().NameQuest = J
							getgenv().IDQuest = q
							C = F
						end
					end
				end
			end
		end
	end
end
function CountQuest()
	local Z = {}
	for C, C in pairs(H) do
		for J, J in pairs(C) do
			for F, q in pairs(J.Task) do
				if F == getgenv().mobv then
					for J, J in pairs(C) do
						if J.LevelReq <= t.Data.Level.Value and J.Name ~= "Town Raid" then
							for C, F in pairs(J.Task) do
								if F > 1 then
									table.insert(Z, C)
								end
							end
						end
					end
				end
			end
		end
	end
	return Z
end
local Z = require(game.ReplicatedStorage:WaitForChild("GuideModule"))
function DontQuest()
	return Z.Data and Z.Data.QuestData ~= nil
end
function GetNameDoubleQuest()
	if DontQuest() then
		for C, J in next, Z.Data.QuestData.Task, nil do
			return C
		end
	end
end
function DoubleQuest()
	wait(0.5)
	B()
	local B = {}
	if DontQuest() and GetNameDoubleQuest() == getgenv().NameMobQuest and #CountQuest() >= 2 then
		for C, J in pairs(H) do
			for F, F in pairs(J) do
				for q in pairs(F.Task) do
					if tostring(q) == getgenv().mobv then
						for F, q in pairs(J) do
							for J, c in pairs(q.Task) do
								if J ~= getgenv().mobv and c > 1 then
									B.Name = J
									B.NameQuest = C
									B.ID = F
									return B
								end
							end
						end
					end
				end
			end
		end
	else
		B.Name = getgenv().NameMobQuest
		B.NameQuest = getgenv().NameQuest
		B.ID = getgenv().IDQuest
	end
	return B
end
function CFrameQuest()
	local B = {}
	for C, J in next, H, nil do
		if C ~= "MarineQuest" then
			for F, F in next, J, nil do
				B[F.LevelReq] = C
			end
		end
	end
	getgenv().questpoint = {}
	for C, J in next, Z.Data.NPCList, nil do
		for F, q in next, J.Levels, nil do
			F = B[q]
			if C.Parent.Name ~= "Marine Leader" and F and not getgenv().questpoint[F] then
				getgenv().questpoint[F] = CFrame.new(J.Position)
			end
		end
	end
	getgenv().questpoint.SkyExp1Quest = CFrame.new(-7857.28516, 5544.34033, -382.321503)
end
local function B(C)
	local J = Z.Data.QuestData
	local F, q, c = J and (next(J.Task)), 0, {}
	for D, r in pairs(Z.Data.NPCList) do
		if not table.find(V, r.InternalQuestName) then
			for V, n in pairs(r.Levels) do
				D = H[r.InternalQuestName][V]
				if D then
					local u, W = next(D.Task)
					if W and W > 1 and n <= C and n >= q then
						c = {
							Level = n,
							Name = r.NPCName,
							QuestName = r.InternalQuestName,
							Pos = r.Position,
							Id = V,
							Mob = u,
						}
						if F == u and V > 1 then
							J = H[r.InternalQuestName][V - 1]
							if J and J.Task then
								for H, C in pairs(J.Task) do
									if H ~= F and C > 1 then
										c.Mob = H
										c.Id = V - 1
										break
									end
								end
							end
						end
						q = n
					end
				end
			end
		end
	end
	return c
end

TakeQuestLevel = function()
	local V = B(t.Data.Level.Value)
	if not V or not V.Pos then
		return
	end
	local H, B, C =
		typeof(V.Pos) == "CFrame" and V.Pos.Position or V.Pos,
		t.Character and (t.Character:FindFirstChild("HumanoidRootPart")),
		t.Character and (t.Character:FindFirstChild("Humanoid"))
	if not B or not C then
		return
	end
	if (H - B.Position).Magnitude <= 8 and C.Health > 0 then
		wait(2)
		CommF:InvokeServer("StartQuest", tostring(V.QuestName), V.Id)
	else
		toTarget(CFrame.new(H) * CFrame.new(0, 4, 2), true)
	end
end

function DetectPartSpawnMob(V, H)
	local function B(C)
		return C:gsub(" %p?Lv%.? %d+%p?", "")
	end
	local C = string.find(V, "Lv.") and (B(V)) or V
	for J, F in pairs(TableMobSpawn) do
		if F:IsA("Part") then
			J = string.find(F.Name, "Lv.") and (B(F.Name)) or F.Name
			if (J == V or J == C) and (not H or not F:FindFirstChild("Ignored")) then
				return F
			end
		end
	end
	for J, F in pairs(workspace._WorldOrigin.EnemySpawns:GetChildren()) do
		if F:IsA("Part") then
			J = string.find(F.Name, "Lv.") and (B(F.Name)) or F.Name
			if (J == V or J == C) and (not H or not F:FindFirstChild("Ignored")) then
				table.insert(TableMobSpawn, F)
				return F
			end
		end
	end
	for J, F in pairs(getnilinstances()) do
		if F:IsA("Part") then
			J = string.find(F.Name, "Lv.") and (B(F.Name)) or F.Name
			if (J == V or J == C) and (not H or not F:FindFirstChild("Ignored")) then
				table.insert(TableMobSpawn, F)
				return F
			end
		end
	end
	return nil
end
function DeleteIgnoredMobSpawn()
	for V, V in pairs(TableMobSpawn) do
		if V:FindFirstChild("Ignored") then
			V.Ignored:Destroy()
		end
	end
end
function DetectNameTablePart(V)
	for H, H in next, V, nil do
		if not table.find(N, H) then
			return H
		end
	end
end
function TeleportSpawnMob(V)
	if typeof(V) == "table" then
		if #N >= #V then
			N = {}
			return
		end
		local H = DetectPartSpawnMob(DetectNameTablePart(V))
		if H then
			toTarget(H.CFrame * CFrame.new(0, 60, 0))
			wait(0.5)
		end
	else
		wait(0.5)
		local H = DetectPartSpawnMob(V, true)
		if H then
			if (H.Position - t.Character.HumanoidRootPart.Position).Magnitude <= 100 or (DetectMob(V)) then
				Instance.new("IntValue", H).Name = "Ignored"
			end
			toTarget(H.CFrame * CFrame.new(0, 60, 0))
		else
			DeleteIgnoredMobSpawn()
		end
	end
end
function QuestBoneAndkatakuri(V, H)
	local B = getgenv().questpoint[V]
	if not B then
		CFrameQuest()
		task.wait(1.5)
		B = getgenv().questpoint[V]
		if not B then
			return
		end
	end
	local C, J =
		t.Character and (t.Character:FindFirstChild("HumanoidRootPart")),
		t.Character and (t.Character:FindFirstChildOfClass("Humanoid"))
	if not C or not J then
		return
	end
	if (B.Position - C.Position).Magnitude <= 8 then
		if J.Health > 0 then
			CommF:InvokeServer("StartQuest", V, H)
			task.wait(0.5)
		end
	else
		toTarget(B * CFrame.new(0, 4, 2), true)
	end
end
local V = { "Control-Control", "Buddha-Buddha", "Diamond-Diamond", "Falcon-Falcon" }
local function H(B, C)
	local J = t.PlayerGui.Main.Skills[B]:FindFirstChild(C)
	if not J then
		return false
	end
	return J:IsA("Frame") and J.Title.TextColor3 == Color3.new(1, 1, 1) and J.Cooldown.Size == UDim2.new(0, 0, 1, -1)
		or J.Cooldown.Size == UDim2.new(1, 0, 1, -1)
end
local function B(C)
	if H(C, "Z") then
		local H = game:GetService("VirtualInputManager")
		H:SendKeyEvent(true, "Z", false, game)
		H:SendKeyEvent(false, "Z", false, game)
	end
end
local function H(C)
	local J = t.PlayerGui.Main.Skills[C.Name]
	if not J then
		return nil
	end
	for F, F in ipairs(J:GetChildren()) do
		if
			F:IsA("Frame")
			and F.Name ~= "Template"
			and (F.Name ~= "Z" or F.Name == "Z" and not table.find(V, C.Name))
			and Settings["Select Skills " .. C.ToolTip]
			and Settings["Select Skills " .. C.ToolTip][F.Name]
			and (
				F.Title.TextColor3 == Color3.new(1, 1, 1) and F.Cooldown.Size == UDim2.new(0, 0, 1, -1)
				or F.Cooldown.Size == UDim2.new(1, 0, 1, -1)
			)
		then
			return F.Name
		end
	end
end
function UsedualFlock()
	equiptool(NameWeapon(Settings["Select Weapon"] or "Melee"))
end
function FarmMastery(V)
	if not V or not V:FindFirstChild("Humanoid") or not V:FindFirstChild("HumanoidRootPart") then
		return
	end
	getgenv().AimPos = V.HumanoidRootPart.CFrame
	if not Settings["Farm Mastery"] then
		UsedualFlock()
		return
	end
	if V.Humanoid.Health / V.Humanoid.MaxHealth > (Settings["Health %"] or 100) / 100 then
		UsedualFlock()
		return
	end
	local C = Settings["Select Method Farm Mastery"]
	local J, F = NameWeapon(C), NameWeapon(C, true)
	if not J or not F then
		return
	end
	if C == "Gun" and (t.Character:FindFirstChild(J)) then
		ShootM1(V)
	end
	equiptool(J)
	if J == "Control-Control" then
		C = workspace._WorldOrigin:FindFirstChild("Globe")
		if not C or t:DistanceFromCharacter(C.Position) > C.AB.CurveSize0 / 1.75 then
			B(J)
			return
		end
	elseif J == "Buddha-Buddha" then
		if not t.Character.HumanoidRootPart:FindFirstChild("Buddha") then
			B(J)
			return
		end
	elseif J == "Diamond-Diamond" then
		if not t.Character:FindFirstChild("DiamondBody") then
			B(J)
			return
		end
	elseif J == "Falcon-Falcon" then
		if not t.Character:FindFirstChild("FalconWings") then
			B(J)
			return
		end
	end
	C = H(F)
	if C then
		V, J = Settings["Skill " .. C .. " " .. F.ToolTip] or 0.5, game:GetService("VirtualInputManager")
		J:SendKeyEvent(true, C, false, game)
		if Settings["Use skill fast dont hold"] then
			task.wait(0.05)
		else
			task.wait(V)
		end
		J:SendKeyEvent(false, C, false, game)
	end
end
getgenv().StackFarm = true
getgenv().StackFarmOther = true
StackFarm = getgenv().StackFarm
StackFarmOther = getgenv().StackFarmOther
function DetectMobAura()
	local V, H = typeof(Settings["Distance Farm Aura"]) ~= "number" and (tonumber(Settings["Distance Farm Aura"]))
		or Settings["Distance Farm Aura"]
		or 300
	for B, C in pairs(game.Workspace.Enemies:GetChildren()) do
		if IsMobAlive(C) then
			B = (
				C.HumanoidRootPart.Position - game:GetService("Players").LocalPlayer.Character.HumanoidRootPart.Position
			).magnitude
			if B < V then
				V, H = B, C.Name
			end
		end
	end
	return H
end
getgenv().StackFarm = true
getgenv().YPosFruit = 20
function CheckCDSkillTransformation(V, H)
	local B, C, J = next, game:GetService("Players").LocalPlayer.PlayerGui.Main.Skills[V.Name]:GetChildren()
	for F, F in B, C, J do
		if F:IsA("Frame") then
			if
				F.Name ~= "Template"
					and not string.find(F.Title.Text, "Transformation")
					and H[F.Name]
					and F.Title.TextColor3 == Color3.new(1, 1, 1)
					and F.Cooldown.Size == UDim2.new(0, 0, 1, -1)
				or F.Cooldown.Size == UDim2.new(1, 0, 1, -1)
			then
				return F, Settings["Skill " .. F.Name .. " " .. V.ToolTip]
			end
		end
	end
end
function AutoAllSkill(V)
	local V, H, B, C, J =
		NameWeapon("Melee", true) or false,
		NameWeapon("Sword", true) or false,
		NameWeapon("Blox Fruit", true) or false,
		NameWeapon("Gun", true) or false,
		game:GetService("Players").LocalPlayer.PlayerGui.Main.Skills
	if V and not J:FindFirstChild(V.Name) then
		equiptool(V.Name)
		return
	end
	if H and not J:FindFirstChild(H.Name) then
		equiptool(H.Name)
		return
	end
	if B and not J:FindFirstChild(B.Name) then
		equiptool(B.Name)
		return
	end
	if C and not J:FindFirstChild(C.Name) then
		equiptool(C.Name)
		return
	end
	J = if V and (CheckCDSkillTransformation(V, Settings["Select Skills " .. V.ToolTip]))
		then (CheckCDSkillTransformation(V, Settings["Select Skills " .. V.ToolTip]))
		else if H and (CheckCDSkillTransformation(H, Settings["Select Skills " .. H.ToolTip]))
			then (CheckCDSkillTransformation(H, Settings["Select Skills " .. H.ToolTip]))
			else if C and (CheckCDSkillTransformation(C, Settings["Select Skills " .. C.ToolTip]))
				then (CheckCDSkillTransformation(C, Settings["Select Skills " .. C.ToolTip]))
				else if B and (CheckCDSkillTransformation(B, Settings["Select Skills " .. B.ToolTip]))
					then (CheckCDSkillTransformation(B, Settings["Select Skills " .. B.ToolTip]))
					else nil
	if J then
		B = J.Parent.Name
		equiptool(B)
		if t.Character:FindFirstChild(B) then
			game:GetService("VirtualInputManager"):SendKeyEvent(true, J.Name, false, game)
			if Settings["Use skill fast dont hold"] then
				task.wait(0.05)
			else
				task.wait(tonumber(holdskill))
			end
			game:GetService("VirtualInputManager"):SendKeyEvent(false, J.Name, false, game)
		end
	end
end
local V, H =
	require(game:GetService("ReplicatedStorage"):WaitForChild("ItemReplicationService")),
	require(game:GetService("ReplicatedStorage"):WaitForChild("ItemConfig"))
local function B()
	local C, J = {}, require(game:GetService("ReplicatedStorage"):WaitForChild("ItemReplicationService")).KEYS
	for F, F in V:GetItems(J.QUANTITY) do
		if F.Value and F.Value > 0 then
			local q, c = pcall(function()
				return H.match(F.ItemId):unwrap()
			end)
			if q and c and c.Display then
				local H, q = c.Display.Category, c.Index and c.Index.StorageKey
				local D, r =
					if H == "Blox Fruit"
						then q or c.Display.Name or "ItemId_" .. F.ItemId
						else c.Display.Name or q or "ItemId_" .. F.ItemId,
					V:ReadItem(J.MASTERY, F.ItemId, F.NetworkedUID) or 0
				table.insert(
					C,
					{ Name = D, Type = H, Count = F.Value, Mastery = r, ItemId = F.ItemId, UID = F.NetworkedUID }
				)
			end
		end
	end
	return C
end
do
	local V
	local H = 0
	function CheckItemInventory(C)
		if not V or tick() - H > 1 then
			V = {}
			for J, J in B() do
				V[J.Name] = true
			end
			H = tick()
		end
		return V[C] == true
	end
end
function DetectModelDestroyTyrant()
	local V, H, C =
		next,
		(workspace.Map:FindFirstChild("TikiOutpost") and (workspace.Map.TikiOutpost.IslandModel:FindFirstChild(
			"EagleBossArena",
			true
		))):GetChildren()
	for J, J in V, H, C do
		if J.Name == "Tree" and not J:GetAttribute("AlreadyDestroyedClient") then
			return J
		end
	end
end
(function()
	local V = "ABCDEFGHIJKLMNOPQRSTUVWXYZabcdefghijklmnopqrstuvwxyz0123456789+/"
	return {
		encode = function(H)
			return (H:gsub(".", function(C)
				local J, F = C:byte(), ""
				for C = 8, 1, -1 do
					F ..= J % 2 ^ C - J % 2 ^ (C - 1) > 0 and "1" or "0"
				end
				return F
			end) .. "0000"):gsub("%d%d%d?%d?%d?%d?", function(C)
				if #C < 6 then
					return ""
				end
				local J = 0
				for F = 1, 6, 1 do
					J += C:sub(F, F) == "1" and 2 ^ (6 - F) or 0
				end
				return V:sub(J + 1, J + 1)
			end) .. ({ "", "==", "=" })[#H % 3 + 1]
		end,
		decode = function(H)
			return string
				.gsub(H, "[^" .. V .. "=]", "")
				:gsub(".", function(H)
					if H == "=" then
						return ""
					end
					local C, J = V:find(H) - 1, ""
					for V = 6, 1, -1 do
						J ..= C % 2 ^ V - C % 2 ^ (V - 1) > 0 and "1" or "0"
					end
					return J
				end)
				:gsub("%d%d%d?%d?%d?%d?%d?%d?", function(V)
					if #V ~= 8 then
						return ""
					end
					local H = 0
					for C = 1, 8, 1 do
						H += V:sub(C, C) == "1" and 2 ^ (8 - C) or 0
					end
					return string.char(H)
				end)
		end,
	}
end)()
local V = "https://raw.banana-hub.xyz/api"
local function H(C, J)
	local J
	local F, F = pcall(function()
		J =
			ExploitReq({ Url = ("%s/data/recent?name=%s&limit=%s"):format(V, C, 100):gsub(" ", "%%20"), Method = "GET" })
	end)
	if F then
		return false
	end
	return J.Body
end
local V
function SpecialHop(C)
	if getgenv().Key and #getgenv().Key == 32 then
		return
	end
	if V and tick() - V < 5 then
		return
	end
	local J, F = {}, H(C, 700)
	if not F then
		return
	end
	Servers = game:GetService("HttpService"):JSONDecode(F)
	for H, q in next, Servers.data, nil do
		if q and q.name == C then
			table.insert(J, H)
		end
	end
	V = tick()
	if #J > 0 then
		F = {}
		for V, V in next, Servers.data, nil do
			if V and V.name == C then
				local H, C, J, q, q = V.jobid, V.Players, V.placeid, f()
				H = if string.find(H, "BananaCat") then (q(H)) else H
				if
					H
					and H ~= game.JobId
					and not table.find(F, H)
					and not CheckIsplayingRaid()
					and not Settings[H]
					and (C and C < game.Players.MaxPlayers or not V.Players)
					and (J and game.PlaceId == J or not J)
				then
					table.insert(F, H)
					game:GetService("ReplicatedStorage").__ServerBrowser:InvokeServer("teleport", tostring(H))
					SaveSettings(tostring(H), true)
					getgenv().limit_type("clearAll")
				end
			end
		end
	end
end
function FarmMethod()
	local f, V, H = Settings["Select Method Farm"]
	local C, J = 9999, 2
	if f == "Farm Katakuri" then
		C, V, H = 2275, y, "CakeQuest2"
	elseif f == "Farm Bones" then
		C, V, H = 2050, e, "HauntedQuest2"
	elseif f == "Farm Tyrant of the Skies" then
		C, V, H = 2575, Y, "TikiQuest3"
	else
		V = if f == "Aura Farm" and (DetectMobAura()) then { DetectMobAura() } else V
	end
	if Settings["Farm Material"] then
		V = NameMaterials[Settings["Select Material"]]
		if not NameWorldMaterials[Settings["Select Material"]][game.PlaceId] then
			f = NameWorldMaterials[Settings["Select Material"]][getgenv().CheckPlaceId2]
				or NameWorldMaterials[Settings["Select Material"]][getgenv().CheckPlaceId3]
				or NameWorldMaterials[Settings["Select Material"]][getgenv().CheckPlaceId]
			game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer(f)
			return
		end
	end
	f = V or (GetNameDoubleQuest()) or ""
	if not t.PlayerGui.Main:FindFirstChild("Quest").Visible and typeof(f) == "string" then
		TakeQuestLevel()
	else
		if
			Settings["Auto Quest [Katakuri/Bone/Tyrant]"]
			and t.Data.Level.Value >= C
			and not t.PlayerGui.Main:FindFirstChild("Quest").Visible
		then
			QuestBoneAndkatakuri(H, J)
			return
		end
		if not Settings["Farm Material"] and Settings["Select Method Farm"] == "Farm Tyrant of the Skies" then
			if CheckNameBoss("Tyrant of the Skies") then
				V = CheckNameBoss("Tyrant of the Skies")
				repeat
					task.wait()
					sizepart(V)
					if
						game:GetService("Players").LocalPlayer.PlayerGui.TransformationHUD.ImageLabel.Visible
						and (Settings["Auto Finish Train Quest"] or Settings["Auto Finish Train Draco Quest"])
					then
						toTarget(V.HumanoidRootPart.CFrame * CFrame.new(7, 20, 0))
					elseif Settings["Select Weapon"] == "Blox Fruit" then
						toTarget(V.HumanoidRootPart.CFrame * CFrame.new(-7, 20, 0))
					else
						toTarget(V.HumanoidRootPart.CFrame * CFrame.new(7, 20, 0))
					end
					UsedualFlock()
					ClickM1(V)
				until not IsMobAlive(V) or not Settings["Start Farm"] or not StackFarm
				return
			else
				local V = workspace:FindFirstChild("Map", true)
					and (workspace.Map:FindFirstChild("TikiOutpost", true))
					and (workspace.Map.TikiOutpost:FindFirstChild("IslandModel", true))
				if V then
					local Y, H, C, J =
						V:FindFirstChild("Eye1", true),
						V:FindFirstChild("Eye2", true),
						V:FindFirstChild("Eye3", true),
						V:FindFirstChild("Eye4", true)
					if
						Y
						and H
						and C
						and J
						and Y.Transparency == 0
						and H.Transparency == 0
						and C.Transparency == 0
						and J.Transparency == 0
					then
						local V = DetectModelDestroyTyrant()
						if V then
							if t:DistanceFromCharacter(V.WorldPivot.Position) > 10 then
								toTarget(V.WorldPivot)
							elseif CheckItemInventory("Skull Guitar") then
								if not NameWeapon("Gun") or NameWeapon("Gun") ~= "Skull Guitar" then
									game:GetService("ReplicatedStorage").Remotes.CommF_
										:InvokeServer(unpack({ [1] = "LoadItem", [2] = "Skull Guitar" }))
								else
									equiptool(NameWeapon("Gun"))
									getgenv().SpamGunSkullGuitar(V.WorldPivot)
								end
							else
								getgenv().AimPos = V.WorldPivot
								AutoAllSkill()
							end
						end
						return
					end
				end
			end
		end
		if
			not Settings["Farm Material"]
			and Settings["Select Method Farm"] == "Farm Katakuri"
			and not Settings["Ignore Attack Katakuri"]
		then
			if CheckNameBoss("Cake Prince") then
				local V = CheckNameBoss("Cake Prince")
				repeat
					task.wait()
					sizepart(V)
					if
						game:GetService("Players").LocalPlayer.PlayerGui.TransformationHUD.ImageLabel.Visible
						and (Settings["Auto Finish Train Quest"] or Settings["Auto Finish Train Draco Quest"])
					then
						toTarget(V.HumanoidRootPart.CFrame * CFrame.new(7, 20, 0))
					elseif Settings["Select Weapon"] == "Blox Fruit" then
						toTarget(V.HumanoidRootPart.CFrame * CFrame.new(-7, 20, 0))
					else
						toTarget(V.HumanoidRootPart.CFrame * CFrame.new(7, 20, 0))
					end
					UsedualFlock()
					ClickM1(V)
				until not IsMobAlive(V) or not Settings["Start Farm"] or not StackFarm
				return
			else
				spawn(function()
					if Settings["Hop Find Katakuri"] then
						SpecialHop("Cake Prince")
					end
				end)
			end
		end
		local V = DetectMob(f)
		if not V then
			if typeof(f) == "table" then
				if #N >= #f then
					N = {}
					return
				end
				local Y = DetectNameTablePart(f)
				local H = DetectPartSpawnMob(Y)
				if H then
					table.insert(N, Y)
					repeat
						task.wait()
						toTarget(H.CFrame * CFrame.new(0, 60, 0))
					until (H.Position - t.Character.HumanoidRootPart.Position).Magnitude <= 100
						or (DetectMob(f))
						or not Settings["Start Farm"]
						or not StackFarm
					wait(1)
				end
			else
				local Y = DetectPartSpawnMob(f, true)
				if Y then
					Instance.new("IntValue", Y).Name = "Ignored"
					repeat
						task.wait()
						toTarget(Y.CFrame * CFrame.new(0, 60, 0))
					until (Y.Position - t.Character.HumanoidRootPart.Position).Magnitude <= 100
						or (DetectMob(f))
						or not Settings["Start Farm"]
						or not StackFarm
					wait(1)
				else
					DeleteIgnoredMobSpawn()
				end
			end
		else
			repeat
				task.wait()
				sizepart(V)
				BringMob(V)
				FarmMastery(V)
				ClickM1(V)
				if
					game:GetService("Players").LocalPlayer.PlayerGui.TransformationHUD.ImageLabel.Visible
					and (Settings["Auto Finish Train Quest"] or Settings["Auto Finish Train Draco Quest"])
				then
					toTarget(V.HumanoidRootPart.CFrame * CFrame.new(7, 20, 0))
				elseif Settings["Select Weapon"] == "Blox Fruit" then
					toTarget(V.HumanoidRootPart.CFrame * CFrame.new(-7, getgenv().YPosFruit, 0))
				else
					toTarget(V.HumanoidRootPart.CFrame * CFrame.new(7, 20, 0))
				end
			until not IsMobAlive(V) or not Settings["Start Farm"] or not StackFarm
			if getgenv().QuestTrainer and getgenv().QuestTrainer.CountKillMob then
				getgenv().QuestTrainer.CountKillMob = getgenv().QuestTrainer.CountKillMob + 1
			end
		end
	end
end
spawn(function()
	while task.wait() do
		local f, f = pcall(function()
			if Settings["Start Farm"] and StackFarm then
				FarmMethod()
			end
		end)
		if f then
			print(f)
		end
	end
end)
stackFarmMain = Main.CreatePage({ Page_Name = "Stack Farming", Page_Title = "Stack Farming" })
AutoWorldSection = stackFarmMain.CreateSection("Auto World")
AutoWorldSection.CreateToggle(
	{ Title = "Auto New World", Desc = nil, Default = Settings["Auto New World"] or false },
	function(f)
		SaveSettings("Auto New World", f)
	end
)
AutoWorldSection.CreateToggle(
	{ Title = "Auto Third World", Desc = nil, Default = Settings["Auto Third World"] or false },
	function(f)
		SaveSettings("Auto Third World", f)
	end
)
getgenv().GetTime = nil
NotiGetTime = true
function timeToSeconds(f)
	local V, Y, H = f:match("^(%d+):(%d+):(%d+)$")
	if not V then
		Y, H = f:match("^(%d+):(%d+)$")
		V = 0
	end
	return tonumber(V) * 3600 + tonumber(Y) * 60 + tonumber(H)
end
function secondsToTime(f)
	local V, Y, H = math.floor(f / 3600), math.floor(f % 3600 / 60), f % 60
	return string.format("%d:%02d:%02d", V, Y, H)
end
function DetectPresent()
	for f, f in t.Backpack:GetChildren() do
		if string.find(f.Name, "Holiday Gift") then
			return f
		end
	end
	for f, f in t.Character:GetChildren() do
		if string.find(f.Name, "Holiday Gift") then
			return f
		end
	end
end
function DetectPresentStore()
	for f, f in t.Backpack:GetChildren() do
		if string.find(f.Name, "Holiday Gift") and not f:FindFirstChild("Ignored") then
			return f
		end
	end
	for f, f in t.Character:GetChildren() do
		if string.find(f.Name, "Holiday Gift") and not f:FindFirstChild("Ignored") then
			return f
		end
	end
end
function GetCountDownTime()
	if not getgenv().GetTime and not game.workspace:FindFirstChild("Countdown") then
		return "Go Get Time"
	end
	if workspace:FindFirstChild("Countdown") and (workspace.Countdown.SurfaceGui.TextLabel.Text:find("START")) then
		return 0
	end
	local f = workspace:FindFirstChild("Countdown") and workspace.Countdown.SurfaceGui.TextLabel.Text
		or (secondsToTime(getgenv().GetTime))
	if tonumber(f:split(":")[1]) == 0 then
		return tonumber(f:split(":")[2])
	else
		return 55
	end
end
function getGift()
	if not workspace._WorldOrigin:FindFirstChild("Present") then
		return
	end
	for f, f in pairs(workspace._WorldOrigin:GetChildren()) do
		if
			f.Name == "Present"
			and (f:FindFirstChild("Highlight"))
			and (f:FindFirstChild("Box"))
			and (f.Box:FindFirstChild("ProximityPrompt"))
		then
			return f
		end
	end
end
StackDevilFruitSection = stackFarmMain.CreateSection("Devil Fruit")
StackDevilFruitSection.CreateToggle(
	{
		Title = "Collect Chest When Server Spawn\10God's Chalice or Fist of Darkness",
		Desc = nil,
		Default = Settings["Collect Chest When Server Spawn God's Chalice or Fist of Darkness"] or false,
	},
	function(f)
		SaveSettings("Collect Chest When Server Spawn God's Chalice or Fist of Darkness", f)
	end
)
StackDevilFruitSection.CreateToggle(
	{ Title = "Teleport To Fruit", Desc = nil, Default = Settings["Teleport To Fruit"] or false },
	function(f)
		SaveSettings("Teleport To Fruit", f)
	end
)
StackDevilFruitSection.CreateToggle(
	{
		Title = "Teleport To Fruit [ Hop Server ]",
		Desc = nil,
		Default = Settings["Teleport To Fruit [ Hop Server ]"] or false,
	},
	function(f)
		SaveSettings("Teleport To Fruit [ Hop Server ]", f)
	end
)
EventGameSection = stackFarmMain.CreateSection("Event Game")
EventGameSection.CreateToggle(
	{ Title = "Auto Factory", Desc = nil, Default = Settings["Auto Factory"] or false },
	function(f)
		SaveSettings("Auto Factory", f)
	end
)
EventGameSection.CreateToggle(
	{ Title = "Auto Pirate Raid", Desc = nil, Default = Settings["Auto Pirate Raid"] or false },
	function(f)
		SaveSettings("Auto Pirate Raid", f)
	end
)
BossRipIndraSection = stackFarmMain.CreateSection("Boss Rip Indra")
BossRipIndraSection.CreateToggle(
	{ Title = "Auto Elite Hunter", Desc = nil, Default = Settings["Auto Elite Hunter"] or false },
	function(f)
		SaveSettings("Auto Elite Hunter", f)
	end
)
BossRipIndraSection.CreateToggle(
	{
		Title = 'Hop Server Elite Hunter"',
		Desc = "Hop if u have God chalice and teleport in safezone",
		Default = Settings["Hop Server Elite Hunter"] or false,
	},
	function(f)
		SaveSettings("Hop Server Elite Hunter", f)
	end
)
BossRipIndraSection.CreateToggle(
	{ Title = "Auto Touch Pad Haki", Desc = nil, Default = Settings["Auto Touch Pad Haki"] or false },
	function(f)
		SaveSettings("Auto Touch Pad Haki", f)
	end
)
BossRipIndraSection.CreateToggle(
	{ Title = "Auto Summon Rip Indra", Desc = nil, Default = Settings["Auto Summon Rip Indra"] or false },
	function(f)
		SaveSettings("Auto Summon Rip Indra", f)
	end
)
BossRipIndraSection.CreateToggle(
	{ Title = "Attack Rip Indra", Desc = nil, Default = Settings["Attack Rip Indra"] or false },
	function(f)
		SaveSettings("Attack Rip Indra", f)
	end
)
BossSoulReaperSection = stackFarmMain.CreateSection("Boss Soul Reaper")
BossSoulReaperSection.CreateToggle(
	{ Title = "Attack Soul Reaper", Desc = nil, Default = Settings["Attack Soul Reaper"] or false },
	function(f)
		SaveSettings("Attack Soul Reaper", f)
	end
)
BossSoulReaperSection.CreateToggle(
	{ Title = "Summon Soul Reaper", Desc = nil, Default = Settings["Summon Soul Reaper"] or false },
	function(f)
		if f and not Settings["Attack Soul Reaper"] then
			A.CreateNoti({ Title = "Banana Cat Hub", Desc = "Turn On Attack Soul Reaper Plz", ShowTime = 5 })
		end
		SaveSettings("Summon Soul Reaper", f)
	end
)
BossDoughKingSection = stackFarmMain.CreateSection("Boss Dough King")
BossDoughKingSection.CreateToggle(
	{ Title = "Attack Dough King", Desc = nil, Default = Settings["Attack Dough King"] or false },
	function(f)
		SaveSettings("Attack Dough King", f)
	end
)
BossDoughKingSection.CreateToggle(
	{ Title = "Summon Dough King", Desc = nil, Default = Settings["Summon Dough King"] or false },
	function(f)
		if f and not Settings["Attack Dough King"] then
			A.CreateNoti({ Title = "Banana Cat Hub", Desc = "Turn On Attack Dough King Plz", ShowTime = 5 })
		end
		if f then
			spawn(function()
				while Settings["Summon Dough King"] and (task.wait()) do
					if DetectItemPlr("Sweet Chalice") then
						game.ReplicatedStorage.Remotes.CommF_:InvokeServer("CakePrinceSpawner")
					end
				end
			end)
		end
		SaveSettings("Summon Dough King", f)
	end
)
BossDoughKingSection.CreateToggle(
	{ Title = "Hop Find Dough King", Desc = nil, Default = Settings["Hop Find Dough King"] or false },
	function(f)
		if f and not Settings["Attack Dough King"] then
			A.CreateNoti({ Title = "Banana Cat Hub", Desc = "Turn On Attack Dough King Plz", ShowTime = 5 })
		end
		SaveSettings("Hop Find Dough King", f)
	end
)
BossDarkbeardSection = stackFarmMain.CreateSection("Boss Darkbeard")
BossDarkbeardSection.CreateToggle(
	{ Title = "Attack Darkbeard", Desc = nil, Default = Settings["Attack Darkbeard"] or false },
	function(f)
		SaveSettings("Attack Darkbeard", f)
	end
)
BossDarkbeardSection.CreateToggle(
	{ Title = "Summon Darkbeard", Desc = nil, Default = Settings["Summon Darkbeard"] or false },
	function(f)
		if f and not Settings["Attack Darkbeard"] then
			A.CreateNoti({ Title = "Banana Cat Hub", Desc = "Turn On Attack Darkbeard Plz", ShowTime = 5 })
		end
		SaveSettings("Summon Darkbeard", f)
	end
)
BossDarkbeardSection.CreateToggle(
	{ Title = "Hop Find Darkbeard", Desc = nil, Default = Settings["Hop Find Darkbeard"] or false },
	function(f)
		if f and not Settings["Attack Darkbeard"] then
			A.CreateNoti({ Title = "Banana Cat Hub", Desc = "Turn On Attack Darkbeard Plz", ShowTime = 5 })
		end
		SaveSettings("Hop Find Darkbeard", f)
	end
)
function GetPathFruit()
	local f, V, Y = next, game.Workspace:GetChildren()
	for H, H in f, V, Y do
		if (H:IsA("Tool") or (H:IsA("Model"))) and (string.find(H.Name, "Fruit")) and (H:FindFirstChild("Handle")) then
			return H
		end
	end
end
function GetPirateRaid(f)
	for V, V in ipairs((if f then game.ReplicatedStorage else game.workspace.Enemies):GetChildren()) do
		if
			V:IsA("Model")
			and V.Name ~= "Oni2"
			and not string.find(V.Name, "Boss")
			and not string.find(V.Name, "Friend")
			and not string.find(V.Name, "Wraith")
			and V.Name ~= "rip_indra True Form"
			and (IsMobAlive(V))
			and (V.HumanoidRootPart.Position - Vector3.new(-5543, 313, -2964)).magnitude < 1000
		then
			return V
		end
	end
end
function DetectButtons()
	local f, V, Y = next, game:GetService("Workspace").Map["Boat Castle"].Summoner.Circle:GetChildren()
	for H, H in f, V, Y do
		if H:IsA("Part") and H.Part.BrickColor.Name ~= "Lime green" then
			return H
		end
	end
end
local f = { "Winter Sky", "Pure Red", "Snow White" }
function IsMisisngLegHaki(V)
	V = V and {}
	local Y
	for H, H in pairs(CommF:InvokeServer("getColors")) do
		if table.find(f, H.HiddenName) and not H.Unlocked then
			if V then
				table.insert(V, H.HiddenName)
			else
				Y = if not Y then H.HiddenName else Y .. ", " .. H.HiddenName
			end
		end
	end
	if V then
		return V
	end
	return Y
end
function TouchPadHaki()
	local f = DetectButtons()
	if f then
		if f.BrickColor.Name == "Hot pink" then
			game:GetService("ReplicatedStorage").Modules.Net
				:FindFirstChild("RF/FruitCustomizerRF")
				:InvokeServer(unpack({ [1] = { StorageName = "Winter Sky", Type = "AuraSkin", Context = "Equip" } }))
			toTarget(f.CFrame)
			wait(2)
		elseif f.BrickColor.Name == "Really red" then
			game:GetService("ReplicatedStorage").Modules.Net
				:FindFirstChild("RF/FruitCustomizerRF")
				:InvokeServer(unpack({ [1] = { StorageName = "Pure Red", Type = "AuraSkin", Context = "Equip" } }))
			game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("activateColor", "Pure Red")
			toTarget(f.CFrame)
			wait(2)
		elseif f.BrickColor.Name == "Oyster" then
			game:GetService("ReplicatedStorage").Modules.Net
				:FindFirstChild("RF/FruitCustomizerRF")
				:InvokeServer(unpack({ [1] = { StorageName = "Snow White", Type = "AuraSkin", Context = "Equip" } }))
			game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("activateColor", "Snow White")
			toTarget(f.CFrame)
			wait(2)
		end
	end
end
getgenv().CheckCountItem = function(f, V)
	local Y, H, C = next, B()
	for J, J in Y, H, C do
		if J.Name == f and J.Count and J.Count >= V then
			return true
		end
	end
	return false
end
function getbackpack()
	mybackpack = {}
	local f, V, Y = next, game.Players.LocalPlayer.Backpack:GetChildren()
	for H, H in f, V, Y do
		if H:IsA("Tool") and (table.find(whitelistedfruit, H.Name)) then
			table.insert(mybackpack, H.Name)
		end
	end
	f, Y, V = next, game.Players.LocalPlayer.Character:GetChildren()
	for H, H in f, Y, V do
		if H:IsA("Tool") and (table.find(whitelistedfruit, H.Name)) then
			table.insert(mybackpack, H.Name)
		end
	end
	return mybackpack
end
function CheckFruitplr()
	local f
	for V, V in pairs(t.Backpack:GetChildren()) do
		f = if string.find(V.Name, "Fruit") then V.Name else f
	end
	for V, V in pairs(t.Character:GetChildren()) do
		f = if string.find(V.Name, "Fruit") then V.Name else f
	end
	return f
end
function TakeFruitInventory(f)
	local V, Y, H = next, B()
	local C, J = 1 / 0
	for F, F in V, Y, H do
		if F.Type == "Blox Fruit" then
			if not f then
				for f, V in pairs(getgenv().tablefruitausea3) do
					if F.Name == f then
						if tonumber(V) < tonumber(C) then
							C, J = V, f
						end
					end
				end
			elseif not getgenv().tablefruitausea3[F.Name] then
				return F.Name
			end
		end
	end
	return J
end
cframethangdaubuoiredhead = CFrame.new(
	-1926.78772,
	12.1678171,
	1739.80884,
	0.956294656,
	-0.0,
	-0.292404652,
	0,
	1,
	-0.0,
	0.292404652,
	0,
	0.956294656
)
function StopThirdSea()
	if game.PlaceId == getgenv().CheckPlaceId2 and t.Data.Level.Value >= 1500 then
		if game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("BartiloQuestProgress", "Bartilo") == 3 then
			if game.ReplicatedStorage.Remotes.CommF_:InvokeServer("TalkTrevor", "1") ~= 0 then
				if #getbackpack() >= 1 then
					return true
				elseif not CheckFruitplr() and (TakeFruitInventory()) then
					StopStoreFruit = true
					game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("LoadFruit", TakeFruitInventory())
				end
			elseif not game.ReplicatedStorage.Remotes.CommF_:InvokeServer("ZQuestProgress", "Check") then
				if CheckNameBoss("Don Swan") then
					return true
				end
			elseif game.ReplicatedStorage.Remotes.CommF_:InvokeServer("ZQuestProgress", "Check") == 0 then
				return true
			end
		else
			return true
		end
	end
end
function checkplatebarito()
	return if game:GetService("Workspace").Map.Dressrosa.BartiloPlates.Plate1.BrickColor
			== BrickColor.new("Sand yellow")
		then "Plate1"
		else if game:GetService("Workspace").Map.Dressrosa.BartiloPlates.Plate2.BrickColor
				== BrickColor.new("Sand yellow")
			then "Plate2"
			else if game:GetService("Workspace").Map.Dressrosa.BartiloPlates.Plate3.BrickColor
					== BrickColor.new("Sand yellow")
				then "Plate3"
				else if game:GetService("Workspace").Map.Dressrosa.BartiloPlates.Plate4.BrickColor
						== BrickColor.new("Sand yellow")
					then "Plate4"
					else if game:GetService("Workspace").Map.Dressrosa.BartiloPlates.Plate5.BrickColor
							== BrickColor.new("Sand yellow")
						then "Plate5"
						else if game:GetService("Workspace").Map.Dressrosa.BartiloPlates.Plate6.BrickColor
								== BrickColor.new("Sand yellow")
							then "Plate6"
							else if game:GetService("Workspace").Map.Dressrosa.BartiloPlates.Plate7.BrickColor
									== BrickColor.new("Sand yellow")
								then "Plate7"
								else if game:GetService("Workspace").Map.Dressrosa.BartiloPlates.Plate8.BrickColor
										== BrickColor.new("Sand yellow")
									then "Plate8"
									else nil
end
function AutoQuestBarito()
	if game.ReplicatedStorage.Remotes.CommF_:InvokeServer("BartiloQuestProgress", "Bartilo") == 0 then
		if
			string.find(game.Players.LocalPlayer.PlayerGui.Main.Quest.Container.QuestTitle.Title.Text, "Swan Pirates")
			and (string.find(game.Players.LocalPlayer.PlayerGui.Main.Quest.Container.QuestTitle.Title.Text, "50"))
			and game.Players.LocalPlayer.PlayerGui.Main.Quest.Visible
		then
			local f, V = "Swan Pirate", DetectMob("Swan Pirate")
			if not V then
				if typeof(f) == "table" then
					if #N >= 11 then
						N = {}
						return
					end
					local Y = DetectPartSpawnMob(DetectNameTablePart(f))
					if Y then
						table.insert(N, DetectNameTablePart(f))
						repeat
							wait()
							toTarget(Y.CFrame * CFrame.new(0, 60, 0))
						until (Y.Position - t.Character.HumanoidRootPart.Position).Magnitude <= 100 or (DetectMob(f))
						wait(1)
					end
				else
					local Y = DetectPartSpawnMob(f, true)
					if Y then
						Instance.new("IntValue", Y).Name = "Ignored"
						repeat
							wait()
							toTarget(Y.CFrame * CFrame.new(0, 60, 0))
						until (Y.Position - t.Character.HumanoidRootPart.Position).Magnitude <= 100 or (DetectMob(f))
						wait(1)
					else
						DeleteIgnoredMobSpawn()
					end
				end
			else
				repeat
					task.wait()
					sizepart(V)
					BringMob(V)
					UsedualFlock()
					ClickM1(V)
					if Settings["Select Weapon"] == "Blox Fruit" then
						toTarget(V.HumanoidRootPart.CFrame * CFrame.new(-7, 20, 0))
					else
						toTarget(V.HumanoidRootPart.CFrame * CFrame.new(7, 20, 0))
					end
				until not IsMobAlive(V)
			end
		elseif
			(t.Character.HumanoidRootPart.Position - CFrame.new(-456.28952, 73.0200958, 299.895966).Position).Magnitude
			> 8
		then
			toTarget(CFrame.new(-456.28952, 73.0200958, 299.895966))
		else
			game:GetService("ReplicatedStorage").Remotes.CommF_
				:InvokeServer(unpack({ [1] = "StartQuest", [2] = "BartiloQuest", [3] = 1 }))
		end
	elseif game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("BartiloQuestProgress", "Bartilo") == 1 then
		local f = CheckNameBoss("Jeremy")
		if f then
			repeat
				task.wait()
				sizepart(f)
				UsedualFlock()
				ClickM1(f)
				if Settings["Select Weapon"] == "Blox Fruit" then
					toTarget(f.HumanoidRootPart.CFrame * CFrame.new(-7, 20, 0))
				else
					toTarget(f.HumanoidRootPart.CFrame * CFrame.new(7, 20, 0))
				end
			until not IsMobAlive(f)
		end
	elseif game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("BartiloQuestProgress", "Bartilo") == 2 then
		repeat
			task.wait()
			if (t.Character.HumanoidRootPart.Position - Vector3.new(-1835.65, 10.4325, 1679.75)).Magnitude > 100 then
				toTarget(CFrame.new(-1835.65, 10.4325, 1679.75))
			else
				t.Character.HumanoidRootPart.CFrame =
					game:GetService("Workspace").Map.Dressrosa.BartiloPlates[checkplatebarito()].CFrame
				task.wait()
				firetouchinterest(
					game:GetService("Workspace").Map.Dressrosa.BartiloPlates[checkplatebarito()],
					game.Players.LocalPlayer.Character.HumanoidRootPart,
					0
				)
				firetouchinterest(
					game:GetService("Workspace").Map.Dressrosa.BartiloPlates[checkplatebarito()],
					game.Players.LocalPlayer.Character.HumanoidRootPart,
					1
				)
			end
		until game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("BartiloQuestProgress", "Bartilo") == 3
	end
end
function SeaThird()
	if
		game.ReplicatedStorage.Remotes.CommF_:InvokeServer("TalkTrevor", "1") == 0
		and game.ReplicatedStorage.Remotes.CommF_:InvokeServer("ZQuestProgress", "Check") == 1
		and game.ReplicatedStorage.Remotes.CommF_:InvokeServer("ZQuestProgress", "Zou") == 0
	then
		game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("TravelZou")
	end
	if game.PlaceId == getgenv().CheckPlaceId2 and t.Data.Level.Value >= 1500 then
		if game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("BartiloQuestProgress", "Bartilo") == 3 then
			if game.ReplicatedStorage.Remotes.CommF_:InvokeServer("TalkTrevor", "1") ~= 0 then
				if #getbackpack() >= 1 then
					toTarget(CFrame.new(-339.79840087891, 331.86065673828, 643.83178710938))
					if
						(
							Vector3.new(-339.79840087891, 331.86065673828, 643.83178710938)
							- t.Character.HumanoidRootPart.Position
						).Magnitude <= 5
					then
						if game.ReplicatedStorage.Remotes.CommF_:InvokeServer("TalkTrevor", "1") ~= 1 then
							local f, V, Y = next, getbackpack()
							for H, H in f, V, Y do
								t.Character.Humanoid:EquipTool(game.Players.LocalPlayer.Backpack:FindFirstChild(H))
							end
							game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("TalkTrevor", "1")
							game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("TalkTrevor", "2")
							game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("TalkTrevor", "3")
						end
					end
				elseif not CheckFruitplr() and (TakeFruitInventory()) then
					game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("LoadFruit", TakeFruitInventory())
				end
			elseif
				game.ReplicatedStorage.Remotes.CommF_:InvokeServer("TalkTrevor", "1") == 0
				and game.ReplicatedStorage.Remotes.CommF_:InvokeServer("ZQuestProgress", "Check") == 1
				and game.ReplicatedStorage.Remotes.CommF_:InvokeServer("ZQuestProgress", "Zou") == 0
			then
				game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("TravelZou")
			elseif not game.ReplicatedStorage.Remotes.CommF_:InvokeServer("ZQuestProgress", "Check") then
				if CheckNameBoss("Don Swan") then
					local f = CheckNameBoss("Don Swan")
					repeat
						task.wait()
						sizepart(f)
						if Settings["Select Weapon"] == "Blox Fruit" then
							toTarget(f.HumanoidRootPart.CFrame * CFrame.new(-7, 20, 0))
						else
							toTarget(f.HumanoidRootPart.CFrame * CFrame.new(7, 20, 0))
						end
						UsedualFlock()
						ClickM1(f)
					until not f or not f.Parent or f.Humanoid.Health == 0
				end
			elseif game.ReplicatedStorage.Remotes.CommF_:InvokeServer("ZQuestProgress", "Check") == 0 then
				if
					(t.Character.HumanoidRootPart.Position - game:GetService("Workspace").Map.IndraIsland.Part.Position).Magnitude
					> 1000
				then
					toTarget(cframethangdaubuoiredhead)
					if (cframethangdaubuoiredhead.p - t.Character.HumanoidRootPart.Position).Magnitude <= 5 then
						game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("ZQuestProgress", "Begin")
					end
				else
					local f, V, Y = next, workspace.Enemies:GetChildren()
					for H, H in f, V, Y do
						if
							H.Name == "rip_indra"
							and (H:FindFirstChild("HumanoidRootPart"))
							and (H:FindFirstChild("Humanoid"))
							and H.Humanoid.Health > 0
						then
							if
								(H.HumanoidRootPart.Position - t.Character.HumanoidRootPart.Position).Magnitude > 300
							then
								toTarget(H.HumanoidRootPart.CFrame)
							else
								repeat
									task.wait()
									sizepart(H)
									if Settings["Select Weapon"] == "Blox Fruit" then
										toTarget(H.HumanoidRootPart.CFrame * CFrame.new(-7, 20, 0))
									else
										toTarget(H.HumanoidRootPart.CFrame * CFrame.new(7, 20, 0))
									end
									ClickM1(H)
									UsedualFlock()
								until not workspace.Enemies:FindFirstChild("rip_indra")
							end
						end
					end
				end
			end
		else
			AutoQuestBarito()
		end
	end
end
local f = 0
function PathFindChest()
	local V, Y, H = next, game:GetService("Workspace")._WorldOrigin.PlayerSpawns.Pirates:GetChildren()
	for C, C in V, Y, H do
		if C:IsA("Model") and (C:FindFirstChild("Part")) and not C:FindFirstChild("Ignored") then
			return C
		end
	end
end
function GetNearestChest()
	local V, Y, H = next, game:GetService("CollectionService"):GetTagged("_ChestTagged")
	local C, J, F = 1 / 0
	for q, c in V, Y, H do
		if not c:GetAttribute("IsDisabled") and not c:FindFirstChild("Ignored") then
			q = t:DistanceFromCharacter(c.Position)
			if q < C then
				C, J, F = q, i, c
			end
		end
	end
	return F
end
getgenv().DetectRaidCastle = false
getgenv().ValueCollectChestSpawnGod = 0
task.spawn(function()
	while task.wait() do
		local V, V = pcall(function()
			if Settings["Auto New World"] then
				if game.PlaceId == getgenv().CheckPlaceId3 and t.Data.Level.Value >= 700 then
					StackFarm = false
					StackFarmOther = false
					if
						game.ReplicatedStorage.Remotes.CommF_:InvokeServer("DressrosaQuestProgress", "Dressrosa") ~= 0
					then
						if game.Workspace.Map.Ice.Door.CanCollide then
							if not t.Character:FindFirstChild("Key") and not t.Backpack:FindFirstChild("Key") then
								if
									(
										CFrame.new(4852.2895507813, 5.651451587677, 718.53070068359).Position
										- t.Character.HumanoidRootPart.Position
									).magnitude < 5
								then
									game.ReplicatedStorage.Remotes.CommF_:InvokeServer(
										"DressrosaQuestProgress",
										"Detective"
									)
									equiptool("Key")
								else
									toTarget(CFrame.new(4852.2895507813, 5.651451587677, 718.53070068359))
								end
							else
								equiptool("Key")
								if t.Character:FindFirstChild("Key") then
									toTarget(game.Workspace.Map.Ice.Door.CFrame)
								end
							end
						elseif CheckNameBoss("Ice Admiral") then
							local Y = CheckNameBoss("Ice Admiral")
							repeat
								task.wait()
								sizepart(Y)
								if Settings["Select Weapon"] == "Blox Fruit" then
									toTarget(Y.HumanoidRootPart.CFrame * CFrame.new(-7, 20, 0))
								else
									toTarget(Y.HumanoidRootPart.CFrame * CFrame.new(7, 20, 0))
								end
								ClickM1(Y)
								UsedualFlock()
							until not Y or not Y.Parent or Y.Humanoid.Health == 0 or not Settings["Auto New World"]
						end
					else
						game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("TravelDressrosa")
					end
					return
				end
			end
			if
				Settings["Collect Chest When Server Spawn God's Chalice or Fist of Darkness"]
				and getgenv().GoCollectChest
			then
				StackFarm = false
				StackFarmOther = false
				if getgenv().ValueCollectChestSpawnGod >= 10 then
					getgenv().GoCollectChest = false
					getgenv().ValueCollectChestSpawnGod = 0
				end
				local Y = GetNearestChest()
				if Y then
					getgenv().ValueCollectChestSpawnGod = getgenv().ValueCollectChestSpawnGod + 1
					local H
					repeat
						task.wait()
						if
							(game.Players.LocalPlayer.Character.HumanoidRootPart.Position - Y.Position).Magnitude <= 5
						then
							if not H then
								H = (tick())
							elseif tick() - H >= 5 then
								Instance.new("IntValue", Y).Name = "Ignored"
								wait(0.1)
							end
							if not Settings["Use Method Teleport"] then
								game:GetService("VirtualInputManager"):SendKeyEvent(true, "Space", false, game)
								wait()
								game:GetService("VirtualInputManager"):SendKeyEvent(false, "Space", false, game)
							end
							TweenManager.CancelCurrent()
						end
						if Settings["Use Method Teleport"] then
							t.Character.HumanoidRootPart.CFrame = Y.CFrame
							TweenManager.CancelCurrent()
						else
							toTarget(Y.CFrame, true)
						end
					until not Y
						or not Y.Parent
						or not Settings["Collect Chest When Server Spawn God's Chalice or Fist of Darkness"]
						or (Y:GetAttribute("IsDisabled"))
						or (Y:FindFirstChild("Ignored"))
						or not Y:FindFirstChild("TouchInterest")
					return
				else
					local Y = PathFindChest()
					if Y then
						toTarget(Y.Part.CFrame)
						if
							(Y.Part.Position - t.Character.HumanoidRootPart.Position).Magnitude <= 100
							or (GetNearestChest())
						then
							Instance.new("IntValue", Y).Name = "Ignored"
						end
					else
						for Y, Y in pairs(game:GetService("Workspace")._WorldOrigin.PlayerSpawns.Pirates:GetChildren()) do
							if Y:FindFirstChild("Ignored") then
								Y:FindFirstChild("Ignored"):Destroy()
							end
						end
					end
				end
			end
			if game.PlaceId == getgenv().CheckPlaceId2 and Settings["Auto Third World"] then
				if StopThirdSea() then
					StackFarm = false
					StackFarmOther = false
					SeaThird()
					return
				end
			end
			if Settings["Attack Darkbeard"] then
				local Y = CheckNameBoss("Darkbeard")
				if Y then
					StackFarm = false
					StackFarmOther = false
					repeat
						task.wait()
						sizepart(Y)
						if Settings["Select Weapon"] == "Blox Fruit" then
							toTarget(Y.HumanoidRootPart.CFrame * CFrame.new(-7, 20, 0))
						else
							toTarget(Y.HumanoidRootPart.CFrame * CFrame.new(7, 20, 0))
						end
						ClickM1(Y)
						UsedualFlock()
					until not IsMobAlive(Y) or not Settings["Attack Darkbeard"]
					return
				else
					if Settings["Summon Darkbeard"] and (DetectItemPlr("Fist of Darkness")) then
						StackFarm = false
						StackFarmOther = false
						if
							(
								game:GetService("Workspace").Map.DarkbeardArena.Summoner.Detection.Position
								- t.Character.HumanoidRootPart.Position
							).Magnitude <= 5
						then
							equiptool("Fist of Darkness")
							firetouchinterest(
								game.Players.LocalPlayer.Character["Fist of Darkness"].Handle,
								game:GetService("Workspace").Map.DarkbeardArena.Summoner.Detection,
								0
							)
							firetouchinterest(
								game.Players.LocalPlayer.Character["Fist of Darkness"].Handle,
								game:GetService("Workspace").Map.DarkbeardArena.Summoner.Detection,
								1
							)
							firetouchinterest(
								t.Character.HumanoidRootPart,
								game:GetService("Workspace").Map.DarkbeardArena.Summoner.Detection,
								0
							)
							firetouchinterest(
								t.Character.HumanoidRootPart,
								game:GetService("Workspace").Map.DarkbeardArena.Summoner.Detection,
								1
							)
						else
							toTarget(game:GetService("Workspace").Map.DarkbeardArena.Summoner.Detection.CFrame)
						end
						return
					end
					spawn(function()
						if Settings["Hop Find Darkbeard"] then
							SpecialHop("Darkbeard")
						end
					end)
				end
			end
			if Settings["Attack Rip Indra"] then
				local Y = CheckNameBoss("rip_indra True Form")
				if Y then
					StackFarm = false
					StackFarmOther = false
					repeat
						task.wait()
						sizepart(Y)
						if Settings["Select Weapon"] == "Blox Fruit" then
							toTarget(Y.HumanoidRootPart.CFrame * CFrame.new(-7, 20, 0))
						else
							toTarget(Y.HumanoidRootPart.CFrame * CFrame.new(7, 20, 0))
						end
						ClickM1(Y)
						UsedualFlock()
					until not IsMobAlive(Y) or not Settings["Attack Rip Indra"]
					return
				end
			end
			if Settings["Auto Touch Pad Haki"] and Settings["Auto Summon Rip Indra"] then
				if DetectItemPlr("God's Chalice") then
					StackFarm = false
					StackFarmOther = false
					if
						not game:GetService("Workspace").Map:FindFirstChild("Boat Castle")
						or not game:GetService("Workspace").Map["Boat Castle"].Summoner.Circle
							:FindFirstChildOfClass("Part")
					then
						toTarget(CFrame.new(-5500, 314, -2855))
						return
					end
					if DetectButtons() then
						TouchPadHaki()
						return
					elseif not DetectButtons() then
						equiptool("God's Chalice")
						toTarget(game:GetService("Workspace").Map["Boat Castle"].Summoner.Detection.CFrame)
						return
					end
				end
			elseif Settings["Auto Touch Pad Haki"] then
				StackFarm = false
				StackFarmOther = false
				if
					not game:GetService("Workspace").Map:FindFirstChild("Boat Castle")
					or not game:GetService("Workspace").Map["Boat Castle"].Summoner.Circle:FindFirstChildOfClass("Part")
				then
					toTarget(CFrame.new(-5500, 314, -2855))
					return
				end
				if DetectButtons() then
					TouchPadHaki()
				end
				return
			elseif Settings["Auto Summon Rip Indra"] and (DetectItemPlr("God's Chalice")) then
				StackFarm = false
				StackFarmOther = false
				if
					not game:GetService("Workspace").Map:FindFirstChild("Boat Castle")
					or not game:GetService("Workspace").Map["Boat Castle"].Summoner.Circle:FindFirstChildOfClass("Part")
				then
					toTarget(CFrame.new(-5500, 314, -2855))
					return
				end
				equiptool("God's Chalice")
				toTarget(game:GetService("Workspace").Map["Boat Castle"].Summoner.Detection.CFrame)
				return
			end
			if Settings["Attack Soul Reaper"] then
				local Y = CheckNameBoss("Soul Reaper")
				if Y then
					StackFarm = false
					StackFarmOther = false
					repeat
						task.wait()
						sizepart(Y)
						if Settings["Select Weapon"] == "Blox Fruit" then
							toTarget(Y.HumanoidRootPart.CFrame * CFrame.new(-7, 20, 0))
						else
							toTarget(Y.HumanoidRootPart.CFrame * CFrame.new(7, 20, 0))
						end
						ClickM1(Y)
						UsedualFlock()
					until not IsMobAlive(Y) or not Settings["Attack Soul Reaper"]
					return
				else
					StackFarm = false
					StackFarmOther = false
					if Settings["Summon Soul Reaper"] and (DetectItemPlr("Hallow Essence")) then
						if
							not game:GetService("Workspace").Map:FindFirstChild("Haunted Castle")
							or not game:GetService("Workspace").Map["Haunted Castle"].Summoner
								:FindFirstChild("Detection")
						then
							toTarget((CFrame.new(-9513.466796875, 142.09776306152344, 5528.83740234375)))
							return
						end
						if
							(
								t.Character.HumanoidRootPart.Position
								- game:GetService("Workspace").Map["Haunted Castle"].Summoner.Detection.Position
							).Magnitude > 8
						then
							toTarget(game:GetService("Workspace").Map["Haunted Castle"].Summoner.Detection.CFrame)
						else
							equiptool("Hallow Essence", true)
						end
						return
					end
				end
			end
			if Settings["Attack Dough King"] then
				local Y = CheckNameBoss("Dough King")
				if Y then
					StackFarm = false
					StackFarmOther = false
					repeat
						task.wait()
						sizepart(Y)
						if Settings["Select Weapon"] == "Blox Fruit" then
							toTarget(Y.HumanoidRootPart.CFrame * CFrame.new(-7, 20, 0))
						else
							toTarget(Y.HumanoidRootPart.CFrame * CFrame.new(7, 20, 0))
						end
						ClickM1(Y)
						UsedualFlock()
					until not IsMobAlive(Y) or not Settings["Attack Dough King"]
					return
				else
					spawn(function()
						if Settings["Hop Find Dough King"] then
							SpecialHop("Dough King")
						end
					end)
					if Settings["Summon Dough King"] then
						if not DetectItemPlr("Sweet Chalice") then
							if
								game.ReplicatedStorage.Remotes.CommF_:InvokeServer("SweetChaliceNpc")
								== "Where are the items?"
							then
								if not CheckCountItem("Conjured Cocoa", 10) then
									StackFarm = false
									StackFarmOther = false
									if not DetectMob(P) then
										if typeof(P) == "table" then
											if #N >= #P then
												N = {}
												return
											end
											local Y = DetectPartSpawnMob(DetectNameTablePart(P))
											if Y then
												table.insert(N, DetectNameTablePart(P))
												repeat
													wait()
													toTarget(Y.CFrame * CFrame.new(0, 60, 0))
												until (Y.Position - t.Character.HumanoidRootPart.Position).Magnitude
														<= 100
													or (DetectMob(P))
													or not Settings["Attack Dough King"]
												wait(1)
											end
										else
											local Y = DetectPartSpawnMob(P, true)
											if Y then
												Instance.new("IntValue", Y).Name = "Ignored"
												repeat
													wait()
													toTarget(Y.CFrame * CFrame.new(0, 60, 0))
												until (Y.Position - t.Character.HumanoidRootPart.Position).Magnitude
														<= 100
													or (DetectMob(P))
													or not Settings["Attack Dough King"]
												wait(1)
											else
												DeleteIgnoredMobSpawn()
											end
										end
									else
										local Y = DetectMob(P)
										repeat
											task.wait()
											sizepart(Y)
											BringMob(Y)
											UsedualFlock()
											ClickM1(Y)
											if Settings["Select Weapon"] == "Blox Fruit" then
												toTarget(Y.HumanoidRootPart.CFrame * CFrame.new(-7, 20, 0))
											else
												toTarget(Y.HumanoidRootPart.CFrame * CFrame.new(7, 20, 0))
											end
										until not Y
											or not Y.Parent
											or Y.Humanoid.Health == 0
											or not Settings["Attack Dough King"]
									end
								elseif not DetectItemPlr("God's Chalice") then
									local P = DetectEliteHunter()
									if P then
										StackFarm = false
										StackFarmOther = false
										if
											not string.find(
												game.Players.LocalPlayer.PlayerGui.Main.Quest.Container.QuestTitle.Title.Text,
												P.Name
											)
											or not game:GetService("Players").LocalPlayer.PlayerGui.Main.Quest.Visible
										then
											game:GetService("ReplicatedStorage").Remotes.CommF_
												:InvokeServer("AbandonQuest")
											game:GetService("ReplicatedStorage").Remotes.CommF_
												:InvokeServer("EliteHunter")
										else
											repeat
												task.wait()
												sizepart(P)
												if Settings["Select Weapon"] == "Blox Fruit" then
													toTarget(P.HumanoidRootPart.CFrame * CFrame.new(-7, 20, 0))
												else
													toTarget(P.HumanoidRootPart.CFrame * CFrame.new(7, 20, 0))
												end
												ClickM1(P)
												UsedualFlock()
											until not P
												or not P.Parent
												or P.Humanoid.Health == 0
												or not Settings["Attack Dough King"]
										end
										return
									else
										A.CreateNoti({
											Title = "Banana Cat Hub",
											Desc = "Waiting Elite Hunter",
											ShowTime = 5,
										})
										wait(5)
									end
								end
							end
						elseif not DetectMob(y) then
							if typeof(y) == "table" then
								if #N >= #y then
									N = {}
									return
								end
								local P = DetectPartSpawnMob(DetectNameTablePart(y))
								if P then
									table.insert(N, DetectNameTablePart(y))
									repeat
										wait()
										toTarget(P.CFrame * CFrame.new(0, 60, 0))
									until (P.Position - t.Character.HumanoidRootPart.Position).Magnitude <= 100
										or (DetectMob(y))
										or not Settings["Attack Dough King"]
									wait(1)
								end
							else
								local P = DetectPartSpawnMob(y, true)
								if P then
									Instance.new("IntValue", P).Name = "Ignored"
									repeat
										wait()
										toTarget(P.CFrame * CFrame.new(0, 60, 0))
									until (P.Position - t.Character.HumanoidRootPart.Position).Magnitude <= 100
										or (DetectMob(y))
										or not Settings["Attack Dough King"]
									wait(1)
								else
									DeleteIgnoredMobSpawn()
								end
							end
						else
							local P = DetectMob(y)
							repeat
								task.wait()
								sizepart(P)
								BringMob(P)
								UsedualFlock()
								ClickM1(P)
								if Settings["Select Weapon"] == "Blox Fruit" then
									toTarget(P.HumanoidRootPart.CFrame * CFrame.new(-7, 20, 0))
								else
									toTarget(P.HumanoidRootPart.CFrame * CFrame.new(7, 20, 0))
								end
							until not P or not P.Parent or P.Humanoid.Health == 0 or not Settings["Attack Dough King"]
						end
					end
				end
			end
			if Settings["Auto Elite Hunter"] then
				local y = DetectEliteHunter()
				if y then
					StackFarm = false
					StackFarmOther = false
					if
						not string.find(
							game.Players.LocalPlayer.PlayerGui.Main.Quest.Container.QuestTitle.Title.Text,
							y.Name
						) or not game:GetService("Players").LocalPlayer.PlayerGui.Main.Quest.Visible
					then
						game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("AbandonQuest")
						game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("EliteHunter")
					else
						repeat
							task.wait()
							sizepart(y)
							if Settings["Select Weapon"] == "Blox Fruit" then
								toTarget(y.HumanoidRootPart.CFrame * CFrame.new(-7, 20, 0))
							else
								toTarget(y.HumanoidRootPart.CFrame * CFrame.new(7, 20, 0))
							end
							ClickM1(y)
							UsedualFlock()
						until not IsMobAlive(y) or not Settings["Auto Elite Hunter"]
						if getgenv().QuestTrainer and getgenv().QuestTrainer.CountKillMob then
							getgenv().QuestTrainer.CountKillMob = getgenv().QuestTrainer.CountKillMob + 1
						end
					end
					return
				elseif Settings["Hop Server Elite Hunter"] then
					if not DetectItemPlr("God's Chalice") then
						HopServer()
					else
						toTarget(CFrame.new(-12463.8740234375, 374.9144592285156, -7523.77392578125))
					end
				end
			end
			if Settings["Auto Factory"] then
				CoreBoss = CheckNameBoss("Core")
				if CoreBoss then
					StackFarm = false
					StackFarmOther = false
					repeat
						task.wait()
						toTarget(CoreBoss.HumanoidRootPart.CFrame * CFrame.new(0, 20, 0))
						ClickM1(CoreBoss)
						UsedualFlock()
					until not IsMobAlive(CoreBoss) or not Settings["Auto Factory"]
					return
				end
			end
			if Settings["Auto Pirate Raid"] then
				local y = GetPirateRaid() or (GetPirateRaid(true))
				if y then
					getgenv().DetectRaidCastle = true
					StackFarm = false
					StackFarmOther = false
					local P = Settings["Select Weapon"] == "Blox Fruit" and (CFrame.new(-7, 20, 0))
						or (CFrame.new(7, 20, 0))
					repeat
						task.wait()
						UsedualFlock()
						sizepart(y)
						ClickM1(y)
						toTarget(y.HumanoidRootPart.CFrame * P)
					until not IsMobAlive(y) or not Settings["Auto Pirate Raid"]
				elseif getgenv().DetectRaidCastle then
					StackFarm = false
					StackFarmOther = false
					local y, P = os.clock(), false
					repeat
						task.wait()
						P = if GetPirateRaid() or (GetPirateRaid(true)) then true else P
					until os.clock() - y >= 10 or P
					if not P then
						getgenv().DetectRaidCastle = false
					end
				end
			end
			if Settings["Teleport To Fruit"] then
				local y = GetPathFruit()
				if y then
					StackFarm = false
					StackFarmOther = false
					if (y.Handle.Position - t.Character.HumanoidRootPart.Position).Magnitude <= 5 then
						getgenv().noclip = false
						game:GetService("VirtualInputManager"):SendKeyEvent(true, "Space", false, game)
						wait()
						game:GetService("VirtualInputManager"):SendKeyEvent(false, "Space", false, game)
					else
						toTarget(y.Handle.CFrame, true)
					end
					return
				elseif Settings["Teleport To Fruit [ Hop Server ]"] then
					HopServer()
					wait(5)
				end
			end
			if not StackFarm then
				StackFarm = true
			end
			if not StackFarmOther then
				StackFarmOther = true
			end
		end)
		if V then
			print(V)
		end
	end
end)
FarmotherMain = Main.CreatePage({ Page_Name = "Farming Other", Page_Title = "Farming Other" })
EventEasterSection = FarmotherMain.CreateSection("Event Easter")
EventEasterSection.CreateButton({ Title = "Open Easter Shop" }, function()
	require(game.ReplicatedStorage.Controllers.UI.EventShop):Open("Easter2026")
end)
function DetectEgg()
	local V, y, P = t.Character.PrimaryPart.Position, 1 / 0
	for Y, H in pairs(game:GetService("CollectionService"):GetTagged("EasterEgg26")) do
		Y = (V - H:GetAttribute("CFrame").Position).Magnitude
		if Y < y then
			y, P = Y, H
		end
	end
	return P
end
EventEasterSection.CreateToggle(
	{ Title = "Auto Collect Egg Easter", Desc = nil, Default = Settings["Auto Collect Egg Easter"] or false },
	function(V)
		if V then
			spawn(function()
				while Settings["Auto Collect Egg Easter"] and (task.wait()) do
					local y, y = pcall(function()
						if not StackFarmOther then
							return
						end
						local P = DetectEgg()
						if P then
							toTarget(P:GetAttribute("CFrame"))
						end
					end)
					if y then
						print(y)
					end
				end
			end)
		end
		SaveSettings("Auto Collect Egg Easter", V)
	end
)
FishingSection = FarmotherMain.CreateSection("Fishing")
FishingSection.CreateToggle(
	{ Title = "Change Size Reel", Desc = nil, Default = Settings["Change Size Reel"] or false },
	function(V)
		if V then
			spawn(function()
				while Settings["Change Size Reel"] and (task.wait()) do
					pcall(function()
						if game:GetService("Players").LocalPlayer.PlayerGui:FindFirstChild("Fishing_Reeling") then
							game:GetService("Players").LocalPlayer.PlayerGui.Fishing_Reeling.Minigame.Container.ReelZone.Size =
								UDim2.new(0.98, 0, 0.13, 0)
						end
					end)
				end
			end)
		end
		SaveSettings("Change Size Reel", V)
	end
)
FishingSection.CreateToggle(
	{
		Title = "Auto Slap Battle",
		Desc = "There\226\128\153s still a chance of a misclick",
		Default = Settings["Auto Slap Battle"] or false,
	},
	function(V)
		if V then
			spawn(function()
				while Settings["Auto Slap Battle"] and (task.wait()) do
					pcall(function()
						if not game:GetService("Players").LocalPlayer:FindFirstChild("RemoteEvent") then
							repeat
								wait()
							until game:GetService("Players").LocalPlayer:FindFirstChild("RemoteEvent")
							local y, P = game:GetService("Players").LocalPlayer.RemoteEvent
							y.OnClientEvent:Connect(function(Y, H, C, J, F, F, F, q)
								if Y == "startBar" and J == game.Players.LocalPlayer then
									local J, q = 0.96 / (C * 0.5), 0.2 / (C * 1.5)
									if P then
										P:Disconnect()
									end
									P = game:GetService("RunService").Heartbeat:Connect(function()
										local c = workspace:GetServerTimeNow()
										local D = 0.02 + (c - H) % C * J
										D = if D >= 0.98 then 0.98 - (D - 0.98) else D
										local J
										if F then
											J = 0.5
										else
											J = 0.4 + (c - H) % (C * 3) * q
											J = if J >= 0.6 then 0.6 - (J - 0.6) else J
										end
										if math.abs(D - J) < 0.03 then
											y:FireServer("Jump", workspace:GetServerTimeNow())
										end
									end)
								elseif Y == "killBar" then
									if P then
										P:Disconnect()
										P = nil
									end
								end
							end)
						end
					end)
				end
			end)
		end
		SaveSettings("Auto Slap Battle", V)
	end
)
_, R = Settings["Save Position Fishing"], "Position : "
if _ then
	I = Vector3.new(_.posX, _.posY, _.posZ)
	R = (
		string.format(
			"Position : %.2f, %.2f, %.2f | Angle(deg) : %.1f, %.1f, %.1f",
			I.X,
			I.Y,
			I.Z,
			math.deg(_.rx),
			math.deg(_.ry),
			math.deg(_.rz)
		)
	)
end
LocalPositionPlantSeed = FishingSection.CreateLabel({ Title = R })
FishingSection.CreateButton({ Title = "Save Position Fishing" }, function()
	local _ = t.Character and (t.Character:FindFirstChild("HumanoidRootPart"))
	if not _ then
		return
	end
	local V = _.CFrame
	local _, y, P, Y = V.Position, V:ToOrientation()
	LocalPositionPlantSeed.SetText(
		string.format(
			"Position : %.2f, %.2f, %.2f | Angle(deg) : %.1f, %.1f, %.1f",
			_.X,
			_.Y,
			_.Z,
			math.deg(y),
			math.deg(P),
			math.deg(Y)
		)
	)
	SaveSettings("Save Position Fishing", { posX = _.X, posY = _.Y, posZ = _.Z, rx = y, ry = P, rz = Y })
end)
a = {}
for _, V in next, require(game:GetService("ReplicatedStorage").FishReplicated.BaitData).Types, nil do
	table.insert(a, _)
end
FishingSection.CreateDropdown(
	{ Title = "Select Bait", List = a, Search = true, Selected = false, Default = Settings["Select Bait"] or nil },
	function(_)
		SaveSettings("Select Bait", _)
	end
)
local _, V, y, P, Y, H =
	game.ReplicatedStorage.FishReplicated.FishingRequest,
	require(game.ReplicatedStorage.Modules.Net):RemoteEvent("FishingRemote", true),
	require(game.ReplicatedStorage.Util.GetWaterHeightAtLocation),
	game:GetService("CollectionService"),
	require(game.ReplicatedStorage.FishReplicated.FishingClient.Config).WATER_BODY_TAG,
	require(game.ReplicatedStorage.FishReplicated.FishingClient.Config).Rod
require(game:GetService("ReplicatedStorage").FishReplicated.FishingClient.Components)
local function C(J, F, q)
	local c, D, r =
		y(J.Position),
		J.Parent.Head.Position,
		J.CFrame.LookVector * (F:GetAttribute("MaxLaunchDistance") or H.MaxLaunchDistance) * (0.5 + q / 201)
	q, F = workspace:FindPartOnRayWithIgnoreList(Ray.new(D, r), { J.Parent, workspace.Characters, workspace.Enemies })
	D, r = workspace:FindPartOnRayWithIgnoreList(
		Ray.new(F + Vector3.new(0, 3, 0), Vector3.new(0, -500, 0)),
		{ J.Parent, workspace.Characters, workspace.Enemies }
	)
	if not r then
		return
	end
	J = Vector3.new(F.X, math.max(r.Y, c), F.Z)
	return J, D and (P:HasTag(D, Y)) or J.Y <= c
end
function DetectRod()
	if not t then
		return nil
	end
	local y = (t.Character or (t.CharacterAdded:Wait())):FindFirstChild("FishingRodData", true)
	if y then
		return y.Parent
	end
	for y, y in ipairs(t.Backpack:GetChildren()) do
		if y:FindFirstChild("FishingRodData") then
			return y
		end
	end
	return nil
end
require(game:GetService("ReplicatedStorage").FishReplicated.FishingClient.Components.CatchingMinigame)
local function y()
	local P = t.Character
	local Y, H = P and (P:FindFirstChild("HumanoidRootPart")), DetectRod()
	if not Y or not H then
		return
	end
	if H.Parent == t.Backpack then
		equiptool(H.Name)
		task.wait(0.5)
		return
	end
	P = H:GetAttribute("ServerState")
	if P then
		StatusFishingLabel.SetText("Status Fishing : " .. P)
	end
	if H:GetAttribute("SkillChargeAlpha") >= 1 then
		game:GetService("ReplicatedStorage").Modules.Net
			:FindFirstChild("RF/JobToolAbilities")
			:InvokeServer(unpack({ "Z", true }))
	end
	if not P or P == "ReeledIn" then
		getgenv().delaytimeBiting = nil
		_:InvokeServer("StartCasting")
		task.wait(0.7)
		local J, F = C(Y, H, 98)
		if not J then
			return
		end
		if not _:InvokeServer("CastLineAtLocation", J, 98, F) then
			equiptool(NameWeapon("Melee"))
			return
		end
		if not getgenv().LoadFishingRemote then
			V.OnClientEvent:Connect(function(V, Y, ...)
				if Settings["Auto Fishing"] then
					if V ~= t then
						return
					end
					if Y == "SpawnFishOnBob" then
						task.wait(0.2)
						_:InvokeServer("Catching", true, { fastBite = true })
						task.wait(2)
						game.ReplicatedStorage.FishReplicated.FishingRequest:InvokeServer("Catch", 1, 1, 1)
						game.ReplicatedStorage.FishReplicated.FishingRequest:InvokeServer("Catch", 1, 0, 1)
					end
				end
			end)
			getgenv().LoadFishingRemote = true
		end
	elseif P == "Biting" then
		if not getgenv().delaytimeBiting then
			getgenv().delaytimeBiting = tick()
		end
		if tick() - (getgenv().delaytimeBiting or 0) >= 5 then
			equiptool(NameWeapon("Melee"))
			task.wait(1)
		end
	else
		getgenv().delaytimeBiting = nil
	end
end
local function _(V, P)
	local Y, H = 1 / 0
	for C, J in ipairs((P or (workspace:WaitForChild("Map"))):GetDescendants()) do
		if J:IsA("BasePart") and J.CanCollide then
			if J.Position.Y + J.Size.Y / 2 > V.Y then
				C = (J.Position - V).Magnitude
				if C < Y then
					Y, H = C, J
				end
			end
		end
	end
	if H then
		return Vector3.new(H.Position.X, H.Position.Y + H.Size.Y / 2, H.Position.Z), H
	end
	return nil
end
local function V(P, Y)
	local H = (Vector3.new(Y.X, P.Position.Y, Y.Z) - P.Position).Unit
	P.CFrame = CFrame.new(P.Position, P.Position + H)
end
X = game.Players.LocalPlayer.Character.HumanoidRootPart
function GetGoldenVortex()
	local X, P, Y = next, workspace.ActiveFishingSpots:GetChildren()
	local H, C = 1 / 0
	for J, F in X, P, Y do
		if F.Name == "GoldenVortex" then
			J = (game.Players.LocalPlayer.Character.HumanoidRootPart.Position - F.Position).Magnitude
			if J < H then
				H, C = J, F
			end
		end
	end
	return C
end
okz, execc = pcall(function()
	return identifyexecutor and (identifyexecutor())
end)
if okz and typeof(execc) == "string" then
	if execc:find("Seliware") then
		task.wait(2)
	elseif execc:find("Velocity") or (execc:find("Delta")) or (execc:find("Real")) then
		task.wait(5)
	end
end
StatusFishingLabel = FishingSection.CreateLabel({ Title = "Status Fishing :" })
FishingSection.CreateToggle(
	{
		Title = "Auto Tween To Event Fishing Spot",
		Desc = nil,
		Default = Settings["Auto Tween To Event Fishing Spot"] or false,
	},
	function(X)
		SaveSettings("Auto Tween To Event Fishing Spot", X)
	end
)
function CheckChestplr()
	local X
	for P, P in pairs(t.Backpack:GetChildren()) do
		X = if string.find(P.Name, "Chest") then P else X
	end
	for P, P in pairs(t.Character:GetChildren()) do
		X = if string.find(P.Name, "Chest") then P else X
	end
	return X
end
FishingSection.CreateToggle(
	{ Title = "Auto Fishing", Desc = nil, Default = Settings["Auto Fishing"] or false },
	function(X)
		if X then
			spawn(function()
				while Settings["Auto Fishing"] and (task.wait()) do
					local P, P = pcall(function()
						if not StackFarmOther then
							return
						end
						if Settings["Auto Celestial Soldier"] and getgenv().AttackOniSoldier then
							return
						end
						if Settings["Auto Rip Commander"] and getgenv().AttackBossRedCommander then
							return
						end
						if
							game:GetService("Players").LocalPlayer.Data.FishingData:GetAttribute("SelectedBait")
							and game:GetService("Players").LocalPlayer.Data.FishingData:GetAttribute("SelectedBait")
								~= "None"
						then
							local Y = t.Character and (t.Character:FindFirstChild("HumanoidRootPart"))
							if Settings["Auto Tween To Event Fishing Spot"] and (GetGoldenVortex()) then
								if not getgenv().Vortex or not getgenv().Vortex.Parent then
									getgenv().Vortex = GetGoldenVortex()
									task.wait(1)
									local H = getgenv()
									H.higherPos, getgenv().partHigher =
										_(getgenv().Vortex.Position, workspace:WaitForChild("Map"))
									return
								end
								if getgenv().Vortex then
									local _ = GetGoldenVortex().Position
									if not ((Y.CFrame.Position - getgenv().higherPos).Magnitude <= 5) then
										toTarget(CFrame.new(getgenv().higherPos))
									else
										if t:DistanceFromCharacter(_) > 100 then
											getgenv().Vortex = nil
											return
										end
										V(Y, _)
										y()
									end
									return
								end
							end
							local _ = Settings["Save Position Fishing"]
							if not _ then
								return
							end
							local V = Vector3.new(_.posX, _.posY, _.posZ)
							local H = CFrame.new(V) * CFrame.fromOrientation(_.rx, _.ry, _.rz)
							if Y then
								_ = Y.CFrame
								if not ((_.Position - V).Magnitude <= 10 and _.LookVector:Dot(H.LookVector) > 0.99) then
									toTarget(H)
								else
									y()
								end
							end
						else
							local _ = Settings["Select Bait"] or "Basic Bait"
							if CheckItemInventory(_) then
								game:GetService("ReplicatedStorage").Remotes.CommF_
									:InvokeServer(unpack({ [1] = "LoadItem", [2] = _, [3] = { [1] = "Usables" } }))
							else
								game:GetService("ReplicatedStorage").Modules.Net
									:FindFirstChild("RF/Craft")
									:InvokeServer(unpack({ [1] = "Craft", [2] = _, [3] = 1, [4] = {} }))
							end
						end
					end)
					if P then
						print(P)
					end
				end
			end)
		end
		SaveSettings("Auto Fishing", X)
	end
)
local X = require(game.ReplicatedStorage.JobsReplicated)
FishingSection.CreateToggle(
	{ Title = "Auto Sell Fishing", Desc = nil, Default = Settings["Auto Sell Fishing"] or false },
	function(_)
		if _ then
			spawn(function()
				while Settings["Auto Sell Fishing"] and (task.wait(0.2)) do
					local V, V = pcall(function()
						X.InvokeServer("FishingNPC", "SellFish")
					end)
					if V then
						print(V)
					end
				end
			end)
		end
		SaveSettings("Auto Sell Fishing", _)
	end
)
FishingSection.CreateToggle(
	{ Title = "Auto Open Chest", Desc = nil, Default = Settings["Auto Open Chest"] or false },
	function(_)
		if _ then
			spawn(function()
				while Settings["Auto Open Chest"] and (task.wait(0.2)) do
					local V, V = pcall(function()
						local y = CheckChestplr()
						if y then
							y.RemoteEvent:FireServer(unpack({ [1] = "Visual" }))
							task.wait(0.1)
							y.RemoteEvent:FireServer(unpack({ [1] = "Open" }))
						end
					end)
					if V then
						print(V)
					end
				end
			end)
		end
		SaveSettings("Auto Open Chest", _)
	end
)
local _ = {}
for V, V in next, require(game:GetService("ReplicatedStorage").Modules.Asset.RarityUtil.RarityData), nil do
	_[V.Name] = false
end
function DetectQuestFishing()
	local V = GetNameDoubleQuest()
	if not V then
		return false
	end
	local y
	for P, Y in pairs(_) do
		if string.find(V, P) then
			y = P
			break
		end
	end
	if y and Settings["Select Quest Fishing"] then
		for y, P in next, Settings["Select Quest Fishing"], nil do
			if string.find(V, y) then
				return true
			end
		end
		return false
	end
	return true
end
FishingSection.CreateDropdown(
	{
		Title = "Select Quest Fishing",
		List = PrepareMultiSelectList(_, Settings["Select Quest Fishing"]),
		Search = true,
		Selected = true,
		Default = Settings["Select Quest Fishing"] or nil,
	},
	function(_, V)
		SaveSettings("Select Quest Fishing", _, V)
	end
)
FishingSection.CreateToggle(
	{ Title = "Auto Accept Quest Fishing", Desc = nil, Default = Settings["Auto Accept Quest Fishing"] or false },
	function(_)
		if _ then
			spawn(function()
				while Settings["Auto Accept Quest Fishing"] and (task.wait()) do
					local V, V = pcall(function()
						if Settings["Auto Event Pain"] and getgenv().AttackEventLightning then
							return
						end
						if Settings["Auto Celestial Soldier"] and getgenv().AttackOniSoldier then
							return
						end
						if Settings["Auto Rip Commander"] and getgenv().AttackBossRedCommander then
							return
						end
						if not StackFarmOther then
							return
						end
						X.InvokeServer("FishingNPC", "Angler", "CheckQuest")
						local y = X.InvokeServer("FishingNPC", "Angler", "Speak")
						if y.canAccept then
							X.InvokeServer("FishingNPC", "Angler", "AskQuest")
						elseif y.FailedAnglerQuest or not DetectQuestFishing() then
							game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("AbandonQuest")
						end
						task.wait(2)
					end)
					if V then
						print(V)
					end
				end
			end)
		end
		SaveSettings("Auto Accept Quest Fishing", _)
	end
)
QuestDragonSection = FarmotherMain.CreateSection("Quest Dragon")
function QuestDojoTrainer()
	return game:GetService("ReplicatedStorage")
		:WaitForChild("Modules")
		:WaitForChild("Net")
		:WaitForChild("RF/InteractDragonQuest")
		:InvokeServer(unpack({ [1] = { NPC = "Dojo Trainer", Command = "RequestQuest" } }))
end
AttackAllMobSection = FarmotherMain.CreateSection("Attack All Mobs")
function DetectAllMob()
	local X, _, V = next, game:GetService("Workspace").Enemies:GetChildren()
	for y, y in X, _, V do
		if y.Name ~= "Spirit Tree" and (y:GetAttribute("Level")) and (y:GetAttribute("FruitType")) then
			return y
		end
	end
	X, _, V = next, game:GetService("ReplicatedStorage"):GetChildren()
	for y, y in X, _, V do
		if y.Name ~= "Spirit Tree" and (y:GetAttribute("Level")) and (y:GetAttribute("FruitType")) then
			return y
		end
	end
end
AttackAllMobSection.CreateToggle(
	{ Title = "Auto Attack All Mob and Boss", Desc = nil, Default = Settings["Auto Attack All Mob and Boss"] or false },
	function(X)
		spawn(function()
			while Settings["Auto Attack All Mob and Boss"] and (wait()) do
				local _, _ = pcall(function()
					if not StackFarmOther then
						return
					end
					local V = DetectAllMob()
					if V then
						repeat
							task.wait()
							UsedualFlock()
							ClickM1(V)
							if Settings["Select Weapon"] == "Blox Fruit" then
								toTarget(V.HumanoidRootPart.CFrame * CFrame.new(-7, getgenv().YPosFruit, 0))
							else
								toTarget(V.HumanoidRootPart.CFrame * CFrame.new(7, 20, 0))
							end
						until not IsMobAlive(V) or not Settings["Auto Attack All Mob and Boss"] or not StackFarmOther
					end
				end)
				if _ then
					print(_)
				end
			end
		end)
		SaveSettings("Auto Attack All Mob and Boss", X)
	end
)
local X, _ = { "PirateBrigade", "PirateGrandBrigade" }, { "Fish Crew Member", "Shark" }
function DetectQuestSeaDragon()
	local V, y, P = next, game:GetService("Workspace").Enemies:GetChildren()
	for Y, Y in V, y, P do
		if
			Y:FindFirstChild("Engine")
			and (Y:FindFirstChild("Health"))
			and Y.Health.Value > 0
			and t:DistanceFromCharacter(Y.Engine.Position) < 500
		then
			return Y
		end
	end
	V = DetectMob(_)
	if V and t:DistanceFromCharacter(V.HumanoidRootPart.Position) < 500 then
		return V
	end
	V = DetectMob("Piranha")
	if V and t:DistanceFromCharacter(V.HumanoidRootPart.Position) < 500 then
		return V
	end
end
function checkboat()
	local V = t.Name
	V = if Settings["Auto Sea Event With Friend"] and Settings["Auto Sea Event"] then Settings["Select Friend"] else V
	local y, P, Y = next, game:GetService("Workspace").Boats:GetChildren()
	for H, H in y, P, Y do
		if H:IsA("Model") then
			if H:FindFirstChild("Owner") and tostring(H.Owner.Value) == V and H.Humanoid.Value > 0 then
				return H
			end
		end
	end
	return false
end
getgenv().PosSEaY = -50
function TeleportSeaEvents(V)
	if not V then
		return
	end
	if V:FindFirstChild("Engine") and (V:FindFirstChild("Health")) and V.Health.Value > 0 then
		local y = Settings["Use Click M1 Fruit For Sea Event"] and -25 or -15
		toTarget(V.Engine.CFrame * CFrame.new(0, y, 0))
		return
	end
	if V.Name == "SeaBeast1" and (V:FindFirstChild("HumanoidRootPart")) then
		if
			(Vector3.new(0, V:FindFirstChild("HumanoidRootPart").Position.Y, 0) - Vector3.new(0, -60, 0)).Magnitude
			<= 175
		then
			if Settings["Use Click M1 Fruit For Sea Event"] then
				toTarget(V.HumanoidRootPart.CFrame * CFrame.new(0, 200 + PosDodgeskill, 0), true)
			else
				toTarget(V.HumanoidRootPart.CFrame * CFrame.new(0, 200 + PosDodgeskill, 50), true)
			end
		else
			toTarget(CFrame.new(V.HumanoidRootPart.Position.X, 140, V.HumanoidRootPart.Position.Z), true)
		end
	else
		local y = V.Name
		local P = if Settings["Use Click M1 Fruit For Sea Event"] then 20 else if y == "Terrorshark" then 60 else 20
		if V:FindFirstChildWhichIsA("Humanoid") and V.Humanoid.Health > 0 then
			toTarget(V.HumanoidRootPart.CFrame * CFrame.new(0, P, 0))
		end
	end
end
local V = 0
function DecectPartRoughSea()
	local y, P, Y = next, game.workspace._WorldOrigin.Locations:GetChildren()
	for H, H in y, P, Y do
		if
			H.Name == "Rough Sea"
			and t:DistanceFromCharacter(H.Position) <= 3000
			and Vector3.new(0.0010000000474974513, 0.0010000000474974513, 0.0010000000474974513) ~= workspace._WorldOrigin.RainEmitterPart.Size
			and not H:FindFirstChild("Ignored")
		then
			return H
		end
	end
end
function AutoQuestDojo()
	local y, P =
		QuestDojoTrainer(), CFrame.new(5868.453125, 1207.7784423828125, 870.819580078125) * CFrame.new(0, 4, -2)
	if not getgenv().QuestTrainer then
		if t:DistanceFromCharacter(P.Position) > 8 then
			toTarget(P)
		elseif y then
			if y.Quest.Progress >= y.Quest.Goal then
				game:GetService("ReplicatedStorage")
					:WaitForChild("Modules")
					:WaitForChild("Net")
					:WaitForChild("RF/InteractDragonQuest")
					:InvokeServer(unpack({ [1] = { NPC = "Dojo Trainer", Command = "ClaimQuest" } }))
				wait(1)
				return
			end
			if y.Quest.BeltName == "White" then
				getgenv().QuestTrainer = { BeltName = "White", CountKillMob = 0 }
			elseif y.Quest.BeltName == "Yellow" then
				getgenv().QuestTrainer = { BeltName = "Yellow", CountKillMob = 0 }
			elseif y.Quest.BeltName == "Green" then
				getgenv().QuestTrainer = { BeltName = "Green", CountKillMob = 300, Progress = y.Quest.Progress }
			elseif y.Quest.BeltName == "Purple" then
				getgenv().QuestTrainer = { BeltName = "Purple", CountKillMob = 0 }
			elseif y.Quest.BeltName == "Red" then
				getgenv().QuestTrainer = { BeltName = "Red", CountKillMob = 0 }
			else
				A.CreateNoti({
					Title = "Banana Cat Hub",
					Desc = "That's enough training for today... Come back tomorrow and we can continue.\10 or dont support Belt Currently",
					ShowTime = 5,
				})
				wait(5)
				return
			end
		end
	elseif getgenv().QuestTrainer.BeltName == "White" and getgenv().QuestTrainer.CountKillMob < 20 then
		SaveSettings("QuestDojo", true)
		local y = GetNameDoubleQuest() or ""
		if not t.PlayerGui.Main:FindFirstChild("Quest").Visible and typeof(y) == "string" then
			TakeQuestLevel()
		else
			local P = DetectMob(y)
			if not P then
				local Y = DetectPartSpawnMob(y, true)
				if Y then
					Instance.new("IntValue", Y).Name = "Ignored"
					repeat
						task.wait()
						toTarget(Y.CFrame * CFrame.new(0, 60, 0))
					until (Y.Position - t.Character.HumanoidRootPart.Position).Magnitude <= 100
						or (DetectMob(y))
						or not Settings["Auto Quest Dojo Trainer"]
					wait(1)
				else
					DeleteIgnoredMobSpawn()
				end
			else
				repeat
					task.wait()
					sizepart(P)
					BringMob(P)
					UsedualFlock()
					ClickM1(P)
					if
						game:GetService("Players").LocalPlayer.PlayerGui.TransformationHUD.ImageLabel.Visible
						and (Settings["Auto Finish Train Quest"] or Settings["Auto Finish Train Draco Quest"])
					then
						toTarget(P.HumanoidRootPart.CFrame * CFrame.new(7, 20, 0))
					elseif Settings["Select Weapon"] == "Blox Fruit" then
						toTarget(P.HumanoidRootPart.CFrame * CFrame.new(-7, getgenv().YPosFruit, 0))
					else
						toTarget(P.HumanoidRootPart.CFrame * CFrame.new(7, 20, 0))
					end
				until not IsMobAlive(P) or not Settings["Auto Quest Dojo Trainer"]
				if getgenv().QuestTrainer and getgenv().QuestTrainer.CountKillMob then
					getgenv().QuestTrainer.CountKillMob = getgenv().QuestTrainer.CountKillMob + 1
				end
			end
		end
	elseif getgenv().QuestTrainer.BeltName == "White" and getgenv().QuestTrainer.CountKillMob >= 20 then
		SaveSettings("QuestDojo", false)
		getgenv().QuestTrainer = nil
	elseif getgenv().QuestTrainer.BeltName == "Yellow" and getgenv().QuestTrainer.CountKillMob < 5 then
		SaveSettings("QuestDojo", true)
		local y, P = DetectQuestSeaDragon(), checkboat()
		if not y then
			if not P then
				local Y = CFrame.new(-16204.0810546875, 9.0863618850708, 479.2259521484375)
				if (Y.Position - t.Character.HumanoidRootPart.Position).Magnitude > 8 then
					toTarget(Y)
				else
					game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("BuyBoat", "PirateBrigade")
				end
			else
				task.spawn(function()
					NoclipBoat(P)
				end)
				local Y = DecectPartRoughSea()
				if Y then
					wait(1)
					V = if V == 0 then 7000 else 0
					Instance.new("IntValue", Y).Name = "Ignored"
					wait(0.5)
				end
				getgenv().RoughSea = V
				Y = CFrame.new(-32975.9921875, P.WorldPivot.Y, 25963.7109375)
					* CFrame.new(0, P.WorldPivot.Y, 0 + RoughSea)
				if not t.Character.Humanoid.Sit then
					toTarget(P.VehicleSeat.CFrame)
				else
					manageTween(P.VehicleSeat, Y, 350, "TweenBoat")
				end
			end
		else
			repeat
				task.wait()
				TeleportSeaEvents(y)
				local P = y:FindFirstChild("HumanoidRootPart") or (y:FindFirstChild("Engine"))
				getgenv().AimPos = CFrame.new(P.Position.X, 40, P.Position.Z)
				if y:FindFirstChildWhichIsA("Humanoid") then
					UsedualFlock()
					ClickM1(y, true)
				elseif t:DistanceFromCharacter(P.Position) < 400 then
					AutoAllSkill()
				end
			until not y
				or not y.Parent
				or y:FindFirstChildWhichIsA("Humanoid") and y.Humanoid.Health <= 0
				or y:FindFirstChild("Health") and y.Health.Value <= 0
				or not Settings["Auto Quest Dojo Trainer"]
			if getgenv().QuestTrainer and getgenv().QuestTrainer.CountKillMob then
				getgenv().QuestTrainer.CountKillMob = getgenv().QuestTrainer.CountKillMob + 1
			end
		end
	elseif getgenv().QuestTrainer.BeltName == "Yellow" and getgenv().QuestTrainer.CountKillMob >= 5 then
		SaveSettings("QuestDojo", false)
		getgenv().QuestTrainer = nil
	elseif getgenv().QuestTrainer.BeltName == "Purple" and getgenv().QuestTrainer.CountKillMob < 3 then
		SaveSettings("QuestDojo", true)
		local y = DetectEliteHunter()
		if y then
			StackFarm = false
			if
				not string.find(game.Players.LocalPlayer.PlayerGui.Main.Quest.Container.QuestTitle.Title.Text, y.Name)
				or not game:GetService("Players").LocalPlayer.PlayerGui.Main.Quest.Visible
			then
				game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("AbandonQuest")
				game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("EliteHunter")
			else
				repeat
					task.wait()
					sizepart(y)
					if Settings["Select Weapon"] == "Blox Fruit" then
						toTarget(y.HumanoidRootPart.CFrame * CFrame.new(-7, 20, 0))
					else
						toTarget(y.HumanoidRootPart.CFrame * CFrame.new(7, 20, 0))
					end
					ClickM1(y)
					UsedualFlock()
				until not IsMobAlive(y) or not Settings["Auto Quest Dojo Trainer"]
				if getgenv().QuestTrainer and getgenv().QuestTrainer.CountKillMob then
					getgenv().QuestTrainer.CountKillMob = getgenv().QuestTrainer.CountKillMob + 1
				end
			end
			return
		end
	elseif getgenv().QuestTrainer.BeltName == "Purple" and getgenv().QuestTrainer.CountKillMob >= 3 then
		SaveSettings("QuestDojo", false)
		getgenv().QuestTrainer = nil
	elseif getgenv().QuestTrainer.BeltName == "Green" and getgenv().QuestTrainer.CountKillMob == 300 then
		SaveSettings("QuestDojo", true)
		if
			game:GetService("Players").LocalPlayer.PlayerGui.Main.Compass.Frame.DangerLevel.Visible
			and tonumber(
					game:GetService("Players").LocalPlayer.PlayerGui.Main.Compass.Frame.DangerLevel.TextLabel.Text
				)
				== 6
		then
			local y = tick()
			repeat
				wait()
			until tick() - y >= getgenv().QuestTrainer.Progress
				or not game:GetService("Players").LocalPlayer.PlayerGui.Main.Compass.Frame.DangerLevel.Visible
				or not Settings["Auto Quest Dojo Trainer"]
			getgenv().QuestTrainer = nil
			SaveSettings("QuestDojo", false)
		else
			local y = checkboat()
			if not y then
				local P = CFrame.new(-16204.0810546875, 9.0863618850708, 479.2259521484375)
				if (P.Position - t.Character.HumanoidRootPart.Position).Magnitude > 8 then
					toTarget(P)
				else
					game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("BuyBoat", "PirateBrigade")
				end
			else
				task.spawn(function()
					NoclipBoat(y)
				end)
				local P = DecectPartRoughSea()
				if P then
					wait(1)
					V = if V == 0 then 7000 else 0
					Instance.new("IntValue", P).Name = "Ignored"
					wait(0.5)
				end
				getgenv().RoughSea = V
				P = CFrame.new(-32975.9921875, y.WorldPivot.Y, 25963.7109375)
					* CFrame.new(0, y.WorldPivot.Y, 0 + RoughSea)
				if not t.Character.Humanoid.Sit then
					toTarget(y.VehicleSeat.CFrame)
				else
					manageTween(y.VehicleSeat, P, 350, "TweenBoat")
				end
			end
		end
	elseif getgenv().QuestTrainer.BeltName == "Red" and getgenv().QuestTrainer.CountKillMob == 0 then
		SaveSettings("QuestDojo", true)
		local y, P = CheckNameBoss("Terrorshark"), checkboat()
		if not y then
			if not P then
				local Y = CFrame.new(-16204.0810546875, 9.0863618850708, 479.2259521484375)
				if (Y.Position - t.Character.HumanoidRootPart.Position).Magnitude > 8 then
					toTarget(Y)
				else
					game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("BuyBoat", "PirateBrigade")
				end
			else
				local Y = DecectPartRoughSea()
				if Y then
					wait(1)
					V = if V == 0 then 7000 else 0
					Instance.new("IntValue", Y).Name = "Ignored"
					wait(0.5)
				end
				getgenv().RoughSea = V
				Y = CFrame.new(-32975.9921875, P.WorldPivot.Y, 25963.7109375)
					* CFrame.new(0, P.WorldPivot.Y, 0 + RoughSea)
				if not t.Character.Humanoid.Sit then
					toTarget(P.VehicleSeat.CFrame)
				else
					manageTween(P.VehicleSeat, Y, 350, "TweenBoat")
				end
			end
		else
			repeat
				task.wait()
				TeleportSeaEvents(y)
				local P = y:FindFirstChild("HumanoidRootPart")
				getgenv().AimPos = CFrame.new(P.Position.X, 40, P.Position.Z)
				if y:FindFirstChildWhichIsA("Humanoid") then
					UsedualFlock()
					ClickM1(y, true)
				elseif t:DistanceFromCharacter(P.Position) < 400 then
					AutoAllSkill()
				end
			until not y or not y.Parent or y.Humanoid.Health <= 0 or not Settings["Auto Quest Dojo Trainer"]
			getgenv().QuestTrainer.CountKillMob = getgenv().QuestTrainer.CountKillMob + 1
		end
	elseif getgenv().QuestTrainer.BeltName == "Red" and getgenv().QuestTrainer.CountKillMob > 0 then
		SaveSettings("QuestDojo", false)
		getgenv().QuestTrainer = nil
	end
end
QuestDragonSection.CreateToggle(
	{ Title = "Auto Quest Dojo Trainer", Desc = nil, Default = Settings["Auto Quest Dojo Trainer"] or false },
	function(y)
		if y then
			spawn(function()
				while Settings["Auto Quest Dojo Trainer"] and (task.wait()) do
					local P, P = pcall(function()
						AutoQuestDojo()
					end)
					if P then
						print(P)
					end
				end
			end)
		end
		SaveSettings("Auto Quest Dojo Trainer", y)
	end
)
game:GetService("Players").LocalPlayer.PlayerGui.Notifications.ChildAdded:Connect(function(y)
	if y.Name == "NotificationTemplate" then
		repeat
			wait()
		until y:FindFirstChild("TranslateMe")
		if y.TranslateMe.Text == "Head back to the Dojo to complete more tasks." then
			getgenv().QuestHunterDragon = nil
		end
	end
	if y.Name == "NotificationTemplate" then
		repeat
			wait()
		until y:FindFirstChild("TranslateMe")
		if y.TranslateMe.Text == "{color1_Red}[ERROR]{color1_/} Can't perform actions while preparing to teleport!" then
			y:Destroy()
		end
	end
end)
function DetectTree()
	local y = workspace.Map:FindFirstChild("Waterfall") and (workspace.Map.Waterfall:FindFirstChild("IslandModel"))
	if not y then
		toTarget((CFrame.new(5251.900390625, 17.18115234375, 453.6025390625)))
		return nil
	end
	local function P(Y)
		for H, C in ipairs(Y:GetChildren()) do
			if
				C:IsA("Model")
				and not C:FindFirstChild("Ignored")
				and C.Name == "Tree"
				and not C:GetAttribute("AlreadyDestroyedClient")
				and (C:FindFirstChild("Group"))
				and (C.Group:FindFirstChild("Meshes/bambootree") or (C.Group:FindFirstChild("Meshes/plant1_Icosphere")))
				and not workspace:FindFirstChild("EmberTemplate")
			then
				return C
			end
			H = P(C)
			if H then
				return H
			end
		end
		return nil
	end
	local Y = P(y)
	if not Y then
		local function P(H)
			for C, C in ipairs(H:GetChildren()) do
				if C:FindFirstChild("Ignored") then
					C.Ignored:Destroy()
				end
				P(C)
			end
		end
		P(y)
	end
	return Y
end
function DetectEmberTemplate()
	for y, y in game.workspace:GetChildren() do
		if
			y.Name == "EmberTemplate"
			and not y:FindFirstChild("Ignored")
			and (y:FindFirstChild("Part"))
			and y.Part.Position.Y > -100
		then
			return y
		end
	end
end
function AutoDragonHunter()
	local y = DetectNpc("Dragon Hunter")
	if not getgenv().QuestHunterDragon then
		if t:DistanceFromCharacter(y.HumanoidRootPart.Position) > 8 then
			toTarget(y.HumanoidRootPart.CFrame * CFrame.new(0, 0, 4))
		else
			local y = game:GetService("ReplicatedStorage")
				:WaitForChild("Modules")
				:WaitForChild("Net")
				:WaitForChild("RF/DragonHunter")
				:InvokeServer(unpack({ [1] = { Context = "Check" } }))
			if not y or y and not y.Text then
				getgenv().QuestHunterDragon = game:GetService("ReplicatedStorage")
					:WaitForChild("Modules")
					:WaitForChild("Net")
					:WaitForChild("RF/DragonHunter")
					:InvokeServer(unpack({ [1] = { Context = "RequestQuest" } })).Text
			else
				getgenv().QuestHunterDragon = y.Text
			end
		end
	else
		local y = DetectEmberTemplate()
		if y then
			Instance.new("IntValue", y).Name = "Ignored"
			repeat
				wait()
				toTarget(y.Part.CFrame)
			until not y or not y.Parent
			return
		end
		if string.find(getgenv().QuestHunterDragon, "Hydra Enforcers") then
			local P = DetectMob("Hydra Enforcer")
			if not P then
				local Y = DetectPartSpawnMob("Hydra Enforcer", true)
				if Y then
					Instance.new("IntValue", Y).Name = "Ignored"
					repeat
						wait()
						toTarget(Y.CFrame * CFrame.new(0, 60, 0))
					until (Y.Position - t.Character.HumanoidRootPart.Position).Magnitude <= 100
						or (DetectMob("Hydra Enforcer"))
						or not Settings["Auto Quest Dragon Hunter"]
						or y
					wait(1)
				else
					DeleteIgnoredMobSpawn()
				end
			else
				repeat
					task.wait()
					sizepart(P)
					BringMob(P)
					UsedualFlock()
					ClickM1(P)
					if Settings["Select Weapon"] == "Blox Fruit" then
						toTarget(P.HumanoidRootPart.CFrame * CFrame.new(-7, 20, 0))
					else
						toTarget(P.HumanoidRootPart.CFrame * CFrame.new(7, 20, 0))
					end
				until not IsMobAlive(P) or not Settings["Auto Quest Dragon Hunter"] or y
			end
		elseif string.find(getgenv().QuestHunterDragon, "Venomous Assailants") then
			local P = DetectMob("Venomous Assailant")
			if not P then
				local Y = DetectPartSpawnMob("Venomous Assailant", true)
				if Y then
					Instance.new("IntValue", Y).Name = "Ignored"
					repeat
						wait()
						toTarget(Y.CFrame * CFrame.new(0, 60, 0))
					until (Y.Position - t.Character.HumanoidRootPart.Position).Magnitude <= 100
						or (DetectMob("Venomous Assailant"))
						or not Settings["Auto Quest Dragon Hunter"]
						or y
					wait(1)
				else
					DeleteIgnoredMobSpawn()
				end
			else
				repeat
					task.wait()
					sizepart(P)
					BringMob(P)
					UsedualFlock()
					ClickM1(P)
					if Settings["Select Weapon"] == "Blox Fruit" then
						toTarget(P.HumanoidRootPart.CFrame * CFrame.new(-7, 20, 0))
					else
						toTarget(P.HumanoidRootPart.CFrame * CFrame.new(7, 20, 0))
					end
				until not IsMobAlive(P) or not Settings["Auto Quest Dragon Hunter"] or y
			end
		elseif string.find(getgenv().QuestHunterDragon, "trees") then
			local P, Y = workspace.CurrentCamera, DetectTree()
			if Y then
				Instance.new("IntValue", Y).Name = "Ignored"
				local H = tick()
				repeat
					task.wait()
					local C = Y.WorldPivot.Position
					if t:DistanceFromCharacter(C) < 50 then
						AutoAllSkill()
					end
					if Y:FindFirstChild("Meshes/plant1_Icosphere", true) then
						toTarget(Y.WorldPivot)
						getgenv().AimPos = Y.WorldPivot
						G.Hit = CFrame.new(P.CFrame.Position, C)
						G.Target = Y
					else
						local C, J =
							(Y.WorldPivot * CFrame.new(5, -20, 0)).Position,
							(Y.WorldPivot * CFrame.new(0, -20, 0)).Position
						toTarget(CFrame.new(C))
						getgenv().AimPos = CFrame.new(J)
						G.Hit = CFrame.new(P.CFrame.Position, J)
						G.Target = Y
					end
				until not Y
					or not Y.Parent
					or not Settings["Auto Quest Dragon Hunter"]
					or y
					or (Y:GetAttribute("AlreadyDestroyedClient"))
					or tick() - H >= 15
			end
		end
	end
end
QuestDragonSection.CreateToggle(
	{ Title = "Auto Quest Dragon Hunter", Desc = nil, Default = Settings["Auto Quest Dragon Hunter"] or false },
	function(y)
		if y then
			spawn(function()
				while Settings["Auto Quest Dragon Hunter"] and (task.wait(0.1)) do
					local P, P = pcall(function()
						AutoDragonHunter()
					end)
					if P then
						print(P)
					end
				end
			end)
		end
		SaveSettings("Auto Quest Dragon Hunter", y)
	end
)
function DetectBerryCFrame(y)
	for P, P in next, y, nil do
		if P then
			return P
		end
	end
end
function DetectBerry()
	local y, P, Y = next, game:GetService("CollectionService"):GetTagged("BerryBush")
	for H, H in y, P, Y do
		if DetectBerryCFrame(H:GetAttributes()) then
			return H
		end
	end
end
function DetectBerryESP()
	local y, P, Y = next, game:GetService("CollectionService"):GetTagged("BerryBush")
	for H, C in y, P, Y do
		if not C.Parent:FindFirstChild("Ignored") then
			H = DetectBerryCFrame(C:GetAttributes())
			if H then
				return C, H
			end
		end
	end
end
function DetectModelBerry(y)
	for P, P in pairs(y:GetChildren()) do
		if P then
			return P
		end
	end
end
function GetCFrameSpawnBerry()
	local y, P, Y = next, game:GetService("CollectionService"):GetTagged("BerryBush")
	local H, C = 1 / 0
	for J, F in y, P, Y do
		if not F.Parent:FindFirstChild("IgnoredBerry") then
			J = t:DistanceFromCharacter(F.Parent:GetAttribute("CFrame").Position)
			if H > J then
				H, C = J, F
			end
		end
	end
	return C
end
BerrySection = FarmotherMain.CreateSection("Berry")
BerrySection.CreateToggle(
	{ Title = "Hop Find Berry", Desc = nil, Default = Settings["Hop Find Berry"] or false },
	function(y)
		SaveSettings("Hop Find Berry", y)
	end
)
BerrySection.CreateToggle(
	{ Title = "Auto Collect Berry", Desc = nil, Default = Settings["Auto Collect Berry"] or false },
	function(y)
		if y then
			spawn(function()
				while Settings["Auto Collect Berry"] and (task.wait(0.1)) do
					pcall(function()
						local P = DetectBerry()
						if P then
							local Y = DetectModelBerry(P)
							if not Y then
								toTarget(P.Parent.WorldPivot)
							else
								toTarget(Y.WorldPivot)
								local P = Y:FindFirstChild("ProximityPrompt")
								if P then
									fireproximityprompt(P)
								end
							end
						else
							A.CreateNoti({ Title = "Banana Cat Hub", Desc = "Waiting Berry spawn", ShowTime = 5 })
							if Settings["Hop Find Berry"] then
								HopServer()
							end
							wait(5)
						end
					end)
				end
			end)
		end
		SaveSettings("Auto Collect Berry", y)
	end
)
FarmChestSection = FarmotherMain.CreateSection("Farm Chest")
FarmChestSection.CreateSlider(
	{
		Title = "Value Collect Chest to Hop",
		Min = 0,
		Max = 100,
		Default = Settings["Value Collect Chest to Hop"] or 20,
		Precise = true,
	},
	function(y)
		SaveSettings("Value Collect Chest to Hop", y)
	end
)
function AutoChest()
	if not StackFarmOther then
		return
	end
	local y = Settings["Value Collect Chest to Hop"] or 20
	if CheckNameBoss("Darkbeard") and Settings["Attack Darkbeard"] then
		f = y
		return
	end
	if DetectItemPlr("Fist of Darkness") and Settings["Summon Darkbeard"] then
		f = y
		return
	end
	if
		(DetectItemPlr("Fist of Darkness") or (DetectItemPlr("God's Chalice"))) and Settings["Tween Safe if have Items"]
	then
		return
	end
	if f and f >= y and Settings["Auto Chest Hop"] then
		HopServer()
		return
	end
	y = GetNearestChest()
	if y then
		f += 1
		local P
		repeat
			task.wait()
			if (game.Players.LocalPlayer.Character.HumanoidRootPart.Position - y.Position).Magnitude <= 5 then
				if not P then
					P = (tick())
				elseif tick() - P >= 5 then
					Instance.new("IntValue", y).Name = "Ignored"
					wait(0.1)
				end
				if not Settings["Use Method Teleport"] then
					game:GetService("VirtualInputManager"):SendKeyEvent(true, "Space", false, game)
					wait()
					game:GetService("VirtualInputManager"):SendKeyEvent(false, "Space", false, game)
				end
				TweenManager.CancelCurrent()
			end
			if Settings["Use Method Teleport"] then
				t.Character.HumanoidRootPart.CFrame = y.CFrame
				TweenManager.CancelCurrent()
			else
				toTarget(y.CFrame, true)
			end
		until not y
			or not y.Parent
			or not Settings["Auto Chest"]
			or (y:GetAttribute("IsDisabled"))
			or (y:FindFirstChild("Ignored"))
			or not y:FindFirstChild("TouchInterest")
			or not StackFarmOther
	else
		local y = PathFindChest()
		if y then
			toTarget(y.Part.CFrame)
			if (y.Part.Position - t.Character.HumanoidRootPart.Position).Magnitude <= 100 or (GetNearestChest()) then
				Instance.new("IntValue", y).Name = "Ignored"
			end
		else
			for y, y in pairs(game:GetService("Workspace")._WorldOrigin.PlayerSpawns.Pirates:GetChildren()) do
				if y:FindFirstChild("Ignored") then
					y:FindFirstChild("Ignored"):Destroy()
				end
			end
		end
	end
end
FarmChestSection.CreateToggle(
	{ Title = "Auto Chest Hop", Desc = nil, Default = Settings["Auto Chest Hop"] or false },
	function(y)
		SaveSettings("Auto Chest Hop", y)
	end
)
FarmChestSection.CreateToggle(
	{ Title = "Use Method Teleport [ Risk ]", Desc = nil, Default = Settings["Use Method Teleport"] or false },
	function(y)
		SaveSettings("Use Method Teleport", y)
	end
)
FarmChestSection.CreateToggle(
	{ Title = "Auto Chest", Desc = nil, Default = Settings["Auto Chest"] or false },
	function(y)
		if y then
			spawn(function()
				while Settings["Auto Chest"] and (task.wait(0.1)) do
					local P, P = pcall(function()
						AutoChest()
					end)
					if P then
						print(P)
					end
				end
			end)
		end
		SaveSettings("Auto Chest", y)
	end
)
RaidLawSection = FarmotherMain.CreateSection("Raid Law")
RaidLawSection.CreateToggle(
	{ Title = "Auto Buy Chip and Attack Law", Desc = nil, Default = Settings["Auto Buy Chip and Attack Law"] or false },
	function(y)
		if y then
			spawn(function()
				while Settings["Auto Buy Chip and Attack Law"] and (task.wait()) do
					pcall(function()
						if DetectItemPlr("Core Brain") then
							fireclickdetector(
								game:GetService("Workspace").Map.CircleIsland.RaidSummon.Button.Main.ClickDetector
							)
							return
						end
						local P = CheckNameBoss("Order")
						if P then
							repeat
								task.wait()
								sizepart(P)
								UsedualFlock()
								ClickM1(P)
								if Settings["Select Weapon"] == "Blox Fruit" then
									toTarget(P.HumanoidRootPart.CFrame * CFrame.new(-7, 20, 0))
								else
									toTarget(P.HumanoidRootPart.CFrame * CFrame.new(7, 20, 0))
								end
							until not IsMobAlive(P) or not Settings["Auto Buy Chip and Attack Law"]
						elseif
							not DetectItemPlr("Microchip") and game.Players.LocalPlayer.Data.Fragments.Value >= 1000
						then
							BuyChipLaw()
							wait(2)
						elseif DetectItemPlr("Microchip") then
							fireclickdetector(
								game:GetService("Workspace").Map.CircleIsland.RaidSummon.Button.Main.ClickDetector
							)
						end
					end)
				end
			end)
		end
		SaveSettings("Auto Buy Chip and Attack Law", y)
	end
)
FarmObservationSection = FarmotherMain.CreateSection("Farm Observation")
function FarmObservation()
	local y = game.PlaceId == getgenv().CheckPlaceId2 and "Marine Captain" or "Marine Commodore"
	local P = DetectMob(y)
	if not game:GetService("Lighting").Blur.Enabled then
		game:GetService("VirtualInputManager"):SendKeyEvent(true, "E", false, game)
		game:GetService("VirtualInputManager"):SendKeyEvent(false, "E", false, game)
		task.wait()
		local Y, H =
			P and P.HumanoidRootPart or (DetectPartSpawnMob(y)), P and (CFrame.new(0, 0, 50)) or (CFrame.new(0, 60, 0))
		toTarget(Y.CFrame * H)
		task.wait(3)
		if not game:GetService("Lighting").Blur.Enabled and Settings["Farm Observation [ Hop Server ]"] then
			HopServer()
		end
	else
		local Y, H =
			P and P.HumanoidRootPart or (DetectPartSpawnMob(y)), P and (CFrame.new(0, 0, 3)) or (CFrame.new(0, 60, 0))
		if P then
			repeat
				task.wait()
				toTarget(Y.CFrame * H)
			until not Settings["Farm Observation"] or not game:GetService("Lighting").Blur.Enabled
		else
			toTarget(Y.CFrame * H)
		end
	end
end
function ObservationV2()
	if game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("CitizenQuestProgress", "Citizen") == 0 then
		if
			string.find(game.Players.LocalPlayer.PlayerGui.Main.Quest.Container.QuestTitle.Title.Text, "Forest Pirate")
			and (string.find(game.Players.LocalPlayer.PlayerGui.Main.Quest.Container.QuestTitle.Title.Text, "50"))
			and game.Players.LocalPlayer.PlayerGui.Main.Quest.Visible
		then
			local y = DetectMob("Forest Pirate")
			if not y then
				local P = "Forest Pirate"
				if typeof(P) == "table" then
					if #N >= 13 then
						N = {}
						return
					end
					local Y = DetectPartSpawnMob(DetectNameTablePart(P))
					if Y then
						table.insert(N, DetectNameTablePart(P))
						repeat
							wait()
							toTarget(Y.CFrame * CFrame.new(0, 60, 0))
						until (Y.Position - t.Character.HumanoidRootPart.Position).Magnitude <= 100
							or (DetectMob(P))
							or not Settings["Auto UP Observation V2"]
						wait(1)
					end
				else
					local Y = DetectPartSpawnMob(P, true)
					if Y then
						Instance.new("IntValue", Y).Name = "Ignored"
						repeat
							wait()
							toTarget(Y.CFrame * CFrame.new(0, 60, 0))
						until (Y.Position - t.Character.HumanoidRootPart.Position).Magnitude <= 100
							or (DetectMob(P))
							or not Settings["Auto UP Observation V2"]
						wait(1)
					else
						DeleteIgnoredMobSpawn()
					end
				end
			else
				repeat
					task.wait()
					sizepart(y)
					BringMob(y)
					UsedualFlock()
					ClickM1(y)
					if Settings["Select Weapon"] == "Blox Fruit" then
						toTarget(y.HumanoidRootPart.CFrame * CFrame.new(-7, 20, 0))
					else
						toTarget(y.HumanoidRootPart.CFrame * CFrame.new(7, 20, 0))
					end
				until not IsMobAlive(y) or not Settings["Auto UP Observation V2"]
			end
		elseif t:DistanceFromCharacter(Vector3.new(-12441.5908203125, 331.4884948730469, -7676.197265625)) < 10 then
			game:GetService("ReplicatedStorage").Remotes.CommF_
				:InvokeServer(unpack({ [1] = "StartQuest", [2] = "CitizenQuest", [3] = 1 }))
		else
			toTarget(CFrame.new(-12441.5908203125, 331.4884948730469, -7676.197265625))
		end
	elseif game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("CitizenQuestProgress", "Citizen") == 1 then
		if
			string.find(
				game.Players.LocalPlayer.PlayerGui.Main.Quest.Container.QuestTitle.Title.Text,
				"Captain Elephant"
			)
			and (string.find(game.Players.LocalPlayer.PlayerGui.Main.Quest.Container.QuestTitle.Title.Text, "1"))
			and game.Players.LocalPlayer.PlayerGui.Main.Quest.Visible
		then
			local y = CheckNameBoss("Captain Elephant")
			if y then
				repeat
					wait()
					sizepart(y)
					if Settings["Select Weapon"] == "Blox Fruit" then
						toTarget(y.HumanoidRootPart.CFrame * CFrame.new(-7, 20, 0))
					else
						toTarget(y.HumanoidRootPart.CFrame * CFrame.new(7, 20, 0))
					end
					ClickM1(y)
					equiptool(NameWeapon(Settings["Select Weapon"]))
				until not IsMobAlive(y) or not Settings["Auto UP Observation V2"]
			else
				A.CreateNoti({ Title = "Banana Cat Hub", Desc = "Waiting Boss Captain Elephant", ShowTime = 5 })
				wait(5)
			end
		elseif t:DistanceFromCharacter(Vector3.new(-12441.5908203125, 331.4884948730469, -7676.197265625)) < 10 then
			game:GetService("ReplicatedStorage").Remotes.CommF_
				:InvokeServer(unpack({ [1] = "StartQuest", [2] = "CitizenQuest", [3] = 1 }))
		else
			toTarget(CFrame.new(-12441.5908203125, 331.4884948730469, -7676.197265625))
		end
	elseif game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("CitizenQuestProgress", "Citizen") == 2 then
		toTarget(CFrame.new(-12513.8, 336.167, -9872.91))
	elseif game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("CitizenQuestProgress", "Citizen") == 3 then
		if
			tonumber((string.gsub(game.ReplicatedStorage.Remotes.CommF_:InvokeServer("KenTalk", "Status"), "%D", "")))
			>= 5000
		then
			game.ReplicatedStorage.Remotes.CommF_:InvokeServer("KenTalk2", "Start")
			if
				t.Data.Beli.Value >= 5000000
					and (DetectItemPlr("Pineapple") and (DetectItemPlr("Apple")) and (DetectItemPlr("Banana")))
				or (DetectItemPlr("Fruit Bowl"))
			then
				game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("CitizenQuestProgress", "Citizen")
				game.ReplicatedStorage.Remotes.CommF_:InvokeServer("KenTalk2", "Buy")
			else
				local y = { "PineappleSpawner", "BananaSpawner", "AppleSpawner" }
				for P, P in pairs(y) do
					if game:GetService("Workspace"):FindFirstChild(P) then
						if game:GetService("Workspace"):FindFirstChild(P):FindFirstChildOfClass("Tool") then
							firetouchinterest(
								t.Character.HumanoidRootPart,
								game:GetService("Workspace"):FindFirstChild(P):FindFirstChildOfClass("Tool").Handle,
								0
							)
						else
							A.CreateNoti({ Title = "Banana Cat Hub", Desc = "Wating Fruit", ShowTime = 5 })
							wait(3)
						end
					end
				end
			end
		else
			local y, P, Y = next, game.workspace.Enemies:GetChildren()
			local H
			for C, C in y, P, Y do
				H = if C:IsA("Model")
						and C.Name == "Marine Commodore"
						and (C:FindFirstChild("HumanoidRootPart"))
						and C.Humanoid.Health > 0
					then C
					else H
			end
			if not game:GetService("Lighting").Blur.Enabled then
				if H then
					toTarget(H.HumanoidRootPart.CFrame * CFrame.new(0, 0, 50))
				end
				game:GetService("VirtualInputManager"):SendKeyEvent(true, "E", false, game)
				game:GetService("VirtualInputManager"):SendKeyEvent(false, "E", false, game)
				wait(2)
			elseif not H then
				GetPart = DetectPartSpawnMob("Marine Commodore")
				toTarget(GetPart.CFrame * CFrame.new(0, 60, 0))
			else
				repeat
					task.wait()
					toTarget(H.HumanoidRootPart.CFrame * CFrame.new(0, 0, 3))
				until not Settings["Auto UP Observation V2"] or not game:GetService("Lighting").Blur.Enabled
			end
		end
	end
end
FarmObservationSection.CreateToggle(
	{ Title = "Auto UP Observation V2", Desc = nil, Default = Settings["Auto UP Observation V2"] or false },
	function(y)
		if y then
			spawn(function()
				while Settings["Auto UP Observation V2"] and (wait(0.1)) do
					pcall(function()
						ObservationV2()
					end)
				end
			end)
		end
		SaveSettings("Auto UP Observation V2", y)
	end
)
FarmObservationSection.CreateToggle(
	{ Title = "Farm Observation", Desc = nil, Default = Settings["Farm Observation"] or false },
	function(y)
		if y then
			spawn(function()
				while Settings["Farm Observation"] and (wait(0.1)) do
					pcall(function()
						FarmObservation()
					end)
				end
			end)
		end
		SaveSettings("Farm Observation", y)
	end
)
FarmObservationSection.CreateToggle(
	{
		Title = "Farm Observation [ Hop Server ]",
		Desc = nil,
		Default = Settings["Farm Observation [ Hop Server ]"] or false,
	},
	function(y)
		if y and not Settings["Farm Observation"] then
			A.CreateNoti({ Title = "Banana Cat Hub", Desc = "Turn On Farm Observation plz", ShowTime = 5 })
		end
		SaveSettings("Farm Observation [ Hop Server ]", y)
	end
)
AutoKillMobSection = FarmotherMain.CreateSection("Auto Kill Mob")
function TableMob()
	local y, P, Y, H, C = {}, {}, next, require(game:GetService("ReplicatedStorage").Quests)
	for J, J in Y, H, C do
		for Y, Y in next, J, nil do
			for H, C in next, Y.Task, nil do
				if C > 1 then
					table.insert(P, H)
				end
			end
		end
	end
	if game:GetService("Workspace")._WorldOrigin.EnemySpawns:FindFirstChildWhichIsA("Part") then
		for Y, Y in pairs(game:GetService("Workspace")._WorldOrigin.EnemySpawns:GetChildren()) do
			if not string.find(Y.Name, "Boss") and y[Y.Name] == nil then
				y[Y.Name] = false
			end
		end
		if string.find(game:GetService("Workspace")._WorldOrigin.EnemySpawns:GetChildren()[1].Name, "Lv.") then
			for Y, Y in pairs(getnilinstances()) do
				if table.find(P, tostring(Y.Name:gsub(" %pLv. %d+%p", ""))) and y[Y.Name] == nil then
					y[Y.Name] = false
				end
			end
		else
			for Y, Y in pairs(getnilinstances()) do
				if table.find(P, Y.Name) and y[Y.Name] == nil then
					y[Y.Name] = false
				end
			end
		end
	end
	return y
end
AutoKillMobSection.CreateDropdown(
	{
		Title = "Select Mob",
		List = PrepareMultiSelectList(TableMob(), Settings["Select Mob"]),
		Search = true,
		Selected = true,
		Default = Settings["Select Mob"] or nil,
	},
	function(y, P)
		SaveSettings("Select Mob", y, P)
	end
)
function FarmSelectMob()
	if not StackFarmOther then
		return
	end
	local y = {}
	for P, Y in next, Settings["Select Mob"], nil do
		Y = P:gsub(" %pLv. %d+%p", "")
		table.insert(y, Y)
	end
	local P = DetectMob(y)
	if not P then
		if typeof(y) == "table" then
			if #N >= #y then
				N = {}
				return
			end
			local Y = DetectPartSpawnMob(DetectNameTablePart(y))
			if Y then
				table.insert(N, DetectNameTablePart(y))
				repeat
					wait()
					toTarget(Y.CFrame * CFrame.new(0, 60, 0))
				until (Y.Position - t.Character.HumanoidRootPart.Position).Magnitude <= 100
					or (DetectMob(y))
					or not Settings["Kill Mob"]
				wait(1)
			end
		else
			local Y = DetectPartSpawnMob(y, true)
			if Y then
				Instance.new("IntValue", Y).Name = "Ignored"
				repeat
					wait()
					toTarget(Y.CFrame * CFrame.new(0, 60, 0))
				until (Y.Position - t.Character.HumanoidRootPart.Position).Magnitude <= 100
					or (DetectMob(y))
					or not Settings["Kill Mob"]
				wait(1)
			else
				DeleteIgnoredMobSpawn()
			end
		end
	else
		repeat
			task.wait()
			sizepart(P)
			BringMob(P)
			UsedualFlock()
			ClickM1(P)
			if Settings["Select Weapon"] == "Blox Fruit" then
				toTarget(P.HumanoidRootPart.CFrame * CFrame.new(-7, 20, 0))
			else
				toTarget(P.HumanoidRootPart.CFrame * CFrame.new(7, 20, 0))
			end
		until not IsMobAlive(P) or not Settings["Kill Mob"] or not StackFarmOther
	end
end
AutoKillMobSection.CreateToggle({ Title = "Kill Mob", Desc = nil, Default = Settings["Kill Mob"] or false }, function(y)
	if y then
		spawn(function()
			while Settings["Kill Mob"] and (task.wait(0.1)) do
				local P, P = pcall(function()
					FarmSelectMob()
				end)
				if P then
					print(P)
				end
			end
		end)
	end
	SaveSettings("Kill Mob", y)
end)
AutoKillBossSection = FarmotherMain.CreateSection("Auto Boss")
local y = {
	"Gorilla King",
	"Bobby",
	"The Saw",
	"Yeti",
	"Mob Leader",
	"Vice Admiral",
	"Saber Expert",
	"Warden",
	"Chief Warden",
	"Swan",
	"Magma Admiral",
	"Fishman Lord",
	"Wysper",
	"Thunder God",
	"Cyborg",
	"Ice Admiral",
	"Diamond",
	"Jeremy",
	"Orbitus",
	"Don Swan",
	"Smoke Admiral",
	"Awakened Ice Admiral",
	"Tide Keeper",
	"Stone",
	"Island Empress",
	"Kilo Admiral",
	"Captain Elephant",
	"Beautiful Pirate",
	"Longma",
	"Cake Queen",
	"GreyBeard",
	"Order",
	"Cursed Captain",
	"Darkbeard",
	"Soul Reaper",
	"rip_indra True Form",
	"Mihawk",
	"Cake Prince",
	"Dough King",
}
function TableBoss()
	local P = {}
	for Y, Y in pairs(game.Workspace.Enemies:GetChildren()) do
		if table.find(y, Y.Name) then
			table.insert(P, Y.Name)
		end
	end
	for Y, Y in pairs(game.ReplicatedStorage:GetChildren()) do
		if table.find(y, Y.Name) then
			table.insert(P, Y.Name)
		end
	end
	return P
end
local y = AutoKillBossSection.CreateDropdown(
	{
		Title = "Select Boss",
		List = TableBoss(),
		Search = true,
		Selected = false,
		Default = Settings["Select Boss"] or nil,
	},
	function(P)
		SaveSettings("Select Boss", P)
	end
)
AutoKillBossSection.CreateButton({ Title = "Refresh Boss" }, function()
	y:GetNewList(TableBoss())
end)
function AutoKillBoss()
	local y = if Settings["Kill All Boss"]
		then (CheckNameBoss(TableBoss()))
		else (CheckNameBoss(Settings["Select Boss"]))
	if y then
		repeat
			wait()
			sizepart(y)
			if Settings["Select Weapon"] == "Blox Fruit" then
				toTarget(y.HumanoidRootPart.CFrame * CFrame.new(-7, 20, 0))
			else
				toTarget(y.HumanoidRootPart.CFrame * CFrame.new(7, 20, 0))
			end
			ClickM1(y)
			UsedualFlock()
		until not IsMobAlive(y) or not Settings["Kill Boss"]
	elseif Settings["Hop Server Find Boss"] then
		HopServer()
		wait(5)
	end
end
AutoKillBossSection.CreateToggle(
	{ Title = "Kill Boss", Desc = nil, Default = Settings["Kill Boss"] or false },
	function(y)
		spawn(function()
			while Settings["Kill Boss"] and (wait()) do
				pcall(function()
					AutoKillBoss()
				end)
			end
		end)
		SaveSettings("Kill Boss", y)
	end
)
AutoKillBossSection.CreateToggle(
	{ Title = "Kill All Boss", Desc = nil, Default = Settings["Kill All Boss"] or false },
	function(y)
		if y and not Settings["Kill Boss"] then
			A.CreateNoti({ Title = "Banana Cat Hub", Desc = "Turn On Kill Boss plz", ShowTime = 5 })
		end
		SaveSettings("Kill All Boss", y)
	end
)
AutoKillBossSection.CreateToggle(
	{ Title = "Hop Server Find Boss", Desc = nil, Default = Settings["Hop Server Find Boss"] or false },
	function(y)
		SaveSettings("Hop Server Find Boss", y)
	end
)
DFRaidMain = Main.CreatePage({ Page_Name = "Fruit and Raid, Dungeon", Page_Title = "Fruit and Raid and Dungeon Tab" })
DevilFruitSection = DFRaidMain.CreateSection("Devil Fruit")
DevilFruitSection.CreateToggle(
	{ Title = "Random Devil Fruit", Desc = nil, Default = Settings["Random Devil Fruit"] or false },
	function(y)
		SaveSettings("Random Devil Fruit", y)
	end
)
DevilFruitSection.CreateToggle(
	{ Title = "Auto Store Fruit", Desc = nil, Default = Settings["Auto Store Fruit"] or false },
	function(y)
		SaveSettings("Auto Store Fruit", y)
	end
)
DevilFruitSection.CreateDropdown(
	{
		Title = "Blox Fruit Sniper Shop",
		List = PrepareMultiSelectList(TableDevilFruit, Settings["Blox Fruit Sniper Shop"]),
		Search = true,
		Selected = true,
		Default = Settings["Blox Fruit Sniper Shop"] or nil,
	},
	function(y, P)
		SaveSettings("Blox Fruit Sniper Shop", y, P)
	end
)
DevilFruitSection.CreateToggle(
	{ Title = "Buy Blox Fruit Sniper Shop", Desc = nil, Default = Settings["Buy Blox Fruit Sniper Shop"] or false },
	function(y)
		SaveSettings("Buy Blox Fruit Sniper Shop", y)
	end
)
RaidsSection = DFRaidMain.CreateSection("Raids")
g, b, s, R = {}, next, require(game.ReplicatedStorage.Raids)
for y, y in b, s, R do
	for b, b in next, y, nil do
		table.insert(g, b)
	end
end
RaidsSection.CreateDropdown(
	{ Title = "Select Raid", List = g, Search = true, Selected = false, Default = Settings["Select Raid"] or nil },
	function(b)
		SaveSettings("Select Raid", b)
	end
)
RaidsSection.CreateToggle(
	{
		Title = "Get Fruit In Inventory Low Beli",
		Desc = nil,
		Default = Settings["Get Fruit In Inventory Low Beli"] or false,
	},
	function(b)
		SaveSettings("Get Fruit In Inventory Low Beli", b)
	end
)
getgenv().KillRaidEnemy = function()
	for b, b in ipairs(game.workspace.Enemies:GetChildren()) do
		if IsMobAlive(b) then
			b.Humanoid:ChangeState(Enum.HumanoidStateType.Dead)
		end
	end
end
getgenv().KillRaidEnemyLowhealth = function()
	for b, b in ipairs(game.workspace.Enemies:GetChildren()) do
		if IsMobAlive(b) and b.Humanoid.Health / b.Humanoid.MaxHealth < 0.2 then
			b.Humanoid.Health = 0
		end
	end
end
function DetectMobRaid()
	for b, b in ipairs(game.workspace.Enemies:GetChildren()) do
		if IsMobAlive(b) and t:DistanceFromCharacter(b.HumanoidRootPart.Position) <= 400 then
			return b
		end
	end
end
function BringMobNearst(b)
	if DaBringMob then
		delay(0.15, function()
			getgenv().DaBringMob = false
		end)
		return
	end
	if l and (t.Character.HumanoidRootPart.Position - b.HumanoidRootPart.Position).Magnitude <= 50 then
		for y, y in pairs(game:GetService("Workspace").Enemies:GetChildren()) do
			if
				y ~= b
				and not y:FindFirstChild("Ignored")
				and (IsMobAlive(y))
				and (isnetworkowner2(y.HumanoidRootPart))
			then
				if (y.HumanoidRootPart.Position - l.Position).Magnitude <= 350 then
					sizepart(y)
					y.HumanoidRootPart.CFrame = l * CFrame.new(0, math.random(0, 2), math.random(0, 2))
					getgenv().DaBringMob = true
				end
			end
		end
	end
end
function BringMobRaid(b)
	if not Settings["Bring Mob"] then
		return
	end
	if b and E ~= b then
		E = b
		l = b.HumanoidRootPart.CFrame
		DeleteIgnoredMob()
	end
	if DaBringMob then
		delay(0.1, function()
			getgenv().DaBringMob = false
		end)
		return
	end
	local E = {}
	if not b:FindFirstChild("Ignored") then
		table.insert(E, b)
	end
	for y, y in pairs(game:GetService("Workspace").Enemies:GetChildren()) do
		if
			y ~= b
			and y.Name == b.Name
			and not y:FindFirstChild("Ignored")
			and (IsMobAlive(y))
			and (isnetworkowner2(y.HumanoidRootPart))
		then
			if (y.HumanoidRootPart.Position - l.Position).Magnitude <= 200 and #E < 1 then
				table.insert(E, y)
			end
		end
	end
	if
		l
		and (t.Character.HumanoidRootPart.Position - b.HumanoidRootPart.Position).Magnitude <= 50
		and (isnetworkowner2(t.Character.HumanoidRootPart))
	then
		for b, b in pairs(E) do
			sizepart(b)
			b.HumanoidRootPart.CFrame = l * CFrame.new(0, math.random(0, 2), math.random(0, 2))
			task.spawn(function()
				local E = b.Humanoid.Health
				task.wait(3.5)
				if b.Humanoid.Health == E and not b:FindFirstChild("Ignored") then
					b.HumanoidRootPart.CFrame = b.WorldPivot
					Instance.new("IntValue", b).Name = "Ignored"
					task.wait(0.3)
				end
			end)
			getgenv().DaBringMob = true
		end
	end
end
function GetLastRaidIsland()
	local b, E = 0
	for l, y in ipairs(wOrigin.Locations:GetChildren()) do
		if string.find(y.Name, "Island ") and t:DistanceFromCharacter(y.Position) < 3000 then
			l = tonumber((y.Name:gsub("Island ", "")))
			if b < l then
				b, E = l, y
			end
		end
	end
	return E
end
function CheckInRaid()
	for b, b in ipairs(wOrigin.Locations:GetChildren()) do
		if string.find(b.Name, "Island ") and t:DistanceFromCharacter(b.Position) < 3000 then
			return true
		end
	end
end
function CheckAutoRaid()
	if
		not getgenv().buychip
		or game:GetService("Players").LocalPlayer.PlayerGui.Main.TopHUDList.RaidTimer.Visible and (CheckInRaid())
	then
		return true
	end
end
getgenv().CheckIsplayingRaid = function()
	if
		DetectItemPlr("Special Microchip")
		or not getgenv().buychip
		or game:GetService("Players").LocalPlayer.PlayerGui.Main.TopHUDList.RaidTimer.Visible and (CheckInRaid())
	then
		return true
	end
end
getgenv().buychip = true
RaidsSection.CreateToggle({ Title = "Auto Raid", Desc = nil, Default = Settings["Auto Raid"] or false }, function(b)
	if b then
		spawn(function()
			while Settings["Auto Raid"] and (task.wait()) do
				local E, E = pcall(function()
					local l = game.PlaceId == getgenv().CheckPlaceId2
						and (game:GetService("Workspace").Map.CircleIsland.RaidSummon2.Button:FindFirstChild("Main"))
					l = if game.PlaceId == getgenv().CheckPlaceId
						then game:GetService("Workspace").Map:FindFirstChild("Boat Castle") and (game:GetService(
							"Workspace"
						).Map["Boat Castle"].RaidSummon2.Button
							:FindFirstChild("Main"))
						else l
					print("cc")
					if not t.PlayerGui.Main.TopHUDList.RaidTimer.Visible and not CheckInRaid() then
						if getgenv().TickTeleCastle and tick() - getgenv().TickTeleCastle < 5 then
							return
						end
						if not l then
							if not DetectItemPlr("Special Microchip") then
								toTarget(CFrame.new(-5500, 314, -2855))
							else
								toTarget(CFrame.new(-5500, 314, -2855), false, true)
							end
							return
						end
					end
					if DetectItemPlr("Special Microchip") then
						if getgenv().waitgoraid then
							wait(5)
							getgenv().waitgoraid = false
						end
						getgenv().buychip = false
						fireclickdetector(l.ClickDetector)
						getgenv().TickTeleCastle = tick()
						if getgenv().Tween then
							getgenv().Tween:Pause()
							getgenv().Tween:Cancel()
						end
						return
					end
					if t.PlayerGui.Main.TopHUDList.RaidTimer.Visible and (CheckInRaid()) then
						getgenv().waitgoraid = true
						getgenv().buychip = true
						l = DetectMobRaid()
						if l then
							repeat
								task.wait()
								if not getgenv().KillMobRaid and Settings["Kill Aura Only Raid And Volcano"] then
									getgenv().KillMobRaid = true
									local y = Settings["Time Delay Kill"] or 5
									l.Humanoid:ChangeState(Enum.HumanoidStateType.Dead)
									delay(y, function()
										getgenv().KillMobRaid = false
									end)
								end
								UsedualFlock()
								ClickM1(l)
								sizepart(l)
								BringMobRaid(l)
								if Settings["Select Weapon"] == "Blox Fruit" then
									toTarget(l.HumanoidRootPart.CFrame * CFrame.new(-7, 20, 0))
								else
									toTarget(l.HumanoidRootPart.CFrame * CFrame.new(10, 20, 0))
								end
							until not IsMobAlive(l)
						else
							local y = GetLastRaidIsland()
							if y then
								if y.Name == "Island 2" and Settings["Select Raid"] == "Phoenix" then
									toTarget(y.CFrame * CFrame.new(300, 60, 0))
								else
									toTarget(y.CFrame * CFrame.new(0, 60, 0))
								end
							end
						end
						return
					end
					if
						getgenv().buychip
						and t.Data.Level.Value >= 1100
						and not t.PlayerGui.Main.TopHUDList.RaidTimer.Visible
						and not DetectItemPlr("Special Microchip")
						and not CheckInRaid()
					then
						if Settings["Hop Sever Raid"] then
							l = GetPathFruit()
							if l then
								if not ((l.Handle.Position - t.Character.HumanoidRootPart.Position).Magnitude <= 5) then
									toTarget(l.Handle.CFrame, true)
								end
								return
							elseif not CheckFruitplr() then
								HopServer()
								wait(5)
								return
							end
						end
						if
							not CheckFruitplr()
							and (TakeFruitInventory(true))
							and Settings["Get Fruit In Inventory Low Beli"]
						then
							game:GetService("ReplicatedStorage").Remotes.CommF_
								:InvokeServer("LoadFruit", TakeFruitInventory(true))
						end
						game.ReplicatedStorage.Remotes.CommF_:InvokeServer("RaidsNpc", "Check")
						game.ReplicatedStorage.Remotes.CommF_:InvokeServer(
							"RaidsNpc",
							"Select",
							Settings["Select Raid"] or "Flame"
						)
						wait(1)
					end
				end)
				if E then
					print(E)
				end
			end
		end)
	end
	SaveSettings("Auto Raid", b)
end)
RaidsSection.CreateToggle(
	{ Title = "Hop Sever Raid", Desc = nil, Default = Settings["Hop Sever Raid"] or false },
	function(b)
		if b and not Settings["Auto Raid"] then
			A.CreateNoti({ Title = "Banana Cat Hub", Desc = "Turn On Auto Raid Plz", ShowTime = 5 })
		end
		SaveSettings("Hop Sever Raid", b)
	end
)
RaidsSection.CreateToggle(
	{ Title = "Auto Awake Fruit", Desc = nil, Default = Settings["Auto Awake Fruit"] or false },
	function(b)
		SaveSettings("Auto Awake Fruit", b)
	end
)
MultiRaidsSection = DFRaidMain.CreateSection("Multi Raid")
function DetectNamePlayerMulti()
	local b = {}
	for E, E in pairs(game:GetService("Players"):GetChildren()) do
		if E.Name ~= t.Name then
			b[E.Name] = false
		end
	end
	return b
end
DropdownSelectPlayerMultiRaid = MultiRaidsSection.CreateDropdown(
	{
		Title = "Select Player Multi Raid",
		List = PrepareMultiSelectList(DetectNamePlayerMulti(), Settings["Select Player Multi Raid"]),
		Search = true,
		Selected = true,
		Default = Settings["Select Player Multi Raid"] or nil,
	},
	function(b, E)
		SaveSettings("Select Player Multi Raid", b, E)
	end
)
MultiRaidsSection.CreateButton({ Title = "Refresh Player" }, function()
	DropdownSelectPlayerMultiRaid:GetNewList(DetectNamePlayerMulti())
end)
MultiRaidsSection.CreateToggle(
	{ Title = "Account Buy Chip", Desc = nil, Default = Settings["Account Buy Chip"] or false },
	function(b)
		SaveSettings("Account Buy Chip", b)
	end
)
MultiRaidsSection.CreateToggle(
	{ Title = "Account Pick Slot Raid", Desc = nil, Default = Settings["Account Pick Slot Raid"] or false },
	function(b)
		SaveSettings("Account Pick Slot Raid", b)
	end
)
function DetectSlotRaid(b)
	local E, l, y = next, b:GetChildren()
	for b, b in E, l, y do
		if b:FindFirstChild("Hitbox") and b.Color.BrickColor.Name ~= "Lime green" then
			return b
		end
	end
end
function NearSlotRaid(b)
	local E, l, y = next, b:GetChildren()
	for b, b in E, l, y do
		if b:FindFirstChild("Hitbox") then
			if t:DistanceFromCharacter(b.Hitbox.Position) < 10 then
				return true
			end
		end
	end
end
function DetectMultiStartRaid(b)
	local E = {}
	if Settings["Select Player Multi Raid"] then
		local l, y, P = next, b:GetChildren()
		for b, b in l, y, P do
			if b:FindFirstChild("Hitbox") then
				for l, y in next, Settings["Select Player Multi Raid"], nil do
					if game.Players[l]:DistanceFromCharacter(b.Hitbox.Position) > 10 then
						table.insert(E, l)
					end
				end
			end
		end
	end
	if #E == 0 then
		return true
	end
end
function Multiraid(b)
	local E = game.PlaceId == getgenv().CheckPlaceId2
		and (game:GetService("Workspace").Map.CircleIsland.RaidSummon2.Button:FindFirstChild("Main"))
	E = if game.PlaceId == getgenv().CheckPlaceId
		then game:GetService("Workspace").Map:FindFirstChild("Boat Castle")
			and (game:GetService("Workspace").Map["Boat Castle"].RaidSummon2.Button:FindFirstChild("Main"))
		else E
	if not t.PlayerGui.Main.TopHUDList.RaidTimer.Visible and not CheckInRaid() then
		if not E then
			if not DetectItemPlr("Special Microchip") then
				toTarget(CFrame.new(-5500, 314, -2855))
			else
				toTarget(CFrame.new(-5500, 314, -2855), false, true)
			end
			return
		end
	end
	if Settings["Account Pick Slot Raid"] then
		if
			not t.PlayerGui.Main.TopHUDList.RaidTimer.Visible
			and not CheckInRaid()
			and not NearSlotRaid(E.Parent.Parent)
		then
			local l = Random.new():NextNumber(0, 2)
			task.wait(l)
			toTarget(DetectSlotRaid(E.Parent.Parent).Hitbox.CFrame * CFrame.new(0, -2, 0))
		end
	end
	if DetectItemPlr("Special Microchip") then
		if getgenv().waitgoraid then
			wait(5)
			getgenv().waitgoraid = false
		end
		getgenv().buychip = false
		if DetectMultiStartRaid(E.Parent.Parent) and Settings["Account Buy Chip"] then
			fireclickdetector(E.ClickDetector)
		end
		if getgenv().Tween then
			getgenv().Tween:Pause()
			getgenv().Tween:Cancel()
		end
		return
	end
	if t.PlayerGui.Main.TopHUDList.RaidTimer.Visible and (CheckInRaid()) then
		getgenv().waitgoraid = true
		getgenv().buychip = true
		E = DetectMobRaid()
		if E then
			repeat
				task.wait()
				UsedualFlock()
				ClickM1(E)
				if Settings["Select Weapon"] == "Blox Fruit" then
					toTarget(E.HumanoidRootPart.CFrame * CFrame.new(-7, 20, 0))
				else
					toTarget(E.HumanoidRootPart.CFrame * CFrame.new(10, 20, 0))
				end
			until not IsMobAlive(E)
		else
			local E = GetLastRaidIsland()
			if E then
				if E.Name == "Island 2" and Settings["Select Raid"] == "Phoenix" then
					toTarget(E.CFrame * CFrame.new(300, 60, 0))
				else
					toTarget(E.CFrame * CFrame.new(0, 60, 0))
				end
			end
		end
		return
	end
	if
		Settings["Account Buy Chip"]
		and getgenv().buychip
		and t.Data.Level.Value >= 1100
		and not t.PlayerGui.Main.TopHUDList.RaidTimer.Visible
		and not DetectItemPlr("Special Microchip")
		and not CheckInRaid()
	then
		if not CheckFruitplr() and (TakeFruitInventory(true)) and Settings["Get Fruit In Inventory Low Beli"] then
			game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("LoadFruit", TakeFruitInventory(true))
		end
		game.ReplicatedStorage.Remotes.CommF_:InvokeServer("RaidsNpc", "Check")
		game.ReplicatedStorage.Remotes.CommF_:InvokeServer("RaidsNpc", "Select", b or "Flame")
		wait(1)
	end
end
MultiRaidsSection.CreateToggle(
	{ Title = "Auto Multi Raid", Desc = nil, Default = Settings["Auto Multi Raid"] or false },
	function(b)
		if b then
			spawn(function()
				while Settings["Auto Multi Raid"] and (task.wait(0.1)) do
					local E, E = pcall(function()
						Multiraid(Settings["Select Raid"])
					end)
					if E then
						print(E)
					end
				end
			end)
		end
		SaveSettings("Auto Multi Raid", b)
	end
)
local b = require(game:GetService("ReplicatedStorage").Controllers.BannerClient)
local function E()
	local l = b.TryGetBannerItemIfActiveAsync()
	if l and l.BoxName then
		return l.BoxName, l
	end
	return "DLCBoxData", nil
end
local function b()
	local l, y = game:GetService("ReplicatedStorage").Remotes.CommF_, E()
	local E, P, Y = l:InvokeServer("Cousin", "Check", y)
	if (P or 0) < 50 then
		warn("Ch\198\176a Lv50")
		return false
	end
	if (E or 0) < (Y or 1 / 0) then
		return false
	end
	if l:InvokeServer("Cousin", "CheckTime", y) ~= true then
		return false
	end
	if l:InvokeServer("Cousin", y) == 1 then
		return true
	end
	return false
end
function RandomFruit()
	b()
end
function DetectCountDF()
	local b = getbackpack()
	if #b < 1 then
		return
	end
	local E, l = t.Data.FruitCap.Value, B()
	for y, P in b, nil, nil do
		y = P:GetAttribute("OriginalName")
		for b, b in l, nil, nil do
			if b.Type == "Blox Fruit" and (b.Name == y and b.Count < E or b.Name ~= y) then
				return true
			end
		end
	end
end
local b = require(game:GetService("ReplicatedStorage").FruitInfo)
function StoreFruit(E)
	for l, y in pairs(E:GetChildren()) do
		if y:IsA("Tool") and (string.find(y.Name, "Fruit")) and not y:FindFirstChild("Ignored") then
			l = string.gsub(y.Name, " Fruit", "")
			local E
			E = y:GetAttribute("OriginalName") or l .. "-" .. l
			pcall(function()
				game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("StoreFruit", E, y)
			end)
			local l = Instance.new("IntValue")
			l.Name = "Ignored"
			l.Parent = y
			if
				Settings["Webhook Store Fruit"]
				and Settings["Select Rarity Fruit"]
				and (b.List[E] and Settings["Select Rarity Fruit"][b.List[E].Rarity.Name] or SkinFruit[y.Name])
			then
				getgenv().WebhookStoreFruit(y.Name)
			end
			task.wait(2)
		end
	end
end
function DetectFruitShop()
	local b, E, l = next, game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("GetFruits", false)
	for y, y in b, E, l do
		if Settings["Blox Fruit Sniper Shop"][y.Name] then
			if y.OnSale then
				return y.Name
			end
		end
	end
end
function BuyFruitShop()
	local b = DetectFruitShop()
	if not Settings["Blox Fruit Sniper Shop"][game:GetService("Players").LocalPlayer.Data.DevilFruit.Value] and b then
		game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("PurchaseRawFruit", b)
	end
end
DungeonJoinSection = DFRaidMain.CreateSection("Join Dungeon")
function DetectNamePlayer()
	local b = {}
	for E, E in pairs(game:GetService("Players"):GetChildren()) do
		if E.Name ~= t.Name and not table.find(b, E.Name) then
			table.insert(b, E.Name)
		end
	end
	return b
end
DropdownDropdownSelectAccountJoin = DungeonJoinSection.CreateDropdown(
	{
		Title = "Select Account Join",
		List = DetectNamePlayer(),
		Search = true,
		Selected = false,
		Default = Settings["Select Account Join"] or nil,
	},
	function(b)
		SaveSettings("Select Account Join", b)
	end
)
DungeonJoinSection.CreateButton({ Title = "Refresh Player" }, function()
	DropdownDropdownSelectAccountJoin:GetNewList(DetectNamePlayer())
end)
function DetectPadJoinDungeon(b)
	local E, l, y = next, workspace.Map["Simulation Hub"].Pads:GetChildren()
	for P, P in E, l, y do
		if
			b and P:GetAttribute("Initiator") == game.Players.LocalPlayer.UserId
			or P:GetAttribute("NumPlayersOnPad") == 0
		then
			return P
		end
	end
end
DungeonJoinSection.CreateSlider(
	{
		Title = "Min Player Join Dungeon",
		Min = 0,
		Max = 4,
		Default = Settings["Min Player Join Dungeon"] or 2,
		Precise = true,
	},
	function(b)
		SaveSettings("Min Player Join Dungeon", b)
	end
)
DungeonJoinSection.CreateDropdown(
	{
		Title = "Select Difficulty",
		List = { "Normal", "Hard", "Challenge" },
		Search = true,
		Selected = false,
		Default = Settings["Select Difficulty"] or nil,
	},
	function(b)
		SaveSettings("Select Difficulty", b)
	end
)
DungeonJoinSection.CreateToggle(
	{
		Title = "Account Start Dungeon",
		Desc = "Account Start Dungeon",
		Default = Settings["Account Start Dungeon"] or false,
	},
	function(b)
		SaveSettings("Account Start Dungeon", b)
	end
)
DungeonJoinSection.CreateToggle(
	{ Title = "Auto Join Dungeon", Desc = "Auto Join Dungeon", Default = Settings["Auto Join Dungeon"] or false },
	function(b)
		spawn(function()
			while Settings["Auto Join Dungeon"] and (task.wait()) do
				local E, E = pcall(function()
					if
						game:GetService("ReplicatedStorage").DungeonReplicationObjects:FindFirstChildWhichIsA("Folder")
					then
						return
					end
					if Settings["Account Start Dungeon"] then
						if
							not game:GetService("Players").LocalPlayer.PlayerGui
								:FindFirstChild("DungeonQueueSettingsMenu")
							or not game:GetService("Players").LocalPlayer.PlayerGui.DungeonQueueSettingsMenu.Enabled
						then
							local l = DetectPadJoinDungeon()
							if l then
								toTarget(l.PrimaryPart.CFrame * CFrame.new(0, 5, 0))
							end
						else
							local l = DetectPadJoinDungeon(true)
							local y, P =
								l and (l:GetAttribute("NumPlayersOnPad")) or 0,
								Settings["Select Difficulty"] or "Normal"
							if l:GetAttribute("Difficulty") ~= P then
								l.DungeonSettingsChanged:FireServer(unpack({ [1] = "Difficulty", [2] = P }))
							end
							if y >= Settings["Min Player Join Dungeon"] then
								l:FindFirstChild("DungeonSettingsChanged"):FireServer("Start")
								wait(2)
							end
						end
					elseif
						not game:GetService("Players").LocalPlayer.PlayerGui:FindFirstChild("DungeonQueueSettingsMenu")
						or not game:GetService("Players").LocalPlayer.PlayerGui.DungeonQueueSettingsMenu.Enabled
					then
						local l = game:GetService("Players"):FindFirstChild(Settings["Select Account Join"] or "")
						if l then
							toTarget(l.Character.HumanoidRootPart.CFrame)
						end
					end
				end)
				if E then
					print(E)
				end
			end
		end)
		SaveSettings("Auto Join Dungeon", b)
	end
)
DungeonSection = DFRaidMain.CreateSection("Dungeon")
DungeonSection.CreateDropdown(
	{
		Title = "Select Weapon Dungeon",
		List = { "Melee", "Sword", "Blox Fruit", "Gun" },
		Search = true,
		Selected = false,
		Default = Settings["Select Weapon Dungeon"] or nil,
	},
	function(b)
		SaveSettings("Select Weapon Dungeon", b)
	end
)
function GetInfoDungeon(b)
	local E = game.ReplicatedStorage:WaitForChild("DungeonReplicationObjects"):FindFirstChild(b, true)
	if E then
		return E
	end
end
function GetCurrentFloor()
	local b = t:GetAttribute("ExplorerGUID")
	local E = b and (GetInfoDungeon(b))
	if E then
		return E:GetAttribute("FloorId")
	end
end
function GetHightFloor()
	local b = t:GetAttribute("ExplorerGUID")
	local E = b and (GetInfoDungeon(b))
	if E then
		return E.Parent.Parent:GetAttribute("CurrentExploredLevel")
	end
end
function IsPointInsideModel(b, E)
	if not b or not b:IsA("Model") then
		return false
	end
	local l, y = b:GetBoundingBox()
	local b, P = l:PointToObjectSpace(E), y * 0.5
	return math.abs(b.X) <= P.X and math.abs(b.Y) <= P.Y and math.abs(b.Z) <= P.Z
end
function DetectMobDungeon()
	local b = t.Character
	local E = b and (b:FindFirstChild("HumanoidRootPart"))
	if not E then
		return nil
	end
	b = GetHightFloor()
	if not b then
		return nil
	end
	local l = workspace.Map.Dungeon:FindFirstChild(tostring(b))
	if not l then
		return nil
	end
	local y, P = 1 / 0
	for Y, H in ipairs(workspace.Enemies:GetChildren()) do
		if IsMobAlive(H) and H.Name ~= "Blank Buddy" then
			Y = H:FindFirstChild("HumanoidRootPart")
			H:FindFirstChildOfClass("Humanoid")
			if IsPointInsideModel(l, Y.Position) then
				b = (Y.Position - E.Position).Magnitude
				if b < y then
					y, P = b, H
				end
			end
		end
	end
	return P
end
function DetectPropHitboxPlaceholder()
	local b = t.Character
	local E = b and (b:FindFirstChild("HumanoidRootPart"))
	if not E then
		return nil
	end
	b = GetHightFloor()
	if not b then
		return nil
	end
	local l = workspace.Map.Dungeon:FindFirstChild(tostring(b))
	if not l then
		return nil
	end
	local y, P = 1 / 0
	for Y, H in ipairs(workspace.Enemies:GetChildren()) do
		if IsMobAlive(H) and H.Name == "PropHitboxPlaceholder" then
			b = H:FindFirstChild("HumanoidRootPart")
			H:FindFirstChildOfClass("Humanoid")
			if IsPointInsideModel(l, b.Position) then
				Y = (b.Position - E.Position).Magnitude
				if Y < y then
					y, P = Y, H
				end
			end
		end
	end
	return P
end
ExplorerBuffs = require(game:GetService("ReplicatedStorage").DungeonShared.ExplorerBuffs)
function stripFont(b)
	return (b:gsub("<.->", ""))
end
DisplayNameToKey = {}
for b, E in pairs(ExplorerBuffs.ExplorerBuffs) do
	if E.DisplayName then
		DisplayNameToKey[stripFont(E.DisplayName)] = b
	end
end
CORE_BUFF_KEYS = {
	"Lifesteal",
	"AllCooldown",
	"AttackSpeedMultiplier",
	"FruitTAPCooldown",
	"Armor",
	"Sniper",
	"Overflow",
	"Gun",
	"Sword",
	"Melee",
	"Fruit",
	"Defense",
}
TableCardpriority = {}
for b, E in ipairs(CORE_BUFF_KEYS) do
	b = ExplorerBuffs.ExplorerBuffs[E]
	if b and b.DisplayName then
		table.insert(TableCardpriority, stripFont(b.DisplayName))
	end
end
function BuildPriorityMap(b)
	local E = {}
	for l, y in ipairs(b) do
		l = DisplayNameToKey[y]
		if l then
			E[l] = true
		end
	end
	return E
end
function IsSkillCooldown(b)
	if not b then
		return false
	end
	if b:find("Cooldown") then
		if b:find("ZCooldown") or (b:find("XCooldown")) or (b:find("CCooldown")) or (b:find("VCooldown")) then
			return true
		end
	end
	return false
end
DungeonSection.CreateDropdown(
	{
		Title = "Select Card Priority",
		List = TableCardpriority,
		Search = true,
		Priority = true,
		Default = Settings["Select Card Priority"] or {},
	},
	function(b)
		if typeof(b) ~= "table" then
			return
		end
		SaveSettings("Select Card Priority", table.clone(b))
	end
)
function AutoPickDungeonCard()
	local b, E, l, y = Settings["Select Card Priority"] or {}, {}, 1 / 0
	for P, Y in pairs(t.PlayerGui:GetChildren()) do
		local H, C, J =
			Y:FindFirstChild("DisplayName", true),
			Y:FindFirstChild("BuffDescription", true),
			Y:FindFirstChildWhichIsA("TextButton", true)
		if H and C and J and (H:IsA("TextLabel")) then
			P = DisplayNameToKey[stripFont(H.Text)]
			if P then
				if IsSkillCooldown(P) then
					continue
				end
				for Y, H in ipairs(b) do
					if DisplayNameToKey[H] == P then
						if Y < l then
							l, y = Y, J
						end
						break
					end
				end
				table.insert(E, J)
			end
		end
	end
	if y then
		print("AUTO PICK (PRIORITY INDEX):", l)
		for l, l in pairs(getconnections(y.Activated)) do
			l.Function()
		end
		return true
	end
	if #E > 0 then
		b = E[math.random(1, #E)]
		print("AUTO PICK (RANDOM)")
		for E, E in pairs(getconnections(b.Activated)) do
			E.Function()
		end
		return true
	end
	return false
end
DungeonSection.CreateToggle(
	{
		Title = "Auto Attack Dungeon",
		Desc = "Auto Attack Mob and go next Floor",
		Default = Settings["Auto Attack Dungeon"] or false,
	},
	function(b)
		SaveSettings("Auto Attack Dungeon", b)
		if not b then
			return
		end
		task.spawn(function()
			while Settings["Auto Attack Dungeon"] do
				task.wait()
				local b, b = pcall(function()
					if t.Character.Humanoid.Health <= 0 then
						return
					end
					local E, l = GetCurrentFloor(), GetHightFloor()
					if not E or not l then
						return
					end
					if E ~= l then
						getgenv().AutoDungeonNextFloor = true
						local y = l - 1
						local P = workspace.Map.Dungeon:FindFirstChild(tostring(y))
						if
							P
							and (P:FindFirstChild("ExitTeleporter"))
							and (P.ExitTeleporter:FindFirstChild("Root"))
							and (P.ExitTeleporter.Root:FindFirstChild("TouchInterest"))
						then
							if t:DistanceFromCharacter(P.ExitTeleporter.Root.Position) > 15 then
								task.wait(1)
								toTarget(P.ExitTeleporter.Root.CFrame * CFrame.new(0, 5, 0))
							else
								task.wait(3)
							end
						end
						return
					end
					if getgenv().AutoDungeonNextFloor then
						TweenManager.CancelCurrent()
						getgenv().AutoDungeonNextFloor = false
					end
					l, E = DetectMobDungeon(), DetectPropHitboxPlaceholder()
					if not l or not IsMobAlive(l) then
						return
					end
					if E then
						repeat
							task.wait()
							if not Settings["Auto Attack Dungeon"] then
								break
							end
							if not IsMobAlive(E) then
								break
							end
							if not GetCurrentFloor() or GetCurrentFloor() ~= GetHightFloor() then
								break
							end
							local y = Settings["Select Weapon Dungeon"] or "Melee"
							equiptool(NameWeapon(y))
							if y == "Gun" then
								if NameWeapon(y) == "Dragonstorm" then
									SpamGunDragonStorm(E.HumanoidRootPart)
								else
									ShootM1(E)
								end
							else
								ClickM1Dungeon(E)
							end
							sizepart(E)
							if y == "Blox Fruit" then
								toTarget(E.HumanoidRootPart.CFrame * CFrame.new(-7, 12, 0))
							else
								toTarget(E.HumanoidRootPart.CFrame * CFrame.new(10, 20, 0))
							end
						until t.Character.Humanoid.Health <= 0
					else
						repeat
							task.wait()
							if not Settings["Auto Attack Dungeon"] then
								break
							end
							if not IsMobAlive(l) then
								break
							end
							if not GetCurrentFloor() or GetCurrentFloor() ~= GetHightFloor() then
								break
							end
							local E = Settings["Select Weapon Dungeon"] or "Melee"
							equiptool(NameWeapon(E))
							if E == "Gun" then
								if NameWeapon(E) == "Dragonstorm" then
									SpamGunDragonStorm(l.HumanoidRootPart)
								else
									ShootM1(l)
								end
							else
								ClickM1Dungeon(l)
							end
							sizepart(l)
							if E == "Blox Fruit" then
								toTarget(l.HumanoidRootPart.CFrame * CFrame.new(-7, 12, 0))
							else
								toTarget(l.HumanoidRootPart.CFrame * CFrame.new(10, 20, 0))
							end
						until t.Character.Humanoid.Health <= 0 or (DetectPropHitboxPlaceholder())
					end
				end)
				if b then
					warn("[Auto Dungeon Error]:", b)
				end
			end
		end)
	end
)
DungeonSection.CreateToggle(
	{ Title = "Auto Pick Card Dungeon", Desc = nil, Default = Settings["Auto Pick Card Dungeon"] or false },
	function(b)
		SaveSettings("Auto Pick Card Dungeon", b)
		if not b then
			return
		end
		task.spawn(function()
			while Settings["Auto Pick Card Dungeon"] do
				task.wait()
				local b, b = pcall(function()
					AutoPickDungeonCard()
				end)
				if b then
					warn("[Auto Pick Card Dungeon Error]:", b)
				end
			end
		end)
	end
)
local b, E =
	{
		["Zone 1"] = CFrame.new(-21767.4765625, 0, 5815.41259765625),
		["Zone 2"] = CFrame.new(-26017.931640625, 0, 5657.8837890625),
		["Zone 3"] = CFrame.new(-29545.703125, 0, 6377.98974609375),
		["Zone 4"] = CFrame.new(-33609.7578125, 0, 7422.890625),
		["Zone 5"] = CFrame.new(-38480.42578125, 0, 10350.943359375),
		["Zone 6"] = CFrame.new(-32975.9921875, 0, 25963.7109375),
	},
	{ Melee = false, Sword = false, Gun = false, ["Blox Fruit"] = false }
SeaEventTab = Main.CreatePage({ Page_Name = "Sea Event", Page_Title = "Sea Event Tab" })
SettingSeaEventSection = SeaEventTab.CreateSection("Setting")
SettingSeaEventSection.CreateDropdown(
	{
		Title = "Select Zone",
		List = { "Zone 1", "Zone 2", "Zone 3", "Zone 4", "Zone 5", "Zone 6" },
		Search = true,
		Selected = false,
		Default = Settings["Select Zone"] or nil,
	},
	function(l)
		SaveSettings("Select Zone", l)
	end
)
SettingSeaEventSection.CreateDropdown(
	{
		Title = "Select Sea Events",
		List = PrepareMultiSelectList(
			{
				SeaBeast = false,
				Ship = false,
				Shark = false,
				Terrorshark = false,
				Piranha = false,
				["Only Farm Ship Brigade"] = false,
			},
			Settings["Select Sea Events"]
		),
		Search = true,
		Selected = true,
		Default = Settings["Select Sea Events"] or nil,
	},
	function(l, y)
		SaveSettings("Select Sea Events", l, y)
	end
)
SettingSeaEventSection.CreateDropdown(
	{
		Title = "Select Boat",
		List = { "Beast Hunter", "Guardian", "Lantern", "Seleigh", "Brigade", "GrandBrigade" },
		Search = true,
		Selected = false,
		Default = Settings["Select Boat"] or nil,
	},
	function(l)
		SaveSettings("Select Boat", l)
	end
)
SettingSeaEventSection.CreateDropdown(
	{
		Title = "Select Weapons Use Skill",
		List = PrepareMultiSelectList(E, Settings["Select Weapons Use Skill"]),
		Search = true,
		Selected = true,
		Default = Settings["Select Weapons Use Skill"] or nil,
	},
	function(l, y)
		SaveSettings("Select Weapons Use Skill", l, y)
	end
)
SettingSeaEventSection.CreateToggle(
	{
		Title = "Use Dragonstorm For Sea Event",
		Desc = "Only Farm Boat and Fish and TerrorShark",
		Default = Settings["Use Dragonstorm For Sea Event"] or false,
	},
	function(l)
		SaveSettings("Use Dragonstorm For Sea Event", l)
	end
)
SettingSeaEventSection.CreateToggle(
	{
		Title = "Use Click M1 Skull Guitar For Sea Event",
		Desc = "Only Farm Boat and Seabeast",
		Default = Settings["Use Click M1 Skull Guitar For Sea Event"] or false,
	},
	function(l)
		SaveSettings("Use Click M1 Skull Guitar For Sea Event", l)
	end
)
SettingSeaEventSection.CreateToggle(
	{
		Title = "Auto Change Dragonstorm With Skull Guitar",
		Desc = "When Kill Boat and Fish and TerrorShark use Dragonstorm\10Kill Seabeast use Seabeast",
		Default = Settings["Auto Change Dragonstorm With Skull Guitar"] or false,
	},
	function(l)
		SaveSettings("Auto Change Dragonstorm With Skull Guitar", l)
	end
)
SettingSeaEventSection.CreateToggle(
	{
		Title = "Auto Change Dragonstorm When Kill Boat",
		Desc = nil,
		Default = Settings["Auto Change Dragonstorm When Kill Boat"] or false,
	},
	function(l)
		SaveSettings("Auto Change Dragonstorm When Kill Boat", l)
	end
)
SettingSeaEventSection.CreateToggle(
	{
		Title = "Use Click M1 Fruit For Sea Event",
		Desc = nil,
		Default = Settings["Use Click M1 Fruit For Sea Event"] or false,
	},
	function(l)
		SaveSettings("Use Click M1 Fruit For Sea Event", l)
	end
)
SettingSeaEventSection.CreateToggle(
	{
		Title = "Reset Character Buy Boat",
		Desc = "if u spawn in tiki it will reset for buy boat",
		Default = Settings["Reset Character Buy Boat"] or false,
	},
	function(l)
		SaveSettings("Reset Character Buy Boat", l)
	end
)
SettingSeaEventSection.CreateToggle(
	{ Title = "Auto Dodge Skill Terrorshark", Desc = nil, Default = Settings["Auto Dodge Skill Terrorshark"] or false },
	function(l)
		SaveSettings("Auto Dodge Skill Terrorshark", l)
	end
)
local l = { "rbxassetid://8708221792", "rbxassetid://8708222556" }
game.workspace._WorldOrigin.ChildAdded:Connect(function(y)
	if
		(Settings["Auto Sea Event"] or Settings["Auto Shipwright"])
		and Settings["Auto Dodge Skill Terrorshark"]
		and getgenv().PathTerrorshark
	then
		if
			y:IsA("Part")
			and (y.Name == "SharkSplash" or y.Name == "ChargeUp")
			and (getgenv().PathTerrorshark.HumanoidRootPart.Position - y.Position).Magnitude < 20
		then
			getgenv().Doding = true
			getgenv().ReadyToDodge = true
			local P = tick()
			repeat
				wait(0.2)
			until not y or not y.Parent or tick() - P > 14
			if tick() - P < 1 then
				wait(2.5)
			end
			getgenv().Doding = false
			getgenv().ReadyToDodge = false
		end
	end
end)
getgenv().PosDodgeskill = 0
function AddAnimationSeabeastPlayed(y)
	getgenv().PathAnimationSeabit = y.Humanoid.AnimationPlayed:Connect(function(y)
		if table.find(l, tostring(y.Animation.AnimationId)) then
			getgenv().PosDodgeskill = 0
			if tostring(y.Animation.AnimationId) == "rbxassetid://8708222556" then
				task.wait(0.7)
			else
				task.wait(1.9)
			end
			local l = tick()
			getgenv().PosDodgeskill = 600
			repeat
				task.wait()
			until not y.IsPlaying or tick() - l >= 10
			getgenv().PosDodgeskill = 0
		end
	end)
end
SettingSeaEventSection.CreateToggle(
	{
		Title = "Auto Dodge Skill Seabeast",
		Desc = "Dodge Only Skill Kameha and waterbeam",
		Default = Settings["Auto Dodge Skill Seabeast"] or false,
	},
	function(l)
		if l then
			spawn(function()
				while Settings["Auto Dodge Skill Seabeast"] and (task.wait(0.15)) do
					pcall(function()
						if getgenv().PathSeaBeast then
							local y = getgenv().PathSeaBeast
							spawn(function()
								AddAnimationSeabeastPlayed(y)
							end)
							repeat
								wait(0.1)
							until not y
								or not y.Parent
								or getgenv().PathSeaBeast ~= y
								or not Settings["Auto Dodge Skill Seabeast"]
							if getgenv().PathAnimationSeabit then
								getgenv().PathAnimationSeabit:Disconnect()
							end
						end
					end)
				end
			end)
		end
		SaveSettings("Auto Dodge Skill Seabeast", l)
	end
)
SettingSeaEventSection.CreateToggle(
	{
		Title = "Teleport Boat Other CFrame if Rough Sea",
		Desc = nil,
		Default = Settings["Teleport Boat Other CFrame if Rough Sea"] or false,
	},
	function(l)
		SaveSettings("Teleport Boat Other CFrame if Rough Sea", l)
	end
)
SettingSeaEventSection.CreateToggle(
	{
		Title = "Tween Until Have Sea Event",
		Desc = "When there's a sea event, it will stop to fight, and after finishing the fight, it will continue tweening",
		Default = Settings["Tween Until Have Sea Event"] or false,
	},
	function(l)
		SaveSettings("Tween Until Have Sea Event", l)
	end
)
SettingSeaEventSection.CreateToggle(
	{ Title = "Will Back When over 10km", Desc = nil, Default = Settings["Will Back When over 10km"] or false },
	function(l)
		SaveSettings("Will Back When over 10km", l)
	end
)
local function l(y)
	local P = t and t.Character
	if not P then
		return
	end
	for Y, Y in ipairs(P:GetDescendants()) do
		if Y:IsA("BasePart") then
			Y.CanCollide = not y
		end
	end
end
local y, P, Y = setmetatable({}, { __mode = "k" }), 0, getgenv().BoatSpeed
if type(Y) ~= "table" then
	Y = { cap = 100, ceiling = 1 / 0, nextRaise = 0 }
	getgenv().BoatSpeed = Y
end
local H = 5
local function C()
	local J, F = pcall(function()
		return game:GetService("Stats").Network.ServerStatsItem["Data Ping"]:GetValue()
	end)
	return J and F / 1000 or 0.1
end
function manageTween(J, F, q, c)
	if not J or not J:IsA("BasePart") or typeof(F) ~= "CFrame" then
		return
	end
	q, c = math.max(tonumber(Settings["Value Speed Tween Boat"]) or (tonumber(q)) or 350, 1), c or "TweenBoat"
	if not y[J] and (J.Position - F.Position).Magnitude <= H then
		return
	end
	local D = y[J]
	if D and D.TweenKey == c and D.PlaybackState == Enum.PlaybackState.Playing then
		D.Target = F
		D.Speed = q
		getgenv()[c] = D
		return D
	end
	if D then
		D:Cancel()
	end
	local D = getgenv()[c]
	if D then
		pcall(function()
			D:Cancel()
		end)
	end
	local D, r, n, u, W =
		{ PlaybackState = Enum.PlaybackState.Playing, Speed = q, Target = F, TweenKey = c },
		false,
		false,
		false,
		J.CFrame
	local function F(q)
		if u then
			return
		end
		u = true
		D.PlaybackState = q
		P = math.max(P - 1, 0)
		if y[J] == D then
			y[J] = nil
		end
		if getgenv()[c] == D then
			getgenv()[c] = nil
		end
		if P == 0 and not (type(ToggleNoclip) == "function" and ToggleNoclip() == true) then
			l(false)
			getgenv().noclip = false
		end
	end
	D.Play = function(q)
		if u then
			return
		end
		n = false
		q.PlaybackState = Enum.PlaybackState.Playing
	end
	D.Pause = function(q)
		if u then
			return
		end
		n = true
		q.PlaybackState = Enum.PlaybackState.Paused
	end
	D.Cancel = function(q)
		if u then
			return
		end
		r = true
		F(Enum.PlaybackState.Cancelled)
	end
	D.Destroy = function(q)
		q:Cancel()
	end
	y[J] = D
	getgenv()[c] = D
	P += 1
	l(true)
	getgenv().noclip = true
	task.spawn(function()
		while not r and not u and J.Parent do
			local l = x.Heartbeat:Wait()
			if not n then
				local y = t.Character and (t.Character:FindFirstChildOfClass("Humanoid"))
				if not y or y.SeatPart ~= J then
					WarnOnce(
						"BoatNotSeated",
						"Chua ngoi tren ghe thuyen nen server khong nhan vi tri tween. Da dung tween."
					)
					F(Enum.PlaybackState.Cancelled)
					break
				end
				local y, P = math.min(D.Speed, Y.cap), D.Target
				local q, c = (P.Position - W.Position).Magnitude, y * l
				if (J.Position - W.Position).Magnitude > math.max(20, c * 3) then
					Y.ceiling = y * 0.9
					Y.cap = math.max(y * 0.7, 40)
					Y.nextRaise = tick() + math.max(C() * 4, 1)
					W = J.CFrame
					c, q = Y.cap * l, (P.Position - W.Position).Magnitude
				elseif q > c and Y.cap <= D.Speed and Y.cap < Y.ceiling and tick() >= Y.nextRaise then
					Y.cap = math.min(Y.cap * 1.08, Y.ceiling)
					Y.nextRaise = tick() + math.max(C() * 4, 1)
				end
				if q <= c or q <= H then
					W = P
					J.CFrame = P
					J.AssemblyLinearVelocity = Vector3.new(0.0, 0.0, 0.0)
					J.AssemblyAngularVelocity = Vector3.new(0.0, 0.0, 0.0)
					F(Enum.PlaybackState.Completed)
					break
				end
				W = W:Lerp(P, c / q)
				J.CFrame = W
				J.AssemblyLinearVelocity = Vector3.new(0.0, 0.0, 0.0)
				J.AssemblyAngularVelocity = Vector3.new(0.0, 0.0, 0.0)
			end
		end
		if not u then
			F(Enum.PlaybackState.Cancelled)
		end
	end)
	return D
end
local function l(y, P, Y)
	if not (y and (y:FindFirstChild("VehicleSeat"))) then
		return
	end
	return manageTween(y.VehicleSeat, P, Y or 350, "TweenBoat")
end
local function y()
	local P = getgenv().TweenBoat
	if P then
		pcall(function()
			P:Cancel()
		end)
	end
	getgenv().TweenBoat = nil
end
function SpinBoat()
	local P = checkboat()
	if
		getgenv().PathSpinBoat
		and P
		and not Settings["Auto Sea Event With Friend"]
		and game.PlaceId == getgenv().CheckPlaceId
		and not t.Character.Humanoid.Sit
	then
		RoughSeaSpin = Settings["Teleport Boat Other CFrame if Rough Sea"] and V or 0
		local Y, H =
			SelectedZoneCFrame() * CFrame.new(0, P.WorldPivot.Y, 0 + RoughSeaSpin) * CFrameSpinBoat[NumberSpinBoat],
			tick()
		local C = l(P, Y, 300)
		repeat
			task.wait()
		until tick() - H >= 3
			or not getgenv().PathSpinBoat
			or not Settings["Auto Sea Event"]
			or not C
			or C.PlaybackState == Enum.PlaybackState.Completed
		if NumberSpinBoat >= 6 then
			NumberSpinBoat = 1
		else
			NumberSpinBoat += 1
		end
	end
end
function NoclipBoat(P)
	for Y, Y in ipairs(P:GetDescendants()) do
		if (Y:IsA("BasePart") or (Y:IsA("Part")) or (Y:IsA("MeshPart"))) and Y.CanCollide then
			Y.CanCollide = false
		end
	end
end
function TurnOffNoclipBoat(P)
	for Y, Y in ipairs(P:GetDescendants()) do
		if (Y:IsA("BasePart") or (Y:IsA("Part")) or (Y:IsA("MeshPart"))) and not Y.CanCollide then
			Y.CanCollide = true
		end
	end
end
function BuyBoatAndTeleBoat(P)
	local Y = checkboat()
	if Settings["Auto Sea Event With Friend"] and Settings["Auto Sea Event"] then
		toTarget(game:GetService("Players")[Settings["Select Friend"]].Character.HumanoidRootPart.CFrame)
		return
	end
	if not Settings["Auto Sea Event"] and not P then
		return
	end
	if not Y or Y and t:DistanceFromCharacter(Y.VehicleSeat.Position) >= 4000 then
		local H = CFrame.new(-13.488054275512695, 10.311711311340332, 2927.692)
		H = if game.PlaceId == getgenv().CheckPlaceId
			then (CFrame.new(-16204.0810546875, 9.0863618850708, 479.2259521484375))
			else H
		if (H.Position - t.Character.HumanoidRootPart.Position).Magnitude > 8 then
			if
				(H.Position - t.Character.HumanoidRootPart.Position).Magnitude > 1000
				and game.PlaceId == getgenv().CheckPlaceId
			then
				if Settings["Reset Character Buy Boat"] then
					if not t:GetAttribute("CurrentLocation") or t:GetAttribute("CurrentLocation") ~= "Tiki Outpost" then
						if
							game:GetService("Players").LocalPlayer.Data.LastSpawnPoint.Value == "Tiki"
							or game:GetService("Players").LocalPlayer.Data.LastSpawnPoint.Value == "Tiki2"
						then
							t.Character.Humanoid.Health = 0
							return
						end
					end
				end
			end
			toTarget(H)
		else
			local H = Settings["Select Boat"]
			if not H then
				WarnOnce("SelectBoat", "Chon thuyen o Sea Event > Select Boat truoc da.")
				return
			end
			local C = H == "Brigade"
			game:GetService("ReplicatedStorage").Remotes.CommF_
				:InvokeServer("BuyBoat", if C or H == "GrandBrigade" then "Pirate" .. H else H)
			task.wait(3)
		end
	else
		task.spawn(function()
			NoclipBoat(Y)
		end)
		if Settings["Tween Until Have Sea Event"] then
			local H = CFrame.new(-118834.515625, Y.WorldPivot.Y, 999920.0494155884)
			if not t.Character.Humanoid.Sit then
				toTarget(Y.VehicleSeat.CFrame)
			else
				l(Y, H, 350)
			end
		else
			local H, C = CFrame.new(654.3875732421875, Y.WorldPivot.Y, 6321.95947265625), DecectPartRoughSea()
			if C then
				task.wait(1)
				V = if V == 0 then 7000 else 0
				Instance.new("IntValue", C).Name = "Ignored"
				task.wait(0.5)
			end
			getgenv().RoughSea = Settings["Teleport Boat Other CFrame if Rough Sea"] and V or 0
			H = if game.PlaceId == getgenv().CheckPlaceId
				then SelectedZoneCFrame() * CFrame.new(0, Y.WorldPivot.Y, 0 + RoughSea)
				else H
			if (Y.VehicleSeat.Position - H.Position).Magnitude > 200 then
				C = CFrame.new(H.Position.X, Y.WorldPivot.Y, H.Position.Z)
				if not t.Character.Humanoid.Sit then
					toTarget(Y.VehicleSeat.CFrame)
				else
					l(Y, C, 350)
				end
			else
				if Settings["Auto Repair Ur Ship"] then
					if t.PlayerGui.Main.BottomHUDList.ShipHealthBar.Visible then
						local C = string.gsub(
							game:GetService("Players").LocalPlayer.PlayerGui.Main.BottomHUDList.ShipHealthBar.TextLabel.Text,
							"Ship ",
							""
						)
						C = string.split(C, "/")
						if tonumber(C[1]) < tonumber(C[2]) then
							if t:DistanceFromCharacter(Y.PrimaryPart.Position) < 20 then
								if not t.Character.Humanoid.Sit then
									if t.Character:FindFirstChild("_RepairHammer") then
										if t.Character._RepairHammer:FindFirstChild("M1UP") then
											t.Character._RepairHammer.M1UP:Destroy()
										elseif not t.Character._RepairHammer:GetAttribute("Repairing") then
											t.Character._RepairHammer.M1Down:FireServer("Default")
											task.wait(0.5)
										end
									else
										game:GetService("ReplicatedStorage").Remotes.SubclassNetwork.UseSubclass
											:InvokeServer(unpack({ [1] = { Action = "RequestHammer" } }))
										task.wait(3)
									end
								else
									toTarget(Y.PrimaryPart.CFrame * CFrame.new(0, 15, 0))
								end
							else
								toTarget(Y.PrimaryPart.CFrame * CFrame.new(0, 15, 0))
							end
							return
						end
					end
				end
				if not P then
					if not t.Character.Humanoid.Sit then
						toTarget(Y.VehicleSeat.CFrame)
					end
					local P = CFrame.new(H.Position.X, Y.WorldPivot.Y, H.Position.Z)
					if DetectSeaEvents(true) then
						local H = tick()
						repeat
							task.wait()
							toTarget(P * CFrame.new(0, 2500, 0))
						until tick() - H >= 12
					elseif t.Character.Humanoid.Sit then
						l(Y, P, 350)
					end
				end
			end
		end
	end
end
function SafeMultiSelect(l)
	local P = Settings[l]
	if type(P) ~= "table" then
		P = {}
		Settings[l] = P
	end
	return P
end
function SelectedZoneCFrame()
	local l = Settings["Select Zone"]
	return l and b[l] or b["Zone 1"]
end
function WarnOnce(b, l)
	getgenv().__BFWarned = getgenv().__BFWarned or {}
	local P = getgenv().__BFWarned[b]
	if P and tick() - P < 15 then
		return
	end
	getgenv().__BFWarned[b] = tick()
	pcall(function()
		A.CreateNoti({ Title = "Banana Cat Hub", Desc = l, ShowTime = 5 })
	end)
end
function DetectSeaEvents(b)
	local l = SafeMultiSelect("Select Sea Events")
	if b or l.SeaBeast then
		local P, Y, H = next, game:GetService("Workspace").SeaBeasts:GetChildren()
		for C, C in P, Y, H do
			if C.Name == "SeaBeast1" and (C:FindFirstChild("HumanoidRootPart")) and (C:FindFirstChild("HealthBBG")) then
				local P, Y = C.HealthBBG.Frame.TextLabel.Text:gsub("/%d+,%d+", ""), C.HealthBBG.Frame.TextLabel.Text
				if
					tonumber(
							(
								(if string.find(P, ",") then (Y:gsub("%d+,%d+/", "")) else (Y:gsub("%d+/", ""))):gsub(
									",",
									""
								)
							)
						)
						>= 90000
					and t:DistanceFromCharacter(C.HumanoidRootPart.Position) < 2000
				then
					return C
				end
			end
		end
	end
	if b or l.Terrorshark then
		local P = CheckNameBoss("Terrorshark")
		if P and t:DistanceFromCharacter(P.HumanoidRootPart.Position) < 2000 then
			return P
		end
	end
	if b or l.Ship then
		local P, Y, H = next, game:GetService("Workspace").Enemies:GetChildren()
		for C, C in P, Y, H do
			if
				C:FindFirstChild("Engine")
				and (C:FindFirstChild("Health"))
				and C.Health.Value > 0
				and t:DistanceFromCharacter(C.Engine.Position) < 2000
			then
				if l["Only Farm Ship Brigade"] then
					if table.find(X, C.Name) then
						return C
					end
				else
					return C
				end
			end
		end
	end
	if b or l.Shark then
		local X = DetectMob(_)
		if X and t:DistanceFromCharacter(X.HumanoidRootPart.Position) < 2000 then
			return X
		end
	end
	if b or l.Piranha then
		local b = DetectMob("Piranha")
		if b and t:DistanceFromCharacter(b.HumanoidRootPart.Position) < 2000 then
			return b
		end
	end
	return false
end
function UseSkillGun()
	local b = NameWeapon("Gun", true) or false
	if b and not game:GetService("Players").LocalPlayer.PlayerGui.Main.Skills:FindFirstChild(b.Name) then
		equiptool(b.Name)
		return
	end
	local X = if b and (CheckCDSkillTransformation(b, Settings["Select Skills " .. b.ToolTip]))
		then (CheckCDSkillTransformation(b, Settings["Select Skills " .. b.ToolTip]))
		else nil
	if X then
		b = X.Parent.Name
		equiptool(b)
		if t.Character:FindFirstChild(b) then
			task.wait(0.2)
			game:GetService("VirtualInputManager"):SendKeyEvent(true, X.Name, false, game)
			if Settings["Use skill fast dont hold"] then
				task.wait(0.05)
			else
				task.wait(tonumber(holdskill))
			end
			game:GetService("VirtualInputManager"):SendKeyEvent(false, X.Name, false, game)
		end
	end
end
function AutoUseSkillSeabeast(b)
	b = SafeMultiSelect("Select Weapons Use Skill")
	local X, l, _, P, Y =
		b.Melee and (NameWeapon("Melee", true)) or false,
		b.Sword and (NameWeapon("Sword", true)) or false,
		b["Blox Fruit"] and (NameWeapon("Blox Fruit", true)) or false,
		b.Gun and (NameWeapon("Gun", true)) or false,
		game:GetService("Players").LocalPlayer.PlayerGui.Main.Skills
	if X and not Y:FindFirstChild(X.Name) then
		equiptool(X.Name)
		return
	end
	if l and not Y:FindFirstChild(l.Name) then
		equiptool(l.Name)
		return
	end
	if _ and not Y:FindFirstChild(_.Name) then
		equiptool(_.Name)
		return
	end
	if P and not Y:FindFirstChild(P.Name) then
		equiptool(P.Name)
		return
	end
	Y = if X and (CheckCDSkillTransformation(X, Settings["Select Skills " .. X.ToolTip]))
		then (CheckCDSkillTransformation(X, Settings["Select Skills " .. X.ToolTip]))
		else if l and (CheckCDSkillTransformation(l, Settings["Select Skills " .. l.ToolTip]))
			then (CheckCDSkillTransformation(l, Settings["Select Skills " .. l.ToolTip]))
			else if P and (CheckCDSkillTransformation(P, Settings["Select Skills " .. P.ToolTip]))
				then (CheckCDSkillTransformation(P, Settings["Select Skills " .. P.ToolTip]))
				else if _ and (CheckCDSkillTransformation(_, Settings["Select Skills " .. _.ToolTip]))
					then (CheckCDSkillTransformation(_, Settings["Select Skills " .. _.ToolTip]))
					else nil
	if Y then
		X = Y.Parent.Name
		equiptool(X)
		if t.Character:FindFirstChild(X) then
			game:GetService("VirtualInputManager"):SendKeyEvent(true, Y.Name, false, game)
			if Settings["Use skill fast dont hold"] then
				task.wait(0.05)
			else
				task.wait(tonumber(holdskill))
			end
			game:GetService("VirtualInputManager"):SendKeyEvent(false, Y.Name, false, game)
		end
	end
end
function UseSkillonlyFruit()
	local b = NameWeapon("Blox Fruit", true)
	if b and not game:GetService("Players").LocalPlayer.PlayerGui.Main.Skills:FindFirstChild(b.Name) then
		equiptool(b.Name)
		return
	end
	local X = if b and (CheckCDSkillTransformation(b, Settings["Select Skills " .. b.ToolTip]))
		then (CheckCDSkillTransformation(b, Settings["Select Skills " .. b.ToolTip]))
		else nil
	if X then
		b = X.Parent.Name
		equiptool(b)
		if t.Character:FindFirstChild(b) then
			game:GetService("VirtualInputManager"):SendKeyEvent(true, X.Name, false, game)
			if Settings["Use skill fast dont hold"] then
				task.wait(0.05)
			else
				task.wait(tonumber(holdskill))
			end
			game:GetService("VirtualInputManager"):SendKeyEvent(false, X.Name, false, game)
		end
	end
end
function AutoSeabeast()
	if not StackFarmOther then
		return
	end
	local b = false
	for X, l in next, SafeMultiSelect("Select Sea Events"), nil do
		if l and X ~= "Only Farm Ship Brigade" then
			b = true
			break
		end
	end
	if not b then
		WarnOnce("NoSeaEvent", "Chua chon su kien nao o Sea Event > Select Sea Events.")
		return
	end
	b = DetectSeaEvents()
	if not b then
		getgenv().PathSeaBeast = false
		getgenv().PathTerrorshark = false
		getgenv().PathSpinBoat = false
		BuyBoatAndTeleBoat()
	else
		y()
		if b.Name == "Terrorshark" then
			getgenv().PathTerrorshark = b
		end
		getgenv().PathSpinBoat = b
		repeat
			task.wait()
			TeleportSeaEvents(b)
			if b:FindFirstChildWhichIsA("Humanoid") then
				if Settings["Use Dragonstorm For Sea Event"] then
					if Settings["Auto Change Dragonstorm With Skull Guitar"] then
						if not NameWeapon("Gun") or NameWeapon("Gun") ~= "Dragonstorm" then
							game:GetService("ReplicatedStorage").Remotes.CommF_
								:InvokeServer(unpack({ [1] = "LoadItem", [2] = "Dragonstorm" }))
						end
					end
					equiptool(NameWeapon("Gun"))
					SpamGunDragonStorm(b.HumanoidRootPart)
					if t:DistanceFromCharacter(b.HumanoidRootPart.Position) < 400 then
						UseSkillGun()
					end
				elseif Settings["Use Click M1 Fruit For Sea Event"] then
					equiptool(NameWeapon("Blox Fruit"))
					local X = NameWeapon("Blox Fruit")
					if t.Character:FindFirstChild(X) and (t.Character[X]:FindFirstChild("LeftClickRemote")) then
						getgenv().UseFruitM1(b)
					end
				else
					UsedualFlock()
					ClickM1(b, true)
				end
			else
				local X = b:FindFirstChild("HumanoidRootPart") or (b:FindFirstChild("Engine"))
				if X then
					if b.Name == "SeaBeast1" then
						getgenv().PathSeaBeast = b
						getgenv().AimPos = CFrame.new(X.Position.X, 40, X.Position.Z)
					else
						getgenv().AimPos = CFrame.new(
							t.Character.HumanoidRootPart.Position.X,
							-58,
							t.Character.HumanoidRootPart.Position.Z
						)
					end
					if Settings["Use Dragonstorm For Sea Event"] and b.Name ~= "SeaBeast1" then
						if Settings["Auto Change Dragonstorm With Skull Guitar"] then
							if not NameWeapon("Gun") or NameWeapon("Gun") ~= "Dragonstorm" then
								game:GetService("ReplicatedStorage").Remotes.CommF_
									:InvokeServer(unpack({ [1] = "LoadItem", [2] = "Dragonstorm" }))
							end
						end
						equiptool(NameWeapon("Gun"))
						SpamGunDragonStorm(X)
						if t:DistanceFromCharacter(X.Position) < 400 then
							UseSkillGun()
						end
					elseif Settings["Use Click M1 Skull Guitar For Sea Event"] then
						if Settings["Auto Change Dragonstorm With Skull Guitar"] then
							if not NameWeapon("Gun") or NameWeapon("Gun") ~= "Skull Guitar" then
								game:GetService("ReplicatedStorage").Remotes.CommF_
									:InvokeServer(unpack({ [1] = "LoadItem", [2] = "Skull Guitar" }))
							end
						end
						equiptool(NameWeapon("Gun"))
						SpamGunSkullGuitar(X)
						if t:DistanceFromCharacter(X.Position) < 400 then
							UseSkillGun()
						end
					elseif
						Settings["Auto Change Dragonstorm When Kill Boat"]
						and (b:FindFirstChild("Health"))
						and b.Health.Value > 0
						and (b:FindFirstChild("Engine"))
					then
						if not NameWeapon("Gun") or NameWeapon("Gun") ~= "Dragonstorm" then
							game:GetService("ReplicatedStorage").Remotes.CommF_
								:InvokeServer(unpack({ [1] = "LoadItem", [2] = "Dragonstorm" }))
						end
						equiptool(NameWeapon("Gun"))
						SpamGunDragonStorm(X)
						if t:DistanceFromCharacter(X.Position) < 400 then
							UseSkillGun()
						end
					elseif Settings["Use Click M1 Fruit For Sea Event"] then
						equiptool(NameWeapon("Blox Fruit"))
						local l = NameWeapon("Blox Fruit")
						if t.Character:FindFirstChild(l) and (t.Character[l]:FindFirstChild("LeftClickRemote")) then
							if b.Name == "SeaBeast1" then
								getgenv().UseFruitM1(b)
							else
								getgenv().UseFruitM1Boat(X.CFrame * CFrame.new(0, -35, 0))
							end
						end
					elseif t:DistanceFromCharacter(X.Position) < 400 then
						AutoUseSkillSeabeast()
					end
				end
			end
		until not b
			or not b.Parent
			or not Settings["Auto Sea Event"]
			or b:FindFirstChild("Health") and b.Health.Value == 0
			or b:FindFirstChildWhichIsA("Humanoid") and b.Humanoid.Health == 0
			or not StackFarmOther
	end
end
FarmingSeaEventSection = SeaEventTab.CreateSection("Farming")
local b = FarmingSeaEventSection.CreateDropdown(
	{
		Title = "Select Friend",
		List = DetectNamePlayer(),
		Search = true,
		Selected = false,
		Default = Settings["Select Friend"] or nil,
	},
	function(X)
		SaveSettings("Select Friend", X)
	end
)
FarmingSeaEventSection.CreateButton({ Title = "Refresh Player" }, function()
	b:GetNewList(DetectNamePlayer())
end)
FarmingSeaEventSection.CreateToggle(
	{ Title = "Auto Sea Event With Friend", Desc = nil, Default = Settings["Auto Sea Event With Friend"] or false },
	function(b)
		SaveSettings("Auto Sea Event With Friend", b)
	end
)
local b, X, l = 0, 0, false
spawn(function()
	repeat
		wait()
	until game:GetService("Players").LocalPlayer.PlayerGui:FindFirstChild("Main")
		and (game:GetService("Players").LocalPlayer.PlayerGui:FindFirstChild("Main"):FindFirstChild("DmgCounter"))
	game:GetService("Players").LocalPlayer.PlayerGui.Main.DmgCounter.Text
		:GetPropertyChangedSignal("Text")
		:Connect(function()
			if tonumber(game:GetService("Players").LocalPlayer.PlayerGui.Main.DmgCounter.Text.Text) == 0 then
				b, X, l = 0, 0, false
			else
				l = true
				b = tonumber(game:GetService("Players").LocalPlayer.PlayerGui.Main.DmgCounter.Text.Text) - X
			end
		end)
end)
FarmingSeaEventSection.CreateToggle(
	{ Title = "Auto Repair Ur Ship", Desc = nil, Default = Settings["Auto Repair Ur Ship"] or false },
	function(_)
		SaveSettings("Auto Repair Ur Ship", _)
	end
)
FarmingSeaEventSection.CreateToggle(
	{ Title = "Auto Sea Event", Desc = nil, Default = Settings["Auto Sea Event"] or false },
	function(_)
		if _ then
			getgenv().StopBoatSeaEvent = true
			spawn(function()
				while Settings["Auto Sea Event"] and (task.wait()) do
					local P, Y = pcall(function()
						AutoSeabeast()
					end)
					if not P and Y then
						print(Y)
					end
				end
			end)
		elseif getgenv().StopBoatSeaEvent then
			y()
			getgenv().StopBoatSeaEvent = false
		end
		SaveSettings("Auto Sea Event", _)
	end
)
local _
if game.PlaceId == getgenv().CheckPlaceId then
	_ = require(game:GetService("ReplicatedStorage").DangerDistance)
end
function DistanceFindLeviathan()
	local y = Z:GetNearestNPC(game.Players.LocalPlayer.Character.HumanoidRootPart.Position, 2600)[1]
	return (
		math.floor((Z:GetDistance(y) - game.Players.LocalPlayer.Character.HumanoidRootPart.Position).magnitude / 10)
	)
end
ToggleFindMirage = FarmingSeaEventSection.CreateToggle(
	{ Title = "Auto Find Mirage", Desc = nil, Default = Settings["Auto Find Mirage"] or false },
	function(y)
		spawn(function()
			while Settings["Auto Find Mirage"] and (wait(0.1)) do
				pcall(function()
					if not game:GetService("Workspace").Map:FindFirstChild("MysticIsland") then
						getgenv().RespawnMirage = true
						local P = checkboat()
						if not P or P and t:DistanceFromCharacter(P.VehicleSeat.Position) >= 4000 then
							local Y = CFrame.new(-16204.0810546875, 9.0863618850708, 479.2259521484375)
							if (Y.Position - t.Character.HumanoidRootPart.Position).Magnitude > 8 then
								if (Y.Position - t.Character.HumanoidRootPart.Position).Magnitude > 1000 then
									if game:GetService("Players").LocalPlayer.Data.LastSpawnPoint.Value == "Tiki" then
										t.Character.Humanoid.Health = 0
										return
									end
								end
								toTarget(Y)
							else
								game:GetService("ReplicatedStorage").Remotes.CommF_
									:InvokeServer("BuyBoat", "PirateBrigade")
								wait(3)
							end
						elseif t.Character.Humanoid.Sit then
							local Y, H, Z =
								CFrame.new(-118834.515625, 160, -78.9505844116211) * CFrame.new(0, 0, 99999999),
								CFrame.new(-32975.9921875, 160, 25963.7109375),
								if Settings["Will Back When over 10km"]
									then if DistanceFindLeviathan() >= 12000
										then true
										else if DistanceFindLeviathan() <= 4800 then false else false
									else false
							repeat
								task.wait(0.5)
								NoclipBoat(P)
								if Settings["Will Back When over 10km"] then
									Z = if DistanceFindLeviathan() >= 10000
										then true
										else if DistanceFindLeviathan() <= 4800 then false else Z
									if Z then
										manageTween(P.VehicleSeat, H, 350, "TweenBoatBack")
									end
								end
								if not Z or not Settings["Will Back When over 10km"] then
									manageTween(P.VehicleSeat, Y, 350, "TweenBoat")
								end
							until not Settings["Auto Find Mirage"]
								or not t.Character.Humanoid.Sit
								or (game:GetService("Workspace").Map:FindFirstChild("MysticIsland"))
							if getgenv().TweenBoat then
								getgenv().TweenBoat:Pause()
								getgenv().TweenBoat:Cancel()
							end
							if getgenv().TweenBoatBack then
								getgenv().TweenBoatBack:Pause()
								getgenv().TweenBoatBack:Cancel()
							end
						else
							if getgenv().TweenBoat then
								getgenv().TweenBoat:Pause()
								getgenv().TweenBoat:Cancel()
							end
							if getgenv().TweenBoatBack then
								getgenv().TweenBoatBack:Pause()
								getgenv().TweenBoatBack:Cancel()
							end
							toTarget(P.VehicleSeat.CFrame)
						end
					else
						if getgenv().RespawnMirage and Settings["Webhook Find Mirage"] then
							getgenv().RespawnMirage = false
							WebhookFindMirage()
						end
						if getgenv().TweenBoat then
							getgenv().TweenBoat:Pause()
							getgenv().TweenBoat:Cancel()
						end
						A.CreateNoti({ Title = "Banana Cat Hub", Desc = "Mirage Island Spawned", ShowTime = 5 })
						ToggleFindMirage:SetStage(false)
						wait(5)
					end
				end)
			end
		end)
		SaveSettings("Auto Find Mirage", y)
	end
)
KitsuneEventSection = SeaEventTab.CreateSection("Kitsune Event")
KitsuneEventSection.CreateToggle(
	{ Title = "Teleport To Kitsune Island", Desc = nil, Default = Settings["Teleport To Kitsune Island"] or false },
	function(y)
		SaveSettings("Teleport To Kitsune Island", y)
	end
)
KitsuneEventSection.CreateToggle(
	{
		Title = "Hop Server [ Next Night or Near Full Moon > 2m ]",
		Desc = nil,
		Default = Settings["Hop Server Kitsune Island"] or false,
	},
	function(y)
		SaveSettings("Hop Server Kitsune Island", y)
	end
)
KitsuneEventSection.CreateToggle(
	{ Title = "Auto Spawn Kitsune Island", Desc = nil, Default = Settings["Auto Spawn Kitsune Island"] or false },
	function(y)
		if y then
			A.CreateNoti({
				Title = "Banana Cat Hub",
				Desc = "Turn On after Status Full Moon|( Will Full Moon In >= 0 Minutes )",
				ShowTime = 5,
			})
		end
		SaveSettings("Auto Spawn Kitsune Island", y)
	end
)
KitsuneEventSection.CreateToggle(
	{ Title = "Auto Summon Soul Ember", Desc = nil, Default = Settings["Auto Summon Soul Ember"] or false },
	function(y)
		SaveSettings("Auto Summon Soul Ember", y)
	end
)
KitsuneEventSection.CreateToggle(
	{ Title = "Auto Collect Soul Ember", Desc = nil, Default = Settings["Auto Collect Soul Ember"] or false },
	function(y)
		SaveSettings("Auto Collect Soul Ember", y)
	end
)
KitsuneEventSection.CreateSlider(
	{ Title = "Values Azure Ember", Min = 0, Max = 25, Default = Settings["Values Azure Ember"] or 10, Precise = true },
	function(y)
		SaveSettings("Values Azure Ember", y)
	end
)
KitsuneEventSection.CreateToggle(
	{ Title = "Auto Trade Azure Ember", Desc = nil, Default = Settings["Auto Trade Azure Ember"] or false },
	function(y)
		SaveSettings("Auto Trade Azure Ember", y)
	end
)
function DetectIslandKitsune()
	if
		game.workspace.Map:FindFirstChild("KitsuneIsland")
		and workspace.Map.KitsuneIsland.ShrineDialogPart.ProximityPrompt.Enabled
	then
		return true
	end
end
function AutoSpawnKitsune()
	local y, P = game.Lighting.ClockTime, checkboat()
	if Settings["Hop Server Kitsune Island"] then
		local Y = CheckMoon()
		if
			not (
				Y == "Full Moon" and math.floor(18 - y) <= 5 and math.floor(18 - y) >= 0
				or Y == "Next Night"
				or Y == "Full Moon" and y <= 5 and math.floor(5 - y) >= 11
			)
		then
			HopServer()
			return
		end
	end
	if not P then
		local Y = CFrame.new(-13.488054275512695, 10.311711311340332, 2927.692)
		Y = if game.PlaceId == getgenv().CheckPlaceId
			then (CFrame.new(-16204.0810546875, 9.0863618850708, 479.2259521484375))
			else Y
		if (Y.Position - t.Character.HumanoidRootPart.Position).Magnitude > 8 then
			toTarget(Y)
		else
			local Y = Settings["Select Boat"]
			if not Y then
				WarnOnce("SelectBoat", "Chon thuyen o Sea Event > Select Boat truoc da.")
				return
			end
			local H = Y == "Brigade"
			game:GetService("ReplicatedStorage").Remotes.CommF_
				:InvokeServer("BuyBoat", if H or Y == "GrandBrigade" then "Pirate" .. Y else Y)
			task.wait(3)
		end
		return
	end
	NoclipBoat(P)
	local Y = P.WorldPivot.Y
	local H = CFrame.new(-32975.9921875, Y, 25963.7109375) * CFrame.new(0, 0, 1000)
	if CheckMoon() == "Full Moon" and math.floor(18 - y) <= 0 then
		if (P.VehicleSeat.Position - H.Position).Magnitude > 200 then
			if not t.Character.Humanoid.Sit then
				toTarget(P.VehicleSeat.CFrame)
			else
				manageTween(P.VehicleSeat, H, 350, "TweenBoat")
			end
		elseif not t.Character.Humanoid.Sit then
			toTarget(P.VehicleSeat.CFrame)
		end
	else
		if (P.VehicleSeat.Position - H.Position).Magnitude > 200 then
			manageTween(P.VehicleSeat, H, 350, "TweenBoat")
		end
		toTarget(H * CFrame.new(0, 2000, 0))
	end
end
function DetectSoulEmber()
	local y, P, Y = next, game.Workspace:GetChildren()
	for H, H in y, P, Y do
		if H.Name == "EmberTemplate" and (H:FindFirstChild("Part")) then
			return H
		end
	end
end
function CollectSoulEmber()
	local y = DetectSoulEmber()
	if y then
		if t:DistanceFromCharacter(y.Part.Position) > 100 then
			toTarget(y.Part.CFrame)
		else
			t.Character.HumanoidRootPart.CFrame = y.Part.CFrame
		end
	else
		toTarget(game.workspace._WorldOrigin.Locations["Kitsune Island"].CFrame)
	end
end
function AutoSummonAzureEmber()
	if
		not game:GetService("Players").LocalPlayer.PlayerGui.Main.TopHUDList.RaidTimer.Visible
		and (DetectIslandKitsune())
	then
		if t:DistanceFromCharacter(game.Workspace.Map.KitsuneIsland.ShrineInactive.WorldPivot.Position) >= 10 then
			toTarget(game.Workspace.Map.KitsuneIsland.ShrineInactive.WorldPivot)
		else
			game:GetService("ReplicatedStorage").Modules.Net:FindFirstChild("RE/TouchKitsuneStatue"):FireServer()
			wait(5)
		end
	end
end
function TradeAzureEmber()
	if
		CheckCountItem("Azure Ember", tonumber(Settings["Values Azure Ember"]))
		and game:GetService("Players").LocalPlayer.PlayerGui.Main.TopHUDList.RaidTimer.Visible
	then
		game:GetService("ReplicatedStorage").Modules.Net:FindFirstChild("RF/KitsuneStatuePray"):InvokeServer()
		wait(5)
	end
end
spawn(function()
	repeat
		wait(0.15)
	until Settings["Teleport To Kitsune Island"]
		or Settings["Auto Spawn Kitsune Island"]
		or Settings["Auto Collect Soul Ember"]
		or Settings["Auto Trade Azure Ember"]
	while task.wait(0.1) do
		pcall(function()
			if Settings["Teleport To Kitsune Island"] then
				if game.workspace._WorldOrigin.Locations:FindFirstChild("Kitsune Island") then
					toTarget(game.workspace._WorldOrigin.Locations["Kitsune Island"].CFrame)
				end
			end
			if Settings["Auto Spawn Kitsune Island"] then
				pcall(function()
					if not DetectIslandKitsune() then
						AutoSpawnKitsune()
					end
				end)
			end
			if Settings["Auto Collect Soul Ember"] then
				if game:GetService("Players").LocalPlayer.PlayerGui.Main.TopHUDList.RaidTimer.Visible then
					CollectSoulEmber()
				end
			end
			if Settings["Auto Summon Soul Ember"] then
				AutoSummonAzureEmber()
			end
			if Settings["Auto Trade Azure Ember"] then
				TradeAzureEmber()
			end
		end)
	end
end)
LeviathanEventSection = SeaEventTab.CreateSection("Leviathan Event")
LeviathanEventSection.CreateButton({ Title = "Buy Spy" }, function()
	local y = require(game.ReplicatedStorage.DialoguesList).Spy
	require(game.ReplicatedStorage.DialogueController):Start(y)
end)
LeviathanEventSection.CreateButton({ Title = "Teleport your boat to current Position" }, function()
	checkboat().VehicleSeat.CFrame = t.Character.HumanoidRootPart.CFrame
end)
LeviathanEventSection.CreateToggle(
	{ Title = "Auto Buy Spy", Desc = nil, Default = Settings["Auto Buy Spy"] or false },
	function(y)
		if y then
			spawn(function()
				while Settings["Auto Buy Spy"] and (task.wait(5)) do
					pcall(function()
						if StatusCheckLeviathan() == "Buy Find leviathan" then
							game.ReplicatedStorage.Remotes.CommF_:InvokeServer("InfoLeviathan", "1")
							game.ReplicatedStorage.Remotes.CommF_:InvokeServer("InfoLeviathan", "2")
						end
					end)
				end
			end)
		end
		SaveSettings("Auto Buy Spy", y)
	end
)
LeviathanEventSection.CreateToggle(
	{ Title = "Auto Buy Boat Beast Hunter", Desc = nil, Default = Settings["Auto Buy Boat Beast Hunter"] or false },
	function(y)
		SaveSettings("Auto Buy Boat Beast Hunter", y)
	end
)
function checkboatFind()
	local y, P, Y = next, game:GetService("Workspace").Boats:GetChildren()
	for H, H in y, P, Y do
		if H:IsA("Model") then
			if
				H:FindFirstChild("Owner")
				and t:DistanceFromCharacter(H.VehicleSeat.Position) < 10
				and t.Character.Humanoid.SeatPart
				and t.Character.Humanoid.SeatPart.Name == "VehicleSeat"
				and H.Humanoid.Value > 0
			then
				return H
			end
		end
	end
end
g, s, a, I = {}, next, game:GetService("ReplicatedStorage").RockGenerator.Rocks:GetChildren()
for y, y in s, a, I do
	table.insert(g, y.Name)
end
function DetectRockNear(s)
	local g, I = s.VehicleSeat.Position, s:GetAttribute("Size")
	s = workspace:FindPartsInRegion3(Region3.new(g - I / 2, g + I / 2), nil, 1 / 0)
	if #s > 0 then
		for g, g in pairs(s) do
			return true
		end
	end
end
local function s(g, I)
	return I - g
end
function DetectSeaEventDodge(g)
	if g then
		local I, y, P = next, game:GetService("Workspace").SeaBeasts:GetChildren()
		for Y, Y in I, y, P do
			if Y.Name == "SeaBeast1" and (Y:FindFirstChild("HumanoidRootPart")) and (Y:FindFirstChild("HealthBBG")) then
				local I, y = Y.HealthBBG.Frame.TextLabel.Text:gsub("/%d+,%d+", ""), Y.HealthBBG.Frame.TextLabel.Text
				if
					tonumber(
							(
								(if string.find(I, ",") then (y:gsub("%d+,%d+/", "")) else (y:gsub("%d+/", ""))):gsub(
									",",
									""
								)
							)
						)
						>= 90000
					and t:DistanceFromCharacter(Y.HumanoidRootPart.Position) < 2000
				then
					return Y
				end
			end
		end
	end
	if g then
		local I = CheckNameBoss("Terrorshark")
		if I and t:DistanceFromCharacter(I.HumanoidRootPart.Position) < 2000 then
			return I
		end
	end
	if g then
		local g, I, y = next, game:GetService("Workspace").Enemies:GetChildren()
		for P, P in g, I, y do
			if
				P:FindFirstChild("Engine")
				and (P:FindFirstChild("Health"))
				and P.Health.Value > 0
				and t:DistanceFromCharacter(P.Engine.Position) < 2000
			then
				return P
			end
		end
	end
	return false
end
function AutoFindLeviathan()
	if Settings["Auto Destroy IDK"] and getgenv().DesIdk then
		getgenv().DesIdk2 = true
		return
	end
	if Settings["Auto Destroy IDK"] and getgenv().DesIdk2 then
		toTarget(getgenv().OldBoat.VehicleSeat.CFrame)
		if t.Character.Humanoid.Sit then
			getgenv().DesIdk2 = false
		end
		return
	end
	local g = checkboatFind()
	if not game.workspace._WorldOrigin.Locations:FindFirstChild("Frozen Dimension") then
		getgenv().RespawnLeviathan = true
		local I = checkboat()
		if not I and Settings["Auto Buy Boat Beast Hunter"] then
			local y = CFrame.new(-16204.0810546875, 9.0863618850708, 479.2259521484375)
			if (y.Position - t.Character.HumanoidRootPart.Position).Magnitude > 8 then
				if (y.Position - t.Character.HumanoidRootPart.Position).Magnitude > 1000 then
					if game:GetService("Players").LocalPlayer.Data.LastSpawnPoint.Value == "Tiki" then
						t.Character.Humanoid.Health = 0
						return
					end
				end
				toTarget(y)
			else
				game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("BuyBoat", "Beast Hunter")
				wait(3)
			end
		elseif g then
			getgenv().noclip = false
			local y, P, Y, H, Z =
				CFrame.new(-118834.515625, 160, -78.9505844116211) * CFrame.new(0, 0, 99999999),
				CFrame.new(-32975.9921875, 160, 25963.7109375),
				if Settings["Will Back When over 10km"]
					then if DistanceFindLeviathan() >= 12000
						then true
						else if DistanceFindLeviathan() <= 4800 then false else false
					else false,
				g.VehicleSeat.Position.Y,
				g.VehicleSeat.BodyVelocity.MaxForce
			wait(0.5)
			local C = false
			g.VehicleSeat.BodyVelocity.MaxForce = Vector3.new(1 / 0, 1 / 0, 1 / 0)
			local J = s(g.VehicleSeat.Position.Y, 1000)
			if not t.PlayerGui.Main.Compass.Frame.DangerLevel.Visible then
				wait(0.2)
				g.VehicleSeat.CFrame = g.VehicleSeat.CFrame * CFrame.new(0, J, 0)
				wait(1)
				C = true
			else
				wait(0.2)
				g.VehicleSeat.CFrame = g.VehicleSeat.CFrame * CFrame.new(0, s(g.VehicleSeat.Position.Y, 160), 0)
				wait(1)
			end
			J = false
			repeat
				task.wait(0.5)
				NoclipBoat(g)
				if t.Character:FindFirstChild("HumanoidRootPart") and (t.Character:FindFirstChild("Humanoid")) then
					local F, q, c = next, t.Character:GetDescendants()
					for D, D in F, q, c do
						if (D:IsA("MeshPart") or (D:IsA("Part"))) and D.CanCollide then
							D.CanCollide = false
						end
					end
				end
				if
					C
					and (
						t.PlayerGui.Main.Compass.Frame.DangerLevel.Visible
							and t.PlayerGui.Main.Compass.Frame.DangerText.Visible
							and tonumber(
								game:GetService("Players").LocalPlayer.PlayerGui.Main.Compass.Frame.DangerLevel.TextLabel.Text
							) >= 1
						or _(t.Character.HumanoidRootPart.CFrame) >= 4000
					)
				then
					getgenv().TweenBoat:Pause()
					getgenv().TweenBoat:Cancel()
					wait(0.5)
					g.VehicleSeat.CFrame = g.VehicleSeat.CFrame * CFrame.new(0, s(g.VehicleSeat.Position.Y, 160), 0)
					wait(0.5)
					C = false
				end
				if not C and g.VehicleSeat.Position.Y < 150 then
					if getgenv().TweenBoat then
						getgenv().TweenBoat:Pause()
						getgenv().TweenBoat:Cancel()
					end
					if getgenv().TweenBoatBack then
						getgenv().TweenBoatBack:Pause()
						getgenv().TweenBoatBack:Cancel()
					end
					wait(0.5)
					g.VehicleSeat.CFrame = g.VehicleSeat.CFrame * CFrame.new(0, s(g.VehicleSeat.Position.Y, 160), 0)
				end
				if not J and (DetectSeaEventDodge(true)) and g.VehicleSeat.Position.Y < 500 then
					y, P =
						CFrame.new(-118834.515625, 500, -78.9505844116211) * CFrame.new(0, 0, 99999999),
						CFrame.new(-32975.9921875, 500, 25963.7109375)
					if getgenv().TweenBoat then
						getgenv().TweenBoat:Pause()
						getgenv().TweenBoat:Cancel()
					end
					if getgenv().TweenBoatBack then
						getgenv().TweenBoatBack:Pause()
						getgenv().TweenBoatBack:Cancel()
					end
					wait(0.5)
					g.VehicleSeat.CFrame = g.VehicleSeat.CFrame * CFrame.new(0, s(g.VehicleSeat.Position.Y, 500), 0)
					wait(0.5)
					J = true
				elseif J and not DetectSeaEventDodge(true) then
					y, P =
						CFrame.new(-118834.515625, 160, -78.9505844116211) * CFrame.new(0, 0, 99999999),
						CFrame.new(-32975.9921875, 160, 25963.7109375)
					if getgenv().TweenBoat then
						getgenv().TweenBoat:Pause()
						getgenv().TweenBoat:Cancel()
					end
					if getgenv().TweenBoatBack then
						getgenv().TweenBoatBack:Pause()
						getgenv().TweenBoatBack:Cancel()
					end
					wait(0.5)
					g.VehicleSeat.CFrame = g.VehicleSeat.CFrame * CFrame.new(0, s(g.VehicleSeat.Position.Y, 160), 0)
					wait(0.5)
					J = false
				end
				if Settings["Will Back When over 10km"] then
					Y = if DistanceFindLeviathan() >= 10000
						then true
						else if DistanceFindLeviathan() <= 4800 then false else Y
					if Y then
						manageTween(g.VehicleSeat, P, 350, "TweenBoatBack")
					end
				end
				if not Y or not Settings["Will Back When over 10km"] then
					manageTween(g.VehicleSeat, y, 350, "TweenBoat")
				end
			until not Settings["Auto Find Leviathan"]
				or not t.Character.Humanoid.Sit
				or (game.workspace._WorldOrigin.Locations:FindFirstChild("Frozen Dimension"))
				or Settings["Auto Destroy IDK"] and getgenv().DesIdk
			g.VehicleSeat.BodyVelocity.MaxForce = Z
			getgenv().OldBoat = g
			if getgenv().TweenBoat then
				getgenv().TweenBoat:Pause()
				getgenv().TweenBoat:Cancel()
			end
			if getgenv().TweenBoatBack then
				getgenv().TweenBoatBack:Pause()
				getgenv().TweenBoatBack:Cancel()
			end
			g.VehicleSeat.CFrame = CFrame.new(g.VehicleSeat.Position.X, H, g.VehicleSeat.Position.Z)
		elseif I and Settings["Auto Buy Boat Beast Hunter"] then
			if not t.Character.Humanoid.Sit then
				toTarget(I.VehicleSeat.CFrame)
			end
		end
	else
		if getgenv().TweenBoat then
			getgenv().TweenBoat:Pause()
			getgenv().TweenBoat:Cancel()
		end
		if getgenv().TweenBoatBack then
			getgenv().TweenBoatBack:Pause()
			getgenv().TweenBoatBack:Cancel()
		end
		A.CreateNoti({ Title = "Banana Cat Hub", Desc = "Frozen Dimension Spawned", ShowTime = 5 })
		if getgenv().RespawnLeviathan and Settings["Webhook Find Leviathan"] then
			getgenv().RespawnLeviathan = false
			WebhookFindLeviathan()
		end
		wait(5)
	end
end
function DestroyIDK()
	if StatusCheckLeviathan() == "I DONT KNOW" then
		getgenv().WebhookIDK = true
		local s = DetectSeaEvents(true)
		if not s then
			getgenv().PathSeaBeast = false
			getgenv().PathTerrorshark = false
			getgenv().PathSpinBoat = false
		else
			getgenv().DesIdk = true
			if getgenv().TweenBoat then
				getgenv().TweenBoat:Pause()
				getgenv().TweenBoat:Cancel()
			end
			if s.Name == "Terrorshark" then
				getgenv().PathTerrorshark = s
			end
			getgenv().PathSpinBoat = s
			repeat
				task.wait()
				spawn(function()
					TeleportSeaEvents(s)
				end)
				if s:FindFirstChildWhichIsA("Humanoid") then
					if Settings["Use Dragonstorm For Sea Event"] then
						if Settings["Auto Change Dragonstorm With Skull Guitar"] then
							if not NameWeapon("Gun") or NameWeapon("Gun") ~= "Dragonstorm" then
								game:GetService("ReplicatedStorage").Remotes.CommF_
									:InvokeServer(unpack({ [1] = "LoadItem", [2] = "Dragonstorm" }))
							end
						end
						equiptool(NameWeapon("Gun"))
						SpamGunDragonStorm(s.HumanoidRootPart)
						if t:DistanceFromCharacter(s.HumanoidRootPart.Position) < 400 then
							UseSkillGun()
						end
					elseif Settings["Use Click M1 Fruit For Sea Event"] then
						equiptool(NameWeapon("Blox Fruit"))
						local g = NameWeapon("Blox Fruit")
						if t.Character:FindFirstChild(g) and (t.Character[g]:FindFirstChild("LeftClickRemote")) then
							getgenv().UseFruitM1(s)
						end
					else
						UsedualFlock()
						ClickM1(s, true)
					end
				else
					local g = s:FindFirstChild("HumanoidRootPart") or (s:FindFirstChild("Engine"))
					if s.Name == "SeaBeast1" then
						getgenv().PathSeaBeast = s
						getgenv().AimPos = CFrame.new(g.Position.X, 40, g.Position.Z)
					else
						getgenv().AimPos = CFrame.new(
							t.Character.HumanoidRootPart.Position.X,
							-58,
							t.Character.HumanoidRootPart.Position.Z
						)
					end
					if Settings["Use Dragonstorm For Sea Event"] and s.Name ~= "SeaBeast1" then
						if Settings["Auto Change Dragonstorm With Skull Guitar"] then
							if not NameWeapon("Gun") or NameWeapon("Gun") ~= "Dragonstorm" then
								game:GetService("ReplicatedStorage").Remotes.CommF_
									:InvokeServer(unpack({ [1] = "LoadItem", [2] = "Dragonstorm" }))
							end
						end
						equiptool(NameWeapon("Gun"))
						SpamGunDragonStorm(g)
						if t:DistanceFromCharacter(g.Position) < 400 then
							UseSkillGun()
						end
					elseif Settings["Use Click M1 Skull Guitar For Sea Event"] then
						if Settings["Auto Change Dragonstorm With Skull Guitar"] then
							if not NameWeapon("Gun") or NameWeapon("Gun") ~= "Skull Guitar" then
								game:GetService("ReplicatedStorage").Remotes.CommF_
									:InvokeServer(unpack({ [1] = "LoadItem", [2] = "Skull Guitar" }))
							end
						end
						equiptool(NameWeapon("Gun"))
						SpamGunSkullGuitar(g)
						if t:DistanceFromCharacter(g.Position) < 400 then
							UseSkillGun()
						end
					elseif Settings["Use Click M1 Fruit For Sea Event"] then
						equiptool(NameWeapon("Blox Fruit"))
						local I = NameWeapon("Blox Fruit")
						if t.Character:FindFirstChild(I) and (t.Character[I]:FindFirstChild("LeftClickRemote")) then
							if s.Name == "SeaBeast1" then
								getgenv().UseFruitM1(s)
							else
								getgenv().UseFruitM1Boat(g.CFrame * CFrame.new(0, -35, 0))
							end
						end
					elseif t:DistanceFromCharacter(g.Position) < 400 then
						AutoUseSkillSeabeast()
					end
				end
			until not s
				or not s.Parent
				or not Settings["Auto Destroy IDK"]
				or s:FindFirstChild("Health") and s.Health.Value == 0
				or s:FindFirstChildWhichIsA("Humanoid") and s.Humanoid.Health == 0
			getgenv().DesIdk = false
		end
	elseif getgenv().WebhookIDK and Settings["Webhook Destroy IDK"] then
		getgenv().WebhookDestroyIdk()
		getgenv().WebhookIDK = false
	end
	getgenv().DesIdk = false
end
getgenv().SpeedTeleportTiki = 70
local s = LeviathanEventSection.CreateDropdown(
	{
		Title = "Select Owner Boat Find Leviathan",
		List = DetectNamePlayer(),
		Search = true,
		Selected = false,
		Default = Settings["Select Owner Boat Find Leviathan"] or nil,
	},
	function(g)
		SaveSettings("Select Owner Boat Find Leviathan", g)
	end
)
LeviathanEventSection.CreateButton({ Title = "Refresh Player" }, function()
	s:GetNewList(DetectNamePlayer())
end)
function checkboatMulti()
	local s, g, I, _ =
		Settings["Select Owner Boat Find Leviathan"], next, game:GetService("Workspace").Boats:GetChildren()
	local y
	for P, P in g, I, _ do
		y = if P:IsA("Model")
			then if P:FindFirstChild("Owner") and tostring(P.Owner.Value) == s and P.Humanoid.Value > 0 then P else y
			else y
	end
	if y then
		I, g, s = next, y:GetChildren()
		for _, _ in I, g, s do
			if _.Name == "Cannon" and not _.Seat:FindFirstChild("SeatWeld") then
				return _
			end
		end
	end
	return false
end
LeviathanEventSection.CreateToggle(
	{ Title = "Multi Find Leviathan", Desc = nil, Default = Settings["Multi Find Leviathan"] or false },
	function(s)
		if s then
			spawn(function()
				while Settings["Multi Find Leviathan"] and (task.wait(0.1)) do
					pcall(function()
						if Settings["Auto Destroy IDK"] and getgenv().DesIdk then
							return
						end
						local g = checkboatMulti()
						if g and not t.Character.Humanoid.Sit then
							toTarget(g.Seat.CFrame)
						elseif
							t.Character.Humanoid.Sit
							and (t.Character:FindFirstChild("HumanoidRootPart"))
							and (t.Character:FindFirstChild("HumanoidRootPart"):FindFirstChild("FloatForce"))
						then
							TweenManager.CancelCurrent()
						end
					end)
				end
			end)
		end
		SaveSettings("Multi Find Leviathan", s)
	end
)
LeviathanEventSection.CreateToggle(
	{ Title = "Auto Find Leviathan", Desc = nil, Default = Settings["Auto Find Leviathan"] or false },
	function(s)
		if s then
			spawn(function()
				while Settings["Auto Find Leviathan"] and (task.wait()) do
					local g, g = pcall(function()
						AutoFindLeviathan()
					end)
					if g then
						print(g)
					end
				end
			end)
		end
		SaveSettings("Auto Find Leviathan", s)
	end
)
LeviathanEventSection.CreateToggle(
	{ Title = "Auto Start Leviathan", Desc = nil, Default = Settings["Auto Start Leviathan"] or false },
	function(s)
		if s then
			spawn(function()
				while Settings["Auto Start Leviathan"] and (task.wait(2.5)) do
					local g, g = pcall(function()
						if game.workspace._WorldOrigin.Locations:FindFirstChild("Frozen Dimension") then
							local I
							for _, _ in pairs(game:GetService("Workspace").NPCs:GetChildren()) do
								I = if _.Name == "Frozen Watcher" then _ else I
							end
							for _, _ in pairs(game:GetService("ReplicatedStorage").NPCs:GetChildren()) do
								I = if _.Name == "Frozen Watcher" then _ else I
							end
							if I and t:DistanceFromCharacter(I.HumanoidRootPart.Position) < 8 then
								game.ReplicatedStorage.Remotes.CommF_:InvokeServer("OpenLeviathanGate")
							else
								toTarget(I.HumanoidRootPart.CFrame)
							end
						end
					end)
					if g then
						print(g)
					end
				end
			end)
		end
		SaveSettings("Auto Start Leviathan", s)
	end
)
LeviathanEventSection.CreateToggle(
	{ Title = "Auto Destroy IDK", Desc = nil, Default = Settings["Auto Destroy IDK"] or false },
	function(s)
		if s then
			spawn(function()
				while Settings["Auto Destroy IDK"] and (task.wait(0.1)) do
					local g, g = pcall(function()
						DestroyIDK()
					end)
					if g then
						print(g)
					end
				end
			end)
		end
		SaveSettings("Auto Destroy IDK", s)
	end
)
LeviathanEventSection.CreateToggle(
	{
		Title = "Attack Multi Segments Leviathan",
		Desc = "Please enable the damage counter so I can calculate the damage dealt to that segment.\10plz Turn on multi Segments first.",
		Default = Settings["Attack Multi Segments Leviathan"] or false,
	},
	function(s)
		if s and not Settings["Auto Attack Leviathan"] then
			A.CreateNoti({ Title = "Banana Cat Hub", Desc = "Turn On Auto Attack Leviathan, plz", ShowTime = 5 })
		end
		SaveSettings("Attack Multi Segments Leviathan", s)
	end
)
LeviathanEventSection.CreateSlider(
	{
		Title = "Value Damage Multi Segments",
		Min = 0,
		Max = 1000000,
		Default = Settings["Value Damage Multi Segments"] or 30000,
		Precise = true,
	},
	function(s)
		SaveSettings("Value Damage Multi Segments", s)
	end
)
function DetectLeviathan(s, g)
	local I, _, y = next, s:GetChildren()
	for P, P in I, _, y do
		if P.Name == "Leviathan Tail" and (P:GetAttribute("HealthEnabled")) and P.Health.Value > 0 then
			return P
		end
	end
	y, I, _ = next, s:GetChildren()
	for P, P in y, I, _ do
		if P.Name == "Leviathan" and not P:GetAttribute("Armored") and P.Health.Value > 0 then
			return P
		end
	end
	if g then
		_, I, y = next, s:GetChildren()
		for s, s in _, I, y do
			if s.Name == "Leviathan Segment" and s:GetAttribute("SegmentId") == g and s.Health.Value > 0 then
				return s
			end
		end
	end
end
function MultiSegmentLeviathan(s, g)
	if g then
		local I, _, y, P = Settings["Value Damage Multi Segments"] or 30000, next, s:GetChildren()
		for s, s in _, y, P do
			if
				s.Name == "Leviathan Segment"
				and s:GetAttribute("SegmentId") == g
				and s.Health.Value > 0
				and (not s:FindFirstChild("Tinhdamage") or s:FindFirstChild("Tinhdamage") and s.Tinhdamage.Value < I)
			then
				return s
			end
		end
	end
end
getgenv().CFrameLeviathan = CFrame.new(0, 142, 0)
function AutoAttackLeviathan()
	local s = MultiSegmentLeviathan(game.workspace.SeaBeasts, 2)
		or (MultiSegmentLeviathan(game.workspace.SeaBeasts, 3))
		or (MultiSegmentLeviathan(game.workspace.SeaBeasts, 4))
	if Settings["Attack Multi Segments Leviathan"] then
		local g = Settings["Value Damage Multi Segments"] or 30000
		if s then
			repeat
				task.wait()
				if not s:FindFirstChild("Tinhdamage") then
					Instance.new("IntValue", s).Name = "Tinhdamage"
				end
				if s:FindFirstChild("Tinhdamage") and s.Tinhdamage.Value < g then
					if game:GetService("Players").LocalPlayer.PlayerGui.Main.DmgCounter.Visible and l then
						s.Tinhdamage.Value = s.Tinhdamage.Value + b
						X, l = b, false
						task.wait(0.1)
					end
				end
				if s.Name == "Leviathan" then
					getgenv().AimPos = s.Hitbox11.CFrame
					spawn(function()
						toTarget((CFrame.new(s.HumanoidRootPart.Position.X, 140, s.HumanoidRootPart.Position.Z)))
					end)
				else
					getgenv().AimPos = s.Hitbox11.CFrame
					spawn(function()
						toTarget((CFrame.new(s.HumanoidRootPart.Position.X, 142, s.HumanoidRootPart.Position.Z)))
					end)
				end
				if Settings["Use Click M1 Fruit Leviathan"] then
					equiptool(NameWeapon("Blox Fruit"))
					local b = NameWeapon("Blox Fruit")
					if t.Character:FindFirstChild(b) and (t.Character[b]:FindFirstChild("LeftClickRemote")) then
						getgenv().UseFruitM1(s, true)
					end
				elseif Settings["Use Click M1 Skull Guitar Leviathan"] then
					equiptool(NameWeapon("Gun"))
					SpamGunSkullGuitar(v.Hitbox11)
					if t:DistanceFromCharacter(v.Hitbox11.Position) < 400 then
						UseSkillGun()
					end
				elseif t:DistanceFromCharacter(s.RootPart.Position) < 400 then
					AutoUseSkillSeabeast()
				end
			until not s
				or not s.Parent
				or s.Health.Value == 0
				or not Settings["Auto Attack Leviathan"]
				or s:FindFirstChild("Tinhdamage") and s.Tinhdamage.Value >= g
			return
		end
	end
	local b = DetectLeviathan(game.workspace.SeaBeasts, 2)
		or (DetectLeviathan(game.workspace.SeaBeasts, 3))
		or (DetectLeviathan(game.workspace.SeaBeasts, 4))
		or (DetectLeviathan(game.workspace.SeaBeasts))
	if b then
		repeat
			task.wait()
			if b.Name == "Leviathan" then
				getgenv().AimPos = b.Hitbox11.CFrame
				spawn(function()
					toTarget((CFrame.new(b.HumanoidRootPart.Position.X, 140, b.HumanoidRootPart.Position.Z)))
				end)
			else
				getgenv().AimPos = b.Hitbox11.CFrame
				spawn(function()
					toTarget((CFrame.new(b.HumanoidRootPart.Position.X, 142, b.HumanoidRootPart.Position.Z)))
				end)
			end
			if Settings["Use Click M1 Fruit Leviathan"] then
				equiptool(NameWeapon("Blox Fruit"))
				local X = NameWeapon("Blox Fruit")
				if t.Character:FindFirstChild(X) and (t.Character[X]:FindFirstChild("LeftClickRemote")) then
					getgenv().UseFruitM1(b, true)
				end
			elseif Settings["Use Click M1 Skull Guitar Leviathan"] then
				equiptool(NameWeapon("Gun"))
				SpamGunSkullGuitar(b.Hitbox11)
				if t:DistanceFromCharacter(b.Hitbox11.Position) < 400 then
					UseSkillGun()
				end
			elseif t:DistanceFromCharacter(b.Hitbox11.Position) < 400 then
				AutoUseSkillSeabeast()
			end
		until not b
			or not b.Parent
			or b.Health.Value == 0
			or not Settings["Auto Attack Leviathan"]
			or Settings["Attack Multi Segments Leviathan"] and s
	end
end
local function b(s, X)
	local g = s.PrimaryPart.CFrame
	local l, I = g.Position, (g.LookVector * Vector3.new(1, 0, 1)).Unit
	s = ((X - l) * Vector3.new(1, 0, 1)).Unit
	l = I:Dot(s)
	X, g = math.acos(math.clamp(l, -1, 1)), I:Cross(s)
	I = math.deg(X)
	return if g.Y < 0 then -I else I
end
local function s(X, g)
	local l = X.PrimaryPart.Position
	local I = Vector3.new(g.X, l.Y, g.Z)
	X:SetPrimaryPartCFrame((CFrame.lookAt(l, I)))
end
game:GetService("VirtualInputManager")
local X, g =
	{
		Vector3.new(7415.83251953125, 24.0008487701416, -6664.6826171875),
		Vector3.new(-4703.16015625, 24.000019073486328, -7.822202682495117),
		Vector3.new(-8762.3310546875, 23.99974822998047, -452.2586669921875),
		Vector3.new(-15018.0634765625, 23.999053955078125, 199.0315399169922),
		Vector3.new(-16065.728515625, 23.9991512298584, 421.8982238769531),
	},
	{
		Vector3.new(7415.83251953125, 24.0008487701416, -6664.6826171875),
		Vector3.new(1162.8353271484375, 24.00018882751465, -1825.8121337890625),
		Vector3.new(2517.887451171875, 24.000118255615234, 5109.43115234375),
		Vector3.new(5172.72607421875, 23.999813079833984, 3893.62451171875),
		Vector3.new(5203.80908203125, 24.001039505004883, 2013.0904541015625),
	}
playerModule = require(game.Players.LocalPlayer:WaitForChild("PlayerScripts"):WaitForChild("PlayerModule"))
function AutoMoveTo(l)
	playerModule:GetClickToMoveController():MoveTo(l, false, false)
end
function DriveBoatToTiki()
	for l, I in ipairs(X) do
		while _G.autoDrive and (task.wait()) do
			local X = checkboatFind()
			if not X then
				return
			end
			l = b(X, I)
			if (X.PrimaryPart.Position - I).Magnitude < 10 then
				X.PrimaryPart.ThrottleFloat = 0
				X.PrimaryPart.Throttle = 0
				break
			end
			spawn(function()
				X.VehicleSeat.MaxSpeed = Settings["Speed Boat Auto Drive"] or 300
				NoclipBoat(X)
			end)
			if math.abs(l) > 5 then
				s(X, I)
				X.PrimaryPart.ThrottleFloat = 0
				X.PrimaryPart.Throttle = 0
			else
				X.PrimaryPart.ThrottleFloat = 1
				X.PrimaryPart.Throttle = 1
			end
		end
	end
end
function DriveBoatToHydra()
	for X, l in ipairs(g) do
		while _G.autoDrive and (task.wait(0.1)) do
			local g = checkboatFind()
			if not g then
				return
			end
			X = b(g, l)
			if (g.PrimaryPart.Position - l).Magnitude < 10 then
				g.PrimaryPart.ThrottleFloat = 0
				g.PrimaryPart.Throttle = 0
				break
			end
			spawn(function()
				g.VehicleSeat.MaxSpeed = Settings["Speed Boat Auto Drive"] or 300
				NoclipBoat(g)
			end)
			if math.abs(X) > 5 then
				s(g, l)
				g.PrimaryPart.ThrottleFloat = 0
				g.PrimaryPart.Throttle = 0
			else
				g.PrimaryPart.ThrottleFloat = 1
				g.PrimaryPart.Throttle = 1
			end
		end
	end
end
LeviathanEventSection.CreateToggle(
	{ Title = "Auto Attack Leviathan", Desc = nil, Default = Settings["Auto Attack Leviathan"] or false },
	function(b)
		if b then
			spawn(function()
				while Settings["Auto Attack Leviathan"] and (wait(0.1)) do
					local X, X = pcall(function()
						AutoAttackLeviathan()
					end)
					if X then
						print(X)
					end
				end
			end)
		end
		SaveSettings("Auto Attack Leviathan", b)
	end
)
LeviathanEventSection.CreateToggle(
	{ Title = "Use Click M1 Fruit Leviathan", Desc = nil, Default = Settings["Use Click M1 Fruit Leviathan"] or false },
	function(b)
		SaveSettings("Use Click M1 Fruit Leviathan", b)
	end
)
LeviathanEventSection.CreateToggle(
	{
		Title = "Use Click M1 Skull Guitar Leviathan",
		Desc = nil,
		Default = Settings["Use Click M1 Skull Guitar Leviathan"] or false,
	},
	function(b)
		SaveSettings("Use Click M1 Skull Guitar Leviathan", b)
	end
)
local b = LeviathanEventSection.CreateDropdown(
	{
		Title = "Select Owner Boat Beast Hunter Shoot Heart",
		List = DetectNamePlayer(),
		Search = true,
		Selected = false,
		Default = Settings["Select Owner Boat Beast Hunter"] or nil,
	},
	function(X)
		SaveSettings("Select Owner Boat Beast Hunter", X)
	end
)
LeviathanEventSection.CreateButton({ Title = "Refresh Player" }, function()
	b:GetNewList(DetectNamePlayer())
end)
LeviathanEventSection.CreateToggle(
	{ Title = "Use Your Boat Beast Hunter", Desc = nil, Default = Settings["Use Your Boat Beast Hunter"] or false },
	function(b)
		SaveSettings("Use Your Boat Beast Hunter", b)
	end
)
function checkboatBeastHunter()
	local b = Settings["Select Owner Boat Beast Hunter"]
	b = if Settings["Use Your Boat Beast Hunter"] then t.Name else b
	local X, g, l = next, game:GetService("Workspace").Boats:GetChildren()
	for I, I in X, g, l do
		if I:IsA("Model") then
			if I:FindFirstChild("Owner") and tostring(I.Owner.Value) == b and I.Humanoid.Value > 0 then
				return I
			end
		end
	end
	return false
end
function ShootHeartLeviathan()
	if workspace.Map:FindFirstChild("FrozenHeart") then
		if not workspace.Map.FrozenHeart.Inside:GetAttribute("Harpooned") then
			local b = checkboatBeastHunter()
			NoclipBoat(b)
			local X, g, l, I =
				game:service("TweenService"),
				CFrame.new(
					workspace.Map:FindFirstChild("FrozenHeart").Cube.Position.X,
					b.WorldPivot.Y,
					workspace.Map:FindFirstChild("FrozenHeart").Cube.Position.Z
				) * CFrame.new(0, 0, 300),
				CFrame.Angles,
				math.rad
			local I = g * l(0, 6.283185307179586, 0)
			if (I.Position - b.VehicleSeat.Position).Magnitude > 5 then
				if t.Character.Humanoid.SeatPart and t.Character.Humanoid.SeatPart.Name == "VehicleSeat" then
					l = TweenInfo.new((I.Position - b.VehicleSeat.Position).Magnitude / 150, Enum.EasingStyle.Quad)
					g = X:Create(b.VehicleSeat, l, { CFrame = I })
					g:Play()
					g.Completed:wait()
					wait(1)
					s(b, workspace.Map:FindFirstChild("FrozenHeart").Inside.Position)
				else
					toTarget(b.VehicleSeat.CFrame)
				end
			elseif t.Character.Humanoid.SeatPart and t.Character.Humanoid.SeatPart.Parent.Name == "Harpoon" then
				local s = {
					[1] = "FireHarpoon",
					[2] = 0.7853981633974483,
					[3] = 4.4342573293783646E-4,
					[4] = b.Harpoon,
					[5] = workspace:GetServerTimeNow(),
				}
				game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer(unpack(s))
			else
				toTarget(b.Harpoon.Seat.CFrame)
			end
		else
			A.CreateNoti({ Title = "Banana Cat Hub", Desc = "Successfully Fire Shoot Heart Leviathan", ShowTime = 5 })
			wait(5)
		end
	end
end
LeviathanEventSection.CreateToggle(
	{
		Title = "Auto Fire Shoot Heart Leviathan",
		Desc = nil,
		Default = Settings["Auto Fire Shoot Heart Leviathan"] or false,
	},
	function(b)
		if b then
			spawn(function()
				while Settings["Auto Fire Shoot Heart Leviathan"] and (task.wait(0.1)) do
					local s, s = pcall(function()
						ShootHeartLeviathan()
					end)
					if s then
						print(s)
					end
				end
			end)
		end
		SaveSettings("Auto Fire Shoot Heart Leviathan", b)
	end
)
LeviathanEventSection.CreateToggle(
	{ Title = "Teleport Frozen Dimension", Desc = nil, Default = Settings["Teleport Frozen Dimension"] or false },
	function(b)
		if b then
			spawn(function()
				while Settings["Teleport Frozen Dimension"] and (wait()) do
					pcall(function()
						if game.workspace._WorldOrigin.Locations:FindFirstChild("Frozen Dimension") then
							local s = DetectNpc("Frozen Watcher")
							if s then
								toTarget(s.HumanoidRootPart.CFrame)
								return
							end
						end
					end)
				end
			end)
		end
		SaveSettings("Teleport Frozen Dimension", b)
	end
)
LeviathanEventSection.CreateToggle(
	{
		Title = "Tween Boat To Frozen Dimension",
		Desc = nil,
		Default = Settings["Tween Boat To Frozen Dimension"] or false,
	},
	function(b)
		if b then
			spawn(function()
				while Settings["Tween Boat To Frozen Dimension"] and (wait()) do
					pcall(function()
						if game.workspace._WorldOrigin.Locations:FindFirstChild("Frozen Dimension") then
							AllNPCS = {}
							for s, s in pairs(game:GetService("Workspace").NPCs:GetChildren()) do
								table.insert(AllNPCS, s)
							end
							for s, s in pairs(game:GetService("ReplicatedStorage").NPCs:GetChildren()) do
								table.insert(AllNPCS, s)
							end
							for s, X in pairs(AllNPCS) do
								if X.Name == "Frozen Watcher" then
									s = checkboatFind()
									repeat
										task.wait()
										local g = CFrame.new(
											X.HumanoidRootPart.Position.X,
											s.VehicleSeat.Position.Y,
											X.HumanoidRootPart.Position.Z
										)
										manageTween(s.VehicleSeat, g, 350, "TweenBoatToFrozen")
										NoclipBoat(s)
									until game:GetService("Workspace").NPCs:FindFirstChild("Frozen Watcher")
										or not Settings["Tween Boat To Frozen Dimension"]
									if getgenv().TweenBoatToFrozen then
										getgenv().TweenBoatToFrozen:Pause()
										getgenv().TweenBoatToFrozen:Cancel()
									end
								end
							end
						end
					end)
				end
			end)
		end
		SaveSettings("Tween Boat To Frozen Dimension", b)
	end
)
LeviathanEventSection.CreateSlider(
	{
		Title = "Speed Boat Auto Drive",
		Min = 0,
		Max = 500,
		Default = Settings["Speed Boat Auto Drive"] or 300,
		Precise = true,
	},
	function(b)
		SaveSettings("Speed Boat Auto Drive", b)
	end
)
LeviathanEventSection.CreateToggle(
	{ Title = "Drive Boat To Tiki", Desc = nil, Default = Settings["Drive Boat To Tiki"] or false },
	function(b)
		_G.autoDrive = b
		if b then
			spawn(function()
				local s, X = pcall(DriveBoatToTiki)
				if not s then
					warn("L\225\187\151i khi ch\225\186\161y DriveBoatToTiki:", X)
				end
			end)
		end
		SaveSettings("Drive Boat To Tiki", b)
	end
)
LeviathanEventSection.CreateToggle(
	{ Title = "Drive Boat To Hydra", Desc = nil, Default = Settings["Drive Boat To Hydra"] or false },
	function(b)
		_G.autoDrive = b
		if b then
			spawn(function()
				local s, X = pcall(DriveBoatToHydra)
				if not s then
					warn("L\225\187\151i khi ch\225\186\161y DriveBoatToHydra:", X)
				end
			end)
		end
		SaveSettings("Drive Boat To Hydra", b)
	end
)
BoatSettingSection = SeaEventTab.CreateSection("Boat Setting")
local b = table.find({ Enum.Platform.IOS, Enum.Platform.Android }, game:GetService("UserInputService"):GetPlatform())
FLYING = false
QEfly = true
iyflyspeed = 1
function getRoot(s)
	return s:FindFirstChild("HumanoidRootPart") or (s:FindFirstChild("Torso")) or (s:FindFirstChild("UpperTorso"))
end
function sFLY(s)
	repeat
		wait()
	until t and t.Character and (getRoot(t.Character)) and (t.Character:FindFirstChildOfClass("Humanoid"))
	repeat
		wait()
	until IYMouse
	if flyKeyDown or flyKeyUp then
		flyKeyDown:Disconnect()
		flyKeyUp:Disconnect()
	end
	local X, g, l, I =
		getRoot(t.Character),
		{ F = 0, B = 0, L = 0, R = 0, Q = 0, E = 0 },
		{ F = 0, B = 0, L = 0, R = 0, Q = 0, E = 0 },
		0
	local function _()
		FLYING = true
		local y = Instance.new("BodyVelocity")
		y.Parent = X
		y.velocity = Vector3.new(0, 0, 0)
		y.maxForce = Vector3.new(9000000000, 9000000000, 9000000000)
		task.spawn(function()
			repeat
				wait()
				if not s and (S.LocalPlayer.Character:FindFirstChildOfClass("Humanoid")) then
					S.LocalPlayer.Character:FindFirstChildOfClass("Humanoid").PlatformStand = true
				end
				local X = g.L + g.R ~= 0 or g.F + g.B ~= 0 or g.Q + g.E ~= 0
				if X then
					I = 50
				else
					local X = not (g.L + g.R ~= 0 or g.F + g.B ~= 0 or g.Q + g.E ~= 0) and I ~= 0
					if X then
						I = 0
					end
				end
				if g.L + g.R ~= 0 or g.F + g.B ~= 0 or g.Q + g.E ~= 0 then
					y.velocity = (
						workspace.CurrentCamera.CoordinateFrame.lookVector * (g.F + g.B)
						+ (
							workspace.CurrentCamera.CoordinateFrame
								* CFrame.new(g.L + g.R, (g.F + g.B + g.Q + g.E) * 0.2, 0).p
							- workspace.CurrentCamera.CoordinateFrame.p
						)
					) * I
					l = { F = g.F, B = g.B, L = g.L, R = g.R }
				elseif g.L + g.R == 0 and g.F + g.B == 0 and g.Q + g.E == 0 and I ~= 0 then
					y.velocity = (
						workspace.CurrentCamera.CoordinateFrame.lookVector * (l.F + l.B)
						+ (
							workspace.CurrentCamera.CoordinateFrame
								* CFrame.new(l.L + l.R, (l.F + l.B + g.Q + g.E) * 0.2, 0).p
							- workspace.CurrentCamera.CoordinateFrame.p
						)
					) * I
				else
					y.velocity = Vector3.new(0, 0, 0)
				end
			until not FLYING
			g, l, I = { F = 0, B = 0, L = 0, R = 0, Q = 0, E = 0 }, { F = 0, B = 0, L = 0, R = 0, Q = 0, E = 0 }, 0
			y:Destroy()
			if S.LocalPlayer.Character:FindFirstChildOfClass("Humanoid") then
				S.LocalPlayer.Character:FindFirstChildOfClass("Humanoid").PlatformStand = false
			end
		end)
	end
	flyKeyDown = IYMouse.KeyDown:Connect(function(X)
		if X:lower() == "w" then
			g.F = s and vehicleflyspeed or iyflyspeed
		elseif X:lower() == "s" then
			g.B = -(s and vehicleflyspeed or iyflyspeed)
		elseif X:lower() == "a" then
			g.L = -(s and vehicleflyspeed or iyflyspeed)
		elseif X:lower() == "d" then
			g.R = s and vehicleflyspeed or iyflyspeed
		elseif QEfly and X:lower() == "e" then
			g.Q = (s and vehicleflyspeed or iyflyspeed) * 2
		elseif QEfly and X:lower() == "q" then
			g.E = -(s and vehicleflyspeed or iyflyspeed) * 2
		end
		pcall(function()
			workspace.CurrentCamera.CameraType = Enum.CameraType.Track
		end)
	end)
	flyKeyUp = IYMouse.KeyUp:Connect(function(s)
		if s:lower() == "w" then
			g.F = 0
		elseif s:lower() == "s" then
			g.B = 0
		elseif s:lower() == "a" then
			g.L = 0
		elseif s:lower() == "d" then
			g.R = 0
		elseif s:lower() == "e" then
			g.Q = 0
		elseif s:lower() == "q" then
			g.E = 0
		end
	end)
	_()
end
function randomStringfly()
	local s = {}
	for X = 1, math.random(10, 20), 1 do
		s[X] = string.char(math.random(32, 126))
	end
	return table.concat(s)
end
function NOFLY()
	FLYING = false
	if game.Players.LocalPlayer.PlayerGui:FindFirstChild("ScreenGuiFly") then
		game.Players.LocalPlayer.PlayerGui.ScreenGuiFly:Destroy()
	end
	if flyKeyDown or flyKeyUp then
		flyKeyDown:Disconnect()
		flyKeyUp:Disconnect()
	end
	if S.LocalPlayer.Character:FindFirstChildOfClass("Humanoid") then
		S.LocalPlayer.Character:FindFirstChildOfClass("Humanoid").PlatformStand = false
	end
	pcall(function()
		workspace.CurrentCamera.CameraType = Enum.CameraType.Custom
	end)
end
local s, X = randomStringfly(), randomStringfly()
local g, l
local function S(I)
	pcall(function()
		FLYING = false
		game.Players.LocalPlayer.PlayerGui.ScreenGuiFly:Destroy()
		local _ = getRoot(I.Character)
		_:FindFirstChild(s):Destroy()
		_:FindFirstChild(X):Destroy()
		I.Character:FindFirstChildWhichIsA("Humanoid").PlatformStand = false
		g:Disconnect()
		l:Disconnect()
	end)
end
local function X(I, _)
	S(I)
	FLYING = true
	local y, P, Y, H, Z, C, J =
		getRoot(I.Character),
		workspace.CurrentCamera,
		Vector3.new(),
		Vector3.new(0, 0, 0),
		Vector3.new(9000000000, 9000000000, 9000000000),
		require(I.PlayerScripts:WaitForChild("PlayerModule"):WaitForChild("ControlModule")),
		Instance.new("BodyVelocity")
	J.Name = s
	J.Parent = y
	J.MaxForce = H
	J.Velocity = H
	g = I.CharacterAdded:Connect(function()
		local g = Instance.new("BodyVelocity")
		g.Name = s
		g.Parent = y
		g.MaxForce = H
		g.Velocity = H
	end)
	local g, H, J = Instance.new("ScreenGui"), Instance.new("TextButton"), Instance.new("TextButton")
	g.Name = "ScreenGuiFly"
	g.Parent = game.Players.LocalPlayer:WaitForChild("PlayerGui")
	g.ZIndexBehavior = Enum.ZIndexBehavior.Sibling
	g.ResetOnSpawn = false
	H.Name = "FlyUp"
	H.Parent = g
	H.BackgroundColor3 = Color3.fromRGB(255, 255, 255)
	H.BackgroundTransparency = 1
	H.BorderColor3 = Color3.fromRGB(0, 0, 0)
	H.BorderSizePixel = 0
	H.Position = UDim2.new(0.158661261, 0, 0.82663101, 0)
	H.Size = UDim2.new(0.0538219661, 0, 0.0765434727, 0)
	H.Font = Enum.Font.SourceSans
	H.Text = "\226\134\145"
	H.TextColor3 = Color3.fromRGB(0, 0, 0)
	H.TextScaled = true
	H.TextSize = 14
	H.TextWrapped = true
	J.Name = "FlyDown"
	J.Parent = g
	J.BackgroundColor3 = Color3.fromRGB(255, 255, 255)
	J.BackgroundTransparency = 1
	J.BorderColor3 = Color3.fromRGB(0, 0, 0)
	J.BorderSizePixel = 0
	J.Position = UDim2.new(0.158661261, 0, 0.922887683, 0)
	J.Size = UDim2.new(0.0538219661, 0, 0.0765434727, 0)
	J.Font = Enum.Font.SourceSans
	J.Text = "\226\134\147"
	J.TextColor3 = Color3.fromRGB(0, 0, 0)
	J.TextScaled = true
	J.TextSize = 14
	J.TextWrapped = true
	l = game:GetService("RunService").RenderStepped:Connect(function()
		y = getRoot(I.Character)
		P = workspace.CurrentCamera
		if I.Character:FindFirstChildWhichIsA("Humanoid") and y and (y:FindFirstChild(s)) then
			local g, l = I.Character:FindFirstChildWhichIsA("Humanoid"), y:FindFirstChild(s)
			l.MaxForce = Z
			if not _ then
				g.PlatformStand = true
			end
			l.Velocity = Y
			g = C:GetMoveVector()
			if g.X > 0 then
				l.Velocity = l.Velocity + P.CFrame.RightVector * (g.X * ((_ and vehicleflyspeed or iyflyspeed) * 50))
			end
			if g.X < 0 then
				l.Velocity = l.Velocity + P.CFrame.RightVector * (g.X * ((_ and vehicleflyspeed or iyflyspeed) * 50))
			end
			if g.Z > 0 then
				l.Velocity = l.Velocity - P.CFrame.LookVector * (g.Z * ((_ and vehicleflyspeed or iyflyspeed) * 50))
			end
			if g.Z < 0 then
				l.Velocity = l.Velocity - P.CFrame.LookVector * (g.Z * ((_ and vehicleflyspeed or iyflyspeed) * 50))
			end
			J.MouseButton1Click:Connect(function()
				l.Velocity = Vector3.new(0, -20, 0)
			end)
			H.MouseButton1Click:Connect(function()
				l.Velocity = Vector3.new(0, 20, 0)
			end)
		end
	end)
end
BoatSettingSection.CreateToggle({ Title = "Fly Boat", Desc = nil, Default = Settings["Fly Boat"] or false }, function(s)
	if s then
		spawn(function()
			while Settings["Fly Boat"] and (wait(0.1)) do
				pcall(function()
					if t.Character.Humanoid.Sit then
						if not b then
							NOFLY()
							wait()
							sFLY(true)
						else
							X(t, true)
						end
						repeat
							wait()
						until not Settings["Fly Boat"] or not t.Character.Humanoid.Sit
						if not b then
							NOFLY()
						else
							S(t)
						end
					end
				end)
			end
		end)
	end
	SaveSettings("Fly Boat", s)
end)
R = Settings["Value Speed Fly Boat"]
BoatSettingSection.CreateSlider(
	{ Title = "Value Speed Boat", Min = 0, Max = 500, Default = Settings["Value Speed Boat"] or 200, Precise = true },
	function(b)
		SaveSettings("Value Speed Boat", b)
	end
)
BoatSettingSection.CreateSlider(
	{
		Title = "Value Speed Tween Boat",
		Min = 50,
		Max = 2000,
		Default = tonumber(Settings["Value Speed Tween Boat"]) or 350,
		Precise = true,
	},
	function(b)
		SaveSettings("Value Speed Tween Boat", b)
		local s = getgenv().TweenBoat
		if s and s.Speed then
			s.Speed = math.max(tonumber(b) or 350, 1)
		end
	end
)
BoatSettingSection.CreateSlider(
	{
		Title = "Value Speed Fly Boat",
		Min = 0,
		Max = 10,
		Default = Settings["Value Speed Fly Boat"] or 3,
		Precise = true,
	},
	function(b)
		SaveSettings("Value Speed Fly Boat", b)
	end
)
function checkSpeedboat()
	local b, s = tonumber(Settings["Value Speed Boat"]) or 200, checkboat()
	if s then
		local X = s:FindFirstChild("VehicleSeat")
		if X and X.MaxSpeed + 1 < b then
			return s
		end
	end
	return false
end
function ChangeSpeedBoat()
	local b, s = tonumber(Settings["Value Speed Boat"]) or 200, checkSpeedboat()
	if s then
		s.VehicleSeat.MaxSpeed = b
	end
end
BoatSettingSection.CreateToggle(
	{ Title = "Change Speed Boat", Desc = nil, Default = Settings["Change Speed Boat"] or false },
	function(b)
		if b then
			spawn(function()
				while Settings["Change Speed Boat"] and (task.wait(0.3)) do
					local s, X = pcall(ChangeSpeedBoat)
					if not s then
						WarnOnce("ChangeSpeedBoat", "Change Speed Boat loi: " .. tostring(X))
					end
				end
			end)
		end
		SaveSettings("Change Speed Boat", b)
	end
)
RaceMain = Main.CreatePage({ Page_Name = "Upgrade Race", Page_Title = "Upgrade Race Tab" })
RaceDracoSection = RaceMain.CreateSection("Race Draco")
function DetectGearUp(b)
	local s = require(game:GetService("Players").LocalPlayer.PlayerGui.TempleGui.LocalScriptTemple.Buttons)
	b = b or (game.ReplicatedStorage.Remotes.CommF_:InvokeServer("TempleClock", "Check"))
	if type(b) ~= "table" then
		return
	end
	local X, g = b.HadPoint == true, b.RaceLevel >= 2
	s.Gear1.GearType = "Default"
	s.Gear4.GearType = "Default"
	s.Gear5.GearType = "Default"
	s.Gear2.GearType = "Alpha"
	s.Gear2.CanSelect = false
	s.Gear3.CanSelect = false
	s.Gear2.GearType = b.RaceDetails.Gears[1] == "A" and "Alpha" or b.RaceDetails.Gears[1] == "B" and "Omega" or "Blank"
	s.Gear3.GearType = b.RaceDetails.Gears[2] == "A" and "Alpha" or b.RaceDetails.Gears[2] == "B" and "Omega" or "Blank"
	s.Gear4.GearType = b.RaceDetails.Gears[3] == "A" and "Alpha" or b.RaceDetails.Gears[3] == "B" and "Omega" or "Blank"
	s.Gear2.Unlocked = if b.RaceDetails.A + b.RaceDetails.B >= 0 then g else false
	s.Gear3.Unlocked = if b.RaceDetails.A + b.RaceDetails.B >= 1 then g else false
	s.Gear4.Unlocked = if b.RaceDetails.A + b.RaceDetails.B >= 2 then g else false
	s.Gear5.CanSelect = false
	s.Gear5.Unlocked = false
	if b.RaceDetails.C >= 1 then
		s.Gear5.Unlocked = true
	end
	s.Gear1.Unlocked = true
	if not g then
		s.Gear1.CanSelect = true
		s.Gear1.GearType = "Blank"
		X = true
	else
		s.Gear1.CanSelect = false
		s.Gear1.GearType = "Default"
	end
	if not X then
		s.Gear2.CanSelect = false
		s.Gear3.CanSelect = false
		s.Gear4.CanSelect = false
	else
		s.Gear2.CanSelect = if b.RaceDetails.A + b.RaceDetails.B == 0 then g else false
		s.Gear3.CanSelect = if b.RaceDetails.A + b.RaceDetails.B == 1 then g else false
		s.Gear4.CanSelect = if b.RaceDetails.A + b.RaceDetails.B >= 2 then g else false
		if b.RaceDetails.A + b.RaceDetails.B >= 3 then
			s.Gear2.CanSelect = true
			s.Gear3.CanSelect = true
			s.Gear4.CanSelect = true
			if s.Gear2.GearType == "Alpha" and s.Gear3.GearType == "Alpha" and s.Gear4.GearType == "Omega" then
				s.Gear4.CanSelect = false
			elseif s.Gear2.GearType == "Omega" and s.Gear3.GearType == "Omega" and s.Gear4.GearType == "Alpha" then
				s.Gear4.CanSelect = false
			elseif s.Gear2.GearType == "Alpha" and s.Gear3.GearType == "Omega" and s.Gear4.GearType == "Omega" then
				s.Gear4.CanSelect = false
				s.Gear2.CanSelect = false
			elseif s.Gear2.GearType == "Omega" and s.Gear3.GearType == "Alpha" and s.Gear4.GearType == "Omega" then
				s.Gear4.CanSelect = false
				s.Gear3.CanSelect = false
			elseif s.Gear2.GearType == "Omega" and s.Gear3.GearType == "Alpha" and s.Gear4.GearType == "Alpha" then
				s.Gear4.CanSelect = false
				s.Gear2.CanSelect = false
			elseif s.Gear2.GearType == "Alpha" and s.Gear3.GearType == "Omega" and s.Gear4.GearType == "Alpha" then
				s.Gear4.CanSelect = false
				s.Gear3.CanSelect = false
			end
		end
	end
	for X = 1, 5, 1 do
		b = s["Gear" .. X]
		if b and b.CanSelect then
			return "Gear" .. X
		end
	end
end
function ChooseGearV4()
	local b = game.ReplicatedStorage.Remotes.CommF_:InvokeServer("TempleClock", "Check")
	if not b or not b.HadPoint then
		return
	end
	local s = DetectGearUp(b)
	if not s then
		return
	end
	b = Settings["Select Gear V4"] == "Alpha" and "Alpha" or "Omega"
	game.ReplicatedStorage.Remotes.CommF_:InvokeServer("TempleClock", "SpendPoint", s, b)
	local X = game.ReplicatedStorage.Remotes.CommF_:InvokeServer("TempleClock", "Check")
	if X and X.HadPoint and DetectGearUp(X) == s then
		game.ReplicatedStorage.Remotes.CommF_:InvokeServer(
			"TempleClock",
			"SpendPoint",
			s,
			b == "Alpha" and "Omega" or "Alpha"
		)
	end
end
function DetectFireFlower()
	local b, s, X = next, workspace.FireFlowers:GetChildren()
	for g, g in b, s, X do
		if g:IsA("Model") then
			return g
		end
	end
end
local b = { "V2InProgress", "V3InProgress", "V2TurnInReady", "V3TurnInReady" }
function AutoUpgradeRaceDraco()
	if game.Players.LocalPlayer.Data.Race.Value ~= "Draco" then
		A.CreateNoti({ Title = "Banana Cat Hub", Desc = "Change Race Draco plz", ShowTime = 5 })
		wait(5)
		return
	elseif DetectItemPlr("Primordial Reign") then
		A.CreateNoti({ Title = "Banana Cat Hub", Desc = "Done V3 Draco", ShowTime = 5 })
		wait(5)
		return
	end
	local s = workspace.NPCs:FindFirstChild("Dragon Wizard")
		or (game:GetService("ReplicatedStorage").NPCs:FindFirstChild("Dragon Wizard"))
		or NPCManager.getNPCsByName("Dragon Wizard")[1]._modelState._instance
	if not getgenv().QuestDraco or getgenv().QuestDraco and not table.find(b, getgenv().QuestDraco.AvailableVQuest) then
		if t:DistanceFromCharacter(s.HumanoidRootPart.Position) > 8 then
			toTarget(s.HumanoidRootPart.CFrame * CFrame.new(0, 4, 4))
		else
			getgenv().QuestDraco = game:GetService("ReplicatedStorage").Modules.Net["RF/InteractDragonQuest"]
				:InvokeServer({ NPC = "Dragon Wizard", Command = "Speak" })
			wait(1)
			if
				getgenv().QuestDraco and getgenv().QuestDraco.AvailableVQuest == "V2"
				or getgenv().QuestDraco.AvailableVQuest == "V3"
			then
				game:GetService("ReplicatedStorage").Modules.Net["RF/InteractDragonQuest"]
					:InvokeServer({ NPC = "Dragon Wizard", Command = "Ascension", Action = "Begin" })
				getgenv().QuestDraco = game:GetService("ReplicatedStorage").Modules.Net["RF/InteractDragonQuest"]
					:InvokeServer({ NPC = "Dragon Wizard", Command = "Speak" })
			end
		end
	elseif getgenv().QuestDraco.AvailableVQuest == "V2TurnInReady" then
		game:GetService("ReplicatedStorage").Modules.Net["RF/InteractDragonQuest"]
			:InvokeServer({ NPC = "Dragon Wizard", Command = "Ascension", Action = "Complete" })
		getgenv().QuestDraco = nil
	elseif getgenv().QuestDraco.AvailableVQuest == "V3TurnInReady" then
		game:GetService("ReplicatedStorage").Modules.Net["RF/InteractDragonQuest"]
			:InvokeServer({ NPC = "Dragon Wizard", Command = "Ascension", Action = "Complete" })
		getgenv().QuestDraco = nil
	elseif getgenv().QuestDraco.AvailableVQuest == "V2InProgress" then
		if not CheckCountItem("Fire Flower", 5) then
			local b = DetectFireFlower()
			if b then
				toTarget(b.PrimaryPart.CFrame)
				if t:DistanceFromCharacter(b.PrimaryPart.Position) < 8 then
					fireproximityprompt(b.ProximityPrompt, 1)
				end
			else
				local b = DetectMob("Forest Pirate")
				if not b then
					local X = DetectPartSpawnMob("Forest Pirate", true)
					if X then
						Instance.new("IntValue", X).Name = "Ignored"
						repeat
							wait()
							toTarget(X.CFrame * CFrame.new(0, 60, 0))
						until (X.Position - t.Character.HumanoidRootPart.Position).Magnitude <= 100
							or (DetectMob("Forest Pirate"))
							or not Settings["Auto Upgrade Race V2-V3 Draco"]
							or (wait(1))
					else
						DeleteIgnoredMobSpawn()
					end
				else
					repeat
						task.wait()
						sizepart(b)
						BringMob(b)
						UsedualFlock()
						ClickM1(b)
						if Settings["Select Weapon"] == "Blox Fruit" then
							toTarget(b.HumanoidRootPart.CFrame * CFrame.new(-7, 20, 0))
						else
							toTarget(b.HumanoidRootPart.CFrame * CFrame.new(7, 20, 0))
						end
					until not IsMobAlive(b) or not Settings["Auto Upgrade Race V2-V3 Draco"]
				end
			end
		elseif t:DistanceFromCharacter(s.HumanoidRootPart.Position) > 8 then
			toTarget(s.HumanoidRootPart.CFrame * CFrame.new(0, 4, 4))
		else
			game:GetService("ReplicatedStorage").Modules.Net["RF/InteractDragonQuest"]
				:InvokeServer({ NPC = "Dragon Wizard", Command = "Ascension", Action = "Complete" })
			getgenv().QuestDraco = nil
		end
	elseif getgenv().QuestDraco.AvailableVQuest == "V3InProgress" then
		SaveSettings("V3InProgress", true)
		if not getgenv().KilledTerroshark then
			local b, X = CheckNameBoss("Terrorshark"), checkboat()
			if not b then
				if not X then
					local g = CFrame.new(-16204.0810546875, 9.0863618850708, 479.2259521484375)
					if (g.Position - t.Character.HumanoidRootPart.Position).Magnitude > 8 then
						toTarget(g)
					else
						game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("BuyBoat", "PirateBrigade")
					end
				else
					local g = DecectPartRoughSea()
					if g then
						wait(1)
						V = if V == 0 then 7000 else 0
						Instance.new("IntValue", g).Name = "Ignored"
						wait(0.5)
					end
					getgenv().RoughSea = V
					g = CFrame.new(-32975.9921875, X.WorldPivot.Y, 25963.7109375)
						* CFrame.new(0, X.WorldPivot.Y, 0 + RoughSea)
					if not t.Character.Humanoid.Sit then
						toTarget(X.VehicleSeat.CFrame)
					else
						manageTween(X.VehicleSeat, g, 350, "TweenBoat")
					end
				end
			else
				repeat
					task.wait()
					TeleportSeaEvents(b)
					local X = b:FindFirstChild("HumanoidRootPart")
					getgenv().AimPos = CFrame.new(X.Position.X, 40, X.Position.Z)
					UsedualFlock()
					ClickM1(b, true)
				until not IsMobAlive(b) or not Settings["Auto Upgrade Race V2-V3 Draco"]
				getgenv().KilledTerroshark = true
			end
		elseif t:DistanceFromCharacter(s.HumanoidRootPart.Position) > 8 then
			toTarget(s.HumanoidRootPart.CFrame * CFrame.new(0, 4, 4))
		else
			game:GetService("ReplicatedStorage").Modules.Net["RF/InteractDragonQuest"]
				:InvokeServer({ NPC = "Dragon Wizard", Command = "Ascension", Action = "Complete" })
			getgenv().QuestDraco = nil
			getgenv().KilledTerroshark = false
		end
	end
end
RaceDracoSection.CreateToggle(
	{ Title = "Auto Upgrade Race V2-V3 Draco", Desc = nil, Default = Settings["Auto Upgrade Race V2-V3 Draco"] or false },
	function(b)
		if b then
			spawn(function()
				while Settings["Auto Upgrade Race V2-V3 Draco"] and (task.wait()) do
					local s, s = pcall(function()
						AutoUpgradeRaceDraco()
					end)
					if s then
						print(s)
					end
				end
			end)
		end
		SaveSettings("Auto Upgrade Race V2-V3 Draco", b)
	end
)
function CheckRelicChuaDat(b)
	for s, s in pairs(b:GetDescendants()) do
		if s:IsA("ParticleEmitter") and s.Enabled then
			return true
		end
	end
end
function GetRelicChuaDat(b)
	for s, X in next, b, nil do
		if string.find(s, "RelicModel") and (CheckRelicChuaDat(X)) then
			return X, s
		end
	end
end
function GetRelicChuanbiDat(b)
	for s, X in next, b, nil do
		if
			string.find(s, "RelicModel")
			and (X.PrimaryPart:FindFirstChild("AlignPosition"))
			and (CheckRelicChuaDat(X))
		then
			return X, s
		end
	end
end
function CheckModelTrialDraco()
	local b = {}
	v28 = workspace:WaitForChild("Map"):WaitForChild("DracoTrial")
	local s = {
		"Relic1",
		"Relic2",
		"Relic3",
		"EndRelic1",
		"EndRelic2",
		"EndRelic3",
		"Door1",
		"Door2",
		"Door3",
		"Brazier1",
		"Brazier2",
		"Brazier3",
		"Center",
		"EndPlatform",
		"TeleportOut",
	}
	for X, X in pairs(s) do
		b[X] = v28:FindFirstChild(X, true)
	end
	local X, g, R = next, workspace._WorldOrigin:GetChildren()
	for l, l in X, g, R do
		if l:IsA("Model") and l.Name == "Relic" then
			s = l:FindFirstChildWhichIsA("MeshPart")
			if s.Color == Color3.fromRGB(132, 203, 0) then
				b.RelicModel1 = l
			end
			if s.Color == Color3.fromRGB(232, 106, 110) then
				b.RelicModel2 = l
			end
			if s.Color == Color3.fromRGB(191, 153, 0) then
				b.RelicModel3 = l
			end
		end
	end
	return b
end
getgenv().StatusGearDraco = RaceDracoSection.CreateLabel({ Title = "Acient One Draco Status" })
ToggleAutoTrialDraco = RaceDracoSection.CreateToggle(
	{ Title = "Auto Trial Draco", Desc = nil, Default = Settings["Auto Trial Draco"] or false },
	function(b)
		if b then
			spawn(function()
				while Settings["Auto Trial Draco"] and (task.wait(0.1)) do
					local s, s = pcall(function()
						if
							t:DistanceFromCharacter(workspace._WorldOrigin.Locations["Trial of Flames"].Position)
							<= 3000
						then
							if workspace.Map.DracoTrial.TrialDoor.DoorTouch:FindFirstChild("TouchInterest") then
								getgenv().DoneTrialDraco = true
								toTarget(workspace.Map.DracoTrial.TrialDoor.DoorTouch.CFrame)
								wait(2)
								return
							end
							if game:GetService("Players").LocalPlayer.PlayerGui.Main.TopHUDList.RaidTimer.Visible then
								local X = CheckModelTrialDraco()
								local g, R = GetRelicChuaDat(X)
								local l, S = GetRelicChuanbiDat(X)
								if l then
									local l = X["EndRelic" .. S:split("RelicModel")[2]]
									local S = l:FindFirstChildWhichIsA("ProximityPrompt", true)
									if t:DistanceFromCharacter(l.WorldPivot.Position) > 8 then
										toTarget(l.WorldPivot)
									else
										wait(2)
										fireproximityprompt(S)
										wait(2)
									end
								elseif g then
									local g = X["Relic" .. R:split("RelicModel")[2]]
									local X = g:FindFirstChildWhichIsA("ProximityPrompt", true)
									if t:DistanceFromCharacter(g.WorldPivot.Position) > 8 then
										toTarget(g.WorldPivot)
									else
										wait(2)
										fireproximityprompt(X)
										wait(2)
									end
								end
							else
								game.ReplicatedStorage.Remotes.DracoTrial:InvokeServer()
								wait(3)
							end
						else
							if getgenv().DoneTrialDraco then
								A.CreateNoti({ Title = "Banana Cat Hub", Desc = "Done Trial", ShowTime = 5 })
								getgenv().DoneTrialDraco = false
								ToggleAutoTrialDraco:SetStage(false)
								return
							end
							if game:GetService("Workspace").Map:FindFirstChild("PrehistoricIsland") then
								if workspace.Map.PrehistoricIsland:FindFirstChild("TrialTeleport") then
									toTarget(workspace.Map.PrehistoricIsland.TrialTeleport.CFrame)
								else
									local X = DetectNpc("Fossil Expert")
									if X then
										toTarget(X.HumanoidRootPart.CFrame)
										return
									end
								end
							else
								A.CreateNoti({
									Title = "Banana Cat Hub",
									Desc = "Not have Prehistoric Island",
									ShowTime = 5,
								})
								wait(5)
							end
						end
					end)
					if s then
						print(s)
					end
				end
			end)
		end
		SaveSettings("Auto Trial Draco", b)
	end
)
function DetectRockVolcano()
	local b, s, X = next, workspace.Map.PrehistoricIsland.Core.VolcanoRocks:GetChildren()
	local g, R = 1 / 0
	for l, S in b, s, X do
		if
			S.Name == "Rock"
			and (S:FindFirstChild("VFXLayer"))
			and (S.VFXLayer:FindFirstChild("Specs"))
			and S.VFXLayer.Specs.Enabled
		then
			l = t:DistanceFromCharacter(S.WorldPivot.Position)
			if g > l then
				g, R = l, S
			end
		end
	end
	return R
end
function AutoUseSkillFixLava(b)
	b = Settings["Select Weapons Fix Lava"] or {}
	local s, X, g, R, l =
		b.Melee and (NameWeapon("Melee", true)) or false,
		b.Sword and (NameWeapon("Sword", true)) or false,
		b["Blox Fruit"] and (NameWeapon("Blox Fruit", true)) or false,
		b.Gun and (NameWeapon("Gun", true)) or false,
		game:GetService("Players").LocalPlayer.PlayerGui.Main.Skills
	if s and not l:FindFirstChild(s.Name) then
		equiptool(s.Name)
		return
	end
	if X and not l:FindFirstChild(X.Name) then
		equiptool(X.Name)
		return
	end
	if g and not l:FindFirstChild(g.Name) then
		equiptool(g.Name)
		return
	end
	if R and not l:FindFirstChild(R.Name) then
		equiptool(R.Name)
		return
	end
	l = if s and (CheckCDSkillTransformation(s, Settings["Select Skills " .. s.ToolTip]))
		then (CheckCDSkillTransformation(s, Settings["Select Skills " .. s.ToolTip]))
		else if X and (CheckCDSkillTransformation(X, Settings["Select Skills " .. X.ToolTip]))
			then (CheckCDSkillTransformation(X, Settings["Select Skills " .. X.ToolTip]))
			else if R and (CheckCDSkillTransformation(R, Settings["Select Skills " .. R.ToolTip]))
				then (CheckCDSkillTransformation(R, Settings["Select Skills " .. R.ToolTip]))
				else if g and (CheckCDSkillTransformation(g, Settings["Select Skills " .. g.ToolTip]))
					then (CheckCDSkillTransformation(g, Settings["Select Skills " .. g.ToolTip]))
					else nil
	if l then
		X = l.Parent.Name
		equiptool(X)
		if t.Character:FindFirstChild(X) then
			game:GetService("VirtualInputManager"):SendKeyEvent(true, l.Name, false, game)
			if Settings["Use skill fast dont hold"] then
				task.wait(0.05)
			else
				task.wait(tonumber(holdskill))
			end
			game:GetService("VirtualInputManager"):SendKeyEvent(false, l.Name, false, game)
		end
	end
end
function DetectLava()
	local b, s, X = next, workspace.Map.PrehistoricIsland:GetDescendants()
	for g, g in b, s, X do
		if g.Name == "TouchInterest" and g.Parent.Name ~= "TrialTeleport" then
			return true
		end
	end
end
function DetectGolem()
	for b, b in ipairs(game.workspace.Enemies:GetChildren()) do
		if
			b.Name == "Lava Golem"
			and (IsMobAlive(b))
			and t:DistanceFromCharacter(b.HumanoidRootPart.Position) <= 1500
		then
			return b
		end
	end
end
function DeleteLava()
	local b, s, X = next, workspace.Map.PrehistoricIsland.Core.InteriorLava:GetChildren()
	for g, g in b, s, X do
		g:Destroy()
	end
end
function DetectPositionVolcano()
	local b, s, X, g =
		{ [1] = workspace.Map.PrehistoricIsland.Core.PrehistoricRelic.Skull.Position },
		next,
		workspace.Map.PrehistoricIsland:GetDescendants()
	for R, R in s, X, g do
		if R:IsA("MeshPart") and R.MeshId == "rbxassetid://87519803677536" and math.floor(R.Position.Y) == 293 then
			b[2] = R.Position
		end
		if R:IsA("MeshPart") and R.MeshId == "rbxassetid://9664674474" and math.floor(R.Position.Y) == 234 then
			b[3] = R.Position
		end
		if R:IsA("MeshPart") and R.MeshId == "rbxassetid://14130842310" and math.floor(R.Position.Y) == 266 then
			b[4] = R.Position
		end
		if R:IsA("MeshPart") and R.MeshId == "rbxassetid://15672470777" and math.floor(R.Position.Y) == 86 then
			b[5] = R.Position
		end
		if R:IsA("MeshPart") and R.MeshId == "rbxassetid://5159878936" and math.floor(R.Position.Y) == 261 then
			b[6] = R.Position
		end
		if R:IsA("MeshPart") and R.MeshId == "rbxassetid://138849514693209" and math.floor(R.Position.Y) == 242 then
			b[7] = R.Position
		end
		if R:IsA("MeshPart") and R.MeshId == "rbxassetid://87519803677536" and math.floor(R.Position.Y) == 279 then
			b[8] = R.Position
		end
	end
	return b
end
function CheckPosnearRock(b, s)
	local X, g = 1 / 0
	local R = 0
	for l, S in next, b, nil do
		local b = Vector3.new(S.X, 0, S.Z)
		local I = (Vector3.new(s.Position.X, 0, s.Position.Z) - b).Magnitude
		if X > I then
			X, g, R = I, S, l
		end
	end
	return g, R
end
local b, s, X =
	false,
	1,
	{
		[273] = CFrame.new(40, 0, 0),
		[286] = CFrame.new(40, 0, 0),
		[246] = CFrame.new(0, -40, 0),
		[486] = CFrame.new(40, 0, 0),
		[364] = CFrame.new(40, 0, 0),
		[682] = CFrame.new(0, 0, -40),
		[490] = CFrame.new(0, 40, 0),
		[691] = CFrame.new(40, 0, 0),
		[502] = CFrame.new(-40, 0, 0),
		[256] = CFrame.new(-40, 0, 0),
		[290] = CFrame.new(0, 40, 0),
		[427] = CFrame.new(0, 40, 0),
		[692] = CFrame.new(0, 0, 40),
		[316] = CFrame.new(0, 40, 0),
		[481] = CFrame.new(0, 40, 0),
		[594] = CFrame.new(0, 40, 0),
		[649] = CFrame.new(40, 0, 0),
		[285] = CFrame.new(0, -40, 0),
		[250] = CFrame.new(0, 40, 0),
		[454] = CFrame.new(-40, 0, 0),
	}
function BuyGearDracoV4()
	if string.find(CheckAcientOneDracoStatus(), "Can Buy Gear") then
		game.ReplicatedStorage.Remotes.CommF_:InvokeServer("UpgradeRace", "Buy", 2)
	end
end
function FullyDraco()
	if not Settings["Auto Turn On V4"] then
		m:SetStage(true)
	end
	if not Settings["Auto Choose Gears"] and getgenv().ToggleAutoChooseGears then
		getgenv().ToggleAutoChooseGears:SetStage(true)
	end
	if CheckAcientOneDracoStatus() == "Ready For Trial" then
		if getgenv().WaitingjoinTrial then
			wait(5)
			getgenv().WaitingjoinTrial = false
		end
		if t:DistanceFromCharacter(workspace._WorldOrigin.Locations["Trial of Flames"].Position) <= 3000 then
			if workspace.Map.DracoTrial.TrialDoor.DoorTouch:FindFirstChild("TouchInterest") then
				getgenv().DoneTrialDraco = true
				toTarget(workspace.Map.DracoTrial.TrialDoor.DoorTouch.CFrame)
				wait(2)
				return
			end
			if game:GetService("Players").LocalPlayer.PlayerGui.Main.TopHUDList.RaidTimer.Visible then
				local g = CheckModelTrialDraco()
				local R, m = GetRelicChuaDat(g)
				local l, S = GetRelicChuanbiDat(g)
				if l then
					local l = g["EndRelic" .. S:split("RelicModel")[2]]
					local S = l:FindFirstChildWhichIsA("ProximityPrompt", true)
					if t:DistanceFromCharacter(l.WorldPivot.Position) > 8 then
						toTarget(l.WorldPivot)
					else
						wait(2)
						fireproximityprompt(S)
						wait(2)
					end
				elseif R then
					local R = g["Relic" .. m:split("RelicModel")[2]]
					local g = R:FindFirstChildWhichIsA("ProximityPrompt", true)
					if t:DistanceFromCharacter(R.WorldPivot.Position) > 8 then
						toTarget(R.WorldPivot)
					else
						wait(2)
						fireproximityprompt(g)
						wait(2)
					end
				end
			else
				game.ReplicatedStorage.Remotes.DracoTrial:InvokeServer()
				wait(3)
			end
		else
			if getgenv().DoneTrialDraco then
				wait(5)
				getgenv().DoneTrialDraco = false
				return
			end
			if not game:GetService("Workspace").Map:FindFirstChild("PrehistoricIsland") then
				getgenv().RespawnVolcano = true
				getgenv().turnoffnoclipBoatt = true
				if not CheckItemInventory("Volcanic Magnet") and not Settings["Ignore Craft Volcanic Magnet Draco"] then
					if getgenv().dacoMagnet then
						local g = tick()
						repeat
							wait()
						until tick() - g >= 5 or (game:GetService("Workspace").Map:FindFirstChild("PrehistoricIsland"))
						getgenv().dacoMagnet = false
						return
					end
					if not CheckCountItem("Scrap Metal", 10) then
						local g = { "Jungle Pirate", "Musketeer Pirate" }
						local R = DetectMob(g)
						if not R then
							if typeof(g) == "table" then
								if #N >= #g then
									N = {}
									return
								end
								local m = DetectPartSpawnMob(DetectNameTablePart(g))
								if m then
									table.insert(N, DetectNameTablePart(g))
									repeat
										wait()
										toTarget(m.CFrame * CFrame.new(0, 60, 0))
									until (m.Position - t.Character.HumanoidRootPart.Position).Magnitude <= 100
										or (DetectMob(g))
										or not Settings["Fully Trial Draco"]
									wait(1)
								end
							end
						else
							repeat
								task.wait()
								sizepart(R)
								BringMob(R)
								UsedualFlock()
								ClickM1(R)
								if Settings["Select Weapon"] == "Blox Fruit" then
									toTarget(R.HumanoidRootPart.CFrame * CFrame.new(-7, 20, 0))
								else
									toTarget(R.HumanoidRootPart.CFrame * CFrame.new(7, 20, 0))
								end
							until not IsMobAlive(R) or not Settings["Fully Trial Draco"]
						end
						return
					elseif not CheckCountItem("Blaze Ember", 15) then
						local g = workspace.NPCs:FindFirstChild("Dragon Hunter")
							or (game:GetService("ReplicatedStorage").NPCs:FindFirstChild("Dragon Hunter"))
							or NPCManager.getNPCsByName("Dragon Hunter")[1]._modelState._instance
						if not getgenv().QuestHunterDragon then
							if t:DistanceFromCharacter(g.HumanoidRootPart.Position) > 8 then
								toTarget(g.HumanoidRootPart.CFrame * CFrame.new(0, 4, 4))
							else
								local g = game:GetService("ReplicatedStorage")
									:WaitForChild("Modules")
									:WaitForChild("Net")
									:WaitForChild("RF/DragonHunter")
									:InvokeServer(unpack({ [1] = { Context = "Check" } }))
								if not g or g and not g.Text then
									getgenv().QuestHunterDragon = game:GetService("ReplicatedStorage")
										:WaitForChild("Modules")
										:WaitForChild("Net")
										:WaitForChild("RF/DragonHunter")
										:InvokeServer(unpack({ [1] = { Context = "RequestQuest" } })).Text
								else
									getgenv().QuestHunterDragon = g.Text
								end
							end
						else
							local g = DetectEmberTemplate()
							if g then
								Instance.new("IntValue", g).Name = "Ignored"
								repeat
									wait()
									toTarget(g.Part.CFrame)
								until not g or not g.Parent
								return
							end
							if string.find(getgenv().QuestHunterDragon, "Hydra Enforcers") then
								local R = DetectMob("Hydra Enforcer")
								if not R then
									local m = DetectPartSpawnMob("Hydra Enforcer", true)
									if m then
										Instance.new("IntValue", m).Name = "Ignored"
										repeat
											wait()
											toTarget(m.CFrame * CFrame.new(0, 60, 0))
										until (m.Position - t.Character.HumanoidRootPart.Position).Magnitude
												<= 100
											or (DetectMob("Hydra Enforcer"))
											or not Settings["Fully Trial Draco"]
											or g
										wait(1)
									else
										DeleteIgnoredMobSpawn()
									end
								else
									repeat
										task.wait()
										sizepart(R)
										BringMob(R)
										UsedualFlock()
										ClickM1(R)
										if Settings["Select Weapon"] == "Blox Fruit" then
											toTarget(R.HumanoidRootPart.CFrame * CFrame.new(-7, 20, 0))
										else
											toTarget(R.HumanoidRootPart.CFrame * CFrame.new(7, 20, 0))
										end
									until not IsMobAlive(R) or not Settings["Fully Trial Draco"] or g
								end
							elseif string.find(getgenv().QuestHunterDragon, "Venomous Assailants") then
								local R = DetectMob("Venomous Assailant")
								if not R then
									local m = DetectPartSpawnMob("Venomous Assailant", true)
									if m then
										Instance.new("IntValue", m).Name = "Ignored"
										repeat
											wait()
											toTarget(m.CFrame * CFrame.new(0, 60, 0))
										until (m.Position - t.Character.HumanoidRootPart.Position).Magnitude
												<= 100
											or (DetectMob("Venomous Assailant"))
											or not Settings["Fully Trial Draco"]
											or g
										wait(1)
									else
										DeleteIgnoredMobSpawn()
									end
								else
									repeat
										task.wait()
										sizepart(R)
										BringMob(R)
										UsedualFlock()
										ClickM1(R)
										if Settings["Select Weapon"] == "Blox Fruit" then
											toTarget(R.HumanoidRootPart.CFrame * CFrame.new(-7, 20, 0))
										else
											toTarget(R.HumanoidRootPart.CFrame * CFrame.new(7, 20, 0))
										end
									until not IsMobAlive(R) or not Settings["Fully Trial Draco"] or g
								end
							elseif string.find(getgenv().QuestHunterDragon, "trees") then
								local R, m = workspace.CurrentCamera, DetectTree()
								if m then
									Instance.new("IntValue", m).Name = "Ignored"
									local l = tick()
									repeat
										wait()
										local S = m.WorldPivot.Position
										if t:DistanceFromCharacter(S) < 50 then
											AutoAllSkill()
										end
										if m:FindFirstChild("Meshes/plant1_Icosphere", true) then
											toTarget(m.WorldPivot)
											getgenv().AimPos = m.WorldPivot
											G.Hit = CFrame.new(R.CFrame.Position, S)
											G.Target = m
										else
											local S, I =
												(m.WorldPivot * CFrame.new(5, -20, 0)).Position,
												(m.WorldPivot * CFrame.new(0, -20, 0)).Position
											toTarget(CFrame.new(S))
											getgenv().AimPos = CFrame.new(I)
											G.Hit = CFrame.new(R.CFrame.Position, I)
											G.Target = m
										end
									until not m
										or not m.Parent
										or not Settings["Fully Trial Draco"]
										or g
										or (m:GetAttribute("AlreadyDestroyedClient"))
										or tick() - l >= 15
								end
							end
						end
						return
					end
					if CheckCountItem("Scrap Metal", 10) and (CheckCountItem("Blaze Ember", 15)) then
						game:GetService("ReplicatedStorage").Modules.Net
							:FindFirstChild("RF/Craft")
							:InvokeServer(unpack({ [1] = "Craft", [2] = "Volcanic Magnet", [3] = 1, [4] = {} }))
						wait(2)
					end
				else
					getgenv().dacoMagnet = true
					if
						not game:GetService("Workspace").Map:FindFirstChild("PrehistoricIsland")
						and not game:GetService("Players").LocalPlayer.PlayerGui.Main.TopHUDList.PrehistoricRaidTimer.Visible
						and not game:GetService("Players").LocalPlayer.PlayerGui.Main.TopHUDList.RaidTimer.Visible
					then
						local g = checkboat()
						if not g or g and t:DistanceFromCharacter(g.VehicleSeat.Position) >= 4000 then
							local R = CFrame.new(-16204.0810546875, 9.0863618850708, 479.2259521484375)
							if (R.Position - t.Character.HumanoidRootPart.Position).Magnitude > 8 then
								if (R.Position - t.Character.HumanoidRootPart.Position).Magnitude > 1000 then
									if
										not t:GetAttribute("CurrentLocation")
										or t:GetAttribute("CurrentLocation") ~= "Tiki Outpost"
									then
										if
											game:GetService("Players").LocalPlayer.Data.LastSpawnPoint.Value
												== "Tiki"
											or game:GetService("Players").LocalPlayer.Data.LastSpawnPoint.Value
												== "Tiki2"
										then
											t.Character.Humanoid.Health = 0
											return
										end
									end
								end
								toTarget(R)
							else
								game:GetService("ReplicatedStorage").Remotes.CommF_
									:InvokeServer("BuyBoat", "PirateBrigade")
								wait(3)
							end
						elseif t.Character.Humanoid.Sit then
							task.spawn(function()
								NoclipBoat(g)
							end)
							local R = CFrame.new(-118834.515625, g.WorldPivot.Y, -78.9505844116211)
								* CFrame.new(0, 0, 99999999)
							manageTween(g.VehicleSeat, R, 350, "TweenBoat")
						else
							if getgenv().TweenBoat then
								getgenv().TweenBoat:Pause()
								getgenv().TweenBoat:Cancel()
							end
							toTarget(g.VehicleSeat.CFrame)
						end
					end
				end
			else
				if getgenv().turnoffnoclipBoatt then
					getgenv().turnoffnoclipBoatt = false
					local g = checkboat()
					if g then
						TurnOffNoclipBoat(g)
					end
				end
				if getgenv().RespawnVolcano and Settings["Webhook Find Prehistoric Island"] then
					getgenv().RespawnVolcano = false
					WebhookFindVolcano()
				end
				if getgenv().TweenBoat then
					getgenv().TweenBoat:Pause()
					getgenv().TweenBoat:Cancel()
				end
				if
					not t:GetAttribute("CurrentLocation")
					or t:GetAttribute("CurrentLocation") ~= "Prehistoric Island"
				then
					local g = DetectNpc("Fossil Expert")
					if g then
						toTarget(g.HumanoidRootPart.CFrame)
						return
					end
				end
				if workspace.Map.PrehistoricIsland:FindFirstChild("TrialRock", true).Transparency == 1 then
					getgenv().WaitingjoinTrial = true
					toTarget(workspace.Map.PrehistoricIsland.TrialTeleport.CFrame)
					return
				end
				if DetectLava() then
					local g, R, m = next, workspace.Map.PrehistoricIsland:GetDescendants()
					for l, l in g, R, m do
						if l.Name == "TouchInterest" and l.Parent.Name ~= "TrialTeleport" then
							l:Destroy()
						end
					end
				end
				if #workspace.Map.PrehistoricIsland.Core.InteriorLava:GetChildren() > 0 then
					DeleteLava()
				end
				if
					not game:GetService("Players").LocalPlayer.PlayerGui.Main.TopHUDList.PrehistoricRaidTimer.Visible
					and not game:GetService("Players").LocalPlayer.PlayerGui.Main.TopHUDList.RaidTimer.Visible
				then
					if
						workspace.Map.PrehistoricIsland.Core:FindFirstChild("ActivationPrompt")
						and (workspace.Map.PrehistoricIsland.Core.ActivationPrompt:FindFirstChild("ProximityPrompt"))
					then
						toTarget(workspace.Map.PrehistoricIsland.Core.ActivationPrompt.CFrame)
						if
							t:DistanceFromCharacter(workspace.Map.PrehistoricIsland.Core.ActivationPrompt.Position) < 8
						then
							fireproximityprompt(
								workspace.Map.PrehistoricIsland.Core.ActivationPrompt.ProximityPrompt,
								1
							)
							wait(3)
						end
						return
					elseif
						not workspace.Map.PrehistoricIsland.Core:FindFirstChild("ActivationPrompt")
						and not workspace.Map.PrehistoricIsland.Core:FindFirstChild("FossilExpertSpawn")
					then
						local g = DetectNpc("Fossil Expert")
						if g then
							toTarget(g.HumanoidRootPart.CFrame)
							return
						end
					end
				else
					if b then
						local g = workspace.Map.PrehistoricIsland.Core.PrehistoricRelic.Skull
						repeat
							task.wait()
							toTarget(g.Position, g.CFrame)
						until t:DistanceFromCharacter(g.Position) <= 200 or (DetectGolem()) or (DetectRockVolcano())
						b = false
						return
					end
					local g = DetectGolem()
					if g then
						repeat
							task.wait()
							toTarget(g.HumanoidRootPart.CFrame * CFrame.new(0, 20, 7))
							if
								Settings["Select Method Kill Golem"] == "Instant Kill [ Risk and can bug no die mob ]"
							then
								if t:DistanceFromCharacter(g.HumanoidRootPart.Position) < 50 then
									KillRaidEnemy()
								end
							else
								equiptool(NameWeapon(Settings["Select Weapon Kill Golem"] or "Melee"))
								getgenv().ClickM1Volcano(g)
							end
							if not getgenv().KillMobRaid and Settings["Kill Aura Only Raid And Volcano"] then
								getgenv().KillMobRaid = true
								local R = Settings["Time Delay Kill"] or 5
								g.Humanoid:ChangeState(Enum.HumanoidStateType.Dead)
								delay(R, function()
									getgenv().KillMobRaid = false
								end)
							end
						until not IsMobAlive(g)
							or not Settings["Fully Trial Draco"]
							or not game:GetService("Workspace").Map:FindFirstChild("PrehistoricIsland")
							or not game:GetService("Players").LocalPlayer.PlayerGui.Main.TopHUDList.PrehistoricRaidTimer.Visible
								and not game:GetService("Players").LocalPlayer.PlayerGui.Main.TopHUDList.RaidTimer.Visible
					end
					g = DetectRockVolcano()
					if g then
						if Settings["Fix Volcano Safe"] then
							local R = DetectPositionVolcano()
							local m, m = CheckPosnearRock(R, t.Character.HumanoidRootPart)
							if t:DistanceFromCharacter((CheckPosnearRock(R, g.WorldPivot))) >= 400 then
								s = m + 1
								if m >= 7 then
									s = 1
								end
								local m = R[s]
								toTarget(CFrame.new(m))
							else
								local R = X[math.floor(g.WorldPivot.Position.Y)]
								repeat
									task.wait()
									if t:DistanceFromCharacter((g.WorldPivot * R).Position) > 8 then
										toTarget(g.WorldPivot * R)
									end
									if t:DistanceFromCharacter(g.WorldPivot.Position) < 100 then
										AutoUseSkillFixLava()
									end
									getgenv().AimPos = g.WorldPivot
									local m = workspace.CurrentCamera
									G.Hit = g.WorldPivot
									G.Target = g
								until not g
									or not g.Parent
									or not Settings["Fully Trial Draco"]
									or not g.VFXLayer.Specs.Enabled
									or (DetectGolem())
									or not game:GetService("Workspace").Map:FindFirstChild("PrehistoricIsland")
									or not game:GetService("Players").LocalPlayer.PlayerGui.Main.TopHUDList.PrehistoricRaidTimer.Visible
										and not game:GetService("Players").LocalPlayer.PlayerGui.Main.TopHUDList.RaidTimer.Visible
								R = DetectGolem()
								if not R then
									b = true
								end
								wait(1)
							end
						else
							local R = X[math.floor(g.WorldPivot.Position.Y)]
							repeat
								task.wait()
								if t:DistanceFromCharacter((g.WorldPivot * R).Position) > 8 then
									toTarget(g.WorldPivot * R)
								end
								if t:DistanceFromCharacter(g.WorldPivot.Position) < 100 then
									AutoUseSkillFixLava()
								end
								getgenv().AimPos = g.WorldPivot
								local m = workspace.CurrentCamera
								G.Hit = g.WorldPivot
								G.Target = g
							until not g
								or not g.Parent
								or not Settings["Fully Trial Draco"]
								or not g.VFXLayer.Specs.Enabled
								or (DetectGolem())
								or not game:GetService("Workspace").Map:FindFirstChild("PrehistoricIsland")
								or not game:GetService("Players").LocalPlayer.PlayerGui.Main.TopHUDList.PrehistoricRaidTimer.Visible
									and not game:GetService("Players").LocalPlayer.PlayerGui.Main.TopHUDList.RaidTimer.Visible
							R = DetectGolem()
							if not R then
								b = true
							end
						end
					end
				end
			end
		end
	elseif string.find(CheckAcientOneDracoStatus(), "Can Buy Gear") then
		BuyGearDracoV4()
	else
		local g = DetectMob(e)
		if g then
			repeat
				task.wait()
				sizepart(g)
				BringMob(g)
				UsedualFlock()
				ClickM1(g)
				if Settings["Select Weapon"] == "Blox Fruit" then
					toTarget(g.HumanoidRootPart.CFrame * CFrame.new(-7, 20, 0))
				else
					toTarget(g.HumanoidRootPart.CFrame * CFrame.new(7, 20, 0))
				end
			until not IsMobAlive(g) or not Settings["Fully Trial Draco"]
		elseif typeof(e) == "table" then
			if #N >= #e then
				N = {}
				return
			end
			local g = DetectPartSpawnMob(DetectNameTablePart(e))
			if g then
				table.insert(N, DetectNameTablePart(e))
				repeat
					wait()
					toTarget(g.CFrame * CFrame.new(0, 60, 0))
				until (g.Position - t.Character.HumanoidRootPart.Position).Magnitude <= 100
					or (DetectMob(e))
					or not Settings["Fully Trial Draco"]
				wait(1)
			end
		else
			local g = DetectPartSpawnMob(e, true)
			if g then
				Instance.new("IntValue", g).Name = "Ignored"
				repeat
					wait()
					toTarget(g.CFrame * CFrame.new(0, 60, 0))
				until (g.Position - t.Character.HumanoidRootPart.Position).Magnitude <= 100
					or (DetectMob(e))
					or not Settings["Fully Trial Draco"]
				wait(1)
			else
				DeleteIgnoredMobSpawn()
			end
		end
	end
end
RaceDracoSection.CreateToggle(
	{
		Title = "Fully Trial Draco",
		Desc = "Auto Craft and Auto Find and Auto Attack and Fix\10 Auto Trial and auto Train Race and Buy Gear and Choose Gear",
		Default = Settings["Fully Trial Draco"] or false,
	},
	function(g)
		if g then
			spawn(function()
				while Settings["Fully Trial Draco"] and (task.wait(0.1)) do
					local R, R = pcall(function()
						FullyDraco()
					end)
					if R then
						print(R)
					end
				end
			end)
		end
		SaveSettings("Fully Trial Draco", g)
	end
)
RaceDracoSection.CreateToggle(
	{
		Title = "Ignore Craft Volcanic Magnet [ Fully Draco ]",
		Desc = nil,
		Default = Settings["Ignore Craft Volcanic Magnet Draco"] or false,
	},
	function(g)
		SaveSettings("Ignore Craft Volcanic Magnet Draco", g)
	end
)
RaceDracoSection.CreateToggle(
	{ Title = "Auto Buy Gear Draco", Desc = nil, Default = Settings["Auto Buy Gear Draco"] or false },
	function(g)
		if g then
			spawn(function()
				while Settings["Auto Buy Gear Draco"] and (wait(0.3)) do
					pcall(function()
						BuyGearDracoV4()
					end)
				end
			end)
		end
		SaveSettings("Auto Buy Gear Draco", g)
	end
)
RaceDracoSection.CreateToggle(
	{ Title = "Auto Finish Train Draco Quest", Desc = nil, Default = Settings["Auto Finish Train Draco Quest"] or false },
	function(g)
		if g then
			spawn(function()
				while Settings["Auto Finish Train Draco Quest"] and (wait(0.1)) do
					pcall(function()
						if string.find(CheckAcientOneDracoStatus(), "Can Buy Gear") then
							BuyGearDracoV4()
						else
							local R = DetectMob(e)
							if R then
								repeat
									task.wait()
									sizepart(R)
									BringMob(R)
									UsedualFlock()
									ClickM1(R)
									if Settings["Select Weapon"] == "Blox Fruit" then
										toTarget(R.HumanoidRootPart.CFrame * CFrame.new(-7, 20, 0))
									else
										toTarget(R.HumanoidRootPart.CFrame * CFrame.new(7, 20, 0))
									end
								until not IsMobAlive(R) or not Settings["Auto Finish Train Draco Quest"]
							elseif typeof(e) == "table" then
								if #N >= #e then
									N = {}
									return
								end
								local R = DetectPartSpawnMob(DetectNameTablePart(e))
								if R then
									table.insert(N, DetectNameTablePart(e))
									repeat
										wait()
										toTarget(R.CFrame * CFrame.new(0, 60, 0))
									until (R.Position - t.Character.HumanoidRootPart.Position).Magnitude <= 100
										or (DetectMob(e))
										or not Settings["Auto Finish Train Draco Quest"]
									wait(1)
								end
							else
								local R = DetectPartSpawnMob(e, true)
								if R then
									Instance.new("IntValue", R).Name = "Ignored"
									repeat
										wait()
										toTarget(R.CFrame * CFrame.new(0, 60, 0))
									until (R.Position - t.Character.HumanoidRootPart.Position).Magnitude <= 100
										or (DetectMob(e))
										or not Settings["Auto Finish Train Draco Quest"]
									wait(1)
								else
									DeleteIgnoredMobSpawn()
								end
							end
						end
					end)
				end
			end)
		end
		SaveSettings("Auto Finish Train Draco Quest", g)
	end
)
RaceNormalSection = RaceMain.CreateSection("Race Normal")
function AutoMinkV2()
	local g = GetNearestChest()
	if g then
		local R
		repeat
			task.wait()
			if (game.Players.LocalPlayer.Character.HumanoidRootPart.Position - g.Position).Magnitude <= 5 then
				if not R then
					R = (tick())
				elseif tick() - R >= 5 then
					Instance.new("IntValue", g).Name = "Ignored"
					wait(0.5)
				end
				game:GetService("VirtualInputManager"):SendKeyEvent(true, "Space", false, game)
				wait()
				game:GetService("VirtualInputManager"):SendKeyEvent(false, "Space", false, game)
				TweenManager.CancelCurrent()
			end
			toTarget(g.CFrame, true)
		until not g
			or not g.Parent
			or not Settings["Auto Upgrade Race V2-V3"]
			or (g:GetAttribute("IsDisabled"))
			or (g:FindFirstChild("Ignored"))
			or not g:FindFirstChild("TouchInterest")
	else
		local g = PathFindChest()
		if g then
			toTarget(g.Part.CFrame)
			if (g.Part.Position - t.Character.HumanoidRootPart.Position).Magnitude <= 100 or (GetNearestChest()) then
				Instance.new("IntValue", g).Name = "Ignored"
			end
		else
			for g, g in pairs(game:GetService("Workspace")._WorldOrigin.PlayerSpawns.Pirates:GetChildren()) do
				if g:FindFirstChild("Ignored") then
					g:FindFirstChild("Ignored"):Destroy()
				end
			end
		end
	end
end
function DetectSeabeast()
	local g, R, m = next, game:GetService("Workspace").SeaBeasts:GetChildren()
	for l, l in g, R, m do
		if l.Name == "SeaBeast1" then
			local g, R = l.HealthBBG.Frame.TextLabel.Text:gsub("/%d+,%d+", ""), l.HealthBBG.Frame.TextLabel.Text
			if
				tonumber(
					((if string.find(g, ",") then (R:gsub("%d+,%d+/", "")) else (R:gsub("%d+/", ""))):gsub(",", ""))
				) >= 90000
			then
				return l
			end
		end
	end
	return false
end
function AutoFishV2()
	local g, R = DetectSeabeast(), checkboat()
	if not g then
		if not R then
			local m = CFrame.new(-11.94833755493164, 10.293913841247559, 2957.010498046875)
			if (m.Position - t.Character.HumanoidRootPart.Position).Magnitude > 8 then
				toTarget(m)
			else
				game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("BuyBoat", "PirateBrigade")
			end
		else
			local m = CFrame.new(753.0653686523438, R.WorldPivot.Y, 6994.5146484375)
			if (R.VehicleSeat.Position - m.Position).Magnitude > 50 then
				R.VehicleSeat.CFrame = m
			elseif not t.Character.Humanoid.Sit then
				toTarget(R.VehicleSeat.CFrame)
			end
		end
	else
		repeat
			task.wait()
			TeleportSeaEvents(g)
			local R = g:FindFirstChild("HumanoidRootPart")
			getgenv().AimPos = CFrame.new(R.Position.X, 40, R.Position.Z)
			if t:DistanceFromCharacter(R.Position) < 400 then
				AutoAllSkill()
			end
		until not g or not g.Parent or g.Health.Value <= 0 or not Settings["Auto Upgrade Race V2-V3"]
	end
end
function CheckRace()
	local g, R =
		game.ReplicatedStorage.Remotes.CommF_:InvokeServer("Wenlocktoad", "1"),
		game.ReplicatedStorage.Remotes.CommF_:InvokeServer("Alchemist", "1")
	if game.Players.LocalPlayer.Character:FindFirstChild("RaceTransformed") then
		return " V4"
	end
	if g == -2 then
		return " V3"
	end
	if R == -2 then
		return " V2"
	end
	return " V1"
end
getgenv().Chests = {}
getgenv().BlBossHuman = {}
local g, R = {}, {}
function DetectPlayerAngel()
	for m, m in pairs(game:GetService("Players"):GetChildren()) do
		if
			m.Name ~= t.Name
			and (game:GetService("Workspace").Characters:FindFirstChild(m.Name))
			and m.Data.Race.Value == "Skypiea"
			and not table.find(g, m.Name)
			and (m.Character:FindFirstChild("Humanoid"))
			and m.Character.Humanoid.Health > 0
		then
			return m
		end
	end
end
function DetectPlayerGhoul()
	for m, m in pairs(game:GetService("Players"):GetChildren()) do
		if
			m.Name ~= t.Name
			and (game:GetService("Workspace").Characters:FindFirstChild(m.Name))
			and not table.find(R, m.Name)
			and (m.Character:FindFirstChild("Humanoid"))
			and m.Character.Humanoid.Health > 0
		then
			return m
		end
	end
end
function CheckSafezone(m)
	for l, l in pairs(game:GetService("Workspace")._WorldOrigin.SafeZones:GetChildren()) do
		if l:IsA("Part") then
			if
				(l.Position - m.HumanoidRootPart.Position).magnitude <= 400
				and m.Humanoid.Health / m.Humanoid.MaxHealth >= 0.9
			then
				return true
			end
		end
	end
	return false
end
function CheckPlayercantAttack(m)
	for l, S in pairs(game.Players.LocalPlayer.PlayerGui.Notifications:GetDescendants()) do
		if S:IsA("TextLabel") then
			if string.find(S.Text, "attack") and not S:FindFirstChild(m.Name) then
				l = Instance.new("TextBox")
				l.Parent = S.Parent
				l.Name = m.Name
				S:Destroy()
				return true
			end
		end
	end
end
function UpgradeRaceV2AndV3()
	local m = CheckRace()
	if m == " V3" then
		A.CreateNoti({ Title = "Banana Cat Hub", Desc = "Done V3", ShowTime = 5 })
		wait(5)
		return
	end
	if game.PlaceId ~= getgenv().CheckPlaceId2 then
		game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer(unpack({ [1] = "TravelDressrosa" }))
		return
	end
	if m == " V1" then
		if t.Data.Beli.Value < 500000 then
			A.CreateNoti({ Title = "Banana Cat Hub", Desc = "Beli >= 500k", ShowTime = 5 })
			wait(5)
			return
		end
		if game.ReplicatedStorage.Remotes.CommF_:InvokeServer("Alchemist", "1") == 0 then
			game.ReplicatedStorage.Remotes.CommF_:InvokeServer("Alchemist", "2")
		elseif game.ReplicatedStorage.Remotes.CommF_:InvokeServer("Alchemist", "1") == 1 then
			if not DetectItemPlr("Flower 1") then
				toTarget(game:GetService("Workspace").Flower1.CFrame)
			elseif not DetectItemPlr("Flower 2") then
				toTarget(game:GetService("Workspace").Flower2.CFrame)
			elseif not DetectItemPlr("Flower 3") then
				local l = DetectMob("Swan Pirate")
				if not l then
					local S = "Swan Pirate"
					if typeof(S) == "table" then
						if #N >= 11 then
							N = {}
							return
						end
						local I = DetectPartSpawnMob(DetectNameTablePart(S))
						if I then
							table.insert(N, DetectNameTablePart(S))
							repeat
								wait()
								toTarget(I.CFrame * CFrame.new(0, 60, 0))
							until (I.Position - t.Character.HumanoidRootPart.Position).Magnitude <= 100
								or (DetectMob(S))
								or not Settings["Auto Upgrade Race V2-V3"]
							wait(1)
						end
					else
						local I = DetectPartSpawnMob(S, true)
						if I then
							Instance.new("IntValue", I).Name = "Ignored"
							repeat
								wait()
								toTarget(I.CFrame * CFrame.new(0, 60, 0))
							until (I.Position - t.Character.HumanoidRootPart.Position).Magnitude <= 100
								or (DetectMob(S))
								or not Settings["Auto Upgrade Race V2-V3"]
							wait(1)
						else
							DeleteIgnoredMobSpawn()
						end
					end
				else
					repeat
						task.wait()
						sizepart(l)
						BringMob(l)
						UsedualFlock()
						ClickM1(l)
						if Settings["Select Weapon"] == "Blox Fruit" then
							toTarget(l.HumanoidRootPart.CFrame * CFrame.new(-7, 20, 0))
						else
							toTarget(l.HumanoidRootPart.CFrame * CFrame.new(7, 20, 0))
						end
					until not IsMobAlive(l) or not Settings["Auto Upgrade Race V2-V3"]
				end
			end
		elseif game.ReplicatedStorage.Remotes.CommF_:InvokeServer("Alchemist", "1") == 2 then
			if
				(CFrame.new(-2777.6001, 72.9661407, -3571.42285).Position - t.Character.HumanoidRootPart.Position).Magnitude
				< 8
			then
				toTarget(CFrame.new(-2777.6001, 72.9661407, -3571.42285))
			else
				game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("Alchemist", "3")
			end
		else
			AutoQuestBarito()
		end
	else
		local l = game.ReplicatedStorage.Remotes.CommF_:InvokeServer("Wenlocktoad", "1")
		if l == 0 then
			game.ReplicatedStorage.Remotes.CommF_:InvokeServer("Wenlocktoad", "2")
			return
		elseif l == 2 then
			game.ReplicatedStorage.Remotes.CommF_:InvokeServer("Wenlocktoad", "3")
			return
		elseif l == -1 then
			A.CreateNoti({ Title = "Banana Cat Hub", Desc = "Beli >= 2m", ShowTime = 5 })
			wait(5)
			return
		end
		l = game:GetService("Players").LocalPlayer.Data.Race.Value .. m
		if l == "Human V2" then
			local m = not table.find(BlBossHuman, "Jeremy") and (CheckNameBoss("Jeremy"))
				or not table.find(BlBossHuman, "Orbitus") and (CheckNameBoss("Orbitus"))
				or not table.find(BlBossHuman, "Diamond") and (CheckNameBoss("Diamond"))
			if m then
				local S = CheckNameBoss(m.Name)
				if S then
					repeat
						task.wait()
						sizepart(S)
						UsedualFlock()
						ClickM1(S)
						if Settings["Select Weapon"] == "Blox Fruit" then
							toTarget(S.HumanoidRootPart.CFrame * CFrame.new(-7, 20, 0))
						else
							toTarget(S.HumanoidRootPart.CFrame * CFrame.new(7, 20, 0))
						end
					until not IsMobAlive(S)
					if not table.find(BlBossHuman, m.Name) then
						table.insert(BlBossHuman, m.Name)
					end
				end
			else
				A.CreateNoti({ Title = "Banana Cat Hub", Desc = "Waiting Boss Spawn", ShowTime = 5 })
				wait(5)
			end
		elseif l == "Mink V2" then
			AutoMinkV2()
		elseif l == "Cyborg V2" then
			if not CheckFruitplr() then
				if TakeFruitInventory(true) then
					game:GetService("ReplicatedStorage").Remotes.CommF_
						:InvokeServer("LoadFruit", TakeFruitInventory(true))
				end
			end
		elseif l == "Fishman V2" then
			AutoFishV2()
		elseif l == "Skypiea V2" then
			local m = DetectPlayerAngel()
			if m then
				table.insert(g, m.Name)
				local g = tick()
				repeat
					wait()
					spawn(function()
						if game:GetService("Players").LocalPlayer.PlayerGui.Main.BottomHUDList.PvpDisabled.Visible then
							game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("EnablePvp")
						end
					end)
					spawn(function()
						getgenv().AimPos = CFrame.new(
							m.Character.HumanoidRootPart.CFrame.p,
							m.Character.HumanoidRootPart.Position + m.Character.HumanoidRootPart.Velocity / 1.2
						)
						if t:DistanceFromCharacter(m.Character.HumanoidRootPart.Position) < 50 then
							t.Character.HumanoidRootPart.CFrame = m.Character.HumanoidRootPart.CFrame
								* CFrame.new(0, 0, 3)
						else
							toTarget(m.Character.HumanoidRootPart.CFrame * CFrame.new(0, 0, 3))
						end
					end)
					spawn(function()
						if t:DistanceFromCharacter(m.Character.HumanoidRootPart.Position) < 50 then
							AutoAllSkill(true)
						end
					end)
				until tick() - g >= 70
					or not m.Character
					or not m.Character.Parent
					or m.Character.Humanoid.Health == 0
					or (CheckSafezone(m.Character))
					or (CheckPlayercantAttack(m.Character))
					or not Settings["Auto Upgrade Race V2-V3"]
			else
				HopServer()
				wait(5)
			end
		elseif l == "Ghoul V2" then
			local g = DetectPlayerGhoul()
			if g then
				table.insert(R, g.Name)
				local R = tick()
				repeat
					wait()
					spawn(function()
						if game:GetService("Players").LocalPlayer.PlayerGui.Main.BottomHUDList.PvpDisabled.Visible then
							game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("EnablePvp")
						end
					end)
					spawn(function()
						getgenv().AimPos = CFrame.new(
							g.Character.HumanoidRootPart.CFrame.p,
							g.Character.HumanoidRootPart.Position + g.Character.HumanoidRootPart.Velocity / 1.2
						)
						if t:DistanceFromCharacter(g.Character.HumanoidRootPart.Position) < 50 then
							t.Character.HumanoidRootPart.CFrame = g.Character.HumanoidRootPart.CFrame
								* CFrame.new(0, 0, 3)
						else
							toTarget(g.Character.HumanoidRootPart.CFrame * CFrame.new(0, 0, 3))
						end
					end)
					spawn(function()
						if t:DistanceFromCharacter(g.Character.HumanoidRootPart.Position) < 50 then
							AutoAllSkill(true)
						end
					end)
				until tick() - R >= 70
					or not g.Character
					or not g.Character.Parent
					or g.Character.Humanoid.Health == 0
					or (CheckSafezone(g.Character))
					or (CheckPlayercantAttack(g.Character))
					or not Settings["Auto Upgrade Race V2-V3"]
			else
				HopServer()
				wait(5)
			end
		end
	end
end
RaceNormalSection.CreateToggle(
	{ Title = "Auto Upgrade Race V2-V3", Desc = nil, Default = Settings["Auto Upgrade Race V2-V3"] or false },
	function(g)
		if g then
			spawn(function()
				while Settings["Auto Upgrade Race V2-V3"] and (wait(0.1)) do
					local R, R = pcall(function()
						UpgradeRaceV2AndV3()
					end)
					if R then
						print(R)
					end
				end
			end)
		end
		SaveSettings("Auto Upgrade Race V2-V3", g)
	end
)
function BuyChipLaw()
	v354 = game.ReplicatedStorage.Remotes.CommF_:InvokeServer("BlackbeardReward", "Microchip", "2")
	if v354 == 1 then
		return true
	end
	if v354 == 0 then
		return false
	end
	if v354 == 2 then
		return true
	end
end
local g, R, m = 0, false, false
function DetectkeyCyborg(l)
	local S, I, _ = next, game:GetService("Players").LocalPlayer.PlayerGui.Notifications:GetChildren()
	for V, V in S, I, _ do
		if V.Name == "NotificationTemplate" and V.TranslateMe.Text == l then
			return true
		end
	end
end
ToggleAutoGetFullyCyborg = RaceNormalSection.CreateToggle(
	{ Title = "Auto Get Fully Cyborg", Desc = nil, Default = Settings["Auto Get Fully Cyborg"] or false },
	function(l)
		SaveSettings("Auto Get Fully Cyborg", l)
		if l and not Settings["Auto Get Cyborg"] then
			A.CreateNoti({ Title = "Banana Cat Hub", Desc = "Turn On Auto Get Cyborg plz", ShowTime = 5 })
		end
	end
)
RaceNormalSection.CreateToggle(
	{
		Title = "Auto Get Cyborg Hop Collect Chest",
		Desc = nil,
		Default = Settings["Auto Get Cyborg Hop Collect Chest"] or false,
	},
	function(l)
		SaveSettings("Auto Get Cyborg Hop Collect Chest", l)
	end
)
function GetCyborg()
	if game.ReplicatedStorage.Remotes.CommF_:InvokeServer("CyborgTrainer", "Check") == 2 then
		A.CreateNoti({ Title = "Banana Cat Hub", Desc = "Plz Turn Off", ShowTime = 5 })
		wait(5)
		return
	end
	if game.PlaceId ~= getgenv().CheckPlaceId2 then
		game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer(unpack({ [1] = "TravelDressrosa" }))
		return
	end
	if game.ReplicatedStorage.Remotes.CommF_:InvokeServer("CyborgTrainer", "Check") then
		game.ReplicatedStorage.Remotes.CommF_:InvokeServer("CyborgTrainer", "Buy")
		return
	end
	if not m and not DetectItemPlr("Core Brain") then
		repeat
			wait(1)
			fireclickdetector(game:GetService("Workspace").Map.CircleIsland.RaidSummon.Button.Main.ClickDetector)
		until DetectkeyCyborg("{color1_Green}Please supply a {item1} to continue.{color1_/}")
			or (DetectkeyCyborg("{color1_Red}Microchip not found.{color1_/}"))
		local l = DetectkeyCyborg
		if l("{color1_Red}Microchip not found.{color1_/}") then
			R = false
		else
			local l = DetectkeyCyborg
			if l("{color1_Green}Please supply a {item1} to continue.{color1_/}") then
				R = true
			end
		end
		m = true
	end
	if Settings["Auto Get Fully Cyborg"] and not CheckNameBoss("Order") and not R then
		if not DetectItemPlr("Fist of Darkness") then
			if g >= 20 and Settings["Auto Get Cyborg Hop Collect Chest"] then
				if not getgenv().DelayHop then
					task.delay(5, function()
						getgenv().DelayHop = true
						spawn(function()
							HopLessAll()
						end)
						spawn(function()
							HopServer()
						end)
						getgenv().DelayHop = false
					end)
				end
				return
			end
			local m = GetNearestChest()
			if m then
				g += 1
				local g
				repeat
					task.wait()
					if (game.Players.LocalPlayer.Character.HumanoidRootPart.Position - m.Position).Magnitude <= 5 then
						if not g then
							g = (tick())
						elseif tick() - g >= 5 then
							Instance.new("IntValue", m).Name = "Ignored"
							wait(0.5)
						end
						game:GetService("VirtualInputManager"):SendKeyEvent(true, "Space", false, game)
						wait()
						game:GetService("VirtualInputManager"):SendKeyEvent(false, "Space", false, game)
						TweenManager.CancelCurrent()
					end
					toTarget(m.CFrame, true)
				until not m
					or not m.Parent
					or not Settings["Auto Get Cyborg"]
					or (m:GetAttribute("IsDisabled"))
					or (m:FindFirstChild("Ignored"))
					or not m:FindFirstChild("TouchInterest")
			else
				local g = PathFindChest()
				if g then
					toTarget(g.Part.CFrame)
					if
						(g.Part.Position - t.Character.HumanoidRootPart.Position).Magnitude <= 100
						or (GetNearestChest())
					then
						Instance.new("IntValue", g).Name = "Ignored"
					end
				else
					print("delete")
					for g, g in pairs(game:GetService("Workspace")._WorldOrigin.PlayerSpawns.Pirates:GetChildren()) do
						if g:FindFirstChild("Ignored") then
							g:FindFirstChild("Ignored"):Destroy()
						end
					end
				end
			end
		else
			wait(1)
			repeat
				wait()
				fireclickdetector(game:GetService("Workspace").Map.CircleIsland.RaidSummon.Button.Main.ClickDetector)
			until not DetectItemPlr("Fist of Darkness")
			wait(0.5)
			ToggleAutoGetFullyCyborg:SetStage(false)
			R = true
		end
		return
	end
	if R then
		if DetectItemPlr("Core Brain") then
			fireclickdetector(game:GetService("Workspace").Map.CircleIsland.RaidSummon.Button.Main.ClickDetector)
			return
		end
		local g = CheckNameBoss("Order")
		if g then
			repeat
				task.wait()
				sizepart(g)
				UsedualFlock()
				ClickM1(g)
				if Settings["Select Weapon"] == "Blox Fruit" then
					toTarget(g.HumanoidRootPart.CFrame * CFrame.new(-7, 20, 0))
				else
					toTarget(g.HumanoidRootPart.CFrame * CFrame.new(7, 20, 0))
				end
			until not IsMobAlive(g) or not Settings["Auto Get Cyborg"]
		elseif not DetectItemPlr("Microchip") and game.Players.LocalPlayer.Data.Fragments.Value >= 1000 then
			BuyChipLaw()
			wait(2)
		elseif DetectItemPlr("Microchip") then
			fireclickdetector(game:GetService("Workspace").Map.CircleIsland.RaidSummon.Button.Main.ClickDetector)
		end
	end
end
RaceNormalSection.CreateToggle(
	{ Title = "Auto Get Cyborg", Desc = nil, Default = Settings["Auto Get Cyborg"] or false },
	function(g)
		if g then
			spawn(function()
				while Settings["Auto Get Cyborg"] and (wait(0.1)) do
					local R, R = pcall(function()
						GetCyborg()
					end)
					if R then
						print(R)
					end
				end
			end)
		end
		SaveSettings("Auto Get Cyborg", g)
	end
)
function GetRaceGhoul()
	if game.PlaceId ~= getgenv().CheckPlaceId2 then
		game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer(unpack({ [1] = "TravelDressrosa" }))
		return
	end
	if
		game:GetService("Players").LocalPlayer.Data.Race.Value == "Ghoul"
		or game.ReplicatedStorage.Remotes.CommF_:InvokeServer("Ectoplasm", "BuyCheck", 4, true) == 2
		or game.ReplicatedStorage.Remotes.CommF_:InvokeServer("Ectoplasm", "Change", 4, true) == 1
	then
		A.CreateNoti({ Title = "Banana Cat Hub", Desc = "Plz Turn Off", ShowTime = 5 })
		wait(5)
		return
	end
	if not CheckCountItem("Ectoplasm", 100) then
		local g = { "Ship Deckhand", "Ship Steward", "Ship Officer", "Ship Engineer" }
		local R = DetectMob(g)
		if R then
			repeat
				task.wait()
				sizepart(R)
				BringMob(R)
				UsedualFlock()
				ClickM1(R)
				if Settings["Select Weapon"] == "Blox Fruit" then
					toTarget(R.HumanoidRootPart.CFrame * CFrame.new(-7, 20, 0))
				else
					toTarget(R.HumanoidRootPart.CFrame * CFrame.new(7, 20, 0))
				end
			until not IsMobAlive(R) or not Settings["Auto Get Ghoul"]
		elseif typeof(g) == "table" then
			if #N >= #g then
				N = {}
				return
			end
			local R = DetectPartSpawnMob(DetectNameTablePart(g))
			if R then
				table.insert(N, DetectNameTablePart(g))
				repeat
					wait()
					toTarget(R.CFrame * CFrame.new(0, 60, 0))
				until (R.Position - t.Character.HumanoidRootPart.Position).Magnitude <= 100
					or (DetectMob(g))
					or not Settings["Auto Get Ghoul"]
				wait(1)
			end
		else
			local R = DetectPartSpawnMob(g, true)
			if R then
				Instance.new("IntValue", R).Name = "Ignored"
				repeat
					wait()
					toTarget(R.CFrame * CFrame.new(0, 60, 0))
				until (R.Position - t.Character.HumanoidRootPart.Position).Magnitude <= 100
					or (DetectMob(g))
					or not Settings["Auto Get Ghoul"]
				wait(1)
			else
				DeleteIgnoredMobSpawn()
			end
		end
		return
	end
	if DetectItemPlr("Hellfire Torch") then
		if
			(CFrame.new(
				918.615234,
				122.202454,
				33454.3789,
				-0.999998808,
				0,
				0.00172644004,
				0,
				1,
				0,
				-0.00172644004,
				0,
				-0.999998808
			).Position - t.Character.HumanoidRootPart.Position).Magnitude <= 8
		then
			game:GetService("ReplicatedStorage").Remotes.CommF_
				:InvokeServer(unpack({ [1] = "Ectoplasm", [2] = "BuyCheck", [3] = 4 }))
			v352 = game.ReplicatedStorage.Remotes.CommF_:InvokeServer("Ectoplasm", "Buy", 4)
		else
			toTarget(
				CFrame.new(
					918.615234,
					122.202454,
					33454.3789,
					-0.999998808,
					0,
					0.00172644004,
					0,
					1,
					0,
					-0.00172644004,
					0,
					-0.999998808
				)
			)
		end
	else
		local g = CheckNameBoss("Cursed Captain")
		if g then
			repeat
				task.wait()
				sizepart(g)
				UsedualFlock()
				ClickM1(g)
				if Settings["Select Weapon"] == "Blox Fruit" then
					toTarget(g.HumanoidRootPart.CFrame * CFrame.new(-7, 20, 0))
				else
					toTarget(g.HumanoidRootPart.CFrame * CFrame.new(7, 20, 0))
				end
			until not IsMobAlive(g) or not Settings["Auto Get Ghoul"]
			wait(5)
		else
			if Settings["Hop Server Get Ghoul"] then
				SpecialHop("Cursed Captain")
			end
			A.CreateNoti({ Title = "Banana Cat Hub", Desc = "Wating Boss Spawn", ShowTime = 5 })
			wait(5)
		end
	end
end
RaceNormalSection.CreateToggle(
	{ Title = "Hop Server Find Boss Cursed Captain", Desc = nil, Default = Settings["Hop Server Get Ghoul"] or false },
	function(g)
		SaveSettings("Hop Server Get Ghoul", g)
	end
)
RaceNormalSection.CreateToggle(
	{ Title = "Auto Get Ghoul", Desc = nil, Default = Settings["Auto Get Ghoul"] or false },
	function(g)
		if g then
			spawn(function()
				while Settings["Auto Get Ghoul"] and (wait(0.1)) do
					local R, R = pcall(function()
						GetRaceGhoul()
					end)
					if R then
						print(R)
					end
				end
			end)
		end
		SaveSettings("Auto Get Ghoul", g)
	end
)
RaceV4Section = RaceMain.CreateSection("Race V4")
RaceV4Section.CreateToggle({ Title = "No Frog", Desc = nil, Default = Settings["No Frog"] or false }, function(g)
	if g then
		local R = game.Lighting
		R.FogEnd = 100000
		for m, m in pairs(R:GetDescendants()) do
			if m:IsA("Atmosphere") then
				m:Destroy()
			end
		end
	end
	SaveSettings("No Frog", g)
end)
RaceV4Section.CreateToggle(
	{ Title = "Teleport Acient Clock", Desc = nil, Default = Settings["Teleport Acient Clock"] or false },
	function(g)
		if g then
			spawn(function()
				while Settings["Teleport Acient Clock"] and (wait()) do
					local R = game:GetService("Workspace").Map["Temple of Time"]:FindFirstChild("Prompt")
					if R then
						toTarget(R.CFrame)
					end
				end
			end)
		end
		SaveSettings("Teleport Acient Clock", g)
	end
)
function BuyGearV4()
	if string.find(CheckAcientOneStatus(), "Can Buy Gear") then
		game.ReplicatedStorage.Remotes.CommF_:InvokeServer("UpgradeRace", "Buy")
		ResetRaceStatus()
	end
end
local g, R =
	CFrame.new(
		28576.4688,
		14935.9512,
		75.469101,
		-1,
		-4.22219593E-8,
		1.13133396E-8,
		0,
		-0.258819044,
		-0.965925813,
		4.37113883E-8,
		-0.965925813,
		0.258819044
	),
	0.2
function getBlueGear()
	if game.workspace.Map:FindFirstChild("MysticIsland") then
		for m, m in pairs(game.workspace.Map.MysticIsland:GetChildren()) do
			if m:IsA("MeshPart") and m.MeshId == "rbxassetid://10153114969" then
				return m
			end
		end
	end
end
function getHighestPoint()
	if not game.workspace.Map:FindFirstChild("MysticIsland") then
		return nil
	end
	for m, m in pairs(game:GetService("Workspace").Map.MysticIsland:GetDescendants()) do
		if m:IsA("MeshPart") then
			if m.MeshId == "rbxassetid://6745037796" then
				return m
			end
		end
	end
end
local m = { "Last Resort", "Agility", "Water Body", "Heavenly Blood", "Energy Core", "Heightened Senses" }
function CheckAbility()
	local l, S, I = next, game.Players.LocalPlayer.Backpack:GetChildren()
	for _, _ in l, S, I do
		if table.find(m, _.Name) then
			return true
		end
	end
	l, S, I = next, game.Players.LocalPlayer.Character:GetChildren()
	for _, _ in l, S, I do
		if table.find(m, _.Name) then
			return true
		end
	end
end
function CollectBlueGear()
	if not getHighestPoint() then
		local l = DetectNpc("Advanced Fruit Dealer")
		if l then
			toTarget(l.HumanoidRootPart.CFrame)
			return
		end
	end
	local l = getBlueGear()
	if l and not l.CanCollide and l.Transparency ~= 1 then
		if game.Players.LocalPlayer.Character.HumanoidRootPart:FindFirstChild("Agility") then
			game.Players.LocalPlayer.Character.HumanoidRootPart:FindFirstChild("Agility"):Destroy()
		end
		toTarget(getBlueGear().CFrame)
	elseif l and l.Transparency == 1 then
		if
			getHighestPoint()
			and (
					getHighestPoint().CFrame * CFrame.new(0, 211.88, 0).Position - t.Character.HumanoidRootPart.Position
				).Magnitude
				> 10
		then
			toTarget(getHighestPoint().CFrame * CFrame.new(0, 211.88, 0))
		else
			game.Players.LocalPlayer.CameraMode = "LockFirstPerson"
			game.Players.LocalPlayer.CameraMode = "Classic"
			local l = tick()
			repeat
				wait()
				game:GetService("Workspace").CurrentCamera.CFrame = CFrame.new(
					game:GetService("Workspace").CurrentCamera.CFrame.Position,
					game:GetService("Lighting"):GetMoonDirection()
						+ game:GetService("Workspace").CurrentCamera.CFrame.Position
				)
			until tick() - l >= 3
			game:GetService("VirtualInputManager"):SendKeyEvent(true, "T", false, game)
			task.wait(0.5)
			game:GetService("VirtualInputManager"):SendKeyEvent(false, "T", false, game)
			if
				not CheckAbility() and not game.Players.LocalPlayer.Character.HumanoidRootPart:FindFirstChild("Agility")
			then
				l = game:GetService("ReplicatedStorage").FX.Agility:Clone()
				l.Parent = game.Players.LocalPlayer.Character.HumanoidRootPart
				l.Enabled = false
			end
			task.wait(1.5)
		end
	end
end
function PullLeverV4()
	if not CheckItemInventory("Valkyrie Helm") or not CheckItemInventory("Mirror Fractal") then
		A.CreateNoti({ Title = "Banana Cat Hub", Desc = "Not Valkyrie Helm or not Mirror Fractal", ShowTime = 5 })
		wait(5)
		return
	end
	if
		not game:GetService("ReplicatedStorage")
			:WaitForChild("Remotes")
			:WaitForChild("CommF_")
			:InvokeServer("CheckTempleDoor")
	then
		local l = game.ReplicatedStorage.Remotes.CommF_:InvokeServer("RaceV4Progress", "Check")
		if l == 1 then
			game.ReplicatedStorage.Remotes.CommF_:InvokeServer("RaceV4Progress", "Begin")
			return
		elseif l == 2 then
			toTarget(CFrame.new(3032.780029296875, 2280.85107421875, -7325.47802734375))
			if
				(
					CFrame.new(3032.780029296875, 2280.85107421875, -7325.47802734375).Position
					- t.Character.HumanoidRootPart.Position
				).Magnitude < 8
			then
				game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("RaceV4Progress", "Teleport")
			end
			return
		elseif l == 3 then
			game.ReplicatedStorage.Remotes.CommF_:InvokeServer("RaceV4Progress", "Continue")
			return
		end
		if game:GetService("Workspace").Map:FindFirstChild("MysticIsland") and CheckClockTime() == "Night" then
			CollectBlueGear()
		elseif game:GetService("Workspace").Map:FindFirstChild("MysticIsland") and CheckClockTime() ~= "Night" then
			if not getHighestPoint() then
				l = DetectNpc("Advanced Fruit Dealer")
				if l then
					toTarget(l.HumanoidRootPart.CFrame)
					return
				end
			end
			if
				getHighestPoint()
				and (
						getHighestPoint().CFrame * CFrame.new(0, 211.88, 0).Position
						- t.Character.HumanoidRootPart.Position
					).Magnitude
					> 10
			then
				toTarget(getHighestPoint().CFrame * CFrame.new(0, 211.88, 0))
			end
		elseif
			not game:GetService("Workspace").Map:FindFirstChild("MysticIsland")
			and Settings["Hop Server [Trial Or Pull Lever]"]
		then
			SpecialHop("Mirage")
		end
	else
		local l = GetTempleOfTime()
		if not l then
			toTarget(CFrame.new(28282.5703125, 14896.8505859375, 105.1042709350586))
			return
		end
		if l.Lever.Lever.CFrame.Z > g.Z + R or l.Lever.Lever.CFrame.Z < g.Z - R then
			if (t.Character.HumanoidRootPart.Position - l.Lever.Part.Position).Magnitude > 10 then
				toTarget(l.Lever.Part.CFrame)
			else
				fireproximityprompt(l.Lever.Prompt.ProximityPrompt, 1)
			end
		else
			A.CreateNoti({ Title = "Banana Cat Hub", Desc = "Done Pull Lever", ShowTime = 5 })
			wait(5)
		end
	end
end
RaceV4Section.CreateToggle(
	{ Title = "Auto Buy Gear", Desc = nil, Default = Settings["Auto Buy Gear"] or false },
	function(g)
		if g then
			spawn(function()
				while Settings["Auto Buy Gear"] and (wait(0.2)) do
					pcall(function()
						BuyGearV4()
					end)
				end
			end)
		end
		SaveSettings("Auto Buy Gear", g)
	end
)
RaceV4Section.CreateDropdown(
	{
		Title = "Select Gear V4",
		List = { "Alpha", "Omega" },
		Search = false,
		Selected = false,
		Default = Settings["Select Gear V4"] or "Omega",
	},
	function(g)
		SaveSettings("Select Gear V4", g)
	end
)
getgenv().ToggleAutoChooseGears = RaceV4Section.CreateToggle(
	{ Title = "Auto Choose Gears", Desc = nil, Default = Settings["Auto Choose Gears"] or false },
	function(g)
		if g then
			spawn(function()
				while Settings["Auto Choose Gears"] and (wait(0.3)) do
					local R, R = pcall(function()
						ChooseGearV4()
					end)
					if R then
						print(R)
					end
				end
			end)
		end
		SaveSettings("Auto Choose Gears", g)
	end
)
RaceV4Section.CreateToggle(
	{ Title = "Auto Finish Train Quest", Desc = nil, Default = Settings["Auto Finish Train Quest"] or false },
	function(g)
		if g then
			spawn(function()
				while Settings["Auto Finish Train Quest"] and (task.wait()) do
					local R, R = pcall(function()
						if Settings["Stack Train With Trial Race"] and not CheckGoTrain() then
							return
						end
						TurnOnV4()
						BuyGearV4()
						local l = DetectMob(e)
						if l then
							repeat
								task.wait()
								sizepart(l)
								BringMob(l)
								UsedualFlock()
								ClickM1(l)
								if Settings["Select Weapon"] == "Blox Fruit" then
									toTarget(l.HumanoidRootPart.CFrame * CFrame.new(-7, 20, 0))
								else
									toTarget(l.HumanoidRootPart.CFrame * CFrame.new(7, 20, 0))
								end
							until not IsMobAlive(l) or not Settings["Auto Finish Train Quest"] or not CheckGoTrain()
						elseif typeof(e) == "table" then
							if #N >= #e then
								N = {}
								return
							end
							local l = DetectPartSpawnMob(DetectNameTablePart(e))
							if l then
								table.insert(N, DetectNameTablePart(e))
								repeat
									wait()
									toTarget(l.CFrame * CFrame.new(0, 60, 0))
								until (l.Position - t.Character.HumanoidRootPart.Position).Magnitude <= 100
									or (DetectMob(e))
									or not Settings["Auto Finish Train Quest"]
									or not CheckGoTrain()
								wait(1)
							end
						else
							local l = DetectPartSpawnMob(e, true)
							if l then
								Instance.new("IntValue", l).Name = "Ignored"
								repeat
									wait()
									toTarget(l.CFrame * CFrame.new(0, 60, 0))
								until (l.Position - t.Character.HumanoidRootPart.Position).Magnitude <= 100
									or (DetectMob(e))
									or not Settings["Auto Finish Train Quest"]
									or not CheckGoTrain()
								wait(1)
							else
								DeleteIgnoredMobSpawn()
							end
						end
					end)
					if R then
						print(R)
					end
				end
			end)
		end
		SaveSettings("Auto Finish Train Quest", g)
	end
)
RaceV4Section.CreateToggle(
	{ Title = "Stack Train With Trial Race", Desc = nil, Default = Settings["Stack Train With Trial Race"] or false },
	function(g)
		SaveSettings("Stack Train With Trial Race", g)
	end
)
getgenv().TurnOffHOPSVPullAndTrial = RaceV4Section.CreateToggle(
	{
		Title = "Hop Server [Trial Or Pull Lever]",
		Desc = nil,
		Default = Settings["Hop Server [Trial Or Pull Lever]"] or false,
	},
	function(g)
		SaveSettings("Hop Server [Trial Or Pull Lever]", g)
	end
)
RaceV4Section.CreateToggle(
	{ Title = "Auto Pull Lever", Desc = nil, Default = Settings["Auto Pull Lever"] or false },
	function(g)
		if g then
			spawn(function()
				while Settings["Auto Pull Lever"] and (wait(0.1)) do
					pcall(function()
						PullLeverV4()
					end)
				end
			end)
		end
		SaveSettings("Auto Pull Lever", g)
	end
)
function DetectNameMulti(g)
	local R = {}
	if Settings["Select Players Multi"] and not g then
		for g, l in next, Settings["Select Players Multi"], nil do
			if l then
				R[g] = true
			end
		end
	end
	for g, g in pairs(game:GetService("Players"):GetChildren()) do
		if g.Name ~= t.Name and not table.find(R, g.Name) then
			R[g.Name] = false
		end
	end
	return R
end
DropdownSelectPlayerMulti = RaceV4Section.CreateDropdown(
	{
		Title = "Select Players Multi",
		List = PrepareMultiSelectList(DetectNameMulti(), Settings["Select Players Multi"]),
		Search = true,
		Selected = true,
		Default = Settings["Select Players Multi"] or nil,
	},
	function(g, R)
		SaveSettings("Select Players Multi", g, R)
	end
)
RaceV4Section.CreateButton({ Title = "Refresh Player" }, function()
	DropdownSelectPlayerMulti:GetNewList(DetectNameMulti(true))
end)
RaceV4Section.CreateToggle(
	{ Title = "Multi Trial", Desc = nil, Default = Settings["Multi Trial"] or false },
	function(g)
		SaveSettings("Multi Trial", g)
	end
)
RaceV4Section.CreateToggle(
	{ Title = "Auto Reset Character", Desc = nil, Default = Settings["Auto Reset Character"] or false },
	function(g)
		SaveSettings("Auto Reset Character", g)
	end
)
ToggleAutoTrial = RaceV4Section.CreateToggle(
	{ Title = "Auto Trial", Desc = nil, Default = Settings["Auto Trial"] or false },
	function(g)
		SaveSettings("Auto Trial", g)
	end
)
RaceV4Section.CreateToggle(
	{
		Title = "Auto Turn On V3 Near Door",
		Desc = "will auto turn on race \10if have players near door",
		Default = Settings["Auto Turn On V3 Near Door"] or false,
	},
	function(g)
		SaveSettings("Auto Turn On V3 Near Door", g)
	end
)
KillTrialSection = RaceMain.CreateSection("Kill Trial")
KillTrialSection.CreateDropdown(
	{
		Title = "Select Weapon Attack Trial",
		List = { "Melee", "Sword", "Blox Fruit" },
		Search = true,
		Selected = false,
		Default = Settings["Select Weapon Attack Trial"] or nil,
	},
	function(g)
		SaveSettings("Select Weapon Attack Trial", g)
	end
)
KillTrialSection.CreateToggle(
	{
		Title = "Kill players When complete Trial",
		Desc = "Turn on before Start Attack and Turn on Auto Trial",
		Default = Settings["Kill players When complete Trial"] or false,
	},
	function(g)
		SaveSettings("Kill players When complete Trial", g)
	end
)
KillTrialSection.CreateToggle(
	{ Title = "Use Skill when Kill Player", Desc = nil, Default = Settings["Use Skill when Kill Player"] or false },
	function(g)
		SaveSettings("Use Skill when Kill Player", g)
	end
)
KillTrialSection.CreateToggle(
	{
		Title = "Just Use Skill when Player Active Ken",
		Desc = nil,
		Default = Settings["Just Use Skill when Player Active Ken"] or false,
	},
	function(g)
		SaveSettings("Just Use Skill when Player Active Ken", g)
	end
)
function DetectNameAbility(g)
	local R, l, S = next, g:GetChildren()
	for g, g in R, l, S do
		if table.find(m, g.Name) then
			return true
		end
	end
end
function GetOtherPlayerRaces()
	local g = {}
	for R, R in pairs(game:GetService("Players"):GetChildren()) do
		if R.Name ~= t.Name then
			g[R.Name] = R.Data.Race.Value
		end
	end
	return g
end
function CheckMultiPlayerNearDoor()
	local g, R, m = next, game.Workspace.Characters:GetChildren()
	local l = 0
	for S, I in g, R, m do
		S = GetOtherPlayerRaces()[I.Name]
		l = if S
				and (DetectNameAbility(I.HumanoidRootPart))
				and (
						I.HumanoidRootPart.Position
						- game:GetService("Workspace").Map["Temple of Time"][S .. "Corridor"].Door.Door.RightDoor.Union.Position
					).Magnitude
					< 100
			then l + 1
			else l
	end
	if l >= 2 then
		return true
	end
end
function CheckMultiAccount()
	local g = {}
	for R, R in pairs(game:GetService("Players"):GetChildren()) do
		if Settings["Select Players Multi"] and Settings["Select Players Multi"][R.Name] then
			g[R.Name] = R.Data.Race.Value
		end
	end
	return g
end
function CheckMultiTeleDoor()
	local g, R, m = next, game.Workspace.Characters:GetChildren()
	local l = 0
	for S, I in g, R, m do
		S = CheckMultiAccount()[I.Name]
		l = if S
				and (
						I.HumanoidRootPart.Position
						- game:GetService("Workspace").Map["Temple of Time"][S .. "Corridor"].Door.Door.RightDoor.Union.Position
					).Magnitude
					< 100
			then l + 1
			else l
	end
	if l >= 2 then
		return true
	end
end
function TrialHuman()
	if game:GetService("Workspace")._WorldOrigin.Locations:FindFirstChild("Trial of Strength") then
		StrengthPart = game:GetService("Workspace")._WorldOrigin.Locations["Trial of Strength"]
		if (game.Players.LocalPlayer.Character.HumanoidRootPart.Position - StrengthPart.Position).Magnitude <= 1000 then
			for g, g in pairs(game.Workspace.Enemies:GetChildren()) do
				if IsMobAlive(g) and (g.HumanoidRootPart.Position - StrengthPart.Position).Magnitude <= 1000 then
					return g
				end
			end
		end
	end
end
function TrialGhoul()
	if game:GetService("Workspace")._WorldOrigin.Locations:FindFirstChild("Trial of Carnage") then
		if
			(
				game.Players.LocalPlayer.Character.HumanoidRootPart.Position
				- game:GetService("Workspace")._WorldOrigin.Locations["Trial of Carnage"].Position
			).Magnitude <= 1000
		then
			for g, g in pairs(game.Workspace.Enemies:GetChildren()) do
				if
					IsMobAlive(g)
					and (
							g.HumanoidRootPart.Position
							- game:GetService("Workspace")._WorldOrigin.Locations["Trial of Carnage"].Position
						).Magnitude
						<= 1000
				then
					return g
				end
			end
		end
	end
end
function GetSeaBeastTrial()
	if not game.Workspace.Map:FindFirstChild("FishmanTrial") then
		return
	end
	local g = if game:GetService("Workspace")._WorldOrigin.Locations:FindFirstChild("Trial of Water")
		then (game:GetService("Workspace")._WorldOrigin.Locations:FindFirstChild("Trial of Water"))
		else nil
	if g then
		local R, m, l = next, game:GetService("Workspace").SeaBeasts:GetChildren()
		for S, S in R, m, l do
			if
				string.find(S.Name, "SeaBeast")
				and (S:FindFirstChild("HumanoidRootPart"))
				and (S.HumanoidRootPart.Position - g.Position).Magnitude <= 1500
			then
				if S.Health.Value > 0 then
					return S
				end
			end
		end
	end
end
getgenv().TrialDone = false
getgenv().KillAuraDone = false
function TeleportSeabeast2(g)
	if
		(Vector3.new(0, g:FindFirstChild("HumanoidRootPart").Position.Y, 0) - Vector3.new(0, -60, 0)).Magnitude <= 175
	then
		toTarget(g.HumanoidRootPart.CFrame * CFrame.new(0, 200, 50))
	else
		toTarget(CFrame.new(g.HumanoidRootPart.Position.X, 140, g.HumanoidRootPart.Position.Z))
	end
end
function DetectPlayerKillName()
	local g, R, m, l = {}, next, game.Workspace.Characters:GetChildren()
	for S, S in R, m, l do
		if
			S:IsA("Model")
			and S.Name ~= game.Players.LocalPlayer.Name
			and (S:FindFirstChild("HumanoidRootPart"))
			and (S:FindFirstChild("Humanoid"))
			and S.Humanoid.Health > 0
			and (S.HumanoidRootPart.Position - Vector3.new(28718.068359375, 14887.5625, -60.5482177734375)).Magnitude
				<= 400
		then
			table.insert(g, S.Name)
		end
	end
	return g
end
getgenv().PlayerKillTrial = {}
getgenv().BlackListPlayerTrial = {}
function NameAttackTrial()
	for g, R in next, getgenv().PlayerKillTrial, nil do
		if not table.find(getgenv().BlackListPlayerTrial, R) then
			return R, g
		end
	end
end
function CheckCDSkill(g)
	if not game:GetService("Players").LocalPlayer.PlayerGui.Main.Skills:FindFirstChild(g) then
		equiptool(g)
		return
	end
	local R, m, l = next, game:GetService("Players").LocalPlayer.PlayerGui.Main.Skills[g]:GetChildren()
	for g, g in R, m, l do
		if g:IsA("Frame") then
			if
				g.Name ~= "Template"
					and g.Title.TextColor3 == Color3.new(1, 1, 1)
					and g.Cooldown.Size == UDim2.new(0, 0, 1, -1)
				or g.Cooldown.Size == UDim2.new(1, 0, 1, -1)
			then
				return g
			end
		end
	end
end
function VerifyNearbyTrial()
	local g, R, m, l =
		{
			"Trial of the Machine",
			"Trial of Speed",
			"Trial of Strength",
			"Trial of Water",
			"Trial of the King",
			"Trial of Carnage",
			"Trial of Flames",
		},
		next,
		workspace._WorldOrigin.Locations:GetChildren()
	for S, S in R, m, l do
		if table.find(g, S.Name) and t:DistanceFromCharacter(S.Position) < 1500 then
			return true
		end
	end
end
function AutoTrialV4()
	if Settings["Auto Finish Train Quest"] and Settings["Stack Train With Trial Race"] and (CheckGoTrain()) then
		return
	end
	local g = game.Lighting.ClockTime
	if
		(CheckMoon() == "Full Moon" and not (g > 5 and g < 12) or CheckMoon() == "Next Night")
		and Settings["Hop Server [Trial Or Pull Lever]"]
	then
		if getgenv().TurnOffHOPSVPullAndTrial then
			getgenv().TurnOffHOPSVPullAndTrial:SetStage(false)
		end
		task.wait(3)
	elseif Settings["Hop Server [Trial Or Pull Lever]"] then
		HopServer()
		return
	end
	g = GetTempleOfTime()
	if not g and not VerifyNearbyTrial() then
		toTarget(CFrame.new(28282.5703125, 14896.8505859375, 105.1042709350586))
		return
	end
	if
		g and (g.FFABorder:FindFirstChild("Forcefield")) and g.FFABorder.Forcefield.Transparency == 1
		or (VerifyNearbyTrial())
	then
		if game:GetService("Players").LocalPlayer.PlayerGui.Main.TopHUDList.RaidTimer.Visible then
			if VerifyNearbyTrial() and not getgenv().VerifyTrial then
				getgenv().VerifyTrial = true
			end
			repeat
				wait()
			until VerifyNearbyTrial()
				or not game:GetService("Players").LocalPlayer.PlayerGui.Main.TopHUDList.RaidTimer.Visible
			local R = game.Players.LocalPlayer.Data.Race.Value
			if R == "Human" then
				repeat
					task.wait()
					local m = TrialHuman()
					if m then
						repeat
							task.wait()
							sizepart(m)
							if Settings["Select Weapon"] == "Blox Fruit" then
								toTarget(m.HumanoidRootPart.CFrame * CFrame.new(-7, 20, 0))
							else
								toTarget(m.HumanoidRootPart.CFrame * CFrame.new(7, 20, 0))
							end
							ClickM1(m)
							UsedualFlock()
						until not IsMobAlive(m)
							or not game:GetService("Players").LocalPlayer.PlayerGui.Main.TopHUDList.RaidTimer.Visible
							or (game.Players.LocalPlayer.Character.HumanoidRootPart.Position - game:GetService(
									"Workspace"
								)._WorldOrigin.Locations["Trial of Strength"].Position).Magnitude
								> 1000
					end
				until not game:GetService("Players").LocalPlayer.PlayerGui.Main.TopHUDList.RaidTimer.Visible
					or (
							game.Players.LocalPlayer.Character.HumanoidRootPart.Position
							- game:GetService("Workspace")._WorldOrigin.Locations["Trial of Strength"].Position
						).Magnitude
						> 1000
			elseif R == "Skypiea" then
				repeat
					task.wait()
					if
						game:GetService("Workspace")._WorldOrigin.Locations["Trial of the King"]
						and (game.Players.LocalPlayer.Character.HumanoidRootPart.Position - game:GetService(
								"Workspace"
							)._WorldOrigin.Locations["Trial of the King"].CFrame.Position).Magnitude
							<= 1000
					then
						toTarget(game:GetService("Workspace").Map.SkyTrial.Model.FinishPart.CFrame)
						task.wait(3)
					end
				until not game:GetService("Players").LocalPlayer.PlayerGui.Main.TopHUDList.RaidTimer.Visible
					or workspace.Map:FindFirstChild("Temple of Time") and workspace.Map["Temple of Time"].FFABorder.Forcefield.Transparency == 0
					or t:DistanceFromCharacter(game:GetService("Workspace").Map.SkyTrial.Model.FinishPart.Position)
						> 1000
			elseif R == "Fishman" then
				local m = if game:GetService("Workspace")._WorldOrigin.Locations:FindFirstChild("Trial of Water")
					then (game:GetService("Workspace")._WorldOrigin.Locations:FindFirstChild("Trial of Water"))
					else nil
				if m and (m.Position - t.Character.HumanoidRootPart.Position).Magnitude < 1500 then
					local m = GetSeaBeastTrial()
					repeat
						task.wait()
						if m then
							local l = m:FindFirstChild("HumanoidRootPart")
							getgenv().AimPos = CFrame.new(l.Position.X, 40, l.Position.Z)
							TeleportSeabeast2(m)
							if t:DistanceFromCharacter(l.Position) < 400 then
								AutoAllSkill()
							end
						end
					until not m
						or not m.Parent
						or m.Health.Value == 0
						or not game:GetService("Players").LocalPlayer.PlayerGui.Main.TopHUDList.RaidTimer.Visible
						or workspace.Map:FindFirstChild("Temple of Time") and workspace.Map["Temple of Time"].FFABorder.Forcefield.Transparency == 0
						or t:DistanceFromCharacter(
								game:GetService("Workspace")._WorldOrigin.Locations
									:FindFirstChild("Trial of Water").Position
							)
							> 1000
				end
			elseif R == "Mink" then
				repeat
					task.wait()
					if
						(
							game.Players.LocalPlayer.Character.HumanoidRootPart.Position
							- game:GetService("Workspace")._WorldOrigin.Locations["Trial of Speed"].Position
						).Magnitude <= 1000
					then
						toTarget(game:GetService("Workspace").StartPoint.CFrame * CFrame.new(0, 2, 0))
					end
				until not game:GetService("Players").LocalPlayer.PlayerGui.Main.TopHUDList.RaidTimer.Visible
					or t:DistanceFromCharacter(
							game:GetService("Workspace")._WorldOrigin.Locations
								:FindFirstChild("Trial of Speed").Position
						)
						> 1000
			elseif R == "Ghoul" then
				repeat
					task.wait()
					local m = TrialGhoul()
					if m then
						repeat
							task.wait()
							sizepart(m)
							if Settings["Select Weapon"] == "Blox Fruit" then
								toTarget(m.HumanoidRootPart.CFrame * CFrame.new(-7, 20, 0))
							else
								toTarget(m.HumanoidRootPart.CFrame * CFrame.new(7, 20, 0))
							end
							UsedualFlock()
							ClickM1(m)
						until not IsMobAlive(m)
							or not game:GetService("Players").LocalPlayer.PlayerGui.Main.TopHUDList.RaidTimer.Visible
							or t:DistanceFromCharacter(
									game:GetService("Workspace")._WorldOrigin.Locations
										:FindFirstChild("Trial of Carnage").Position
								)
								> 1000
					end
				until not game:GetService("Players").LocalPlayer.PlayerGui.Main.TopHUDList.RaidTimer.Visible
					or t:DistanceFromCharacter(
							game:GetService("Workspace")._WorldOrigin.Locations
								:FindFirstChild("Trial of Carnage").Position
						)
						> 1000
			elseif R == "Cyborg" then
				repeat
					task.wait()
					toTarget(CFrame.new(28282.5703125, 14896.8505859375, 105.1042709350586))
				until not game:GetService("Players").LocalPlayer.PlayerGui.Main.TopHUDList.RaidTimer.Visible
			end
		else
			if not g then
				return
			end
			local R = g[t.Data.Race.Value .. "Corridor"].Door.Door.RightDoor.Union
			if t:DistanceFromCharacter(R.Position) > 8 then
				toTarget(R.CFrame)
			end
			if Settings["Multi Trial"] and (CheckMultiTeleDoor()) and t:DistanceFromCharacter(R.Position) <= 8 then
				game:service("VirtualInputManager"):SendKeyEvent(true, "T", false, game)
				task.wait()
				game:service("VirtualInputManager"):SendKeyEvent(false, "T", false, game)
				return
			end
			if Settings["Auto Turn On V3 Near Door"] and (CheckMultiPlayerNearDoor()) then
				game:service("VirtualInputManager"):SendKeyEvent(true, "T", false, game)
				task.wait()
				game:service("VirtualInputManager"):SendKeyEvent(false, "T", false, game)
			end
		end
	elseif getgenv().VerifyTrial then
		if not Settings["Multi Trial"] and not Settings["Auto Reset Character"] then
			Settings["Auto Trial"] = false
			ToggleAutoTrial:SetStage(false)
		end
		getgenv().VerifyTrial = false
	end
end
function PlayerTrial()
	local g = workspace.Map["Temple of Time"].FFABorder.Forcefield
	local R, m = g.Position, g.Size
	for l, S in pairs((workspace:FindPartsInRegion3(Region3.new(R - m / 2, R + m / 2), nil, 1 / 0))) do
		l = S.Parent
		if l and (l:FindFirstChild("Humanoid")) then
			g = game.Players:GetPlayerFromCharacter(l)
			if g and g.Name ~= t.Name and g.Character.Humanoid.Health > 0 then
				return g.Character
			end
		end
	end
end
local g
function hasCooldownChanged(R)
	local m, l = R:GetAttributes(), g
	if not l then
		g = R:GetAttributes()
	end
	for R, l in next, m, nil do
		if
			(
				string.find(R, "GunCooldown")
				or (string.find(R, "MeleeCooldown"))
				or (string.find(R, "SwordCooldown"))
				or (string.find(R, "BloxFruitCooldown"))
			) and l > 0
		then
			if g[R] ~= l then
				g = m
				return true
			end
		end
	end
	return false
end
spawn(function()
	while task.wait(0.1) do
		pcall(function()
			if Settings["Kill players When complete Trial"] then
				if
					workspace.Map:FindFirstChild("Temple of Time")
					and workspace.Map["Temple of Time"].FFABorder.Forcefield.Transparency ~= 1
				then
					if game:GetService("Players").LocalPlayer.PlayerGui.Main.TopHUDList.RaidTimer.Visible then
						local g, R = PlayerTrial(), false
						if g then
							repeat
								task.wait()
								task.spawn(function()
									if not game:GetService("Lighting").Blur.Enabled then
										game:GetService("VirtualInputManager"):SendKeyEvent(true, "E", false, game)
										task.wait()
										game:GetService("VirtualInputManager"):SendKeyEvent(false, "E", false, game)
										task.wait(3)
									end
									getgenv().AimPos = g.HumanoidRootPart.CFrame
								end)
								if hasCooldownChanged(g) then
									local m = tick()
									repeat
										task.wait()
										task.spawn(getgenv().AttackFunctionnhungSuperTrial)
										t.Character.HumanoidRootPart.CFrame = g.HumanoidRootPart.CFrame
											* CFrame.new(0, 50, 0)
									until tick() - m >= 0.75
									R = false
								else
									if R then
										return
									end
									t.Character.HumanoidRootPart.CFrame = g.HumanoidRootPart.CFrame
										* CFrame.new(0, 0, 4)
								end
								task.spawn(getgenv().AttackFunctionnhungSuperTrial)
								equiptool(NameWeapon(Settings["Select Weapon Attack Trial"]))
								if
									Settings["Use Skill when Kill Player"]
									or Settings["Just Use Skill when Player Active Ken"]
								then
									if
										Settings["Just Use Skill when Player Active Ken"]
											and (game.Players[g.Name]:GetAttribute("KenActive"))
										or not Settings["Just Use Skill when Player Active Ken"]
									then
										task.spawn(function()
											local R = CheckCDSkill(NameWeapon(Settings["Select Weapon Attack Trial"]))
											if R then
												game:GetService("VirtualInputManager")
													:SendKeyEvent(true, R.Name, false, game)
												task.wait(0.05)
												game:GetService("VirtualInputManager")
													:SendKeyEvent(false, R.Name, false, game)
											end
										end)
									end
								end
							until not g
								or not g.Parent
								or g.Humanoid.Health <= 0
								or not Settings["Kill players When complete Trial"]
								or not game:GetService("Players").LocalPlayer.PlayerGui.Main.TopHUDList.RaidTimer.Visible
								or t.Character.Humanoid.Health <= 0
						end
					end
				end
			end
		end)
	end
end)
spawn(function()
	while task.wait(0.1) do
		if Settings["Auto Trial"] then
			local g, R = pcall(function()
				AutoTrialV4()
			end)
			if R then
				print(g, R)
			end
		end
		pcall(function()
			if
				workspace.Map:FindFirstChild("Temple of Time")
				and workspace.Map["Temple of Time"].FFABorder.Forcefield.Transparency ~= 1
			then
				if Settings["Auto Reset Character"] then
					t.Character.Humanoid.Health = 0
				end
			end
		end)
	end
end)
GetItemsMain = Main.CreatePage({ Page_Name = "Get and Upgrade Items", Page_Title = "Get and Upgrade Items Tab" })
GetItemsSection = GetItemsMain.CreateSection("Get Items")
GetItemsSection.CreateToggle(
	{ Title = "Auto Trade Bone", Desc = nil, Default = Settings["Auto Trade Bone"] or false },
	function(g)
		SaveSettings("Auto Trade Bone", g)
	end
)
GetItemsSection.CreateToggle(
	{ Title = "Auto Buy Legendary Sword", Desc = nil, Default = Settings["Auto Buy Legendary Sword"] or false },
	function(g)
		SaveSettings("Auto Buy Legendary Sword", g)
	end
)
GetItemsSection.CreateToggle(
	{ Title = "Auto Buy Haki Color", Desc = nil, Default = Settings["Auto Buy Haki Color"] or false },
	function(g)
		SaveSettings("Auto Buy Haki Color", g)
	end
)
GetItemsSection.CreateToggle(
	{
		Title = "Hop Server [ Haki color or Legendary Sword]",
		Desc = nil,
		Default = Settings["Hop Server [ Haki color or Legendary Sword]"] or false,
	},
	function(g)
		SaveSettings("Hop Server [ Haki color or Legendary Sword]", g)
	end
)
local g = { "Stone", "Hydra Leader", "Kilo Admiral", "Captain Elephant", "Beautiful Pirate" }
function DetectQuestRainBowHaki(R)
	if not R then
		for R, R in next, g, nil do
			if
				game:GetService("Players").LocalPlayer.PlayerGui.Main.Quest.Visible
				and (string.find(game.Players.LocalPlayer.PlayerGui.Main.Quest.Container.QuestTitle.Title.Text, R))
			then
				return false
			end
		end
		for R, R in next, g, nil do
			if
				not string.find(game.Players.LocalPlayer.PlayerGui.Main.Quest.Container.QuestTitle.Title.Text, R)
				or not game:GetService("Players").LocalPlayer.PlayerGui.Main.Quest.Visible
			then
				return true
			end
		end
	else
		for R, R in next, g, nil do
			if string.find(game.Players.LocalPlayer.PlayerGui.Main.Quest.Container.QuestTitle.Title.Text, R) then
				return R
			end
		end
	end
end
function GetRainBowHaki()
	if game.ReplicatedStorage.Remotes.CommF_:InvokeServer("HornedMan") == 1 then
		A.CreateNoti({ Title = "Banana Cat Hub", Desc = "Done Get Rainbow Haki", ShowTime = 5 })
		wait(5)
		return
	end
	local g = workspace.NPCs:FindFirstChild("Horned Man")
		or (game:GetService("ReplicatedStorage").NPCs:FindFirstChild("Horned Man"))
		or NPCManager.getNPCsByName("Horned Man")[1]._modelState._instance
	if DetectQuestRainBowHaki() then
		if t:DistanceFromCharacter(g.HumanoidRootPart.Position) > 8 then
			toTarget(g.HumanoidRootPart.CFrame)
		else
			wait(2)
			game.ReplicatedStorage.Remotes.CommF_:InvokeServer("HornedMan", "Bet")
		end
	else
		local g = CheckNameBoss(DetectQuestRainBowHaki(true))
		if g then
			repeat
				task.wait()
				sizepart(g)
				if Settings["Select Weapon"] == "Blox Fruit" then
					toTarget(g.HumanoidRootPart.CFrame * CFrame.new(-7, 20, 0))
				else
					toTarget(g.HumanoidRootPart.CFrame * CFrame.new(7, 20, 0))
				end
				ClickM1(g)
				UsedualFlock()
			until not IsMobAlive(g) or not Settings["Auto Get Rainbow Haki"]
		else
			A.CreateNoti({ Title = "Banana Cat Hub", Desc = "Waiting Boss Spawn", ShowTime = 5 })
			wait(5)
		end
	end
end
GetItemsSection.CreateToggle(
	{ Title = "Auto Get Rainbow Haki", Desc = nil, Default = Settings["Auto Get Rainbow Haki"] or false },
	function(g)
		if g then
			spawn(function()
				while Settings["Auto Get Rainbow Haki"] and (task.wait(0.1)) do
					local R, R = pcall(function()
						GetRainBowHaki()
					end)
					if R then
						print(R)
					end
				end
			end)
		end
		SaveSettings("Auto Get Rainbow Haki", g)
	end
)
function CountZombie(g)
	local R = 0
	for m, m in pairs(game.workspace.Enemies:GetChildren()) do
		R = if m.Name == "Living Zombie" and m.Humanoid.Health > 0 then if not g then R + 1 else R else R
	end
	return R
end
BlankTablets = { "Segment6", "Segment2", "Segment8", "Segment9", "Segment5" }
Trophy =
	{ Segment1 = "Trophy1", Segment3 = "Trophy2", Segment4 = "Trophy3", Segment7 = "Trophy4", Segment10 = "Trophy5" }
Pipes = {
	Part1 = "Really black",
	Part2 = "Really black",
	Part3 = "Dusty Rose",
	Part4 = "Storm blue",
	Part5 = "Really black",
	Part6 = "Parsley green",
	Part7 = "Really black",
	Part8 = "Dusty Rose",
	Part9 = "Really black",
	Part10 = "Storm blue",
}
function DetectHighHealthMob(g)
	local R, m = 0
	for l, S in pairs(game.Workspace.Enemies:GetChildren()) do
		if (typeof(g) == "table" and (table.find(g, S.Name)) or S.Name == g) and (IsMobAlive(S)) then
			l = S.Humanoid.Health
			if l > R then
				R, m = l, S
			end
		end
	end
	return m
end
function GuitarPuzzleProgress()
	if not CommF:InvokeServer("GuitarPuzzleProgress", "Check") then
		if
			game.Lighting.Sky.MoonTextureId == "http://www.roblox.com/asset/?id=9709149431"
			and (game.Lighting.ClockTime > 16 or game.Lighting.ClockTime < 5)
		then
			if t:DistanceFromCharacter(Vector3.new(-8654.314453125, 140.9499053955078, 6167.5283203125)) > 50 then
				toTarget(CFrame.new(-8654.314453125, 140.9499053955078, 6167.5283203125))
			end
			CommF:InvokeServer("gravestoneEvent", 2)
			CommF:InvokeServer("gravestoneEvent", 2, true)
			task.wait(1)
		else
			A.CreateNoti({ Title = "Banana Cat Hub", Desc = "Hop Full Moon", ShowTime = 5 })
			SpecialHop("FullMoon")
		end
	else
		if t.PlayerGui.Main.Dialogue.Visible then
			game:GetService("VirtualUser"):Button1Down(Vector2.new(0, 0))
			game:GetService("VirtualUser"):Button1Down(Vector2.new(0, 0))
		end
		if not CommF:InvokeServer("GuitarPuzzleProgress", "Check").Swamp then
			if
				(
					CFrame.new(-10171.7607421875, 138.62667846679688, 6008.0654296875).Position
					- t.Character.HumanoidRootPart.Position
				).Magnitude > 100
			then
				toTarget(CFrame.new(-10171.7607421875, 158.62667846679688, 6008.0654296875))
			elseif CountZombie() == 6 then
				repeat
					task.wait()
					local g = (DetectHighHealthMob("Living Zombie"))
					repeat
						task.wait()
						g = DetectHighHealthMob("Living Zombie")
						sizepart(g)
						UsedualFlock()
						ClickM1(g)
						if Settings["Select Weapon"] == "Blox Fruit" then
							toTarget(g.HumanoidRootPart.CFrame * CFrame.new(-7, 20, 0))
						else
							toTarget(g.HumanoidRootPart.CFrame * CFrame.new(7, 20, 0))
						end
					until not IsMobAlive(g)
				until CountZombie() == 0
			end
			return
		elseif not CommF:InvokeServer("GuitarPuzzleProgress", "Check").Gravestones then
			if t:DistanceFromCharacter(Vector3.new(-8761.4765625, 142.10487365722656, 6086.07861328125)) > 50 then
				toTarget(CFrame.new(-8761.4765625, 142.10487365722656, 6086.07861328125))
			else
				local g = {
					game.workspace.Map["Haunted Castle"].Placard1.Right.ClickDetector,
					game.workspace.Map["Haunted Castle"].Placard2.Right.ClickDetector,
					game.workspace.Map["Haunted Castle"].Placard3.Left.ClickDetector,
					game.workspace.Map["Haunted Castle"].Placard4.Right.ClickDetector,
					game.workspace.Map["Haunted Castle"].Placard5.Left.ClickDetector,
					game.workspace.Map["Haunted Castle"].Placard6.Left.ClickDetector,
					game.workspace.Map["Haunted Castle"].Placard7.Left.ClickDetector,
				}
				for R, R in pairs(g) do
					fireclickdetector(R)
				end
			end
		elseif not CommF:InvokeServer("GuitarPuzzleProgress", "Check").Ghost then
			if t:DistanceFromCharacter(Vector3.new(-9755.6591796875, 271.0661315917969, 6290.61474609375)) > 50 then
				toTarget(CFrame.new(-9755.6591796875, 271.0661315917969, 6290.61474609375))
			end
			CommF:InvokeServer("GuitarPuzzleProgress", "Ghost")
			task.wait(3)
		elseif not CommF:InvokeServer("GuitarPuzzleProgress", "Check").Trophies then
			if t:DistanceFromCharacter(Vector3.new(-9530.0126953125, 6.104853630065918, 6054.83349609375)) > 50 then
				toTarget(CFrame.new(-9530.0126953125, 6.104853630065918, 6054.83349609375))
			end
			local g = game.workspace.Map["Haunted Castle"].Tablet
			for R, m in pairs(BlankTablets) do
				R = g[m]
				if R.Line.Position.X ~= -9707.86328125 then
					repeat
						task.wait()
						fireclickdetector(R.ClickDetector)
					until R.Line.Position.X == -9707.86328125
				end
			end
			for R, m in pairs(Trophy) do
				local l = tostring(game.workspace.Map["Haunted Castle"].Trophies.Quest[m].Handle.CFrame):split(", ")[4]
				m = if l == "1" or l == "-1" then "90" else "180"
				if not string.find(tostring(g[R].Line.Rotation.Z), m) then
					repeat
						task.wait()
						fireclickdetector(g[R].ClickDetector)
					until string.find(tostring(g[R].Line.Rotation.Z), m)
					print(R, m)
				end
			end
		elseif not CommF:InvokeServer("GuitarPuzzleProgress", "Check").Pipes then
			for g, R in pairs(Pipes) do
				local m = game.workspace.Map["Haunted Castle"]["Lab Puzzle"].ColorFloor.Model[g]
				if m.BrickColor.Name ~= R then
					repeat
						task.wait()
						fireclickdetector(m.ClickDetector)
					until m.BrickColor.Name == R
				end
			end
		end
	end
end
function DetectRequestSoulGuitar()
	local g, R, m = {}
	if not CheckCountItem("Ectoplasm", 250) then
		m, g, R =
			"TravelDressrosa",
			{ "Ship Deckhand", "Ship Steward", "Ship Officer", "Ship Engineer" },
			getgenv().CheckPlaceId2
	elseif not CheckCountItem("Bones", 500) then
		m, g, R =
			"TravelZou",
			{ "Reborn Skeleton", "Demonic Soul", "Living Zombie", "Posessed Mummy" },
			getgenv().CheckPlaceId
	end
	return g, R, m
end
function AutoSoulGuitar()
	if
		game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("soulGuitarBuy", true)
		== "[You already own this item.]"
	then
		A.CreateNoti({ Title = "Banana Cat Hub", Desc = "[You already own this item.]", ShowTime = 5 })
		task.wait(5)
		return
	end
	if t.Data.Fragments.Value < 5000 then
		A.CreateNoti({ Title = "Banana Cat Hub", Desc = "Frag >= 5k", ShowTime = 5 })
		wait(5)
		return
	end
	if CheckCountItem("Dark Fragment", 1) and (CheckCountItem("Ectoplasm", 250)) and (CheckCountItem("Bones", 500)) then
		game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("soulGuitarBuy", true)
		game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("soulGuitarBuy")
		if game.PlaceId == getgenv().CheckPlaceId then
			GuitarPuzzleProgress()
		else
			game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("TravelZou")
		end
		return
	end
	if not CheckCountItem("Dark Fragment", 1) then
		if game.PlaceId == getgenv().CheckPlaceId2 then
			if CheckNameBoss("Darkbeard") then
				local g = CheckNameBoss("Darkbeard")
				if g then
					repeat
						task.wait()
						sizepart(g)
						if Settings["Select Weapon"] == "Blox Fruit" then
							toTarget(g.HumanoidRootPart.CFrame * CFrame.new(-7, 20, 0))
						else
							toTarget(g.HumanoidRootPart.CFrame * CFrame.new(7, 20, 0))
						end
						UsedualFlock()
						ClickM1(g)
					until not IsMobAlive(g) or not Settings["Auto Soul Guitar"]
				end
			elseif
				t.Character:FindFirstChild("Fist of Darkness") or (t.Backpack:FindFirstChild("Fist of Darkness"))
			then
				if
					(
						game:GetService("Workspace").Map.DarkbeardArena.Summoner.Detection.Position
						- t.Character.HumanoidRootPart.Position
					).Magnitude <= 5
				then
					equiptool("Fist of Darkness")
					firetouchinterest(
						game.Players.LocalPlayer.Character["Fist of Darkness"].Handle,
						game:GetService("Workspace").Map.DarkbeardArena.Summoner.Detection,
						0
					)
					firetouchinterest(
						game.Players.LocalPlayer.Character["Fist of Darkness"].Handle,
						game:GetService("Workspace").Map.DarkbeardArena.Summoner.Detection,
						1
					)
					firetouchinterest(
						t.Character.HumanoidRootPart,
						game:GetService("Workspace").Map.DarkbeardArena.Summoner.Detection,
						0
					)
					firetouchinterest(
						t.Character.HumanoidRootPart,
						game:GetService("Workspace").Map.DarkbeardArena.Summoner.Detection,
						1
					)
				else
					toTarget(game:GetService("Workspace").Map.DarkbeardArena.Summoner.Detection.CFrame)
				end
			else
				local g = GetNearestChest()
				if g then
					local R
					repeat
						task.wait()
						if
							(game.Players.LocalPlayer.Character.HumanoidRootPart.Position - g.Position).Magnitude <= 5
						then
							if not R then
								R = (tick())
							elseif tick() - R >= 5 then
								Instance.new("IntValue", g).Name = "Ignored"
								wait(0.5)
							end
							game:GetService("VirtualInputManager"):SendKeyEvent(true, "Space", false, game)
							wait()
							game:GetService("VirtualInputManager"):SendKeyEvent(false, "Space", false, game)
							TweenManager.CancelCurrent()
						end
						toTarget(g.CFrame, true)
					until not g
						or not g.Parent
						or not Settings["Auto Soul Guitar"]
						or (t.Character:FindFirstChild("Fist of Darkness"))
						or (t.Backpack:FindFirstChild("Fist of Darkness"))
						or (g:GetAttribute("IsDisabled"))
						or (g:FindFirstChild("Ignored"))
						or not g:FindFirstChild("TouchInterest")
				else
					local g = PathFindChest()
					if g then
						toTarget(g.Part.CFrame)
						if
							(g.Part.Position - t.Character.HumanoidRootPart.Position).Magnitude <= 100
							or (GetNearestChest())
						then
							Instance.new("IntValue", g).Name = "Ignored"
						end
					else
						print("delete")
						for g, g in pairs(game:GetService("Workspace")._WorldOrigin.PlayerSpawns.Pirates:GetChildren()) do
							if g:FindFirstChild("Ignored") then
								g:FindFirstChild("Ignored"):Destroy()
							end
						end
					end
				end
			end
		else
			game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("TravelDressrosa")
		end
	else
		local g, R, m = DetectRequestSoulGuitar()
		if game.PlaceId == R then
			local R = DetectMob(g)
			if R then
				repeat
					task.wait()
					sizepart(R)
					BringMob(R)
					UsedualFlock()
					ClickM1(R)
					if Settings["Select Weapon"] == "Blox Fruit" then
						toTarget(R.HumanoidRootPart.CFrame * CFrame.new(-7, 20, 0))
					else
						toTarget(R.HumanoidRootPart.CFrame * CFrame.new(7, 20, 0))
					end
				until not IsMobAlive(R) or not Settings["Auto Soul Guitar"]
			elseif typeof(g) == "table" then
				if #N >= #g then
					N = {}
					return
				end
				local R = DetectPartSpawnMob(DetectNameTablePart(g))
				if R then
					table.insert(N, DetectNameTablePart(g))
					repeat
						wait()
						toTarget(R.CFrame * CFrame.new(0, 60, 0))
					until (R.Position - t.Character.HumanoidRootPart.Position).Magnitude <= 100
						or (DetectMob(g))
						or not Settings["Auto Soul Guitar"]
					wait(1)
				end
			else
				local R = DetectPartSpawnMob(g, true)
				if R then
					Instance.new("IntValue", R).Name = "Ignored"
					repeat
						wait()
						toTarget(R.CFrame * CFrame.new(0, 60, 0))
					until (R.Position - t.Character.HumanoidRootPart.Position).Magnitude <= 100
						or (DetectMob(g))
						or not Settings["Auto Soul Guitar"]
					wait(1)
				else
					DeleteIgnoredMobSpawn()
				end
			end
		else
			game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer(m)
		end
	end
end
GetItemsSection.CreateToggle(
	{ Title = "Auto Soul Guitar", Desc = nil, Default = Settings["Auto Soul Guitar"] or false },
	function(g)
		if g then
			spawn(function()
				while Settings["Auto Soul Guitar"] and (task.wait(0.1)) do
					local R, R = pcall(function()
						AutoSoulGuitar()
					end)
					if R then
						print(R)
					end
				end
			end)
		end
		SaveSettings("Auto Soul Guitar", g)
	end
)
StartGood = true
function QuestGood3()
	AllNPCS = {}
	for g, g in pairs(game:GetService("Workspace").NPCs:GetChildren()) do
		table.insert(AllNPCS, g)
	end
	for g, g in pairs(game:GetService("ReplicatedStorage").NPCs:GetChildren()) do
		table.insert(AllNPCS, g)
	end
	for g, g in pairs(AllNPCS) do
		if g.Name:match("Luxury Boat Dealer") then
			t.Character.HumanoidRootPart.CFrame = g.HumanoidRootPart.CFrame
			game:GetService("ReplicatedStorage").Remotes.CommF_
				:InvokeServer(unpack({ [1] = "CDKQuest", [2] = "BoatQuest", [3] = g }))
		end
	end
end
function QuestGood4()
	if
		(game.Players.LocalPlayer.Character.HumanoidRootPart.Position - Vector3.new(
			-5543.5327148438,
			313.80062866211,
			-2964.2585449219
		)).magnitude > 1000
	then
		toTarget(CFrame.new(-5543.5327148438, 313.80062866211, -2964.2585449219))
	else
		local g = GetPirateRaid() or (GetPirateRaid(true))
		if g then
			repeat
				task.wait()
				equiptool(NameWeapon("Sword"))
				sizepart(g)
				ClickM1(g)
				if Settings["Select Weapon"] == "Blox Fruit" then
					toTarget(g.HumanoidRootPart.CFrame * CFrame.new(-7, 20, 0))
				else
					toTarget(g.HumanoidRootPart.CFrame * CFrame.new(7, 20, 0))
				end
			until not IsMobAlive(g)
		else
			if
				(Settings["Select Method Hop CDK1"] or {})["Hop Raid Castle [ Delay 20s Hop Because check Raids Castle ]"]
			then
				A.CreateNoti({
					Title = "Banana Cat Hub",
					Desc = "Waiting 20s for check raid castle if dont have will Server",
					ShowTime = 5,
				})
				local g = tick()
				repeat
					wait()
				until GetPirateRaid() or (GetPirateRaid(true)) or tick() - g >= 20
				if not (GetPirateRaid() or (GetPirateRaid(true))) then
					SpecialHop("Raid Castle")
				end
			else
				A.CreateNoti({ Title = "Banana Cat Hub", Desc = "Waint Raid Castle", ShowTime = 5 })
			end
			wait(5)
		end
	end
end
function TourchGood5()
	return if game:GetService("Workspace").Map.HeavenlyDimension.Torch1.ProximityPrompt.Enabled
		then "1"
		else if game:GetService("Workspace").Map.HeavenlyDimension.Torch2.ProximityPrompt.Enabled
			then "2"
			else if game:GetService("Workspace").Map.HeavenlyDimension.Torch3.ProximityPrompt.Enabled
				then "3"
				else nil
end
function DetectMobCDK()
	for g, g in pairs(game.Workspace.Enemies:GetChildren()) do
		if
			g:IsA("Model")
			and (g:FindFirstChild("Humanoid"))
			and g.Humanoid.Health > 0
			and t:DistanceFromCharacter(g.HumanoidRootPart.Position) < 300
		then
			return g
		end
	end
end
function DetectMobHell()
	local g, R, m = next, game.Workspace.Enemies:GetChildren()
	for l, l in g, R, m do
		if
			l:IsA("Model")
			and (l:FindFirstChild("Humanoid"))
			and l.Humanoid.Health > 0
			and t:DistanceFromCharacter(l.HumanoidRootPart.Position) < 300
		then
			return l
		end
	end
end
function Questgood5()
	if
		(
			game:GetService("Workspace")._WorldOrigin.Locations["Heavenly Dimension"].Position
			- t.Character.HumanoidRootPart.Position
		).Magnitude < 1000
	then
		if game:GetService("Workspace").Map.HeavenlyDimension.Exit.BrickColor == BrickColor.new("Cloudy grey") then
			game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame =
				game:GetService("Workspace").Map.HeavenlyDimension.Exit.CFrame
			toTarget(game:GetService("Workspace").Map.HeavenlyDimension.Exit.CFrame)
			return
		end
		if DetectMobCDK() then
			repeat
				task.wait()
				local g = DetectMobHell()
				sizepart(g)
				equiptool(NameWeapon("Sword"))
				toTarget(g.HumanoidRootPart.CFrame * CFrame.new(7, 20, 0))
				getgenv().ClickM1(g)
			until not DetectMobCDK()
		else
			local g = TourchGood5()
			if g then
				repeat
					task.wait()
					if
						(
							t.Character.HumanoidRootPart.Position
							- game:GetService("Workspace").Map.HeavenlyDimension["Torch" .. g].Position
						).Magnitude > 5
					then
						toTarget(game:GetService("Workspace").Map.HeavenlyDimension["Torch" .. g].CFrame)
					else
						fireproximityprompt(
							game:GetService("Workspace").Map.HeavenlyDimension["Torch" .. g].ProximityPrompt,
							0
						)
						fireproximityprompt(
							game:GetService("Workspace").Map.HeavenlyDimension["Torch" .. g].ProximityPrompt,
							1
						)
					end
				until DetectMobCDK()
				t.Character.HumanoidRootPart.CFrame = t.Character.HumanoidRootPart.CFrame * CFrame.new(0, 50, 0)
			end
		end
	elseif CheckNameBoss("Cake Queen") then
		local g = CheckNameBoss("Cake Queen")
		repeat
			task.wait()
			sizepart(g)
			equiptool(NameWeapon("Sword"))
			ClickM1(g)
			if Settings["Select Weapon"] == "Blox Fruit" then
				toTarget(g.HumanoidRootPart.CFrame * CFrame.new(-7, 20, 0))
			else
				toTarget(g.HumanoidRootPart.CFrame * CFrame.new(7, 20, 0))
			end
		until not IsMobAlive(g) or not Settings["Auto CDK"]
		TweenManager.CancelCurrent()
	else
		if Settings["Select Method Hop CDK1"] and Settings["Select Method Hop CDK1"]["Find Cake Queen"] then
			A.CreateNoti({ Title = "Banana Cat Hub", Desc = 'Hop Server Find Cake Queen"', ShowTime = 5 })
			HopServer()
		else
			A.CreateNoti({ Title = "Banana Cat Hub", Desc = 'Wating Cake Queen"', ShowTime = 5 })
		end
		wait(5)
	end
end
function QuestEvil3()
	local g, R, m = next, game.workspace.Enemies:GetChildren()
	local l
	for S, S in g, R, m do
		l = if S:IsA("Model")
				and S.Name == "Marine Commodore"
				and (S:FindFirstChild("HumanoidRootPart"))
				and S.Humanoid.Health > 0
			then S
			else l
	end
	if not l then
		GetPart = DetectPartSpawnMob("Marine Commodore")
		toTarget(GetPart.CFrame * CFrame.new(0, 60, 0))
	else
		repeat
			task.wait()
			toTarget(l.HumanoidRootPart.CFrame * CFrame.new(0, 0, 3))
		until t.Character.Humanoid.Health <= 0
	end
end
function DetectMobPhaze()
	local g, R, m = next, game.workspace.Enemies:GetChildren()
	local l
	for S, S in g, R, m do
		l = if S:IsA("Model")
				and (S:FindFirstChild("HumanoidRootPart"))
				and (S:FindFirstChild("HazeESP"))
				and (S:FindFirstChild("Humanoid"))
				and S.Humanoid.Health > 0
			then S
			else l
	end
	return l
end
function checknearstpartmobspawn()
	local g, R, m = next, game:GetService("Players").LocalPlayer.QuestHaze:GetChildren()
	for l, l in g, R, m do
		if l.Value > 0 then
			return l.Name
		end
	end
end
function QuestEvil4()
	if DetectMob(checknearstpartmobspawn()) then
		local g = DetectMob(checknearstpartmobspawn())
		repeat
			task.wait()
			sizepart(g)
			BringMob(g)
			equiptool(NameWeapon("Sword"))
			ClickM1(g)
			if Settings["Select Weapon"] == "Blox Fruit" then
				toTarget(g.HumanoidRootPart.CFrame * CFrame.new(-7, 20, 0))
			else
				toTarget(g.HumanoidRootPart.CFrame * CFrame.new(7, 20, 0))
			end
		until not g or not g.Parent or g.Humanoid.Health == 0
	else
		GetPart = DetectPartSpawnMob(checknearstpartmobspawn())
		toTarget(GetPart.CFrame * CFrame.new(0, 15, 0))
	end
end
function TourchEvil5()
	return if game:GetService("Workspace").Map.HellDimension.Torch1.ProximityPrompt.Enabled
		then "1"
		else if game:GetService("Workspace").Map.HellDimension.Torch2.ProximityPrompt.Enabled
			then "2"
			else if game:GetService("Workspace").Map.HellDimension.Torch3.ProximityPrompt.Enabled then "3" else nil
end
function QuestEvil5()
	if
		(
			game:GetService("Workspace")._WorldOrigin.Locations["Hell Dimension"].Position
			- t.Character.HumanoidRootPart.Position
		).Magnitude > 1000
	then
		if not CheckNameBoss("Soul Reaper") then
			if not t.Character:FindFirstChild("Hallow Essence") and not t.Backpack:FindFirstChild("Hallow Essence") then
				local g = DetectMob(e)
				if g then
					repeat
						task.wait()
						sizepart(g)
						BringMob(g)
						equiptool(NameWeapon("Sword"))
						ClickM1(g)
						if Settings["Select Weapon"] == "Blox Fruit" then
							toTarget(g.HumanoidRootPart.CFrame * CFrame.new(-7, 20, 0))
						else
							toTarget(g.HumanoidRootPart.CFrame * CFrame.new(7, 20, 0))
						end
					until not IsMobAlive(g) or not Settings["Auto CDK"]
				elseif typeof(e) == "table" then
					if #N >= #e then
						N = {}
						return
					end
					local g = DetectPartSpawnMob(DetectNameTablePart(e))
					if g then
						table.insert(N, DetectNameTablePart(e))
						repeat
							wait()
							toTarget(g.CFrame * CFrame.new(0, 60, 0))
						until (g.Position - t.Character.HumanoidRootPart.Position).Magnitude <= 100
							or (DetectMob(e))
							or not Settings["Auto CDK"]
						wait(1)
					end
				else
					local g = DetectPartSpawnMob(e, true)
					if g then
						Instance.new("IntValue", g).Name = "Ignored"
						repeat
							wait()
							toTarget(g.CFrame * CFrame.new(0, 60, 0))
						until (g.Position - t.Character.HumanoidRootPart.Position).Magnitude <= 100
							or (DetectMob(e))
							or not Settings["Auto CDK"]
						wait(1)
					else
						DeleteIgnoredMobSpawn()
					end
				end
			elseif
				(
					t.Character.HumanoidRootPart.Position
					- game:GetService("Workspace").Map["Haunted Castle"].Summoner.Detection.Position
				).Magnitude > 8
			then
				toTarget(game:GetService("Workspace").Map["Haunted Castle"].Summoner.Detection.CFrame)
			else
				equiptool("Hallow Essence", true)
			end
		else
			local g = CheckNameBoss("Soul Reaper")
			repeat
				task.wait()
				toTarget(g.HumanoidRootPart.CFrame * CFrame.new(0, 0, 3))
			until t.Character.Humanoid.Health <= 0
				or (
						game:GetService("Workspace")._WorldOrigin.Locations["Hell Dimension"].Position
						- t.Character.HumanoidRootPart.Position
					).Magnitude
					< 1000
			TweenManager.CancelCurrent()
			g = tick()
			repeat
				task.wait()
			until tick() - g >= 5
				or (
						game:GetService("Workspace")._WorldOrigin.Locations["Hell Dimension"].Position
						- t.Character.HumanoidRootPart.Position
					).Magnitude
					< 1000
		end
	else
		if game:GetService("Workspace").Map.HellDimension.Exit.BrickColor == BrickColor.new("Olivine") then
			game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame =
				game:GetService("Workspace").Map.HellDimension.Exit.CFrame
			toTarget(game:GetService("Workspace").Map.HellDimension.Exit.CFrame)
			return
		end
		if DetectMobCDK() then
			repeat
				task.wait()
				local g = DetectMobHell()
				sizepart(g)
				toTarget(g.HumanoidRootPart.CFrame * CFrame.new(7, 20, 0))
				equiptool(NameWeapon("Sword"))
				getgenv().ClickM1(g)
			until not DetectMobCDK()
		else
			local g = TourchEvil5()
			if g then
				repeat
					task.wait()
					if
						(
							t.Character.HumanoidRootPart.Position
							- game:GetService("Workspace").Map.HellDimension["Torch" .. g].Position
						).Magnitude > 5
					then
						toTarget(game:GetService("Workspace").Map.HellDimension["Torch" .. g].CFrame)
					else
						fireproximityprompt(
							game:GetService("Workspace").Map.HellDimension["Torch" .. g].ProximityPrompt,
							0
						)
						fireproximityprompt(
							game:GetService("Workspace").Map.HellDimension["Torch" .. g].ProximityPrompt,
							1
						)
					end
				until DetectMobCDK()
				t.Character.HumanoidRootPart.CFrame = t.Character.HumanoidRootPart.CFrame * CFrame.new(0, 50, 0)
			end
		end
	end
end
function CheckMasterSword(g, R)
	local m, l, S = next, B()
	for I, I in m, l, S do
		if I.Type == "Sword" and I.Name == g and I.Mastery >= R then
			return true
		end
	end
	return false
end
function GetCDK()
	if not CheckItemInventory("Tushita") or not CheckItemInventory("Yama") then
		A.CreateNoti({ Title = "Banana Cat Hub", Desc = "Get Tushita and Yama", ShowTime = 5 })
		wait(5)
		return
	end
	if CheckItemInventory("Tushita") and (CheckItemInventory("Yama")) then
		if not CheckMasterSword("Yama", 350) or not CheckMasterSword("Tushita", 350) then
			A.CreateNoti({ Title = "Banana Cat Hub", Desc = "Mastery >= 350", ShowTime = 5 })
			wait(5)
			return
		end
		if
			not t.Character:FindFirstChild("Tushita")
			and not t.Backpack:FindFirstChild("Tushita")
			and not t.Character:FindFirstChild("Yama")
			and not t.Backpack:FindFirstChild("Yama")
		then
			game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("LoadItem", "Tushita")
			return
		end
		getgenv().Good = game.ReplicatedStorage.Remotes.CommF_:InvokeServer("CDKQuest", "Progress", "Good").Good
		getgenv().Evil = game.ReplicatedStorage.Remotes.CommF_:InvokeServer("CDKQuest", "Progress", "Good").Evil
		local g = if getgenv().Good == 4 and getgenv().Evil == 3
			then "Pedestal2"
			else if getgenv().Good == 3 and getgenv().Evil == 4 then "Pedestal1" else nil
		if g then
			if
				(game:GetService("Workspace").Map.Turtle.Cursed[g].Position - t.Character.HumanoidRootPart.Position).Magnitude
				< 10
			then
				fireproximityprompt(game:GetService("Workspace").Map.Turtle.Cursed[g].ProximityPrompt)
			else
				toTarget(game:GetService("Workspace").Map.Turtle.Cursed[g].CFrame)
			end
		end
		if t.PlayerGui.Main.Dialogue.Visible then
			game:GetService("VirtualUser"):Button1Down(Vector2.new(0, 0))
			game:GetService("VirtualUser"):Button1Down(Vector2.new(0, 0))
		end
		if getgenv().Good == 4 and getgenv().Evil == 4 then
			if
				(
					game:GetService("Workspace").Map.Turtle.Cursed.Pedestal3.Position
					- t.Character.HumanoidRootPart.Position
				).Magnitude > 10
			then
				toTarget(game:GetService("Workspace").Map.Turtle.Cursed.Pedestal3.CFrame)
			elseif game:GetService("Workspace").Map.Turtle.Cursed.PlacedGem.Transparency == 0 then
				if not game.Workspace.Enemies:FindFirstChild("Cursed Skeleton Boss") then
					toTarget(CFrame.new(-12341.66796875, 603.3455810546875, -6550.6064453125))
				else
					local g, R, m = next, game.Workspace.Enemies:GetChildren()
					for l, l in g, R, m do
						if l:IsA("Model") and l.Name == "Cursed Skeleton Boss" and l.Humanoid.Health > 0 then
							repeat
								task.wait()
								sizepart(l)
								equiptool(NameWeapon("Sword"))
								ClickM1(l)
								if Settings["Select Weapon"] == "Blox Fruit" then
									toTarget(l.HumanoidRootPart.CFrame * CFrame.new(-7, 20, 0))
								else
									toTarget(l.HumanoidRootPart.CFrame * CFrame.new(7, 20, 0))
								end
							until not l or not l.Parent or l.Humanoid.Health <= 0
						end
					end
				end
			else
				fireproximityprompt(game:GetService("Workspace").Map.Turtle.Cursed.Pedestal3.ProximityPrompt)
			end
		end
		if getgenv().Good ~= 4 and getgenv().Good ~= -2 then
			game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("CDKQuest", "StartTrial", "Good")
			if getgenv().Good == -3 then
				QuestGood3()
			elseif getgenv().Good == -4 then
				QuestGood4()
			elseif getgenv().Good == -5 then
				Questgood5()
			end
		else
			game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("CDKQuest", "StartTrial", "Evil")
			if getgenv().Evil == -3 then
				QuestEvil3()
			elseif getgenv().Evil == -4 then
				QuestEvil4()
			elseif getgenv().Evil == -5 then
				spawn(function()
					game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("Bones", "Buy", 1, 1)
				end)
				QuestEvil5()
			end
		end
	end
end
MethodHopCDk = { ["Find Cake Queen"] = false, ["Hop Raid Castle [ Delay 20s Hop Because check Raids Castle ]"] = false }
GetItemsSection.CreateDropdown(
	{
		Title = "Select Method Hop CDK",
		List = PrepareMultiSelectList(MethodHopCDk, Settings["Select Method Hop CDK1"]),
		Search = true,
		Selected = true,
		Default = Settings["Select Method Hop CDK1"] or nil,
	},
	function(g, R)
		SaveSettings("Select Method Hop CDK1", g, R)
	end
)
GetItemsSection.CreateToggle({ Title = "Auto CDK", Desc = nil, Default = Settings["Auto CDK"] or false }, function(g)
	if g then
		spawn(function()
			while Settings["Auto CDK"] and (task.wait(0.1)) do
				local R, R = pcall(function()
					GetCDK()
				end)
				if R then
					print(R)
				end
			end
		end)
	end
	SaveSettings("Auto CDK", g)
end)
function GetYama()
	if game.ReplicatedStorage.Remotes.CommF_:InvokeServer("EliteHunter", "Progress") < 30 then
		local g = DetectEliteHunter()
		if
			not string.find(game.Players.LocalPlayer.PlayerGui.Main.Quest.Container.QuestTitle.Title.Text, g.Name)
			or not game:GetService("Players").LocalPlayer.PlayerGui.Main.Quest.Visible
		then
			game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("AbandonQuest")
			game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("EliteHunter")
		else
			repeat
				task.wait()
				sizepart(g)
				if Settings["Select Weapon"] == "Blox Fruit" then
					toTarget(g.HumanoidRootPart.CFrame * CFrame.new(-7, 20, 0))
				else
					toTarget(g.HumanoidRootPart.CFrame * CFrame.new(7, 20, 0))
				end
				UsedualFlock()
				ClickM1(g)
			until not IsMobAlive(g) or not Settings["Auto Yama"]
		end
	else
		if
			not game.Workspace.Map:FindFirstChild("Waterfall")
			or not game.Workspace.Map.Waterfall:FindFirstChild("SealedKatana")
		then
			toTarget((CFrame.new(5251.900390625, 17.18115234375, 453.6025390625)))
			return
		end
		if
			(game.Workspace.Map.Waterfall.SealedKatana.WorldPivot.Position - t.Character.HumanoidRootPart.Position).Magnitude
			> 50
		then
			toTarget(game.Workspace.Map.Waterfall.SealedKatana.WorldPivot)
		elseif game.Workspace.Enemies:FindFirstChild("Ghost") then
			local g = DetectMob("Ghost")
			if g then
				repeat
					task.wait()
					sizepart(g)
					BringMob(g)
					UsedualFlock()
					ClickM1(g)
					if Settings["Select Weapon"] == "Blox Fruit" then
						toTarget(g.HumanoidRootPart.CFrame * CFrame.new(-7, 20, 0))
					else
						toTarget(g.HumanoidRootPart.CFrame * CFrame.new(7, 20, 0))
					end
				until not IsMobAlive(g) or not Settings["Auto Yama"]
			end
		else
			fireclickdetector(workspace.Map.Waterfall.SealedKatana.Hitbox.ClickDetector)
		end
	end
end
GetItemsSection.CreateToggle({ Title = "Auto Yama", Desc = nil, Default = Settings["Auto Yama"] or false }, function(g)
	if g then
		spawn(function()
			while Settings["Auto Yama"] and (task.wait(0.1)) do
				local R, R = pcall(function()
					GetYama()
				end)
				if R then
					print(R)
				end
			end
		end)
	end
	SaveSettings("Auto Yama", g)
end)
function checkTorch()
	local g, R, m, l =
		if not game:GetService("Workspace").Map.Turtle.QuestTorches.Torch1.Particles.Main.Enabled
			then "1"
			else if not game:GetService("Workspace").Map.Turtle.QuestTorches.Torch2.Particles.Main.Enabled
				then "2"
				else if not game:GetService("Workspace").Map.Turtle.QuestTorches.Torch3.Particles.Main.Enabled
					then "3"
					else if not game:GetService("Workspace").Map.Turtle.QuestTorches.Torch4.Particles.Main.Enabled
						then "4"
						else if not game:GetService("Workspace").Map.Turtle.QuestTorches.Torch5.Particles.Main.Enabled
							then "5"
							else nil,
		next,
		game:GetService("Workspace").Map.Turtle.QuestTorches:GetChildren()
	for S, S in R, m, l do
		if S:IsA("MeshPart") and (string.find(S.Name, g)) and not S.Particles.Main.Enabled then
			return S
		end
	end
end
function GetHitBoxTouch()
	local g = workspace.Map:FindFirstChild("Waterfall")
		and (game.Workspace.Map.Waterfall:FindFirstChild("IslandModel"))
		and (workspace.Map.Waterfall.IslandModel:FindFirstChild("Hitbox", true))
	if g then
		return g
	end
	local g, R, m = next, getnilinstances()
	for l, l in g, R, m do
		if l.Name == "Hitbox" then
			if (l.Position - Vector3.new(5713.53759765625, 38.38311767578125, 255.2017059326172)).Magnitude == 0 then
				return l
			end
		end
	end
end
function GetTushita()
	local g = game.ReplicatedStorage:WaitForChild("Remotes"):WaitForChild("CommF_")
	if g:InvokeServer("TushitaProgress").OpenedDoor then
		if CheckNameBoss("Longma") then
			local R = CheckNameBoss("Longma")
			if R then
				repeat
					task.wait()
					sizepart(R)
					if Settings["Select Weapon"] == "Blox Fruit" then
						toTarget(R.HumanoidRootPart.CFrame * CFrame.new(-7, 20, 0))
					else
						toTarget(R.HumanoidRootPart.CFrame * CFrame.new(7, 20, 0))
					end
					UsedualFlock()
					ClickM1(R)
				until not IsMobAlive(R) or not Settings["Auto Tushita"]
			end
		end
	else
		local R = GetHitBoxTouch()
		if not R then
			toTarget((CFrame.new(5677.541015625, 28.533447265625, 357.9483642578125)))
			return
		end
		if R:FindFirstChild("TouchInterest") then
			if not t.Character:FindFirstChild("Holy Torch") and not t.Backpack:FindFirstChild("Holy Torch") then
				toTarget(R.CFrame)
			else
				equiptool("Holy Torch")
				if checkTorch() then
					for R = 1, 5, 1 do
						g:InvokeServer("TushitaProgress", "Torch", R)
					end
					wait(2)
				end
			end
		else
			A.CreateNoti({ Title = "Banana Cat Hub", Desc = "Rip Indra Dont Spawn", ShowTime = 5 })
			wait(5)
		end
	end
end
GetItemsSection.CreateToggle(
	{ Title = "Auto Tushita", Desc = nil, Default = Settings["Auto Tushita"] or false },
	function(g)
		if g then
			spawn(function()
				while Settings["Auto Tushita"] and (task.wait()) do
					local R, R = pcall(function()
						GetTushita()
					end)
					if R then
						print(R)
					end
				end
			end)
		end
		SaveSettings("Auto Tushita", g)
	end
)
GetItemsSection.CreateToggle({ Title = "Auto TTK", Desc = nil, Default = Settings["Auto TTK"] or false }, function(g)
	if g then
		spawn(function()
			while Settings["Auto TTK"] and (task.wait(0.1)) do
				pcall(function()
					if not CheckMasterSword("Oroshi", 300) then
						if not DetectItemPlr("Oroshi") then
							game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("LoadItem", "Oroshi")
						end
					elseif not CheckMasterSword("Saishi", 300) then
						if not DetectItemPlr("Saishi") then
							game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("LoadItem", "Saishi")
						end
					elseif not CheckMasterSword("Shizu", 300) then
						if not DetectItemPlr("Shizu") then
							game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("LoadItem", "Shizu")
						end
					elseif not DetectItemPlr("True Triple Katana") then
						game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("MysteriousMan", "2")
						game:GetService("ReplicatedStorage").Remotes.CommF_
							:InvokeServer("LoadItem", "True Triple Katana")
					end
					local R = DetectMob(e)
					if R then
						repeat
							task.wait()
							sizepart(R)
							BringMob(R)
							equiptool(NameWeapon("Sword"))
							ClickM1(R)
							if Settings["Select Weapon"] == "Blox Fruit" then
								toTarget(R.HumanoidRootPart.CFrame * CFrame.new(-7, 20, 0))
							else
								toTarget(R.HumanoidRootPart.CFrame * CFrame.new(7, 20, 0))
							end
						until not IsMobAlive(R) or not Settings["Auto TTK"]
					elseif typeof(e) == "table" then
						if #N >= #e then
							N = {}
							return
						end
						local R = DetectPartSpawnMob(DetectNameTablePart(e))
						if R then
							table.insert(N, DetectNameTablePart(e))
							repeat
								wait()
								toTarget(R.CFrame * CFrame.new(0, 60, 0))
							until (R.Position - t.Character.HumanoidRootPart.Position).Magnitude <= 100
								or (DetectMob(e))
								or not Settings["Auto TTK"]
							wait(1)
						end
					else
						local R = DetectPartSpawnMob(e, true)
						if R then
							Instance.new("IntValue", R).Name = "Ignored"
							repeat
								wait()
								toTarget(R.CFrame * CFrame.new(0, 60, 0))
							until (R.Position - t.Character.HumanoidRootPart.Position).Magnitude <= 100
								or (DetectMob(e))
								or not Settings["Auto TTK"]
							wait(1)
						else
							DeleteIgnoredMobSpawn()
						end
					end
				end)
			end
		end)
	end
	SaveSettings("Auto TTK", g)
end)
function doorcup()
	local g, R, m = next, game:GetService("Workspace").Map.Desert.Burn:GetChildren()
	for l, l in g, R, m do
		if l:IsA("Part") and not l.CanCollide then
			return true
		end
	end
	return false
end
function doorsaber()
	local g, R, m = next, game:GetService("Workspace").Map.Jungle.Final:GetChildren()
	for l, l in g, R, m do
		if l:IsA("Part") and not l.CanCollide then
			return true
		end
	end
	return false
end
function doortourch()
	local g, R, m = next, game:GetService("Workspace").Map.Jungle.QuestPlates:GetChildren()
	for l, l in g, R, m do
		if l:IsA("Model") then
			if l.Button:FindFirstChild("TouchInterest") then
				return l
			end
		end
	end
end
function SaberSword()
	if t.Data.Level.Value >= 200 then
		if not doorsaber() then
			if game:GetService("Workspace").Map.Jungle.QuestPlates.Door.CanCollide then
				toTarget(doortourch().Button.CFrame)
			elseif doorcup() then
				if
					game.ReplicatedStorage.Remotes.CommF_:InvokeServer("ProQuestProgress", "RichSon") ~= 0
					and game.ReplicatedStorage.Remotes.CommF_:InvokeServer("ProQuestProgress", "RichSon") ~= 1
				then
					if not t.Character:FindFirstChild("Cup") and not t.Backpack:FindFirstChild("Cup") then
						if
							(t.Character.HumanoidRootPart.Position - CFrame.new(
								1112.46521,
								4.92147732,
								4364.55469,
								-0.743286014,
								-4.82822775E-11,
								-0.668973804,
								4.62103383E-10,
								1,
								-5.85609283E-10,
								0.668973804,
								-7.444102E-10,
								-0.743286014
							).Position).Magnitude < 5
						then
							toTarget(
								CFrame.new(
									1113.66992,
									7.5484705,
									4365.27832,
									-0.78613919,
									-2.19578524E-8,
									-0.618049502,
									1.02977182E-9,
									1,
									-3.68374984E-8,
									0.618049502,
									-2.95958493E-8,
									-0.78613919
								)
							)
							firetouchinterest(
								game:GetService("Workspace").Map.Desert.Cup,
								game.Players.LocalPlayer.Character.HumanoidRootPart,
								0
							)
							firetouchinterest(
								game:GetService("Workspace").Map.Desert.Cup,
								game.Players.LocalPlayer.Character.HumanoidRootPart,
								1
							)
							return
						end
						toTarget(
							CFrame.new(
								1112.46521,
								4.92147732,
								4364.55469,
								-0.743286014,
								-4.82822775E-11,
								-0.668973804,
								4.62103383E-10,
								1,
								-5.85609283E-10,
								0.668973804,
								-7.444102E-10,
								-0.743286014
							)
						)
					else
						equiptool("Cup")
						if
							t.Backpack:FindFirstChild("Cup")
								and (t.Backpack.Cup.Handle:FindFirstChild("TouchInterest"))
							or t.Character:FindFirstChild("Cup")
								and (t.Character.Cup.Handle:FindFirstChild("TouchInterest"))
						then
							toTarget(
								CFrame.new(
									1395.77307,
									37.4733238,
									-1324.34631,
									-0.999978602,
									-6.53588605E-9,
									0.00654155109,
									-6.57083277E-9,
									1,
									-5.32077493E-9,
									-0.00654155109,
									-5.3636442E-9,
									-0.999978602
								)
							)
						elseif
							t.Backpack:FindFirstChild("Cup")
								and not t.Backpack.Cup.Handle:FindFirstChild("TouchInterest")
							or t.Character:FindFirstChild("Cup")
								and not t.Character.Cup.Handle:FindFirstChild("TouchInterest")
						then
							if
								(t.Character.HumanoidRootPart.Position - Vector3.new(
									1457.8768310547,
									88.377502441406,
									-1390.6892089844
								)).Magnitude > 8
							then
								toTarget(CFrame.new(1457.8768310547, 88.377502441406, -1390.6892089844))
							else
								game:GetService("ReplicatedStorage").Remotes.CommF_
									:InvokeServer("ProQuestProgress", "SickMan")
							end
						end
					end
				elseif game.ReplicatedStorage.Remotes.CommF_:InvokeServer("ProQuestProgress", "RichSon") == 0 then
					local g = CheckNameBoss("Mob Leader")
					if g then
						repeat
							task.wait()
							sizepart(g)
							if Settings["Select Weapon"] == "Blox Fruit" then
								toTarget(g.HumanoidRootPart.CFrame * CFrame.new(-7, 20, 0))
							else
								toTarget(g.HumanoidRootPart.CFrame * CFrame.new(7, 20, 0))
							end
							UsedualFlock()
							ClickM1(g)
						until not IsMobAlive(g) or not Settings["Auto Saber"]
					end
				elseif game.ReplicatedStorage.Remotes.CommF_:InvokeServer("ProQuestProgress", "RichSon") == 1 then
					if not t.Character:FindFirstChild("Relic") and not t.Backpack:FindFirstChild("Relic") then
						if
							(t.Character.HumanoidRootPart.Position - CFrame.new(
								-1404.07996,
								29.8520069,
								5.26677656,
								0.888123989,
								-4.0340602E-9,
								0.459603906,
								7.5884703E-9,
								1,
								-5.8864642E-9,
								-0.459603906,
								8.71560069E-9,
								0.888123989
							)).Magnitude > 8
						then
							toTarget(
								CFrame.new(
									-1404.07996,
									29.8520069,
									5.26677656,
									0.888123989,
									-4.0340602E-9,
									0.459603906,
									7.5884703E-9,
									1,
									-5.8864642E-9,
									-0.459603906,
									8.71560069E-9,
									0.888123989
								)
							)
						else
							game.ReplicatedStorage.Remotes.CommF_:InvokeServer("ProQuestProgress", "RichSon")
						end
					else
						equiptool("Relic")
						toTarget(CFrame.new(-1405.3677978516, 29.977333068848, 4.5685839653015))
					end
				end
			elseif not t.Character:FindFirstChild("Torch") and not t.Backpack:FindFirstChild("Torch") then
				toTarget(game:GetService("Workspace").Map.Jungle.Torch.CFrame)
			else
				equiptool("Torch")
				if
					(t.Character.HumanoidRootPart.Position - CFrame.new(
						1115.23499,
						4.92147732,
						4349.36963,
						-0.670654476,
						-2.18307523E-8,
						0.74176991,
						-9.06980624E-9,
						1,
						2.1230365E-8,
						-0.74176991,
						7.51052998E-9,
						-0.670654476
					).Position).Magnitude < 5
				then
					toTarget(
						CFrame.new(
							1114.59863,
							4.92147732,
							4350.64258,
							-0.508235395,
							1.00975717E-9,
							0.861218214,
							7.77848985E-9,
							1,
							3.41788708E-9,
							-0.861218214,
							8.43606784E-9,
							-0.508235395
						)
					)
					firetouchinterest(
						game.Players.LocalPlayer.Character.Torch.Handle,
						game:GetService("Workspace").Map.Desert.Burn.Fire,
						0
					)
					firetouchinterest(
						game.Players.LocalPlayer.Character.Torch.Handle,
						game:GetService("Workspace").Map.Desert.Burn.Fire,
						1
					)
					return
				end
				toTarget(
					CFrame.new(
						1115.23499,
						4.92147732,
						4349.36963,
						-0.670654476,
						-2.18307523E-8,
						0.74176991,
						-9.06980624E-9,
						1,
						2.1230365E-8,
						-0.74176991,
						7.51052998E-9,
						-0.670654476
					)
				)
			end
		else
			local g = CheckNameBoss("Saber Expert")
			if g then
				repeat
					task.wait()
					sizepart(g)
					if Settings["Select Weapon"] == "Blox Fruit" then
						toTarget(g.HumanoidRootPart.CFrame * CFrame.new(-7, 20, 0))
					else
						toTarget(g.HumanoidRootPart.CFrame * CFrame.new(7, 20, 0))
					end
					UsedualFlock()
					ClickM1(g)
				until not IsMobAlive(g) or not Settings["Auto Saber"]
			end
		end
	end
end
GetItemsSection.CreateToggle(
	{ Title = "Auto Saber", Desc = nil, Default = Settings["Auto Saber"] or false },
	function(g)
		if g then
			spawn(function()
				while Settings["Auto Saber"] and (task.wait(0.1)) do
					pcall(function()
						SaberSword()
					end)
				end
			end)
		end
		SaveSettings("Auto Saber", g)
	end
)
function autoCraftSharkAnchor()
	if CheckItemInventory("Shark Anchor") then
		A.CreateNoti({ Title = "Banana Cat Hub", Desc = "Done Shark Anchor", ShowTime = 5 })
		wait(5)
		return
	end
	if not CheckItemInventory("Monster Magnet") then
		if
			not CheckItemInventory("Shark Tooth Necklace")
			and (CheckCountItem("Mutant Tooth", 1))
			and (CheckCountItem("Shark Tooth", 5))
		then
			game:GetService("ReplicatedStorage").Modules.Net
				:FindFirstChild("RF/Craft")
				:InvokeServer(unpack({ [1] = "Craft", [2] = "ToothNecklace", [3] = 1, [4] = {} }))
		elseif
			not CheckItemInventory("Terror Jaw")
			and (CheckCountItem("Mutant Tooth", 2))
			and (CheckCountItem("Shark Tooth", 5))
			and (CheckCountItem("Terror Eyes", 1))
			and (CheckCountItem("Fool's Gold", 10))
		then
			game:GetService("ReplicatedStorage").Modules.Net
				:FindFirstChild("RF/Craft")
				:InvokeServer(unpack({ [1] = "Craft", [2] = "TerrorJaw", [3] = 1, [4] = {} }))
		elseif
			CheckItemInventory("Shark Tooth Necklace")
			and (CheckItemInventory("Terror Jaw"))
			and (CheckCountItem("Terror Eyes", 2))
			and (CheckCountItem("Shark Tooth", 10))
			and (CheckCountItem("Electric Wing", 10))
			and (CheckCountItem("Fool's Gold", 20))
		then
			game:GetService("ReplicatedStorage").Modules.Net
				:FindFirstChild("RF/Craft")
				:InvokeServer(unpack({ [1] = "Craft", [2] = "SharkAnchor", [3] = 1, [4] = {} }))
		end
	end
end
GetItemsSection.CreateToggle(
	{ Title = "Auto Craft Item Shark Anchor", Desc = nil, Default = Settings["Auto Craft Item Shark Anchor"] or false },
	function(g)
		if g then
			spawn(function()
				while Settings["Auto Craft Item Shark Anchor"] and (wait(0.1)) do
					pcall(function()
						autoCraftSharkAnchor()
					end)
				end
			end)
		end
		SaveSettings("Auto Craft Item Shark Anchor", g)
	end
)
function AutoYorumini()
	if CheckItemInventory("Dark Dagger") then
		A.CreateNoti({ Title = "Banana Cat Hub", Desc = "u haved Yoru Mini", ShowTime = 5 })
		return
	end
	local g = CheckNameBoss("rip_indra True Form")
	if g then
		repeat
			task.wait()
			sizepart(g)
			if Settings["Select Weapon"] == "Blox Fruit" then
				toTarget(g.HumanoidRootPart.CFrame * CFrame.new(-7, 20, 0))
			else
				toTarget(g.HumanoidRootPart.CFrame * CFrame.new(7, 20, 0))
			end
			UsedualFlock()
			ClickM1(g)
		until not IsMobAlive(g) or not Settings["Auto Yoru Mini"]
	elseif not DetectItemPlr("God's Chalice") then
		elitehunter = DetectEliteHunter()
		if elitehunter then
			local g = elitehunter
			if g then
				if
					not string.find(
						game.Players.LocalPlayer.PlayerGui.Main.Quest.Container.QuestTitle.Title.Text,
						g.Name
					) or not game:GetService("Players").LocalPlayer.PlayerGui.Main.Quest.Visible
				then
					game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("AbandonQuest")
					game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("EliteHunter")
				else
					repeat
						task.wait()
						sizepart(g)
						if Settings["Select Weapon"] == "Blox Fruit" then
							toTarget(g.HumanoidRootPart.CFrame * CFrame.new(-7, 20, 0))
						else
							toTarget(g.HumanoidRootPart.CFrame * CFrame.new(7, 20, 0))
						end
						UsedualFlock()
						ClickM1(g)
					until not IsMobAlive(g) or not Settings["Auto Yoru Mini"]
				end
			end
		else
			local g = Settings["Value Collect Chest to Hop"] or 20
			if f and f >= g and Settings["Auto Yoru Mini (Hop Server)"] then
				HopServer()
				return
			end
			g = GetNearestChest()
			if g then
				f += 1
				local R
				repeat
					task.wait()
					if (game.Players.LocalPlayer.Character.HumanoidRootPart.Position - g.Position).Magnitude <= 5 then
						if not R then
							R = (tick())
						elseif tick() - R >= 5 then
							Instance.new("IntValue", g).Name = "Ignored"
							wait(0.5)
						end
						game:GetService("VirtualInputManager"):SendKeyEvent(true, "Space", false, game)
						wait()
						game:GetService("VirtualInputManager"):SendKeyEvent(false, "Space", false, game)
						TweenManager.CancelCurrent()
					end
					toTarget(g.CFrame, true)
				until not g
					or not g.Parent
					or not Settings["Auto Yoru Mini"]
					or (g:GetAttribute("IsDisabled"))
					or (g:FindFirstChild("Ignored"))
					or not g:FindFirstChild("TouchInterest")
			else
				local g = PathFindChest()
				if g then
					toTarget(g.Part.CFrame)
					if
						(g.Part.Position - t.Character.HumanoidRootPart.Position).Magnitude <= 100
						or (GetNearestChest())
					then
						Instance.new("IntValue", g).Name = "Ignored"
					end
				else
					print("delete")
					for g, g in pairs(game:GetService("Workspace")._WorldOrigin.PlayerSpawns.Pirates:GetChildren()) do
						if g:FindFirstChild("Ignored") then
							g:FindFirstChild("Ignored"):Destroy()
						end
					end
				end
			end
		end
	else
		f = Settings["Value Collect Chest to Hop"] or 20
		if not IsMisisngLegHaki() and (DetectButtons()) then
			TouchPadHaki()
		elseif not DetectButtons() then
			equiptool("God's Chalice")
			toTarget(game:GetService("Workspace").Map["Boat Castle"].Summoner.Detection.CFrame)
		end
	end
end
GetItemsSection.CreateToggle(
	{
		Title = "Auto Yoru Mini",
		Desc = "u need have 3 haki legendary,\10it will auto chest, kill Elite Hunter Find Chalice,\10Summon And Kill Rip Indra",
		Default = Settings["Auto Yoru Mini"] or false,
	},
	function(g)
		if g then
			spawn(function()
				while Settings["Auto Yoru Mini"] and (wait(0.1)) do
					pcall(function()
						AutoYorumini()
					end)
				end
			end)
		end
		SaveSettings("Auto Yoru Mini", g)
	end
)
GetItemsSection.CreateToggle(
	{
		Title = "Auto Yoru Mini (Hop Server)",
		Desc = "u can change value hop chest in Tab Farming Other",
		Default = Settings["Auto Yoru Mini"] or false,
	},
	function(g)
		SaveSettings("Auto Yoru Mini (Hop Server)", g)
	end
)
MasteryWeaponSection = GetItemsMain.CreateSection("Mastery Weapon")
BlMeleeFarmMastery = {}
TableMelees = {
	Superhuman = 1,
	["Death Step"] = 2,
	["Sharkman Karate"] = 3,
	["Electric Claw"] = 4,
	["Dragon Talon"] = 5,
	["Black Leg"] = 6,
	["Fishman Karate"] = 7,
	Electro = 8,
	["Dragon Claw"] = 9,
}
function DetectMeleeFarmMastery()
	local g, f = 1 / 0
	for R, m in next, TableMelees, nil do
		if not table.find(BlMeleeFarmMastery, R) then
			if g > m then
				g, f = m, R
			end
		end
	end
	return f
end
function CheckMasteryMelee(g)
	for f, f in pairs(game.Players.LocalPlayer.Character:GetChildren()) do
		if f:IsA("Tool") and (g and f.Name == g or not g and f.ToolTip == "Melee") then
			return f.Level.Value
		end
	end
	for f, f in pairs(game.Players.LocalPlayer.Backpack:GetChildren()) do
		if f:IsA("Tool") and (g and f.Name == g or not g and f.ToolTip == "Melee") then
			return f.Level.Value
		end
	end
end
MasteryWeaponSection.CreateToggle(
	{ Title = "Auto Farm Mastery 600 Melees", Desc = nil, Default = Settings["Auto Farm Mastery 600 Melees"] or false },
	function(g)
		if g then
			Q = true
			o:SetStage(true)
			d:SetValue("Melee")
		elseif not g and Q then
			o:SetStage(false)
			Q = false
		end
		if g then
			spawn(function()
				while Settings["Auto Farm Mastery 600 Melees"] and (task.wait()) do
					local f, f = pcall(function()
						local R = DetectMeleeFarmMastery()
						if
							not game.Players.LocalPlayer.Character:FindFirstChild(R)
							and not game.Players.LocalPlayer.Backpack:FindFirstChild(R)
						then
							if R == "Dragon Claw" then
								game.ReplicatedStorage.Remotes.CommF_:InvokeServer(
									"BlackbeardReward",
									"DragonClaw",
									"1"
								)
								game.ReplicatedStorage.Remotes.CommF_:InvokeServer(
									"BlackbeardReward",
									"DragonClaw",
									"2"
								)
								return
							end
							local m = string.gsub(R, " ", "")
							game.ReplicatedStorage.Remotes.CommF_:InvokeServer("Buy" .. m)
						elseif CheckMasteryMelee(R) >= 600 then
							table.insert(BlMeleeFarmMastery, R)
						end
					end)
					if f then
						print(f)
					end
				end
			end)
		end
		SaveSettings("Auto Farm Mastery 600 Melees", g)
	end
)
function DetectSwordUnlock()
	local g, f, R = next, B()
	local m, l = 0
	for S, S in g, f, R do
		if S.Type == "Sword" and 600 > S.Mastery then
			if m < S.Rarity then
				m, l = S.Rarity, S.Name
			end
		end
	end
	return l
end
MasteryWeaponSection.CreateToggle(
	{
		Title = "Auto Farm Mastery 600 Sword In Inventory",
		Desc = nil,
		Default = Settings["Auto Farm Mastery 600 Sword In Inventory"] or false,
	},
	function(g)
		if g then
			Q = true
			o:SetStage(true)
			d:SetValue("Sword")
		elseif not g and Q then
			o:SetStage(false)
			Q = false
		end
		if g then
			spawn(function()
				while Settings["Auto Farm Mastery 600 Sword In Inventory"] and (task.wait()) do
					pcall(function()
						local f = DetectSwordUnlock()
						if f and not t.Backpack:FindFirstChild(f) and not t.Character:FindFirstChild(f) then
							game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("LoadItem", f)
						end
					end)
				end
			end)
		end
		SaveSettings("Auto Farm Mastery 600 Sword In Inventory", g)
	end
)
UpgradeWeaponSection = GetItemsMain.CreateSection("Upgrade Weapon")
getgenv().StatusUpgradeWP = UpgradeWeaponSection.CreateLabel({ Title = "" })
function DetectGunUnlock()
	local g, f, R = next, B()
	local m, l = 0
	for Q, Q in g, f, R do
		if Q.Type == "Gun" and 600 > Q.Mastery then
			if m < Q.Rarity then
				m, l = Q.Rarity, Q.Name
			end
		end
	end
	return l
end
function DetectItemUpgrade(g)
	local f, R =
		{},
		{
			[1] = "UpgradeItem",
			[2] = "Check",
			[3] = game:GetService("Players").LocalPlayer.Backpack:FindFirstChild(NameWeapon(g))
				or (game:GetService("Players").LocalPlayer.Character:FindFirstChild(NameWeapon(g))),
		}
	for g, g in next, game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer(unpack(R)).Required, nil do
		f[g.Name] = g.Required
	end
	f.NameWp = game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer(unpack(R)).Result.Name
	f.Physical = game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer(unpack(R)).Result.Physical
	return f
end
function DetectNameWpUpgrade(g)
	local f, R, m = next, B()
	local l, Q = 0
	for S, S in f, R, m do
		if S.Type == g and S.Upgrades == 0 then
			if l < S.Rarity then
				l, Q = S.Rarity, S.Name
			else
				Q = if l == S.Rarity then S.Name else Q
			end
		end
	end
	return Q
end
local g, f
function DetectMaterialsUpgrade()
	for R, m in next, f, nil do
		if
			R ~= "NameWp"
			and R ~= "Physical"
			and not CheckCountItem(R, m)
			and R ~= "Dark Fragment"
			and NameWorldMaterials[R][game.PlaceId]
		then
			return R
		end
	end
	for R, m in next, f, nil do
		if R ~= "NameWp" and R ~= "Physical" and not CheckCountItem(R, m) then
			return R
		end
	end
end
function AutoUpgradeWeapon(R)
	if NameWeapon(R) ~= DetectNameWpUpgrade(R) then
		if getgenv().StatusUpgradeWP then
			StatusUpgradeWP.SetText("Change Weapon" .. DetectNameWpUpgrade(R))
		end
		game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("LoadItem", DetectNameWpUpgrade(R))
		return
	end
	if not f or f.NameWp ~= DetectNameWpUpgrade(R) then
		if not g then
			for m, l in pairs(game.Workspace.NPCs:GetDescendants()) do
				m = l:IsA("Model") and l.Name == "Blacksmith" and (l:FindFirstChild("Head"))
				if m then
					g = l.Head.CFrame * CFrame.new(0, -2, 2)
				end
			end
			for m, l in pairs(game:GetService("ReplicatedStorage").NPCs:GetDescendants()) do
				m = l:IsA("Model") and l.Name == "Blacksmith" and (l:FindFirstChild("Head")) and not g
				if m then
					g = l.Head.CFrame * CFrame.new(0, -2, 2)
				end
			end
		else
			if getgenv().StatusUpgradeWP then
				StatusUpgradeWP.SetText("Get info Upgrade WP")
			end
			if t:DistanceFromCharacter(g.Position) > 10 then
				toTarget(g, true)
			else
				f = DetectItemUpgrade(R)
			end
		end
		return
	end
	local m = if f then (DetectMaterialsUpgrade()) else nil
	if f and not m then
		if getgenv().StatusUpgradeWP then
			StatusUpgradeWP.SetText("Go Upgrade Weapon")
		end
		toTarget(g, true)
		if t:DistanceFromCharacter(g.Position) < 10 then
			if game:GetService("Players").LocalPlayer.PlayerGui.Main.Craft.Visible then
				wait(1)
				for g, g in
					pairs(
						getconnections(
							game:GetService("Players").LocalPlayer.PlayerGui.Main.Craft.Main.Bottom.Confirm.Activated
						)
					)
				do
					g.Function()
				end
				if not game:GetService("Players").LocalPlayer.PlayerGui.Main.Craft.Main.Bottom.Confirm.Visible then
					for g, g in
						pairs(
							getconnections(
								game:GetService("Players").LocalPlayer.PlayerGui.Main.Craft.Main.Bottom.Close.Activated
							)
						)
					do
						g.Function()
					end
				end
			else
				local g = {
					[1] = "UpgradeItem",
					[2] = "Check",
					[3] = game:GetService("Players").LocalPlayer.Backpack:FindFirstChild(NameWeapon(R))
						or (game:GetService("Players").LocalPlayer.Character:FindFirstChild(NameWeapon(R))),
				}
				local f = game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer(unpack(g))
				require(game.Players.LocalPlayer.PlayerGui.Main.UIController.Craft)(f.Required, f.Result, f.ResultStats)
				wait(1)
			end
		end
	end
	if m then
		R = NameMaterials[m]
		if not R then
			A.CreateNoti({ Title = "Banana Cat Hub", Desc = "Not Support Material" .. m .. "Sorry", ShowTime = 5 })
			wait(5)
			return
		end
		if not NameWorldMaterials[m][game.PlaceId] then
			local g = NameWorldMaterials[m][getgenv().CheckPlaceId2]
				or NameWorldMaterials[m][getgenv().CheckPlaceId3]
				or NameWorldMaterials[m][getgenv().CheckPlaceId]
			game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer(g)
			return
		end
		if getgenv().StatusUpgradeWP then
			StatusUpgradeWP.SetText("Farm Material " .. m)
		end
		local g = DetectMob(R)
		if not g then
			if typeof(R) == "table" then
				if #N >= #R then
					N = {}
					return
				end
				local f = DetectPartSpawnMob(DetectNameTablePart(R))
				if f then
					table.insert(N, DetectNameTablePart(R))
					repeat
						wait()
						toTarget(f.CFrame * CFrame.new(0, 60, 0))
					until (f.Position - t.Character.HumanoidRootPart.Position).Magnitude <= 100
						or (DetectMob(R))
						or not Settings["Auto Upgrade Sword Inventory"]
							and not Settings["Auto Upgrade Gun Inventory"]
					wait(1)
				end
			else
				local f = DetectPartSpawnMob(R, true)
				if f then
					Instance.new("IntValue", f).Name = "Ignored"
					repeat
						wait()
						toTarget(f.CFrame * CFrame.new(0, 60, 0))
					until (f.Position - t.Character.HumanoidRootPart.Position).Magnitude <= 100
						or (DetectMob(R))
						or not Settings["Auto Upgrade Sword Inventory"]
							and not Settings["Auto Upgrade Gun Inventory"]
					wait(1)
				else
					DeleteIgnoredMobSpawn()
				end
			end
		else
			repeat
				task.wait()
				sizepart(g)
				BringMob(g)
				UsedualFlock()
				ClickM1(g)
				if Settings["Select Weapon"] == "Blox Fruit" then
					toTarget(g.HumanoidRootPart.CFrame * CFrame.new(-7, 20, 0))
				else
					toTarget(g.HumanoidRootPart.CFrame * CFrame.new(7, 20, 0))
				end
			until not IsMobAlive(g)
				or not Settings["Auto Upgrade Sword Inventory"] and not Settings["Auto Upgrade Gun Inventory"]
		end
	end
end
UpgradeWeaponSection.CreateToggle(
	{ Title = "Auto Upgrade Sword Inventory", Desc = nil, Default = Settings["Auto Upgrade Sword Inventory"] or false },
	function(g)
		if g then
			spawn(function()
				while Settings["Auto Upgrade Sword Inventory"] and (task.wait(0.1)) do
					local f, f = pcall(function()
						AutoUpgradeWeapon("Sword")
					end)
					if f then
						print(f)
					end
				end
			end)
		end
		SaveSettings("Auto Upgrade Sword Inventory", g)
	end
)
UpgradeWeaponSection.CreateToggle(
	{ Title = "Auto Upgrade Gun Inventory", Desc = nil, Default = Settings["Auto Upgrade Gun Inventory"] or false },
	function(g)
		if g then
			spawn(function()
				while Settings["Auto Upgrade Gun Inventory"] and (task.wait(0.1)) do
					local f, f = pcall(function()
						AutoUpgradeWeapon("Gun")
					end)
					if f then
						print(f)
					end
				end
			end)
		end
		SaveSettings("Auto Upgrade Gun Inventory", g)
	end
)
VolcanoTab = Main.CreatePage({ Page_Name = "Volcano Event", Page_Title = "Volcano Event Tab" })
SettingsVolcanoSection = VolcanoTab.CreateSection("Settings Volcano")
SettingsVolcanoSection.CreateDropdown(
	{
		Title = "Select Weapon Kill Golem",
		List = { "Melee", "Sword", "Blox Fruit" },
		Search = true,
		Selected = false,
		Default = Settings["Select Weapon Kill Golem"] or nil,
	},
	function(g)
		SaveSettings("Select Weapon Kill Golem", g)
	end
)
SettingsVolcanoSection.CreateDropdown(
	{
		Title = "Select Weapons Fix Lava",
		List = PrepareMultiSelectList(E, Settings["Select Weapons Fix Lava"]),
		Search = true,
		Selected = true,
		Default = Settings["Select Weapons Fix Lava"] or nil,
	},
	function(g, f)
		SaveSettings("Select Weapons Fix Lava", g, f)
	end
)
SettingsVolcanoSection.CreateDropdown(
	{
		Title = "Select Method Kill Golem",
		List = { "Click M1", "Instant Kill [ Risk and can bug no die mob ]" },
		Search = true,
		Selected = false,
		Default = Settings["Select Method Kill Golem"] or nil,
	},
	function(g)
		SaveSettings("Select Method Kill Golem", g)
	end
)
FarmingVolcanoSection = VolcanoTab.CreateSection("Farming Volcano")
function AutoCraftinMagnetVol()
	if not CheckItemInventory("Volcanic Magnet") then
		if not CheckCountItem("Scrap Metal", 10) then
			local g = { "Jungle Pirate" }
			local f = DetectMob(g)
			if not f then
				if typeof(g) == "table" then
					if #N >= #g then
						N = {}
						return
					end
					local R = DetectPartSpawnMob(DetectNameTablePart(g))
					if R then
						table.insert(N, DetectNameTablePart(g))
						repeat
							wait()
							toTarget(R.CFrame * CFrame.new(0, 60, 0))
						until (R.Position - t.Character.HumanoidRootPart.Position).Magnitude <= 100
							or (DetectMob(g))
							or not Settings["Auto Crafting Volcanic Magnet"]
						wait(1)
					end
				end
			else
				repeat
					task.wait()
					sizepart(f)
					BringMob(f)
					UsedualFlock()
					ClickM1(f)
					if Settings["Select Weapon"] == "Blox Fruit" then
						toTarget(f.HumanoidRootPart.CFrame * CFrame.new(-7, 20, 0))
					else
						toTarget(f.HumanoidRootPart.CFrame * CFrame.new(7, 20, 0))
					end
				until not IsMobAlive(f) or not Settings["Auto Crafting Volcanic Magnet"]
			end
			return
		elseif not CheckCountItem("Blaze Ember", 15) then
			local g = workspace.NPCs:FindFirstChild("Dragon Hunter")
				or (game:GetService("ReplicatedStorage").NPCs:FindFirstChild("Dragon Hunter"))
				or NPCManager.getNPCsByName("Dragon Hunter")[1]._modelState._instance
			if not getgenv().QuestHunterDragon then
				if t:DistanceFromCharacter(g.HumanoidRootPart.Position) > 8 then
					toTarget(g.HumanoidRootPart.CFrame * CFrame.new(0, 4, 4))
				else
					local g = game:GetService("ReplicatedStorage")
						:WaitForChild("Modules")
						:WaitForChild("Net")
						:WaitForChild("RF/DragonHunter")
						:InvokeServer(unpack({ [1] = { Context = "Check" } }))
					if not g or g and not g.Text then
						getgenv().QuestHunterDragon = game:GetService("ReplicatedStorage")
							:WaitForChild("Modules")
							:WaitForChild("Net")
							:WaitForChild("RF/DragonHunter")
							:InvokeServer(unpack({ [1] = { Context = "RequestQuest" } })).Text
					else
						getgenv().QuestHunterDragon = g.Text
					end
				end
			else
				local g = DetectEmberTemplate()
				if g then
					Instance.new("IntValue", g).Name = "Ignored"
					repeat
						wait()
						toTarget(g.Part.CFrame)
					until not g or not g.Parent
					return
				end
				if string.find(getgenv().QuestHunterDragon, "Hydra Enforcers") then
					local f = DetectMob("Hydra Enforcer")
					if not f then
						local R = DetectPartSpawnMob("Hydra Enforcer", true)
						if R then
							Instance.new("IntValue", R).Name = "Ignored"
							repeat
								wait()
								toTarget(R.CFrame * CFrame.new(0, 60, 0))
							until (R.Position - t.Character.HumanoidRootPart.Position).Magnitude <= 100
								or (DetectMob("Hydra Enforcer"))
								or not Settings["Auto Quest Dragon Hunter"]
								or g
							wait(1)
						else
							DeleteIgnoredMobSpawn()
						end
					else
						repeat
							task.wait()
							sizepart(f)
							BringMob(f)
							UsedualFlock()
							ClickM1(f)
							if Settings["Select Weapon"] == "Blox Fruit" then
								toTarget(f.HumanoidRootPart.CFrame * CFrame.new(-7, 20, 0))
							else
								toTarget(f.HumanoidRootPart.CFrame * CFrame.new(7, 20, 0))
							end
						until not IsMobAlive(f) or not Settings["Auto Crafting Volcanic Magnet"] or g
					end
				elseif string.find(getgenv().QuestHunterDragon, "Venomous Assailants") then
					local f = DetectMob("Venomous Assailant")
					if not f then
						local R = DetectPartSpawnMob("Venomous Assailant", true)
						if R then
							Instance.new("IntValue", R).Name = "Ignored"
							repeat
								wait()
								toTarget(R.CFrame * CFrame.new(0, 60, 0))
							until (R.Position - t.Character.HumanoidRootPart.Position).Magnitude <= 100
								or (DetectMob("Venomous Assailant"))
								or not Settings["Auto Crafting Volcanic Magnet"]
								or g
							wait(1)
						else
							DeleteIgnoredMobSpawn()
						end
					else
						repeat
							task.wait()
							sizepart(f)
							BringMob(f)
							UsedualFlock()
							ClickM1(f)
							if Settings["Select Weapon"] == "Blox Fruit" then
								toTarget(f.HumanoidRootPart.CFrame * CFrame.new(-7, 20, 0))
							else
								toTarget(f.HumanoidRootPart.CFrame * CFrame.new(7, 20, 0))
							end
						until not IsMobAlive(f) or not Settings["Auto Crafting Volcanic Magnet"] or g
					end
				elseif string.find(getgenv().QuestHunterDragon, "trees") then
					local f, R = DetectTree(), workspace.CurrentCamera
					if f then
						Instance.new("IntValue", f).Name = "Ignored"
						local m = tick()
						repeat
							wait()
							local E = f.WorldPivot.Position
							if t:DistanceFromCharacter(E) < 50 then
								AutoAllSkill()
							end
							if f:FindFirstChild("Meshes/plant1_Icosphere", true) then
								toTarget(f.WorldPivot)
								getgenv().AimPos = f.WorldPivot
								G.Hit = CFrame.new(R.CFrame.Position, E)
								G.Target = f
							else
								local E, l =
									(f.WorldPivot * CFrame.new(5, -20, 0)).Position,
									(f.WorldPivot * CFrame.new(0, -20, 0)).Position
								toTarget(CFrame.new(E))
								getgenv().AimPos = CFrame.new(l)
								G.Hit = CFrame.new(R.CFrame.Position, l)
								G.Target = f
							end
						until not f
							or not f.Parent
							or not Settings["Auto Crafting Volcanic Magnet"]
							or g
							or (f:GetAttribute("AlreadyDestroyedClient"))
							or tick() - m >= 15
					end
				end
			end
			return
		end
		if CheckCountItem("Scrap Metal", 10) and (CheckCountItem("Blaze Ember", 15)) then
			game:GetService("ReplicatedStorage").Modules.Net
				:FindFirstChild("RF/Craft")
				:InvokeServer(unpack({ [1] = "Craft", [2] = "Volcanic Magnet", [3] = 1, [4] = {} }))
			wait(2)
		end
	else
		A.CreateNoti({ Title = "Banana Cat Hub", Desc = "Done Craft Volcanic Magnet", ShowTime = 5 })
		ToggleAutoCraftingVolcanicMagnet:SetStage(false)
	end
end
ToggleAutoCraftingVolcanicMagnet = FarmingVolcanoSection.CreateToggle(
	{ Title = "Auto Crafting Volcanic Magnet", Desc = nil, Default = Settings["Auto Crafting Volcanic Magnet"] or false },
	function(g)
		if g then
			spawn(function()
				while Settings["Auto Crafting Volcanic Magnet"] and (wait(0.1)) do
					pcall(function()
						AutoCraftinMagnetVol()
					end)
				end
			end)
		end
		SaveSettings("Auto Crafting Volcanic Magnet", g)
	end
)
function AutoFindPrehistoric()
	if
		not game:GetService("Workspace").Map:FindFirstChild("PrehistoricIsland")
		and not game:GetService("Players").LocalPlayer.PlayerGui.Main.TopHUDList.PrehistoricRaidTimer.Visible
		and not game:GetService("Players").LocalPlayer.PlayerGui.Main.TopHUDList.RaidTimer.Visible
	then
		getgenv().RespawnVolcano = true
		local g = checkboat()
		if not g or g and t:DistanceFromCharacter(g.VehicleSeat.Position) >= 4000 then
			local f = CFrame.new(-16204.0810546875, 9.0863618850708, 479.2259521484375)
			if (f.Position - t.Character.HumanoidRootPart.Position).Magnitude > 8 then
				if (f.Position - t.Character.HumanoidRootPart.Position).Magnitude > 1000 then
					if game:GetService("Players").LocalPlayer.Data.LastSpawnPoint.Value == "Tiki" then
						t.Character.Humanoid.Health = 0
						return
					end
				end
				toTarget(f)
			else
				game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("BuyBoat", "PirateBrigade")
				wait(3)
			end
		elseif t.Character.Humanoid.Sit then
			local f, R, m =
				CFrame.new(-118834.515625, 160, -78.9505844116211) * CFrame.new(0, 0, 99999999),
				CFrame.new(-32975.9921875, 160, 25963.7109375),
				if Settings["Will Back When over 10km"]
					then if DistanceFindLeviathan() >= 12000
						then true
						else if DistanceFindLeviathan() <= 4800 then false else false
					else false
			repeat
				task.wait(0.5)
				NoclipBoat(g)
				if Settings["Will Back When over 10km"] then
					m = if DistanceFindLeviathan() >= 10000
						then true
						else if DistanceFindLeviathan() <= 4800 then false else m
					if m then
						manageTween(g.VehicleSeat, R, 350, "TweenBoatBack")
					end
				end
				if not m or not Settings["Will Back When over 10km"] then
					manageTween(g.VehicleSeat, f, 350, "TweenBoat")
				end
			until not Settings["Auto Find Prehistoric Island"]
				or not t.Character.Humanoid.Sit
				or (game:GetService("Workspace").Map:FindFirstChild("PrehistoricIsland"))
			if getgenv().TweenBoat then
				getgenv().TweenBoat:Pause()
				getgenv().TweenBoat:Cancel()
			end
			if getgenv().TweenBoatBack then
				getgenv().TweenBoatBack:Pause()
				getgenv().TweenBoatBack:Cancel()
			end
		else
			if getgenv().TweenBoat then
				getgenv().TweenBoat:Pause()
				getgenv().TweenBoat:Cancel()
			end
			if getgenv().TweenBoatBack then
				getgenv().TweenBoatBack:Pause()
				getgenv().TweenBoatBack:Cancel()
			end
			toTarget(g.VehicleSeat.CFrame)
		end
	else
		if getgenv().RespawnVolcano and Settings["Webhook Find Prehistoric Island"] then
			getgenv().RespawnVolcano = false
			WebhookFindVolcano()
		end
		if getgenv().TweenBoat then
			getgenv().TweenBoat:Pause()
			getgenv().TweenBoat:Cancel()
		end
		A.CreateNoti({ Title = "Banana Cat Hub", Desc = "Prehistoric Island Spawned", ShowTime = 5 })
		ToggleAutoFindPrehistoricIsland:SetStage(false)
		wait(5)
	end
end
ToggleAutoFindPrehistoricIsland = FarmingVolcanoSection.CreateToggle(
	{ Title = "Auto Find Prehistoric Island", Desc = nil, Default = Settings["Auto Find Prehistoric Island"] or false },
	function(g)
		if g then
			spawn(function()
				while Settings["Auto Find Prehistoric Island"] and (wait(0.1)) do
					pcall(function()
						AutoFindPrehistoric()
					end)
				end
			end)
		end
		SaveSettings("Auto Find Prehistoric Island", g)
	end
)
function AutoAttackVolcano()
	if game:GetService("Workspace").Map:FindFirstChild("PrehistoricIsland") then
		if not t:GetAttribute("CurrentLocation") or t:GetAttribute("CurrentLocation") ~= "Prehistoric Island" then
			local g = DetectNpc("Fossil Expert")
			if g then
				toTarget(g.HumanoidRootPart.CFrame)
				return
			end
		end
		if DetectLava() then
			local g, f, R = next, workspace.Map.PrehistoricIsland:GetDescendants()
			for m, m in g, f, R do
				if m.Name == "TouchInterest" and m.Parent.Name ~= "TrialTeleport" then
					m:Destroy()
				end
			end
		end
		if #workspace.Map.PrehistoricIsland.Core.InteriorLava:GetChildren() > 0 then
			DeleteLava()
		end
		if
			not game:GetService("Players").LocalPlayer.PlayerGui.Main.TopHUDList.PrehistoricRaidTimer.Visible
			and not game:GetService("Players").LocalPlayer.PlayerGui.Main.TopHUDList.RaidTimer.Visible
		then
			if
				workspace.Map.PrehistoricIsland.Core:FindFirstChild("ActivationPrompt")
				and (workspace.Map.PrehistoricIsland.Core.ActivationPrompt:FindFirstChild("ProximityPrompt"))
			then
				toTarget(workspace.Map.PrehistoricIsland.Core.ActivationPrompt.CFrame)
				if t:DistanceFromCharacter(workspace.Map.PrehistoricIsland.Core.ActivationPrompt.Position) < 8 then
					fireproximityprompt(workspace.Map.PrehistoricIsland.Core.ActivationPrompt.ProximityPrompt, 1)
					wait(3)
				end
				return
			elseif
				not workspace.Map.PrehistoricIsland.Core:FindFirstChild("ActivationPrompt")
				and not workspace.Map.PrehistoricIsland.Core:FindFirstChild("FossilExpertSpawn")
			then
				local g = DetectNpc("Fossil Expert")
				if g then
					toTarget(g.HumanoidRootPart.CFrame)
					return
				end
			end
		else
			if b then
				local g = workspace.Map.PrehistoricIsland.Core.PrehistoricRelic.Skull
				repeat
					task.wait()
					toTarget(g.CFrame)
				until t:DistanceFromCharacter(g.Position) <= 200 or (DetectGolem()) or (DetectRockVolcano())
				b = false
				return
			end
			local g = DetectGolem()
			if g then
				repeat
					task.wait()
					toTarget(g.HumanoidRootPart.CFrame * CFrame.new(0, 20, 7))
					if Settings["Select Method Kill Golem"] == "Instant Kill [ Risk and can bug no die mob ]" then
						if t:DistanceFromCharacter(g.HumanoidRootPart.Position) < 50 then
							KillRaidEnemy()
						end
					else
						equiptool(NameWeapon(Settings["Select Weapon Kill Golem"] or "Melee"))
						getgenv().ClickM1Volcano(g)
					end
					if not getgenv().KillMobRaid and Settings["Kill Aura Only Raid And Volcano"] then
						getgenv().KillMobRaid = true
						local f = Settings["Time Delay Kill"] or 5
						g.Humanoid:ChangeState(Enum.HumanoidStateType.Dead)
						delay(f, function()
							getgenv().KillMobRaid = false
						end)
					end
				until not IsMobAlive(g) or not Settings["Auto Event Prehistoric Island"]
			end
			g = DetectRockVolcano()
			if g then
				if Settings["Fix Volcano Safe"] then
					local f = DetectPositionVolcano()
					local R, R = CheckPosnearRock(f, t.Character.HumanoidRootPart)
					if t:DistanceFromCharacter((CheckPosnearRock(f, g.WorldPivot))) >= 400 then
						s = R + 1
						if R >= 7 then
							s = 1
						end
						local R = f[s]
						toTarget(CFrame.new(R))
					else
						local f = X[math.floor(g.WorldPivot.Position.Y)]
						repeat
							task.wait()
							if t:DistanceFromCharacter((g.WorldPivot * f).Position) > 8 then
								toTarget(g.WorldPivot * f)
							end
							if t:DistanceFromCharacter(g.WorldPivot.Position) < 100 then
								AutoUseSkillFixLava()
							end
							getgenv().AimPos = g.WorldPivot
							local R = workspace.CurrentCamera
							G.Hit = g.WorldPivot
							G.Target = g
						until not g
							or not g.Parent
							or not Settings["Auto Event Prehistoric Island"]
							or not g.VFXLayer.Specs.Enabled
							or (DetectGolem())
						f = DetectGolem()
						if not f then
							b = true
						end
						wait(1)
					end
				else
					local f = X[math.floor(g.WorldPivot.Position.Y)]
					repeat
						task.wait()
						if t:DistanceFromCharacter((g.WorldPivot * f).Position) > 8 then
							toTarget(g.WorldPivot * f)
						end
						if t:DistanceFromCharacter(g.WorldPivot.Position) < 100 then
							AutoUseSkillFixLava()
						end
						getgenv().AimPos = g.WorldPivot
						local R = workspace.CurrentCamera
						G.Hit = g.WorldPivot
						G.Target = g
					until not g
						or not g.Parent
						or not Settings["Auto Event Prehistoric Island"]
						or not g.VFXLayer.Specs.Enabled
						or (DetectGolem())
					f = DetectGolem()
					if not f then
						b = true
					end
				end
			end
		end
	end
end
FarmingVolcanoSection.CreateToggle(
	{
		Title = "Auto Event Prehistoric Island",
		Desc = "auto Start Event and Auto kill golem, Auto Fix Volcano",
		Default = Settings["Auto Event Prehistoric Island"] or false,
	},
	function(g)
		if g then
			spawn(function()
				while Settings["Auto Event Prehistoric Island"] and (wait(0.1)) do
					local f, f = pcall(function()
						AutoAttackVolcano()
					end)
					if f then
						print(f)
					end
				end
			end)
		end
		SaveSettings("Auto Event Prehistoric Island", g)
	end
)
function DetectBone()
	for g, g in game.workspace:GetChildren() do
		if g.Name == "DinoBone" then
			return g
		end
	end
end
FarmingVolcanoSection.CreateToggle(
	{ Title = "Auto Collect Bone", Desc = nil, Default = Settings["Auto Collect Bone"] or false },
	function(g)
		if g then
			spawn(function()
				while Settings["Auto Collect Bone"] and (wait()) do
					pcall(function()
						local f = DetectBone()
						if
							f
							and not game:GetService("Players").LocalPlayer.PlayerGui.Main.TopHUDList.PrehistoricRaidTimer.Visible
							and not game:GetService("Players").LocalPlayer.PlayerGui.Main.TopHUDList.RaidTimer.Visible
						then
							toTarget(f.CFrame)
						end
					end)
				end
			end)
		end
		SaveSettings("Auto Collect Bone", g)
	end
)
function DetectDragonEggs()
	if #workspace.Map.PrehistoricIsland.Core.SpawnedDragonEggs:GetChildren() > 0 then
		for g, g in workspace.Map.PrehistoricIsland.Core.SpawnedDragonEggs:GetChildren() do
			if
				g.Name == "DragonEgg"
				and (g:FindFirstChild("Molten"))
				and (g.Molten:FindFirstChild("ProximityPrompt"))
			then
				return g
			end
		end
	end
end
FarmingVolcanoSection.CreateToggle(
	{ Title = "Auto Collect Egg", Desc = nil, Default = Settings["Auto Collect Egg"] or false },
	function(g)
		if g then
			spawn(function()
				while Settings["Auto Collect Egg"] and (wait()) do
					pcall(function()
						local f = DetectDragonEggs()
						if f then
							if DetectBone() and Settings["Auto Collect Bone"] then
								return
							end
							toTarget(f.Molten.CFrame)
							if t:DistanceFromCharacter(f.Molten.Position) < 8 then
								fireproximityprompt(f.Molten.ProximityPrompt)
							end
						end
					end)
				end
			end)
		end
		SaveSettings("Auto Collect Egg", g)
	end
)
function FullyEventVolcano()
	if not game:GetService("Workspace").Map:FindFirstChild("PrehistoricIsland") then
		getgenv().RespawnVolcano = true
		getgenv().turnoffnoclipBoatt = true
		if not CheckItemInventory("Volcanic Magnet") and not Settings["Ignore Craft Volcanic Magnet"] then
			if getgenv().dacoMagnet then
				local g = tick()
				repeat
					wait()
				until tick() - g >= 5 or (game:GetService("Workspace").Map:FindFirstChild("PrehistoricIsland"))
				getgenv().dacoMagnet = false
				return
			end
			if not CheckCountItem("Scrap Metal", 10) then
				local g = { "Jungle Pirate", "Musketeer Pirate" }
				local f = DetectMob(g)
				if not f then
					if typeof(g) == "table" then
						if #N >= #g then
							N = {}
							return
						end
						local R = DetectPartSpawnMob(DetectNameTablePart(g))
						if R then
							table.insert(N, DetectNameTablePart(g))
							repeat
								wait()
								toTarget(R.CFrame * CFrame.new(0, 60, 0))
							until (R.Position - t.Character.HumanoidRootPart.Position).Magnitude <= 100
								or (DetectMob(g))
								or not Settings["Fully Event Prehistoric Island"]
							wait(1)
						end
					end
				else
					repeat
						task.wait()
						sizepart(f)
						BringMob(f)
						UsedualFlock()
						ClickM1(f)
						toTarget(f.HumanoidRootPart.CFrame * CFrame.new(7, 20, 0))
					until not IsMobAlive(f) or not Settings["Fully Event Prehistoric Island"]
				end
				return
			elseif not CheckCountItem("Blaze Ember", 15) then
				local g = workspace.NPCs:FindFirstChild("Dragon Hunter")
					or (game:GetService("ReplicatedStorage").NPCs:FindFirstChild("Dragon Hunter"))
					or NPCManager.getNPCsByName("Dragon Hunter")[1]._modelState._instance
				if not getgenv().QuestHunterDragon then
					if t:DistanceFromCharacter(g.HumanoidRootPart.Position) > 8 then
						toTarget(g.HumanoidRootPart.CFrame * CFrame.new(0, 4, 4))
					else
						local g = game:GetService("ReplicatedStorage")
							:WaitForChild("Modules")
							:WaitForChild("Net")
							:WaitForChild("RF/DragonHunter")
							:InvokeServer(unpack({ [1] = { Context = "Check" } }))
						if not g or g and not g.Text then
							getgenv().QuestHunterDragon = game:GetService("ReplicatedStorage")
								:WaitForChild("Modules")
								:WaitForChild("Net")
								:WaitForChild("RF/DragonHunter")
								:InvokeServer(unpack({ [1] = { Context = "RequestQuest" } })).Text
						else
							getgenv().QuestHunterDragon = g.Text
						end
					end
				else
					local g = DetectEmberTemplate()
					if g then
						Instance.new("IntValue", g).Name = "Ignored"
						repeat
							wait()
							toTarget(g.Part.CFrame)
						until not g or not g.Parent
						return
					end
					if string.find(getgenv().QuestHunterDragon, "Hydra Enforcers") then
						local f = DetectMob("Hydra Enforcer")
						if not f then
							local R = DetectPartSpawnMob("Hydra Enforcer", true)
							if R then
								Instance.new("IntValue", R).Name = "Ignored"
								repeat
									wait()
									toTarget(R.CFrame * CFrame.new(0, 60, 0))
								until (R.Position - t.Character.HumanoidRootPart.Position).Magnitude <= 100
									or (DetectMob("Hydra Enforcer"))
									or not Settings["Fully Event Prehistoric Island"]
									or g
								wait(1)
							else
								DeleteIgnoredMobSpawn()
							end
						else
							repeat
								task.wait()
								sizepart(f)
								BringMob(f)
								UsedualFlock()
								ClickM1(f)
								if Settings["Select Weapon"] == "Blox Fruit" then
									toTarget(f.HumanoidRootPart.CFrame * CFrame.new(-7, 20, 0))
								else
									toTarget(f.HumanoidRootPart.CFrame * CFrame.new(7, 20, 0))
								end
							until not IsMobAlive(f) or not Settings["Fully Event Prehistoric Island"] or g
						end
					elseif string.find(getgenv().QuestHunterDragon, "Venomous Assailants") then
						local f = DetectMob("Venomous Assailant")
						if not f then
							local R = DetectPartSpawnMob("Venomous Assailant", true)
							if R then
								Instance.new("IntValue", R).Name = "Ignored"
								repeat
									wait()
									toTarget(R.CFrame * CFrame.new(0, 60, 0))
								until (R.Position - t.Character.HumanoidRootPart.Position).Magnitude <= 100
									or (DetectMob("Venomous Assailant"))
									or not Settings["Fully Event Prehistoric Island"]
									or g
								wait(1)
							else
								DeleteIgnoredMobSpawn()
							end
						else
							repeat
								task.wait()
								sizepart(f)
								BringMob(f)
								UsedualFlock()
								ClickM1(f)
								toTarget(f.HumanoidRootPart.CFrame * CFrame.new(7, 20, 0))
							until not IsMobAlive(f) or not Settings["Fully Event Prehistoric Island"] or g
						end
					elseif string.find(getgenv().QuestHunterDragon, "trees") then
						local f, R = workspace.CurrentCamera, DetectTree()
						if R then
							Instance.new("IntValue", R).Name = "Ignored"
							local m = tick()
							repeat
								wait()
								local E = R.WorldPivot.Position
								if t:DistanceFromCharacter(E) < 50 then
									AutoAllSkill()
								end
								if R:FindFirstChild("Meshes/plant1_Icosphere", true) then
									toTarget(R.WorldPivot)
									getgenv().AimPos = R.WorldPivot
									G.Hit = CFrame.new(f.CFrame.Position, E)
									G.Target = R
								else
									local E, l =
										(R.WorldPivot * CFrame.new(5, -20, 0)).Position,
										(R.WorldPivot * CFrame.new(0, -20, 0)).Position
									toTarget(CFrame.new(E))
									getgenv().AimPos = CFrame.new(l)
									G.Hit = CFrame.new(f.CFrame.Position, l)
									G.Target = R
								end
							until not R
								or not R.Parent
								or not Settings["Fully Event Prehistoric Island"]
								or g
								or (R:GetAttribute("AlreadyDestroyedClient"))
								or tick() - m >= 15
						end
					end
				end
				return
			end
			if CheckCountItem("Scrap Metal", 10) and (CheckCountItem("Blaze Ember", 15)) then
				game:GetService("ReplicatedStorage").Modules.Net
					:FindFirstChild("RF/Craft")
					:InvokeServer(unpack({ [1] = "Craft", [2] = "Volcanic Magnet", [3] = 1, [4] = {} }))
				wait(2)
			end
		else
			getgenv().dacoMagnet = true
			if
				not game:GetService("Workspace").Map:FindFirstChild("PrehistoricIsland")
				and not game:GetService("Players").LocalPlayer.PlayerGui.Main.TopHUDList.PrehistoricRaidTimer.Visible
				and not game:GetService("Players").LocalPlayer.PlayerGui.Main.TopHUDList.RaidTimer.Visible
			then
				local g = checkboat()
				if not g or g and t:DistanceFromCharacter(g.VehicleSeat.Position) >= 4000 then
					local f = CFrame.new(-16204.0810546875, 9.0863618850708, 479.2259521484375)
					if (f.Position - t.Character.HumanoidRootPart.Position).Magnitude > 8 then
						if (f.Position - t.Character.HumanoidRootPart.Position).Magnitude > 1000 then
							if
								not t:GetAttribute("CurrentLocation")
								or t:GetAttribute("CurrentLocation") ~= "Tiki Outpost"
							then
								if
									game:GetService("Players").LocalPlayer.Data.LastSpawnPoint.Value == "Tiki"
									or game:GetService("Players").LocalPlayer.Data.LastSpawnPoint.Value == "Tiki2"
								then
									t.Character.Humanoid.Health = 0
									return
								end
							end
						end
						toTarget(f)
					else
						game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("BuyBoat", "PirateBrigade")
						wait(3)
					end
				elseif t.Character.Humanoid.Sit then
					task.spawn(function()
						NoclipBoat(g)
					end)
					local f = CFrame.new(-118834.515625, g.WorldPivot.Y, -78.9505844116211) * CFrame.new(0, 0, 99999999)
					manageTween(g.VehicleSeat, f, 350, "TweenBoat")
				else
					if getgenv().TweenBoat then
						getgenv().TweenBoat:Pause()
						getgenv().TweenBoat:Cancel()
					end
					toTarget(g.VehicleSeat.CFrame)
				end
			end
		end
	else
		if getgenv().turnoffnoclipBoatt then
			getgenv().turnoffnoclipBoatt = false
			local g = checkboat()
			if g then
				TurnOffNoclipBoat(g)
			end
		end
		if getgenv().RespawnVolcano and Settings["Webhook Find Prehistoric Island"] then
			getgenv().RespawnVolcano = false
			WebhookFindVolcano()
		end
		if getgenv().TweenBoat then
			getgenv().TweenBoat:Pause()
			getgenv().TweenBoat:Cancel()
		end
		if not t:GetAttribute("CurrentLocation") or t:GetAttribute("CurrentLocation") ~= "Prehistoric Island" then
			local g = DetectNpc("Fossil Expert")
			if g then
				toTarget(g.HumanoidRootPart.CFrame)
				return
			end
		end
		local g = DetectDragonEggs()
		if g then
			toTarget(g.Molten.CFrame)
			if t:DistanceFromCharacter(g.Molten.Position) < 8 then
				fireproximityprompt(g.Molten.ProximityPrompt)
			end
			return
		end
		if not Settings["Ignore Collect Bone"] then
			g = DetectBone()
			if
				g
				and not game:GetService("Players").LocalPlayer.PlayerGui.Main.TopHUDList.PrehistoricRaidTimer.Visible
				and not game:GetService("Players").LocalPlayer.PlayerGui.Main.TopHUDList.RaidTimer.Visible
			then
				toTarget(g.CFrame)
				return
			end
		end
		if
			t:GetAttribute("CurrentLocation") == "Prehistoric Island"
			and not game:GetService("Players").LocalPlayer.PlayerGui.Main.TopHUDList.PrehistoricRaidTimer.Visible
			and not game:GetService("Players").LocalPlayer.PlayerGui.Main.TopHUDList.RaidTimer.Visible
			and getgenv().CanReset
		then
			g = tick()
			repeat
				wait()
			until tick() - g >= 10
				or not Settings["Fully Event Prehistoric Island"]
				or DetectBone() and not Settings["Ignore Collect Bone"]
				or (DetectDragonEggs())
			if
				Settings["Fully Event Prehistoric Island"]
				and not DetectDragonEggs()
				and (not DetectBone() and not Settings["Ignore Collect Bone"] or Settings["Ignore Collect Bone"])
			then
				t.Character.Humanoid.Health = 0
				getgenv().CanReset = false
			end
		end
		if DetectLava() then
			local f, R, m = next, workspace.Map.PrehistoricIsland:GetDescendants()
			for E, E in f, R, m do
				if E.Name == "TouchInterest" and E.Parent.Name ~= "TrialTeleport" then
					E:Destroy()
				end
			end
		end
		if #workspace.Map.PrehistoricIsland.Core.InteriorLava:GetChildren() > 0 then
			DeleteLava()
		end
		if
			not game:GetService("Players").LocalPlayer.PlayerGui.Main.TopHUDList.PrehistoricRaidTimer.Visible
			and not game:GetService("Players").LocalPlayer.PlayerGui.Main.TopHUDList.RaidTimer.Visible
		then
			if
				workspace.Map.PrehistoricIsland.Core:FindFirstChild("ActivationPrompt")
				and (workspace.Map.PrehistoricIsland.Core.ActivationPrompt:FindFirstChild("ProximityPrompt"))
			then
				toTarget(workspace.Map.PrehistoricIsland.Core.ActivationPrompt.CFrame)
				if t:DistanceFromCharacter(workspace.Map.PrehistoricIsland.Core.ActivationPrompt.Position) < 8 then
					fireproximityprompt(workspace.Map.PrehistoricIsland.Core.ActivationPrompt.ProximityPrompt, 1)
					wait(3)
				end
				return
			elseif
				not workspace.Map.PrehistoricIsland.Core:FindFirstChild("ActivationPrompt")
				and not workspace.Map.PrehistoricIsland.Core:FindFirstChild("FossilExpertSpawn")
			then
				g = DetectNpc("Fossil Expert")
				if g then
					toTarget(g.HumanoidRootPart.CFrame)
					return
				end
			end
		else
			getgenv().CanReset = true
			if b then
				local g = workspace.Map.PrehistoricIsland.Core.PrehistoricRelic.Skull
				repeat
					task.wait()
					toTarget(g.CFrame)
				until t:DistanceFromCharacter(g.Position) <= 200 or (DetectGolem()) or (DetectRockVolcano())
				b = false
				return
			end
			local g = DetectGolem()
			if g then
				repeat
					task.wait()
					toTarget(g.HumanoidRootPart.CFrame * CFrame.new(0, 20, 7))
					if Settings["Select Method Kill Golem"] == "Instant Kill [ Risk and can bug no die mob ]" then
						if t:DistanceFromCharacter(g.HumanoidRootPart.Position) < 50 then
							KillRaidEnemy()
						end
					else
						equiptool(NameWeapon(Settings["Select Weapon Kill Golem"] or "Melee"))
						getgenv().ClickM1Volcano(g)
					end
					if not getgenv().KillMobRaid and Settings["Kill Aura Only Raid And Volcano"] then
						getgenv().KillMobRaid = true
						local f = Settings["Time Delay Kill"] or 5
						g.Humanoid:ChangeState(Enum.HumanoidStateType.Dead)
						delay(f, function()
							getgenv().KillMobRaid = false
						end)
					end
				until not IsMobAlive(g) or not Settings["Fully Event Prehistoric Island"]
			end
			g = DetectRockVolcano()
			if g then
				if Settings["Fix Volcano Safe"] then
					local f = DetectPositionVolcano()
					local R, R = CheckPosnearRock(f, t.Character.HumanoidRootPart)
					if t:DistanceFromCharacter((CheckPosnearRock(f, g.WorldPivot))) >= 400 then
						s = R + 1
						if R >= 7 then
							s = 1
						end
						local R = f[s]
						toTarget(CFrame.new(R))
					else
						local s = X[math.floor(g.WorldPivot.Position.Y)]
						repeat
							task.wait()
							if t:DistanceFromCharacter((g.WorldPivot * s).Position) > 8 then
								toTarget(g.WorldPivot * s)
							end
							if t:DistanceFromCharacter(g.WorldPivot.Position) < 100 then
								AutoUseSkillFixLava()
							end
							getgenv().AimPos = g.WorldPivot
							local f = workspace.CurrentCamera
							G.Hit = g.WorldPivot
							G.Target = g
						until not g
							or not g.Parent
							or not Settings["Fully Event Prehistoric Island"]
							or not g.VFXLayer.Specs.Enabled
							or (DetectGolem())
						s = DetectGolem()
						if not s then
							b = true
						end
						wait(1)
					end
				else
					local s = X[math.floor(g.WorldPivot.Position.Y)]
					repeat
						task.wait()
						if t:DistanceFromCharacter((g.WorldPivot * s).Position) > 8 then
							toTarget(g.WorldPivot * s)
						end
						if t:DistanceFromCharacter(g.WorldPivot.Position) < 100 then
							AutoUseSkillFixLava()
						end
						getgenv().AimPos = g.WorldPivot
						local X = workspace.CurrentCamera
						G.Hit = g.WorldPivot
						G.Target = g
					until not g
						or not g.Parent
						or not Settings["Fully Event Prehistoric Island"]
						or not g.VFXLayer.Specs.Enabled
						or (DetectGolem())
					s = DetectGolem()
					if not s then
						b = true
					end
				end
			end
		end
	end
end
FullyVolcanoSection = VolcanoTab.CreateSection("Fully Volcano")
FullyVolcanoSection.CreateToggle(
	{
		Title = "Ignore Craft Volcanic Magnet [ Fully ]",
		Desc = nil,
		Default = Settings["Ignore Craft Volcanic Magnet"] or false,
	},
	function(b)
		SaveSettings("Ignore Craft Volcanic Magnet", b)
	end
)
FullyVolcanoSection.CreateToggle(
	{ Title = "Ignore Collect Bone [ Fully ]", Desc = nil, Default = Settings["Ignore Collect Bone"] or false },
	function(b)
		SaveSettings("Ignore Collect Bone", b)
	end
)
FullyVolcanoSection.CreateToggle(
	{
		Title = "Fully Event Prehistoric Island",
		Desc = nil,
		Default = Settings["Fully Event Prehistoric Island"] or false,
	},
	function(b)
		if b then
			spawn(function()
				while Settings["Fully Event Prehistoric Island"] and (task.wait()) do
					local s, s = pcall(function()
						FullyEventVolcano()
					end)
					if s then
						print(s)
					end
				end
			end)
		end
		SaveSettings("Fully Event Prehistoric Island", b)
	end
)
ESPTab = Main.CreatePage({ Page_Name = "ESP", Page_Title = "ESP Tab" })
ESPSection = ESPTab.CreateSection("ESP")
function EspSpawnBerry()
	local b, s = DetectBerryESP()
	if b then
		local X = Instance.new("IntValue", b.Parent)
		X.Name = "Ignored"
		local g = Drawing.new("Text")
		g.Visible = false
		g.Transparency = 1
		g.Text = b.Name
		g.Color = Color3.fromRGB(255, 255, 255)
		g.Size = 20
		g.Outline = true
		g.OutlineColor = Color3.fromRGB(0, 0, 0)
		g.Center = true
		g.Font = 1
		spawn(function()
			repeat
				task.wait()
				local f, R = game.workspace.CurrentCamera:WorldToViewportPoint(b.Parent.WorldPivot.Position)
				if R then
					g.Text = s .. " (" .. math.round(t:DistanceFromCharacter(b.Parent.WorldPivot.Position)) .. ")"
					g.Position = Vector2.new(f.X, f.Y - 20)
					g.Visible = true
				else
					g.Visible = false
				end
			until not b or not b.Parent or not Settings["ESP Berry"] or not DetectBerryCFrame(b:GetAttributes())
			g:Remove()
			if b.Parent then
				X:Destroy()
			end
		end)
	end
end
ESPSection.CreateToggle({ Title = "ESP Berry", Desc = nil, Default = Settings["ESP Berry"] or false }, function(b)
	if b then
		spawn(function()
			while Settings["ESP Berry"] and (wait(0.2)) do
				pcall(function()
					EspSpawnBerry()
				end)
			end
		end)
	end
	SaveSettings("ESP Berry", b)
end)
function DetectIsland()
	local b, s, X = next, workspace._WorldOrigin.Locations:GetChildren()
	for g, g in b, s, X do
		if g and (g:GetAttribute("CFrame")) and not g:FindFirstChild("Ignored") then
			return g
		end
	end
end
function EspIsland()
	local b = DetectIsland()
	if b then
		local s = Instance.new("IntValue", b)
		s.Name = "Ignored"
		local X = Drawing.new("Text")
		X.Visible = false
		X.Transparency = 1
		X.Text = b.Name
		X.Color = Color3.fromRGB(255, 255, 255)
		X.Size = 20
		X.Outline = true
		X.OutlineColor = Color3.fromRGB(0, 0, 0)
		X.Center = true
		X.Font = 1
		spawn(function()
			repeat
				task.wait()
				local g, f = game.workspace.CurrentCamera:WorldToViewportPoint(b:GetAttribute("CFrame").Position)
				if f then
					X.Text = b.Name
						.. " ("
						.. math.round(t:DistanceFromCharacter(b:GetAttribute("CFrame").Position))
						.. ")"
					X.Position = Vector2.new(g.X, g.Y - 20)
					X.Visible = true
				else
					X.Visible = false
				end
			until not b or not b.Parent or not Settings["ESP Island"]
			X:Remove()
			if b.Parent then
				s:Destroy()
			end
		end)
	end
end
ESPSection.CreateToggle({ Title = "ESP Island", Desc = nil, Default = Settings["ESP Island"] or false }, function(b)
	if b then
		spawn(function()
			while Settings["ESP Island"] and (wait(0.2)) do
				pcall(function()
					EspIsland()
				end)
			end
		end)
	end
	SaveSettings("ESP Island", b)
end)
function GetEspFruit()
	local b, s, X = next, game.Workspace:GetChildren()
	for g, g in b, s, X do
		if
			(g:IsA("Tool") or (g:IsA("Model")))
			and (string.find(g.Name, "Fruit"))
			and not g.Handle:FindFirstChild("Ignored")
		then
			return g
		end
	end
end
local b = {
	["rbxassetid://15100283484"] = "Light Fruit",
	["rbxassetid://15116730102"] = "Love Fruit",
	["rbxassetid://15100273645"] = "Dough Fruit",
	["rbxassetid://15116967784"] = "Spider Fruit",
	["rbxassetid://15112263502"] = "Shadow Fruit",
	["rbxassetid://15104782377"] = "Blade Fruit",
	["rbxassetid://15060012861"] = "Rocket Fruit",
	["rbxassetid://15106768588"] = "Leopard Fruit",
	["rbxassetid://15112469964"] = "Falcon Fruit",
	["rbxassetid://15708895165"] = "T-Rex Fruit",
	["rbxassetid://19001642259"] = "Dragon (East) Fruit",
	["rbxassetid://86024571204851"] = "Gas Fruit",
	["rbxassetid://15100246632"] = "Phoenix Fruit",
	["rbxassetid://14661873358"] = "Sound Fruit",
	["rbxassetid://15111584216"] = "Flame Fruit",
	["rbxassetid://15105281957"] = "Spring Fruit",
	["rbxassetid://15116740364"] = "Bomb Fruit",
	["rbxassetid://15104817760"] = "Rubber Fruit",
	["rbxassetid://15057683975"] = "Spin Fruit",
	["rbxassetid://15105350415"] = "Magma Fruit",
	["rbxassetid://15482881956"] = "Kitsune Fruit",
	["rbxassetid://15100485671"] = "Barrier Fruit",
	["rbxassetid://18955022385"] = "Dragon (West) Fruit",
	["rbxassetid://101378450824208"] = "Yeti Fruit",
	["rbxassetid://15116721173"] = "Pain Fruit",
	["https://assetdelivery.roblox.com/v1/asset/?id=10395893751"] = "Venom Fruit",
	["rbxassetid://11908375285"] = "Spirit Fruit",
	["rbxassetid://15100433167"] = "Ice Fruit",
	["rbxassetid://15100299740"] = "Gravity Fruit",
	["rbxassetid://15107005807"] = "Spike Fruit",
	["rbxassetid://15116696973"] = "Smoke Fruit",
	["rbxassetid://15112600534"] = "Diamond Fruit",
	["rbxassetid://15112333093"] = "Ghost Fruit",
	["rbxassetid://15057718441"] = "Quake Fruit",
	["rbxassetid://15111517529"] = "Sand Fruit",
	["rbxassetid://15100313696"] = "Buddha Fruit",
	["rbxassetid://15116747420"] = "Rumble Fruit",
	["rbxassetid://15100384816"] = "Blizzard Fruit",
	["rbxassetid://15111553409"] = "Dark Fruit",
	["rbxassetid://14661837634"] = "Mammoth Fruit",
	["rbxassetid://15100184583"] = "Control Fruit",
}
function GetFruitName(s, X)
	if s.ClassName == "Tool" then
		return s.Name
	end
	local g, f = "Fruit", {}
	for R, R in pairs(s:GetDescendants()) do
		if R:IsA("MeshPart") then
			table.insert(f, R.MeshId)
		end
	end
	if f then
		for R, m in pairs(b) do
			g = if table.find(f, R) then m else g
		end
	end
	if g == "Fruit " then
		f = s:FindFirstChild("Fruit")
		g = if f
			then if f:FindFirstChild("Retopo_Cube.001")
				then "Spirit Fruit"
				else if f:FindFirstChild("Gravity cube.026")
					then if f:FindFirstChild("Gravity cube.001") then "Blizzard Fruit" else "Portal Fruit"
					else if f:FindFirstChild("Cube.011") then "Rubber Fruit" else g
			else g
	end
	return if X then "[Natural Spawn]\10" .. g else g
end
function EspFruit()
	local b = GetEspFruit()
	if not b then
		return
	end
	local s, X = GetFruitName(b), b:FindFirstChild("Handle")
	if not X then
		return
	end
	local g = Instance.new("IntValue")
	g.Name = "Ignored"
	g.Parent = X
	local g, f =
		({
			["Leopard Fruit"] = Color3.fromRGB(255, 170, 0),
			["Dragon (East) Fruit"] = Color3.fromRGB(255, 0, 0),
			["Dragon (West) Fruit"] = Color3.fromRGB(255, 80, 80),
			["Kitsune Fruit"] = Color3.fromRGB(200, 100, 255),
			["Spirit Fruit"] = Color3.fromRGB(120, 200, 255),
			["Venom Fruit"] = Color3.fromRGB(180, 60, 200),
			["Dough Fruit"] = Color3.fromRGB(255, 220, 180),
			["Light Fruit"] = Color3.fromRGB(255, 255, 150),
		})[s] or (Color3.fromRGB(255, 255, 255)),
		Drawing.new("Text")
	f.Visible = false
	f.Transparency = 1
	f.Text = s
	f.Color = g
	f.Size = 20
	f.Outline = true
	f.OutlineColor = Color3.fromRGB(0, 0, 0)
	f.Center = true
	f.Font = 2
	local R = Drawing.new("Square")
	R.Visible = false
	R.Filled = true
	R.Color = Color3.fromRGB(0, 0, 0)
	R.Transparency = 0.4
	spawn(function()
		repeat
			task.wait()
			if X then
				local m, E = workspace.CurrentCamera:WorldToViewportPoint(X.Position)
				if E then
					f.Text = s .. " [" .. math.round(t:DistanceFromCharacter(X.Position)) .. "m]"
					f.Position = Vector2.new(m.X, m.Y - 20)
					f.Color = g
					f.Visible = true
					local s = f.TextBounds
					R.Position = Vector2.new(f.Position.X - s.X / 2 - 4, f.Position.Y - 2)
					R.Size = Vector2.new(s.X + 8, s.Y + 4)
					R.Visible = true
				else
					f.Visible = false
					R.Visible = false
				end
			end
		until not b or not b.Parent or not X.Parent or not Settings["ESP Fruit"]
		f:Remove()
		R:Remove()
		if X:FindFirstChild("Ignored") then
			X.Ignored:Destroy()
		end
	end)
end
ESPSection.CreateToggle({ Title = "ESP Fruit", Desc = nil, Default = Settings["ESP Fruit"] or false }, function(b)
	if b then
		spawn(function()
			while Settings["ESP Fruit"] and (wait()) do
				local s, s = pcall(function()
					EspFruit()
				end)
				if s then
					print(s)
				end
			end
		end)
	end
	SaveSettings("ESP Fruit", b)
end)
function DetectPlayerESP()
	for b, b in pairs(game.Workspace.Characters:GetChildren()) do
		if b.Name ~= t.Name and not b:FindFirstChild("Ignored") then
			return b
		end
	end
end
function ESPPlayer()
	local b = DetectPlayerESP()
	if b then
		local s = Instance.new("IntValue", b)
		s.Name = "Ignored"
		local X = Drawing.new("Text")
		X.Visible = false
		X.Transparency = 1
		X.Text = b.Name
		X.Color = Color3.fromRGB(255, 255, 255)
		X.Size = 20
		X.Outline = true
		X.OutlineColor = Color3.fromRGB(0, 0, 0)
		X.Center = true
		X.Font = 1
		spawn(function()
			repeat
				task.wait()
				local g, f = game.workspace.CurrentCamera:WorldToViewportPoint(b.HumanoidRootPart.Position)
				if f then
					X.Text = b.Name
						.. " ("
						.. math.round(t:DistanceFromCharacter(b.HumanoidRootPart.Position))
						.. ")"
						.. "\10"
						.. b.Humanoid.Health
						.. " / "
						.. b.Humanoid.MaxHealth
					X.Position = Vector2.new(g.X, g.Y - 20)
					X.Visible = true
				else
					X.Visible = false
				end
			until not b or not b.Parent or not Settings["ESP Player"]
			X:Remove()
			if b.Parent then
				s:Destroy()
			end
		end)
	end
end
ESPSection.CreateToggle({ Title = "ESP Player", Desc = nil, Default = Settings["ESP Player"] or false }, function(b)
	if b then
		spawn(function()
			while Settings["ESP Player"] and (wait()) do
				pcall(function()
					ESPPlayer()
				end)
			end
		end)
	end
	SaveSettings("ESP Player", b)
end)
PvpTab = Main.CreatePage({ Page_Name = "PVP", Page_Title = "PVP Tab" })
SettingsAimbotSection = PvpTab.CreateSection("PVP")
local b = SettingsAimbotSection.CreateDropdown(
	{
		Title = "Select Player PVP",
		List = DetectNamePlayer(),
		Search = true,
		Selected = false,
		Default = Settings["Select Player PVP"] or nil,
	},
	function(s)
		SaveSettings("Select Player PVP", s)
	end
)
SettingsAimbotSection.CreateDropdown(
	{
		Title = "Select Method Aimbot",
		List = { "Select Player", "Target nearest Player" },
		Search = true,
		Selected = false,
		Default = Settings["Select Method Aimbot"] or nil,
	},
	function(s)
		SaveSettings("Select Method Aimbot", s)
	end
)
SettingsAimbotSection.CreateButton({ Title = "Refresh Player" }, function()
	b:GetNewList(DetectNamePlayer())
end)
function TeleportPlayer()
	for b, b in pairs(game:GetService("Players"):GetChildren()) do
		if b.Name == Settings["Select Player PVP"] then
			return b
		end
	end
end
SettingsAimbotSection.CreateToggle(
	{ Title = "Teleport Player", Desc = nil, Default = Settings["Teleport Player"] or false },
	function(b)
		if b then
			spawn(function()
				while Settings["Teleport Player"] and (wait()) do
					pcall(function()
						toTarget(TeleportPlayer().Character.HumanoidRootPart.CFrame)
					end)
				end
			end)
		end
		SaveSettings("Teleport Player", b)
	end
)
function ClosestPartaimbot()
	local b, s = 1 / 0
	for X, g in pairs(game.Workspace.Characters:GetChildren()) do
		if g:IsA("Model") then
			if
				g.Name ~= t.Name
				and (
					game.Players.LocalPlayer.Team == game.Teams.Marines
						and game.Players[g.Name].Team ~= game.Teams.Marines
					or game.Players.LocalPlayer.Team ~= game.Teams.Marines
				)
			then
				X = (game.Players.LocalPlayer.Character.HumanoidRootPart.Position - g.HumanoidRootPart.Position).Magnitude
				if X < b then
					b, s = X, g
				end
			end
		end
	end
	return s
end
SettingsAimbotSection.CreateToggle(
	{ Title = "Auto Aimbot", Desc = nil, Default = Settings["Auto Aimbot"] or false },
	function(b)
		if b then
			spawn(function()
				while Settings["Auto Aimbot"] and (task.wait()) do
					pcall(function()
						if Settings["Select Method Aimbot"] == "Select Player" then
							local s, s =
								workspace.CurrentCamera, game.Workspace.Characters[Settings["Select Player PVP"]]
							G.Hit = s.HumanoidRootPart.CFrame
							G.Target = s
							getgenv().AimPos = CFrame.new(
								s.HumanoidRootPart.CFrame.p,
								s.HumanoidRootPart.Position + s.HumanoidRootPart.Velocity / 0.5
							)
						else
							local s, s = workspace.CurrentCamera, ClosestPartaimbot()
							G.Hit = s.HumanoidRootPart.CFrame
							G.Target = s
							getgenv().AimPos = CFrame.new(
								s.HumanoidRootPart.CFrame.p,
								s.HumanoidRootPart.Position + s.HumanoidRootPart.Velocity / 0.5
							)
						end
					end)
				end
			end)
		end
		SaveSettings("Auto Aimbot", b)
	end
)
SettingsAimbotSection.CreateToggle(
	{ Title = "Auto Aimbot Gun", Desc = nil, Default = Settings["Auto Aimbot Gun"] or false },
	function(b)
		SaveSettings("Auto Aimbot Gun", b)
	end
)
local b = require(game:GetService("ReplicatedStorage").Modules.CombatUtil).GetTargetPosition
require(game:GetService("ReplicatedStorage").Modules.CombatUtil).GetTargetPosition = function(s, X, g, f, R)
	if Settings["Auto Aimbot Gun"] then
		local m = if Settings["Select Method Aimbot"] == "Select Player"
			then game.Workspace.Characters[Settings["Select Player PVP"]]
			else (ClosestPartaimbot())
		if m and (m:FindFirstChild("HumanoidRootPart")) then
			return m.HumanoidRootPart.Position
		end
	end
	return b(s, X, g, f, R)
end
MISCPVPSection = PvpTab.CreateSection("MISC PVP")
MISCPVPSection.CreateSlider(
	{ Title = "Input WalkSpeed", Min = 0, Max = 500, Default = Settings["Input WalkSpeed"] or 200, Precise = true },
	function(b)
		SaveSettings("Input WalkSpeed", b)
	end
)
MISCPVPSection.CreateSlider(
	{ Title = "Input JumpPower", Min = 0, Max = 500, Default = Settings["Input JumpPower"] or 200, Precise = true },
	function(b)
		SaveSettings("Input JumpPower", b)
	end
)
MISCPVPSection.CreateToggle(
	{ Title = "Change JumpPower", Desc = nil, Default = Settings["Change JumpPower"] or false },
	function(b)
		SaveSettings("Change JumpPower", b)
	end
)
MISCPVPSection.CreateToggle(
	{ Title = "Change WalkSpeed", Desc = nil, Default = Settings["Change WalkSpeed"] or false },
	function(b)
		SaveSettings("Change WalkSpeed", b)
	end
)
MISCPVPSection.CreateToggle(
	{ Title = "Walk On Water", Desc = nil, Default = Settings["Walk On Water "] or true },
	function(b)
		if b then
			if not game.Workspace:FindFirstChild("WaterWalk") then
				platform = Instance.new("Part")
				platform.Name = "WaterWalk"
				platform.Size = Vector3.new(1 / 0, 1, 1 / 0)
				platform.Transparency = 1
				platform.Anchored = true
				platform.Parent = game.workspace
			end
			spawn(function()
				while Settings["Walk On Water "] and (task.wait()) do
					pcall(function()
						if t.Character.Humanoid.Sit then
							platform.CanCollide = false
							return
						end
						if
							(Vector3.new(
								0,
								game.Players.LocalPlayer.Character:FindFirstChild("HumanoidRootPart").Position.Y,
								0
							) - Vector3.new(0, -60, 0)).Magnitude > 60
						then
							platform.CanCollide = false
							return
						end
						platform.CanCollide = true
						platform.Position = Vector3.new(
							game:GetService("Players").LocalPlayer.Character.HumanoidRootPart.Position.X,
							game:GetService("Players").LocalPlayer.Character.HumanoidRootPart.Position.Y * 0 - 5,
							game:GetService("Players").LocalPlayer.Character.HumanoidRootPart.Position.Z
						)
					end)
				end
			end)
		end
		SaveSettings("Walk On Water ", b)
	end
)
TabWebhook = Main.CreatePage({ Page_Name = "Tab Webhook", Page_Title = "Tab Webhook" })
SectionWebhook = TabWebhook.CreateSection("Webhook")
SectionWebhook.CreateBox(
	{
		Title = "Input Url Webhook",
		Placeholder = "Type here",
		Number = false,
		Default = Settings["Input Url Webhook"] or nil,
	},
	function(b)
		SaveSettings("Input Url Webhook", b)
	end
)
SectionWebhook.CreateBox(
	{
		Title = "Input Discord Ping (Everyone/ID)",
		Placeholder = "Type here",
		Number = false,
		Default = Settings["Input Discord Ping"] or nil,
	},
	function(b)
		SaveSettings("Input Discord Ping", b)
	end
)
SectionWebhook.CreateToggle(
	{ Title = "Ping Everyone/Id Discord", Desc = nil, Default = Settings["Ping Discord"] or false },
	function(b)
		SaveSettings("Ping Discord", b)
	end
)
local b = {
	Username = "Binini Hub",
	AvatarURL = "https://images-ext-1.discordapp.net/external/9LSZu__Uvs7I0N8MWag-JmwF2iT-pHCHSe2UdixGEXQ/%3Fsize%3D4096/https/cdn.discordapp.com/avatars/1262364141968949308/a_0c5fb64e2cbb35d029d73b44576c6a60.gif",
	BannerURL = "https://cdn.discordapp.com/attachments/1017024488665264218/1262729537578471504/banner_server.jpg",
	Title = "Banana Hub Notification",
	FooterText = "Binini Hub",
	Color = 16776960,
}
function safe_str(s)
	local X, g = pcall(function()
		return tostring(s)
	end)
	return X and g or "nil"
end
function get_ping_tag()
	local s, X, g = "", pcall(function()
		return Settings["Ping Discord"]
	end)
	if X and g then
		local X, g = pcall(function()
			return Settings["Input Discord Ping"]
		end)
		s = if X and (tonumber(g)) then "<@" .. g .. ">" else "@everyone"
	end
	return s
end
function get_webhook_url()
	local s, X = pcall(function()
		return Settings["Input Url Webhook"]
	end)
	return s and X or nil
end
function iso8601_utc_now()
	return os.date("!%Y-%m-%dT%H:%M:%SZ")
end
function base_fields(s, X)
	return {
		{ name = "Event", value = "`" .. safe_str(s) .. "`", inline = true },
		{ name = "Detail", value = "`" .. safe_str(X) .. "`", inline = true },
		{ name = "Username", value = "||" .. safe_str(t and t.Name or "Unknown") .. "||", inline = true },
		{ name = "PlaceId", value = "`" .. safe_str(game.PlaceId) .. "`", inline = true },
		{ name = "JobId", value = "`" .. safe_str(game.JobId) .. "`", inline = true },
	}
end
local function s(X, g, f)
	local R = get_webhook_url()
	if not R or R == "" then
		return
	end
	local m = if f
		then {
			{ name = "Stored Fruit", value = "```" .. safe_str(g) .. "```", inline = false },
			{ name = "Username", value = "||" .. safe_str(t and t.Name or "Unknown") .. "||", inline = true },
			{ name = "Time", value = os.date("%Y-%m-%d %H:%M:%S"), inline = true },
			{ name = "PlaceId", value = "`" .. safe_str(game.PlaceId) .. "`", inline = true },
		}
		else (base_fields(X, g))
	local X = {
		content = get_ping_tag(),
		username = b.Username,
		avatar_url = b.AvatarURL,
		embeds = {
			{
				title = b.Title,
				description = "**Main Status**\10Username : ||" .. safe_str(t and t.Name or "Unknown") .. "||",
				color = b.Color,
				footer = { text = b.FooterText },
				fields = m,
				thumbnail = { url = b.BannerURL },
				timestamp = iso8601_utc_now(),
			},
		},
	}
	pcall(function()
		ExploitReq({
			Url = R,
			Method = "POST",
			Headers = { ["Content-Type"] = "application/json" },
			Body = HttpService:JSONEncode(X),
		})
	end)
end
getgenv().WebhookStoreFruit = function(b)
	s("Store Fruit", b, true)
end
getgenv().WebhookFindVolcano = function()
	s("Prehistoric Island", "Spawned", false)
end
getgenv().WebhookFindLeviathan = function()
	s("Frozen Dimension", "Spawned", false)
end
getgenv().WebhookFindMirage = function()
	s("Mirage", "Spawned", false)
end
getgenv().WebhookDestroyIdk = function()
	s("Status", "Can Find Leviathan", false)
end
function Webhookprofile()
	local b, s, X, g =
		{
			Color = 16776960,
			BannerURL = "https://cdn.discordapp.com/attachments/1017024488665264218/1262729537578471504/banner_server.jpg",
			AvatarURL = "https://images-ext-1.discordapp.net/external/9LSZu__Uvs7I0N8MWag-JmwF2iT-pHCHSe2UdixGEXQ/%3Fsize%3D4096/https/cdn.discordapp.com/avatars/1262364141968949308/a_0c5fb64e2cbb35d029d73b44576c6a60.gif",
			Username = "Binini Hub",
			Title = "<:bananacon:1261744974534541352> Banana Hub Notification <:bananacon:1261744974534541352>",
			FooterText = "Binini Hub",
			FruitMinValue = 1000000,
			ItemMinRarity = 3,
			MaxFieldLen = 1024,
			MaxDescLen = 3800,
		},
		game:GetService("Players"),
		game:GetService("HttpService"),
		game.ReplicatedStorage:WaitForChild("Remotes"):WaitForChild("CommF_")
	local f = s.LocalPlayer
	local function s(R)
		local m, E = pcall(function()
			return tostring(R)
		end)
		return m and E or "nil"
	end
	local function R(m, E)
		m = s(m or "")
		if #m > E then
			return m:sub(1, E - 3) .. "..."
		end
		return m
	end
	local function m(E, l)
		return "```\10" .. R(E or "", l - 8) .. "\10```"
	end
	local function E(l)
		local Q = {}
		for S, S in ipairs(l or {}) do
			Q[#Q + 1] = s(S.Name or S)
		end
		return table.concat(Q, ",\10")
	end
	local function l(Q)
		local S = {}
		for d, d in ipairs(Q or {}) do
			S[#S + 1] = s(d)
		end
		return table.concat(S, ",\10")
	end
	local function Q(...)
		local S = { ... }
		local d, I = pcall(function()
			return g:InvokeServer(unpack(S))
		end)
		if d then
			return I
		end
		return nil
	end
	local function g()
		return os.date("!%Y-%m-%dT%H:%M:%SZ")
	end
	local function S()
		local d = f.Data and f.Data.DevilFruit and f.Data.DevilFruit.Value or ""
		local I, _ = d ~= "" and d or "None", 0
		if I ~= "None" then
			d = f.Backpack:FindFirstChild(I) or f.Character and (f.Character:FindFirstChild(I))
			_ = if d and (d:FindFirstChild("Level")) then tonumber(d.Level.Value) or 0 else _
		end
		return I, _
	end
	local function d()
		if not Q("AwakeningChanger", "Check") then
			return {}
		end
		local I, _ = Q("getAwakenedAbilities"), {}
		if type(I) == "table" then
			for o, V in pairs(I) do
				if type(V) == "table" and V.Awakened then
					table.insert(_, s(o))
				end
			end
		end
		table.sort(_)
		return _
	end
	local function I()
		local _, o =
			{
				"Death Step",
				"Sharkman Karate",
				"Electric Claw",
				"Dragon Talon",
				"Superhuman",
				"Godhuman",
				"Sanguine Art",
			},
			{}
		for V, V in ipairs(_) do
			if Q("Buy" .. V:gsub(" ", ""), true) == 1 then
				table.insert(o, V)
			end
		end
		table.sort(o)
		return o
	end
	local function _()
		local o, V = {}, {}
		for N, N in ipairs(B() or {}) do
			if type(N) == "table" then
				local y, P, e = tonumber(N.Value), tonumber(N.Rarity), s(N.Name or "")
				e = if e ~= "" and (e:find("-", 1, true)) then e:split("-")[1] else e
				if y and y >= b.FruitMinValue then
					table.insert(o, { Name = e, Value = y })
				elseif P and P >= b.ItemMinRarity then
					table.insert(V, { Name = e, Rarity = P })
				end
			end
		end
		table.sort(o, function(N, y)
			return (N.Value or 0) > (y.Value or 0)
		end)
		table.sort(V, function(N, y)
			return (N.Rarity or 0) > (y.Rarity or 0)
		end)
		return o, V
	end
	local o, V, N =
		{
			Name = s(f and f.Name or "Unknown"),
			Level = f.Data and f.Data.Level and (tonumber(f.Data.Level.Value)) or 0,
			Race = f.Data and f.Data.Race and (s(f.Data.Race.Value)) or "Unknown",
			RaceVer = "[" .. (function()
				if f.Character and (f.Character:FindFirstChild("RaceTransformed")) then
					return "V4"
				end
				if Q("Wenlocktoad", "1") == -2 then
					return "V3"
				end
				if Q("Alchemist", "1") == -2 then
					return "V2"
				end
				return "V1"
			end)() .. "]",
		},
		S()
	o.Fruit = V
	o.FruitShort = V ~= "None" and V:split("-")[1] or "None"
	o.FruitMastery = N
	S = d()
	d = #S > 0 and " " .. table.concat(S, " ") or ""
	o.FruitText = V == "None" and "None" or o.FruitShort .. " [" .. tostring(N) .. d .. "]"
	o.Melees = I()
	N, I = _()
	o.InventoryFruit = N
	o.Inventory = I
	_, N, d, V =
		R(l(o.Melees), b.MaxFieldLen - 10),
		R(E(o.InventoryFruit), b.MaxFieldLen - 10),
		R(E(o.Inventory), b.MaxFieldLen - 10),
		m(
			R(
				" Username : "
					.. o.Name
					.. ",\10 Level : "
					.. tostring(o.Level)
					.. ",\10 Race : "
					.. o.Race
					.. " "
					.. o.RaceVer
					.. ",\10 Fruits : "
					.. o.FruitText
					.. " ",
				b.MaxDescLen
			),
			b.MaxDescLen
		)
	local s, f, R =
		{
			username = b.Username,
			avatar_url = b.AvatarURL,
			embeds = {
				{
					title = b.Title,
					description = V,
					color = tonumber(b.Color),
					footer = { text = b.FooterText },
					fields = {
						{ name = "**Melee**", value = m(_, b.MaxFieldLen), inline = true },
						{ name = "**Inventory Fruit**", value = m(N, b.MaxFieldLen), inline = true },
						{ name = "**Inventory**", value = m(d, b.MaxFieldLen), inline = false },
					},
					thumbnail = { url = b.BannerURL },
					timestamp = g(),
				},
			},
		},
		pcall(function()
			return Settings["Input Url Webhook"]
		end)
	if not f or not R or R == "" then
		return
	end
	pcall(function()
		ExploitReq({
			Url = R,
			Method = "POST",
			Headers = { ["Content-Type"] = "application/json" },
			Body = X:JSONEncode(s),
		})
	end)
end
SectionWebhook.CreateToggle(
	{ Title = "Noti Profile", Desc = nil, Default = Settings["Noti Profile"] or false },
	function(b)
		if b then
			spawn(function()
				while Settings["Noti Profile"] and (wait()) do
					pcall(function()
						Webhookprofile()
						wait(300)
					end)
				end
			end)
		end
		SaveSettings("Noti Profile", b)
	end
)
TableRarityFruit = { Mythical = false, Legendary = false, Rare = false, Uncommon = false, Common = false }
SectionWebhook.CreateDropdown(
	{
		Title = "Select Rarity Fruit",
		List = PrepareMultiSelectList(TableRarityFruit, Settings["Select Rarity Fruit"]),
		Search = true,
		Selected = true,
		Default = Settings["Select Rarity Fruit"] or nil,
	},
	function(b, s)
		SaveSettings("Select Rarity Fruit", b, s)
	end
)
SectionWebhook.CreateToggle(
	{ Title = "Webhook Store Fruit", Desc = nil, Default = Settings["Webhook Store Fruit"] or false },
	function(b)
		SaveSettings("Webhook Store Fruit", b)
	end
)
SectionWebhook.CreateToggle(
	{
		Title = "Webhook Find Prehistoric Island",
		Desc = nil,
		Default = Settings["Webhook Find Prehistoric Island"] or false,
	},
	function(b)
		SaveSettings("Webhook Find Prehistoric Island", b)
	end
)
SectionWebhook.CreateToggle(
	{ Title = "Webhook Find Leviathan", Desc = nil, Default = Settings["Webhook Find Leviathan"] or false },
	function(b)
		SaveSettings("Webhook Find Leviathan", b)
	end
)
SectionWebhook.CreateToggle(
	{ Title = "Webhook Destroy IDK", Desc = nil, Default = Settings["Webhook Destroy IDK"] or false },
	function(b)
		SaveSettings("Webhook Destroy IDK", b)
	end
)
SectionWebhook.CreateToggle(
	{ Title = "Webhook Find Mirage", Desc = nil, Default = Settings["Webhook Find Mirage"] or false },
	function(b)
		SaveSettings("Webhook Find Mirage", b)
	end
)
SettingPage = Main.CreatePage({ Page_Name = "Setting", Page_Title = "Setting Tab" })
a = SettingPage.CreateSection("Settings")
a.CreateToggle({ Title = "White Screen", Desc = nil, Default = Settings["White Screen"] or false }, function(b)
	if not b then
		game:GetService("RunService"):Set3dRenderingEnabled(true)
	else
		game:GetService("RunService"):Set3dRenderingEnabled(false)
	end
	SaveSettings("White Screen", b)
end)
a.CreateToggle({ Title = "Black Screen", Desc = nil, Default = Settings["Black Screen"] or false }, function(b)
	spawn(function()
		repeat
			wait()
		until K
		if not b then
			K.Visible = false
			game:GetService("RunService"):Set3dRenderingEnabled(true)
			SetRobloxGUI(true)
		else
			K.Visible = true
			game:GetService("RunService"):Set3dRenderingEnabled(false)
			SetRobloxGUI(false)
		end
	end)
	SaveSettings("Black Screen", b)
end)
local function b(s)
	if type(s) ~= "table" then
		return s
	end
	local X, g, f, K, R = {}, {}, {}, "{\10", 1
	while true do
		local m = 0
		for E, E in pairs(s) do
			m += 1
		end
		local E = 1
		for l, Q in pairs(s) do
			if X[s] == nil or E >= X[s] then
				local S, d = string.find, T[24](K:len())
				table.insert(
					f,
					if S(K, "}", T:d5(d))
						then K .. ",\10"
						else if not string.find(K, "\10", K:len()) then K .. "\10" else K
				)
				K = ""
				d, S =
					if type(l) == "number" or type(l) == "boolean"
						then "[" .. tostring(l) .. "]"
						else '["' .. tostring(l) .. '"]',
					type(Q) == "number" or type(Q) == "boolean"
				if S then
					K ..= string.rep("\9", R) .. d .. " = " .. tostring(Q)
				elseif type(Q) == "table" then
					K ..= string.rep("\9", R) .. d .. " = {\10"
					table.insert(g, s)
					table.insert(g, Q)
					X[s] = E + 1
					break
				else
					K ..= string.rep("\9", R) .. d .. ' = "' .. tostring(Q) .. '"'
				end
				K = if E == m then K .. "\10" .. string.rep("\9", R - 1) .. "}" else K .. ","
			else
				K = if E == m then K .. "\10" .. string.rep("\9", R - 1) .. "}" else K
			end
			E += 1
		end
		K = if m == 0 then K .. "\10" .. string.rep("\9", R - 1) .. "}" else K
		if #g > 0 then
			s = g[#g]
			g[#g] = nil
			R = X[s] == nil and R + 1 or R - 1
		else
			break
		end
	end
	table.insert(f, K)
	return "getgenv().Config = " .. table.concat(f)
end
a.CreateToggle(
	{ Title = "Remove Notifications", Desc = nil, Default = Settings["Remove Notifications"] or false },
	function(T)
		SaveSettings("Remove Notifications", T)
	end
)
DisplayNoti = getupvalues(require(game:GetService("ReplicatedStorage").Notification).Display)[1]
spawn(function()
	repeat
		wait(1)
	until Settings["Remove Notifications"]
	require(game:GetService("ReplicatedStorage").Notification).Dead = function(T)
		if Settings["Remove Notifications"] then
			return true
		else
			return tick() - T.CreationTime > T.Duration
		end
	end
	require(game:GetService("ReplicatedStorage").Notification).Display = function(T)
		if Settings["Remove Notifications"] then
			return true
		elseif T.Displayed then
			return false
		else
			T.Displayed = true
			T.CreationTime = tick()
			T.Label.Visible = true
			DisplayNoti:Add(T)
			return true
		end
	end
end)
a.CreateToggle(
	{ Title = "Auto rejoin Disconnect", Desc = nil, Default = Settings["Auto rejoin Disconnect"] or false },
	function(T)
		SaveSettings("Auto rejoin Disconnect", T)
	end
)
a.CreateToggle({ Title = "Auto Load Script", Desc = nil, Default = Settings["Auto Load Script"] or false }, function(T)
	SaveSettings("Auto Load Script", T)
end)
a.CreateToggle({ Title = "Boost Fps", Desc = nil, Default = Settings["Boost Fps"] or false }, function(T)
	if T then
		local s, X = true, game
		local g, f = X.Workspace, X.Lighting
		local K = g.Terrain
		K.WaterWaveSize = 0
		K.WaterWaveSpeed = 0
		K.WaterReflectance = 0
		K.WaterTransparency = 0
		f.GlobalShadows = false
		f.FogEnd = 9000000000
		f.Brightness = 0
		settings().Rendering.QualityLevel = "Level01"
		for R, R in pairs(X:GetDescendants()) do
			if R:IsA("Part") or (R:IsA("Union")) or (R:IsA("CornerWedgePart")) or (R:IsA("TrussPart")) then
				R.Material = "Plastic"
				R.Reflectance = 0
			elseif R:IsA("Decal") or R:IsA("Texture") and s then
				R.Transparency = 1
			elseif R:IsA("ParticleEmitter") or R:IsA("Trail") and R.Parent.Name ~= "RelicFire" then
				R.Lifetime = NumberRange.new(0)
			elseif R:IsA("Explosion") then
				R.BlastPressure = 1
				R.BlastRadius = 1
			elseif R:IsA("Fire") or (R:IsA("SpotLight")) or (R:IsA("Smoke")) or (R:IsA("Sparkles")) then
				R.Enabled = false
			elseif R:IsA("MeshPart") then
				R.Material = "Plastic"
				R.Reflectance = 0
				R.TextureID = 10385902758728956
			end
		end
		for R, R in pairs(f:GetChildren()) do
			if
				R:IsA("BlurEffect")
				or (R:IsA("SunRaysEffect"))
				or (R:IsA("ColorCorrectionEffect"))
				or (R:IsA("BloomEffect"))
				or (R:IsA("DepthOfFieldEffect"))
			then
				R.Enabled = false
			end
		end
		wait(1)
		s, g, X =
			workspace:WaitForChild("Map"), game.ReplicatedStorage:WaitForChild("Unloaded"), Enum.Material.SmoothPlastic
		f = s:GetDescendants()
		wait(0.5)
		K = g:GetDescendants()
		wait(0.5)
		local R, m, E = os.clock, task.wait, g.IsA
		local l, Q, S = R(), tick(), 0
		s = l
		for d, d in next, f, nil do
			if E(d, "BasePart") then
				d.Material = X
				S += 1
				if R() - l > 0.008333333333333333 then
					g = "Working.. " .. S
					m()
					m()
					l = (R())
				end
			elseif d:IsA("Texture") and not d:GetAttribute("Offset") then
				d:Destroy()
			end
		end
		for g, f in next, K, nil do
			if E(f, "BasePart") then
				f.Material = X
				S += 1
				if R() - l > 0.008333333333333333 then
					g = "Working.. " .. S
					m()
					m()
					l = (R())
				end
			elseif f:IsA("Texture") and not f:GetAttribute("Offset") then
				f:Destroy()
			end
		end
		game.Players.LocalPlayer.PlayerScripts.OptimizerClientActor:SendMessage("Optimize", true)
		print("Time taken to Fast Mode: ", tick() - Q, R() - s)
	end
	SaveSettings("Boost Fps", T)
end)
spawn(function()
	repeat
		wait()
	until Settings["Boost Fps"] and (game.Workspace:FindFirstChild("_WorldOrigin"))
	workspace._WorldOrigin.DescendantAdded:Connect(function(T)
		if T:IsA("Part") or (T:IsA("Union")) or (T:IsA("CornerWedgePart")) or (T:IsA("TrussPart")) then
			T.Transparency = 1
			T.Material = "Plastic"
			T.Reflectance = 0
		end
		if T:IsA("Decal") or T:IsA("Texture") and decalsyeeted then
			T.Transparency = 1
		end
		if T:IsA("ParticleEmitter") or (T:IsA("Trail")) then
			if T.Parent.Name ~= "RelicFire" then
				T.Enabled = false
				T.Lifetime = NumberRange.new(0)
			end
		end
		if T:IsA("Explosion") then
			T.Enabled = false
			T.BlastPressure = 1
			T.BlastRadius = 1
		end
		if T:IsA("Fire") or (T:IsA("SpotLight")) or (T:IsA("Smoke")) or (T:IsA("Sparkles")) then
			T.Enabled = false
		end
		if T:IsA("MeshPart") then
			T.Transparency = 1
			T.Material = "Plastic"
			T.Reflectance = 0
			T.TextureID = 10385902758728956
		end
	end)
end)
a.CreateButton({ Title = "Copy Config" }, function()
	setclipboard(b((HttpService:JSONDecode(readfile(FolderName .. "/" .. SaveFileName)))))
	A.CreateNoti({ Title = "Banana Cat Hub", Desc = "Successfully Copy Config", ShowTime = 5 })
end)
a.CreateBind({ Title = "Toggle GUI", Key = Enum.KeyCode.LeftControl }, function()
	getgenv().UIToggled = not getgenv().UIToggled
	if game.CoreGui:FindFirstChild("Nousigi Hub GUI") then
		for T, T in ipairs(game.CoreGui:GetChildren()) do
			if T.Name == "Nousigi Hub GUI" then
				T.Enabled = getgenv().UIToggled
			end
		end
	end
end)
spawn(function()
	pcall(function()
		if not (Settings["Auto Load Script"] and getgenv().Key) then
			repeat
				wait()
			until Settings["Auto Load Script"] and getgenv().Key
		end
		local T = if syn then syn.queue_on_teleport else queue_on_teleport
		if not T then
			return
		end
		T(
			string.format(
				' repeat wait() until game:IsLoaded()\10 getgenv().Key = %q\10 getgenv().__BANANA_SCRIPT_ROUTE = "bf_main"\10 return loadstring(game:HttpGet("https://banana-hub.xyz/loader/banana.lua"))()\10 ',
				getgenv().Key
			)
		)
	end)
end)
loadstring(
	'local MT = getrawmetatable(game)\10local OldNameCall = MT.__namecall\10setreadonly(MT, false)\10MT.__namecall = newcclosure(function(self, ...)\10 local Method = getnamecallmethod()\10 local Args = { ... }\10 if\10 Method == "FireServer"\10 and self.Name == "RemoteEvent"\10 and AimPos\10 and tostring(AimPos.X) ~= "nan"\10 and (\10 Settings["Auto Event Prehistoric Island"]\10 or Settings["Kill players When complete Trial"]\10 or Settings["Auto Quest Dragon Hunter"]\10 or Settings["Auto Quest Dojo Trainer"]\10 or Settings["Farm Mastery"]\10 or Settings["Auto Attack Leviathan"]\10 or Settings["Auto Sea Event"]\10 or Settings["Auto Upgrade Race V2-V3"]\10 or Settings["Auto Trial"]\10 or Settings["Auto Aimbot"]\10 or Settings["Auto Shipwright"]\10 )\10 then\10 if #Args == 1 and typeof(Args[1]) == "Vector3" then\10 Args[1] = AimPos.Position\10 end\10 if #Args == 1 and typeof(Args[1]) == "CFrame" then\10 Args[1] = AimPos\10 end\10 end\10 return OldNameCall(self, unpack(Args))\10end)\10setreadonly(MT, true)\10'
)()
x = game:GetService("RunService")
runAsync = require(game.ReplicatedStorage.Util.runAsync)
Spinner = require(game:GetService("ReplicatedStorage").Controllers.UI.Spinner)
SharedGachaUtil = require(game.ReplicatedStorage.Modules.Gacha.SharedGachaUtil)
TextUtil = require(game.ReplicatedStorage.Modules.Util.TextUtil)
if not getgenv().BananaCatMainLoop then
	getgenv().BananaCatMainLoop = true
	lastHopTick = tick()
	lastFruitTick = tick()
	x.RenderStepped:Connect(function()
		pcall(function()
			sethiddenproperty(t, "SimulationRadius", 5000)
		end)
		if tick() - lastHopTick >= 500 then
			lastHopTick = tick()
			pcall(function()
				writefile("Banana Cat Hub/Jobid.json", HttpService:JSONEncode({}))
			end)
		end
		pcall(function()
			if Settings["Auto Aimbot"] then
				local T = if Settings["Select Method Aimbot"] == "Select Player"
					then workspace.Characters[Settings["Select Player PVP"]]
					else (ClosestPartaimbot())
				if T and (T:FindFirstChild("HumanoidRootPart")) then
					local b = workspace.CurrentCamera
					G.Hit = T.HumanoidRootPart.CFrame
					G.Target = T
					getgenv().AimPos = CFrame.new(
						T.HumanoidRootPart.Position,
						T.HumanoidRootPart.Position + T.HumanoidRootPart.Velocity / 0.5
					)
				end
			end
			local T = t.Character:FindFirstChild("HumanoidRootPart")
			if T and (T:FindFirstChild("FloatForce")) and not TweenManager.currentTween then
				if not ToggleNoclip() or tick() - k.LastCall > 2 then
					TweenManager.CancelCurrent()
				end
			end
			if ToggleNoclip() or Settings.Noclip then
				local T, b, a = next, t.Character:GetDescendants()
				for s, s in T, b, a do
					if (s:IsA("MeshPart") or (s:IsA("Part"))) and s.CanCollide then
						s.CanCollide = false
					end
				end
			end
		end)
		task.spawn(function()
			if Settings["Change WalkSpeed"] then
				t.Character.Humanoid.WalkSpeed = Settings["Input WalkSpeed"] or 16
			end
			if Settings["Change JumpPower"] then
				t.Character.Humanoid.JumpPower = Settings["Input JumpPower"] or 50
			end
		end)
		if tick() - lastFruitTick >= 0.5 then
			lastFruitTick = tick()
			local T, T = pcall(function()
				if Settings["Random Devil Fruit"] then
					if
						not game:GetService("Players").LocalPlayer.PlayerGui:FindFirstChild("SpinnerWindow")
						or not game:GetService("Players").LocalPlayer.PlayerGui:FindFirstChild("SpinnerWindow").Enabled
					then
						RandomFruit()
					elseif
						game:GetService("Players").LocalPlayer.PlayerGui:FindFirstChild("SpinnerWindow").Enabled
						and game:GetService("Players").LocalPlayer.PlayerGui.SpinnerWindow.AboveSpinner.Navigation.CloseButton.Visible
					then
						Spinner:Close()
					end
				end
				if Settings["Auto Trade Bone"] then
					L.Remotes.CommF_:InvokeServer("Bones", "Buy", 1, 1)
				end
				if Settings["Buy Blox Fruit Sniper Shop"] then
					BuyFruitShop()
				end
				if Settings["Auto Store Fruit"] then
					StoreFruit(t.Backpack)
					StoreFruit(t.Character)
				end
				if Settings["Auto Awake Fruit"] then
					L.Remotes.CommF_:InvokeServer("Awakener", "Check")
					L.Remotes.CommF_:InvokeServer("Awakener", "Awaken")
				end
				if Settings["Auto Buy Legendary Sword"] then
					L.Remotes.CommF_:InvokeServer("LegendarySwordDealer", "2")
					if Settings["Hop Server [ Haki color or Legendary Sword]"] then
						local b = CheckSwordLegendary()
						if b then
							SpecialHop(b)
						else
							A.CreateNoti({ Title = "Banana Cat Hub", Desc = "Full Sword Legendary", ShowTime = 5 })
						end
					end
				end
				if Settings["Auto Buy Haki Color"] then
					L.Remotes.CommF_:InvokeServer("ColorsDealer", "2")
					if Settings["Hop Server [ Haki color or Legendary Sword]"] then
						HopServer()
					end
				end
			end)
			if T then
				print(T)
			end
		end
	end)
end
getgenv().__BF_LOADED = true
