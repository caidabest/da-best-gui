-- Gui to Lua
-- Version: 3.2

-- Instances:

local ScreenGui = Instance.new("ScreenGui")
local Frame = Instance.new("Frame")
local bestsilentaim = Instance.new("TextButton")
local bestaimlockkkk = Instance.new("TextButton")
local TextLabel = Instance.new("TextLabel")
local TextButton = Instance.new("TextButton")

--Properties:

ScreenGui.Parent = game.Players.LocalPlayer:WaitForChild("PlayerGui")

Frame.Parent = ScreenGui
Frame.Active = true
Frame.BackgroundColor3 = Color3.fromRGB(0, 0, 0)
Frame.BorderColor3 = Color3.fromRGB(0, 0, 0)
Frame.Position = UDim2.new(0.0517462268, 0, 0.187272727, 0)
Frame.Size = UDim2.new(0, 552, 0, 378)

bestsilentaim.Name = "best silent aim"
bestsilentaim.Parent = ScreenGui
bestsilentaim.BackgroundColor3 = Color3.fromRGB(255, 255, 255)
bestsilentaim.Position = UDim2.new(0.0517462268, 0, 0.187272727, 0)
bestsilentaim.Size = UDim2.new(0, 552, 0, 86)
bestsilentaim.Font = Enum.Font.SourceSans
bestsilentaim.Text = "best silent aim"
bestsilentaim.TextColor3 = Color3.fromRGB(0, 0, 0)
bestsilentaim.TextSize = 14.000

bestaimlockkkk.Name = "best aim lockkkk"
bestaimlockkkk.Parent = ScreenGui
bestaimlockkkk.BackgroundColor3 = Color3.fromRGB(255, 255, 255)
bestaimlockkkk.Position = UDim2.new(0.044291947, 0, 0.654545486, 0)
bestaimlockkkk.Size = UDim2.new(0, 583, 0, 130)
bestaimlockkkk.Font = Enum.Font.SourceSans
bestaimlockkkk.Text = "best aimlock"
bestaimlockkkk.TextColor3 = Color3.fromRGB(0, 0, 0)
bestaimlockkkk.TextSize = 14.000

TextLabel.Parent = ScreenGui
TextLabel.BackgroundColor3 = Color3.fromRGB(255, 255, 255)
TextLabel.Position = UDim2.new(0.0517462268, 0, 0.343636364, 0)
TextLabel.Size = UDim2.new(0, 552, 0, 172)
TextLabel.Font = Enum.Font.SourceSans
TextLabel.Text = "WHO SHARE U IT KYS LMAO"
TextLabel.TextColor3 = Color3.fromRGB(0, 0, 0)
TextLabel.TextSize = 14.000

TextButton.Parent = ScreenGui
TextButton.BackgroundColor3 = Color3.fromRGB(255, 255, 255)
TextButton.Size = UDim2.new(0, 136, 0, 50)
TextButton.Font = Enum.Font.SourceSans
TextButton.Text = "caidabest open"
TextButton.TextColor3 = Color3.fromRGB(0, 0, 0)
TextButton.TextSize = 14.000

-- Scripts:

local function DNOUXY_fake_script() -- bestsilentaim.Script 
	local script = Instance.new('Script', bestsilentaim)

	
	local players = game:GetService("Players")
	local plr = players.LocalPlayer
	local mouse = plr:GetMouse()
	local camera = game.Workspace.CurrentCamera
	local teamcheck = true
	
	local function ClosestPlayerToMouse()
		local target = nil
		local dist = math.huge
		for i,v in pairs(players:GetPlayers()) do
			if v.Name ~= plr.Name then
				if v.Character and v.Character:FindFirstChild("Humanoid") and v.Character.Humanoid.Health ~= 0 and v.Character:FindFirstChild("HumanoidRootPart") and teamcheck and v.TeamColor ~= plr.TeamColor then
					local screenpoint = camera:WorldToScreenPoint(v.Character.HumanoidRootPart.Position)
					local check = (Vector2.new(mouse.X,mouse.Y)-Vector2.new(screenpoint.X,screenpoint.Y)).magnitude
	
					if check < dist then
						target  = v
						dist = check
					end
				end
			end
		end
	
		return target 
	end
	
	local mt = getrawmetatable(game)
	local namecall = mt.__namecall
	setreadonly(mt,false)
	
	mt.__namecall = function(self,...)
		local args = {...}
		local method = getnamecallmethod()
	
		if tostring(self) == "HitPart" and method == "FireServer" then
			args[1] = ClosestPlayerToMouse().Character.Head
			args[2] = ClosestPlayerToMouse().Character.Head.Position
			return self.FireServer(self, unpack(args))
		end
		return namecall(self,...)
	end
end
coroutine.wrap(DNOUXY_fake_script)()
local function OUNJ_fake_script() -- bestaimlockkkk.Script 
	local script = Instance.new('Script', bestaimlockkkk)

	-- Made by Error_IDK
	-- Version: 3.2
	
	-- Instances:
	
	local ScreenGui = Instance.new("ScreenGui")
	local Aimbot = Instance.new("Frame")
	local Title = Instance.new("TextLabel")
	local Toggle = Instance.new("TextButton")
	
	--Properties:
	
	ScreenGui.Parent = game.Players.LocalPlayer:WaitForChild("PlayerGui")
	ScreenGui.ZIndexBehavior = Enum.ZIndexBehavior.Sibling
	
	Aimbot.Name = "Aimbot"
	Aimbot.Parent = ScreenGui
	Aimbot.BackgroundColor3 = Color3.fromRGB(255, 255, 255)
	Aimbot.Position = UDim2.new(0.0599842146, 0, 0.358722359, 0)
	Aimbot.Size = UDim2.new(0, 126, 0, 152)
	
	Title.Name = "Title"
	Title.Parent = Aimbot
	Title.BackgroundColor3 = Color3.fromRGB(255, 255, 255)
	Title.Size = UDim2.new(0, 126, 0, 50)
	Title.Font = Enum.Font.SourceSans
	Title.Text = "Aimbot (Made by Error_IDK)"
	Title.TextColor3 = Color3.fromRGB(0, 0, 0)
	Title.TextSize = 13.300
	
	Toggle.Name = "Toggle"
	Toggle.Parent = Aimbot
	Toggle.BackgroundColor3 = Color3.fromRGB(255, 255, 255)
	Toggle.BorderSizePixel = 0
	Toggle.Position = UDim2.new(0, 0, 0.473684222, 0)
	Toggle.Size = UDim2.new(0, 126, 0, 50)
	Toggle.Font = Enum.Font.SourceSans
	Toggle.Text = "Off"
	Toggle.TextColor3 = Color3.fromRGB(255, 0, 0)
	Toggle.TextSize = 40.000
	
	-- Scripts:
	
	local function PNHLOYF_fake_script() -- Toggle.LocalScript 
		local script = Instance.new('LocalScript', Toggle)
	
		_G.aimbot = false
		local camera = game.Workspace.CurrentCamera
		local localplayer = game:GetService("Players").LocalPlayer
	
		script.Parent.MouseButton1Click:Connect(function()
			if _G.aimbot == false then
				_G.aimbot = true
				script.Parent.TextColor3 = Color3.fromRGB(0,170,0)
				script.Parent.Text = "On"
				function closestplayer()
					local dist = math.huge -- math.huge means a really large number, 1M+.
					local target = nil --- nil means no value
					for i,v in pairs (game:GetService("Players"):GetPlayers()) do
						if v ~= localplayer then
							if v.Character and v.Character:FindFirstChild("Head") and _G.aimbot and v.Character.Humanoid.Health > 0 then --- creating the checks
								local magnitude = (v.Character.Head.Position - localplayer.Character.Head.Position).magnitude
								if magnitude < dist then
									dist = magnitude
									target = v
								end
	
							end
						end
					end
					return target
				end
	
			else
				_G.aimbot = false
				script.Parent.TextColor3 = Color3.fromRGB(255,0,0)
				script.Parent.Text = "Off"
			end
		end)
	
		local settings = {
			keybind = Enum.UserInputType.MouseButton2
		}
	
		local UIS = game:GetService("UserInputService")
		local aiming = false --- this toggle will make it so we lock on to the person when we press our keybind
	
		UIS.InputBegan:Connect(function(inp)
			if inp.UserInputType == settings.keybind then
				aiming = true
			end
		end)
	
		UIS.InputEnded:Connect(function(inp)
			if inp.UserInputType == settings.keybind then ---- when we stop pressing the keybind it would unlock off the player
				aiming = false
			end
		end)
	
		game:GetService("RunService").RenderStepped:Connect(function()
			if aiming then
				camera.CFrame = CFrame.new(camera.CFrame.Position,closestplayer().Character.Head.Position) -- locks into the HEAD
			end
		end)
	end
	coroutine.wrap(PNHLOYF_fake_script)()
end
coroutine.wrap(OUNJ_fake_script)()
