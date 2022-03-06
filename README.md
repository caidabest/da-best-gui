-- Gui to Lua
-- Version: 3.2

-- Instances:

local ScreenGui = Instance.new("ScreenGui")
local caighe = Instance.new("Frame")
local TextButton = Instance.new("TextButton")
local TextLabel = Instance.new("TextLabel")

--Properties:

ScreenGui.Parent = game.Players.LocalPlayer:WaitForChild("PlayerGui")

caighe.Name = "caighe"
caighe.Parent = ScreenGui
caighe.BackgroundColor3 = Color3.fromRGB(0, 0, 0)
caighe.Position = UDim2.new(0.059880238, 0, 0.0345454551, 0)
caighe.Size = UDim2.new(0, 198, 0, 100)

TextButton.Parent = ScreenGui
TextButton.BackgroundColor3 = Color3.fromRGB(0, 255, 255)
TextButton.Position = UDim2.new(0.123752497, 0, 0.105454542, 0)
TextButton.Size = UDim2.new(0, 137, 0, 40)
TextButton.Font = Enum.Font.SourceSans
TextButton.Text = "Auto Farm"
TextButton.TextColor3 = Color3.fromRGB(0, 0, 0)
TextButton.TextSize = 14.000
TextButton.MouseButton1Down:connect(function()
	Scripthere
end) 

TextLabel.Parent = ScreenGui
TextLabel.BackgroundColor3 = Color3.fromRGB(183, 255, 49)
TextLabel.Position = UDim2.new(0.123752497, 0, 0.0345454551, 0)
TextLabel.Size = UDim2.new(0, 138, 0, 24)
TextLabel.Font = Enum.Font.SourceSans
TextLabel.Text = "make by cai"
TextLabel.TextColor3 = Color3.fromRGB(0, 0, 0)
TextLabel.TextSize = 14.000
-- Scripts:

local function ZMXW_fake_script() -- TextButton.Script 
	local script = Instance.new('Script', TextButton)

	--// Services
	local players = game:GetService("Players")
	
	--// Workspace
	local stages = workspace:WaitForChild("BoatStages"):WaitForChild("NormalStages")
	local penguin, gold = workspace:WaitForChild("ChangeCharacter"), workspace:WaitForChild("ClaimRiverResultsGold")
	
	--// Other
	local client = players.LocalPlayer
	
	--// Main
	---------
	_G.Busy = true
	while _G.Busy do
		local bodyVelocity = Instance.new("BodyVelocity")
		bodyVelocity.Velocity = Vector3.new(0, -4, 0)
		bodyVelocity.Parent = client.Character.HumanoidRootPart
	
		for i = 1, 9 do
			if not client.Character or not client.Character:FindFirstChild("Humanoid") then
				repeat wait() until client.Character and client.Character:FindFirstChild("Humanoid")
			end
	
			client.Character.HumanoidRootPart.CFrame = stages["CaveStage"..i].DarknessPart.CFrame wait(0.1)
	
			if not _G.Busy then
				client.Character.Humanoid.Health = 0
				exit(0)
			end
	
			if i == 1 then
				wait(1.5)
			else
				wait(1.8)
			end
	
			gold:FireServer()
		end
	
		penguin:FireServer("PenguinCharacter")
		client.Character:Remove()
	
		repeat wait() 
		until client.Character and client.Character:FindFirstChild("HumanoidRootPart")
	
	
end
coroutine.wrap(ZMXW_fake_script)()
local function YLMQU_fake_script() -- ScreenGui.Script 
	local script = Instance.new('Script', ScreenGui)

	frame = script.Parent.caighe
	frame.Draggable = true
	frame.Active = true
	frame.Selectable = true
end
coroutine.wrap(YLMQU_fake_script)()
