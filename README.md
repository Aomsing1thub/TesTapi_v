local Players = game:GetService("Players")
local CoreGui = game:GetService("CoreGui")

local LocalPlayer = Players.LocalPlayer
local PlayerGui = LocalPlayer:WaitForChild("PlayerGui")

local GUI_NAME = "TestSimpleUI"

local oldGui = CoreGui:FindFirstChild(GUI_NAME) or PlayerGui:FindFirstChild(GUI_NAME)
if oldGui then
    oldGui:Destroy()
end

local screenGui = Instance.new("ScreenGui")
screenGui.Name = GUI_NAME
screenGui.ResetOnSpawn = false
screenGui.Parent = CoreGui

local shadow = Instance.new("Frame")
shadow.Name = "Shadow"
shadow.Size = UDim2.new(0, 310, 0, 176)
shadow.Position = UDim2.new(0.5, -149, 0.5, -82)
shadow.BackgroundColor3 = Color3.fromRGB(0, 0, 0)
shadow.BackgroundTransparency = 0.55
shadow.BorderSizePixel = 0
shadow.Parent = screenGui

local shadowCorner = Instance.new("UICorner")
shadowCorner.CornerRadius = UDim.new(0, 18)
shadowCorner.Parent = shadow

local mainFrame = Instance.new("Frame")
mainFrame.Name = "MainFrame"
mainFrame.Size = UDim2.new(0, 310, 0, 176)
mainFrame.Position = UDim2.new(0.5, -155, 0.5, -88)
mainFrame.BackgroundColor3 = Color3.fromRGB(24, 26, 32)
mainFrame.BorderSizePixel = 0
mainFrame.Parent = screenGui

local mainCorner = Instance.new("UICorner")
mainCorner.CornerRadius = UDim.new(0, 18)
mainCorner.Parent = mainFrame

local mainStroke = Instance.new("UIStroke")
mainStroke.Color = Color3.fromRGB(58, 66, 82)
mainStroke.Thickness = 1
mainStroke.Transparency = 0.15
mainStroke.Parent = mainFrame

local accentBar = Instance.new("Frame")
accentBar.Name = "AccentBar"
accentBar.Size = UDim2.new(1, 0, 0, 5)
accentBar.BackgroundColor3 = Color3.fromRGB(91, 140, 255)
accentBar.BorderSizePixel = 0
accentBar.Parent = mainFrame

local accentCorner = Instance.new("UICorner")
accentCorner.CornerRadius = UDim.new(0, 18)
accentCorner.Parent = accentBar

local accentMask = Instance.new("Frame")
accentMask.Size = UDim2.new(1, 0, 0, 10)
accentMask.Position = UDim2.new(0, 0, 1, -10)
accentMask.BackgroundColor3 = Color3.fromRGB(91, 140, 255)
accentMask.BorderSizePixel = 0
accentMask.Parent = accentBar

local badge = Instance.new("TextLabel")
badge.Name = "Badge"
badge.Size = UDim2.new(0, 58, 0, 22)
badge.Position = UDim2.new(0, 18, 0, 18)
badge.BackgroundColor3 = Color3.fromRGB(36, 46, 68)
badge.BorderSizePixel = 0
badge.Font = Enum.Font.GothamBold
badge.Text = "TEST"
badge.TextColor3 = Color3.fromRGB(161, 195, 255)
badge.TextSize = 11
badge.Parent = mainFrame

local badgeCorner = Instance.new("UICorner")
badgeCorner.CornerRadius = UDim.new(1, 0)
badgeCorner.Parent = badge

local title = Instance.new("TextLabel")
title.Name = "Title"
title.Size = UDim2.new(1, -112, 0, 28)
title.Position = UDim2.new(0, 18, 0, 48)
title.BackgroundTransparency = 1
title.Font = Enum.Font.GothamBold
title.Text = "Compact UI Preview"
title.TextColor3 = Color3.fromRGB(255, 255, 255)
title.TextSize = 22
title.TextXAlignment = Enum.TextXAlignment.Left
title.Parent = mainFrame

local message = Instance.new("TextLabel")
message.Name = "Message"
message.Size = UDim2.new(1, -36, 0, 44)
message.Position = UDim2.new(0, 18, 0, 80)
message.BackgroundTransparency = 1
message.Font = Enum.Font.Gotham
message.Text = "Small test window in CoreGui.\nPrint logs to console, Close removes it."
message.TextColor3 = Color3.fromRGB(197, 203, 214)
message.TextSize = 13
message.TextWrapped = true
message.TextXAlignment = Enum.TextXAlignment.Left
message.TextYAlignment = Enum.TextYAlignment.Top
message.Parent = mainFrame

local printButton = Instance.new("TextButton")
printButton.Name = "PrintButton"
printButton.Size = UDim2.new(0, 74, 0, 28)
printButton.Position = UDim2.new(0, 18, 1, -46)
printButton.BackgroundColor3 = Color3.fromRGB(78, 118, 214)
printButton.BorderSizePixel = 0
printButton.Font = Enum.Font.GothamBold
printButton.Text = "Print"
printButton.TextColor3 = Color3.fromRGB(255, 255, 255)
printButton.TextSize = 12
printButton.Parent = mainFrame

local printCorner = Instance.new("UICorner")
printCorner.CornerRadius = UDim.new(0, 10)
printCorner.Parent = printButton

local destroyButton = Instance.new("TextButton")
destroyButton.Name = "DestroyButton"
destroyButton.Size = UDim2.new(0, 74, 0, 28)
destroyButton.Position = UDim2.new(1, -92, 1, -46)
destroyButton.BackgroundColor3 = Color3.fromRGB(58, 39, 43)
destroyButton.BorderSizePixel = 0
destroyButton.Font = Enum.Font.GothamBold
destroyButton.Text = "Close"
destroyButton.TextColor3 = Color3.fromRGB(255, 214, 214)
destroyButton.TextSize = 12
destroyButton.Parent = mainFrame

local destroyCorner = Instance.new("UICorner")
destroyCorner.CornerRadius = UDim.new(0, 10)
destroyCorner.Parent = destroyButton

local destroyStroke = Instance.new("UIStroke")
destroyStroke.Color = Color3.fromRGB(116, 67, 75)
destroyStroke.Thickness = 1
destroyStroke.Parent = destroyButton

printButton.MouseButton1Click:Connect(function()
    print("Print button clicked")
end)

destroyButton.MouseButton1Click:Connect(function()
    screenGui:Destroy()
end)
