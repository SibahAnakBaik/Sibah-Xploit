-- WHITELIST USERNAME
local Whitelist = {
    "Asdd5644",
    "FATONGJLS",
    "ZADa_62849",
    "NewPlayer29339",
    "mmmjnj",
    "teingsaha_123",
    "Patrickstarnibos"
    "Rezz_8850" 
}

local Players = game:GetService("Players")
local LocalPlayer = Players.LocalPlayer

local function isWhitelisted(name)
    for _, allowed in ipairs(Whitelist) do
        if string.lower(name) == string.lower(allowed) then
            return true
        end
    end
    return false
end

-- welcome gui
local PlayerGui = LocalPlayer:WaitForChild("PlayerGui")

local WelcomeGUI = Instance.new("ScreenGui")
WelcomeGUI.Name = "WelcomeGUI"
WelcomeGUI.ResetOnSpawn = false
WelcomeGUI.Parent = PlayerGui

local Frame = Instance.new("Frame")
Frame.Size = UDim2.new(0.75, 0, 0.45, 0)
Frame.Position = UDim2.new(0.125, 0, 0.275, 0)
Frame.BackgroundColor3 = Color3.fromRGB(20, 20, 20)
Frame.BorderSizePixel = 0
Frame.Parent = WelcomeGUI
Frame.Active = true

local Corner = Instance.new("UICorner")
Corner.CornerRadius = UDim.new(0, 25)
Corner.Parent = Frame

local Title = Instance.new("TextLabel")
Title.Parent = Frame
Title.BackgroundTransparency = 1
Title.Position = UDim2.new(0, 0, 0.06, 0)
Title.Size = UDim2.new(1, 0, 0.28, 0)
Title.Text = "👋 Welcome Back Bro!"
Title.Font = Enum.Font.GothamBold
Title.TextScaled = true
Title.TextColor3 = Color3.fromRGB(0, 200, 255)

local Sub = Instance.new("TextLabel")
Sub.Parent = Frame
Sub.BackgroundTransparency = 1
Sub.Position = UDim2.new(0, 0, 0.38, 0)
Sub.Size = UDim2.new(1, 0, 0.28, 0)
Sub.Text = LocalPlayer.Name .. " kamu terdaftar di database"
Sub.Font = Enum.Font.Gotham
Sub.TextScaled = true
Sub.TextColor3 = Color3.fromRGB(255, 255, 255)

local OK = Instance.new("TextButton")
OK.Parent = Frame
OK.BackgroundColor3 = Color3.fromRGB(0, 200, 255)
OK.Size = UDim2.new(0.5, 0, 0.22, 0)
OK.Position = UDim2.new(0.25, 0, 0.72, 0)
OK.Text = "Continue "
OK.Font = Enum.Font.GothamBold
OK.TextScaled = true
OK.TextColor3 = Color3.fromRGB(20, 20, 20)

local OKCorner = Instance.new("UICorner")
OKCorner.CornerRadius = UDim.new(0, 16)
OKCorner.Parent = OK

OK.MouseButton1Click:Connect(function()
    WelcomeGUI:Destroy()
end)

task.delay(120, function()
    if WelcomeGUI then WelcomeGUI:Destroy() end
end)

if not isWhitelisted(LocalPlayer.Name) then
    local Screen = Instance.new("ScreenGui")
    Screen.Parent = PlayerGui
    Screen.IgnoreGuiInset = true

    local Frame = Instance.new("Frame", Screen)
    Frame.Size = UDim2.new(1,0,1,0)
    Frame.BackgroundColor3 = Color3.fromRGB(0, 0, 0)

    local Text = Instance.new("TextLabel", Frame)
    Text.Size = UDim2.new(1,0,0.2,0)
    Text.Position = UDim2.new(0,0,0.4,0)
    Text.BackgroundTransparency = 1
    Text.Font = Enum.Font.GothamBold
    Text.TextColor3 = Color3.fromRGB(255,60,60)
    Text.TextScaled = true
    Text.Text = "Script Loaded pls wait"

    task.wait(3)
    LocalPlayer:Kick("You're not authorized to use this script")
    return
end

-- gui
local Gui = Instance.new("ScreenGui")
Gui.Name = "Gui"
Gui.Parent = PlayerGui
Gui.ZIndexBehavior = Enum.ZIndexBehavior.Sibling

local Main = Instance.new("Frame")
Main.Name = "Main"
Main.Parent = Gui
Main.BackgroundColor3 = Color3.fromRGB(25, 25, 25)
Main.Position = UDim2.new(0.36, 0, 0.45, 0)
Main.Size = UDim2.new(0.24, 0, 0.17, 0)
Main.Active = true
Main.Draggable = true

local UICorner = Instance.new("UICorner")
UICorner.CornerRadius = UDim.new(0, 12)
UICorner.Parent = Main

local UIStroke = Instance.new("UIStroke")
UIStroke.Thickness = 2
UIStroke.Color = Color3.fromRGB(0, 200, 255)
UIStroke.ApplyStrokeMode = Enum.ApplyStrokeMode.Border
UIStroke.Parent = Main

local UIGradient = Instance.new("UIGradient")
UIGradient.Color = ColorSequence.new{
    ColorSequenceKeypoint.new(0, Color3.fromRGB(50,50,50)),
    ColorSequenceKeypoint.new(1, Color3.fromRGB(25,25,25))
}
UIGradient.Rotation = 90
UIGradient.Parent = Main

local Label = Instance.new("TextLabel")
Label.Parent = Main
Label.BackgroundTransparency = 1
Label.Size = UDim2.new(1, 0, 0.2, 0)
Label.Font = Enum.Font.GothamBold
Label.Text = "Lock PlayerV4 | by: sibah_txt"
Label.TextColor3 = Color3.fromRGB(0, 200, 255)
Label.TextScaled = true

local Box = Instance.new("TextBox")
Box.Parent = Main
Box.BackgroundColor3 = Color3.fromRGB(45, 45, 45)
Box.Position = UDim2.new(0.08, 0, 0.28, 0)
Box.Size = UDim2.new(0.84, 0, 0.32, 0)
Box.Font = Enum.Font.Gotham
Box.PlaceholderText = "Pl4yer here"
Box.PlaceholderColor3 = Color3.fromRGB(160, 160, 160)
Box.Text = ""
Box.TextColor3 = Color3.fromRGB(255, 255, 255)
Box.TextScaled = true

local BoxCorner = Instance.new("UICorner")
BoxCorner.CornerRadius = UDim.new(0, 8)
BoxCorner.Parent = Box

local Button = Instance.new("TextButton")
Button.Parent = Main
Button.BackgroundColor3 = Color3.fromRGB(0, 200, 255)
Button.Position = UDim2.new(0.18, 0, 0.66, 0)
Button.Size = UDim2.new(0.64, 0, 0.27, 0)
Button.Font = Enum.Font.GothamBold
Button.Text = "Lock | Off"
Button.TextColor3 = Color3.fromRGB(25, 25, 25)
Button.TextScaled = true

local ButtonCorner = Instance.new("UICorner")
ButtonCorner.CornerRadius = UDim.new(0, 8)
ButtonCorner.Parent = Button

-- fuction
local RunService = game:GetService("RunService")
local Workspace = game:GetService("Workspace")
local UserInputService = game:GetService("UserInputService")

Workspace.FallenPartsDestroyHeight = 0/0

local character
local humanoidRootPart

local mainStatus = true
UserInputService.InputBegan:Connect(function(input, gameProcessedEvent)
	if input.KeyCode == Enum.KeyCode.RightControl and not gameProcessedEvent then
		mainStatus = not mainStatus
		Main.Visible = mainStatus
	end
end)

local Folder = Instance.new("Folder", Workspace)
local Part = Instance.new("Part", Folder)
local Attachment1 = Instance.new("Attachment", Part)
Part.Anchored = true
Part.CanCollide = false
Part.Transparency = 1

if not getgenv().Network then
	getgenv().Network = {
		BaseParts = {},
		Velocity = Vector3.new(500, 500, 500)
	}

	Network.RetainPart = function(Part)
		if Part:IsA("BasePart") and Part:IsDescendantOf(Workspace) then
			table.insert(Network.BaseParts, Part)
			Part.CustomPhysicalProperties = PhysicalProperties.new(0, 0, 0, 0, 0)
			Part.CanCollide = false
		end
	end

	local function EnablePartControl()
		LocalPlayer.ReplicationFocus = Workspace
		RunService.Heartbeat:Connect(function()
			sethiddenproperty(LocalPlayer, "SimulationRadius", math.huge)
			for _, Part in pairs(Network.BaseParts) do
				if Part:IsDescendantOf(Workspace) then
					Part.Velocity = Network.Velocity
				end
			end
		end)
	end

	EnablePartControl()
end

local affectedParts = {}

local function ForcePart(v)
	if v:IsA("BasePart") and not v.Anchored and not v.Parent:FindFirstChildOfClass("Humanoid")
		and not v.Parent:FindFirstChild("Head") and v.Name ~= "Handle" then

		for _, x in ipairs(v:GetChildren()) do
			if x:IsA("BodyMover") or x:IsA("RocketPropulsion") then x:Destroy() end
		end

		v.CanCollide = false
		local Torque = Instance.new("Torque", v)
		local AlignPosition = Instance.new("AlignPosition", v)
		local Attachment2 = Instance.new("Attachment", v)
		
		Torque.Torque = Vector3.new(50000000, 50000000, 50000000)
		Torque.Attachment0 = Attachment2

		AlignPosition.MaxForce = math.huge
		AlignPosition.Responsiveness = 500
		AlignPosition.Attachment0 = Attachment2
		AlignPosition.Attachment1 = Attachment1
		
		-- Spin awal edan
		pcall(function()
			v.AssemblyAngularVelocity = Vector3.new(math.random(-6000, 6000), math.random(-6000, 6000), math.random(-6000, 6000))
		end)
		
		affectedParts[v] = true
	end
end

local blackHoleActive = false
local DescendantAddedConnection

local function toggleBlackHole()
	blackHoleActive = not blackHoleActive
	Button.Text = blackHoleActive and "Lock | On" or "Lock | Off"

	if blackHoleActive then
		for _, v in ipairs(Workspace:GetDescendants()) do ForcePart(v) end
		
		DescendantAddedConnection = Workspace.DescendantAdded:Connect(function(v)
			if blackHoleActive then ForcePart(v) end
		end)

		-- loop
		task.spawn(function()
			while blackHoleActive do
				Attachment1.WorldCFrame = humanoidRootPart.CFrame
				for part, _ in pairs(affectedParts) do
					if part and part.Parent then
						pcall(function()
							part.AssemblyAngularVelocity = Vector3.new(math.random(-6000, 6000), math.random(-6000, 6000), math.random(-6000, 6000))
						end)
					end
				end
				RunService.Heartbeat:Wait()
			end
		end)

	else
		if DescendantAddedConnection then DescendantAddedConnection:Disconnect() end
		affectedParts = {}
	end
end

local function getPlayer(name)
	for _, p in ipairs(Players:GetPlayers()) do
		if string.find(string.lower(p.Name), string.lower(name)) or string.find(string.lower(p.DisplayName), string.lower(name)) then
			return p
		end
	end
end

local targetPlayer = nil

task.wait(0.5)
if Box then
    Box.FocusLost:Connect(function(enterPressed)
        if enterPressed then
            targetPlayer = getPlayer(Box.Text)
            if targetPlayer then
                Box.Text = targetPlayer.Name
            end
        end
    end)
end

Button.MouseButton1Click:Connect(function()
	if targetPlayer then
		character = targetPlayer.Character or targetPlayer.CharacterAdded:Wait()
		humanoidRootPart = character:WaitForChild("HumanoidRootPart")
		toggleBlackHole()
	end
end)

-- Title Script
spawn(function()
    repeat task.wait() until LocalPlayer.Character and LocalPlayer.Character:FindFirstChild("Head")

    local RE = game:GetService("ReplicatedStorage"):WaitForChild("RE", 5)
    if not RE then return end

    local rpRemote = RE:FindFirstChild("1RPNam1eTex1t")
    if not rpRemote then return end

    local namaToxic = "LockPlayerV4 | By: sibah_txt Loaded! 🚀"

    -- Fire 
    rpRemote:FireServer("RolePlayName", namaToxic)

    -- Limit
    LocalPlayer.CharacterAdded:Connect(function()
        task.wait(1)
        pcall(function()
            rpRemote:FireServer("RolePlayName", namaToxic)
        end)
    end)

    -- Notif
    game.StarterGui:SetCore("SendNotification", {
        Title = "Plenger",
        Text = "Irenk",
        Duration = 4
    })
end)
