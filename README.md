
-- REDZ BANANA V3
-- Script criado por Vn
-- Interface demonstrativa para Roblox Studio

local Players = game:GetService("Players")
local TweenService = game:GetService("TweenService")
local player = Players.LocalPlayer

local gui = Instance.new("ScreenGui")
gui.Name = "RedzBananaV3"
gui.ResetOnSpawn = false
gui.Parent = player:WaitForChild("PlayerGui")

local main = Instance.new("Frame")
main.Size = UDim2.fromOffset(300, 300)
main.Position = UDim2.new(0.5, -150, 0.5, -150)
main.BackgroundColor3 = Color3.fromRGB(20, 20, 24)
main.Parent = gui

Instance.new("UICorner", main).CornerRadius =
    UDim.new(0, 12)

local stroke = Instance.new("UIStroke", main)
stroke.Color = Color3.fromRGB(240, 35, 50)
stroke.Thickness = 2

local title = Instance.new("TextLabel")
title.Size = UDim2.new(1, -50, 0, 50)
title.BackgroundColor3 = Color3.fromRGB(150, 15, 30)
title.Text = "REDZ BANANA V3"
title.TextColor3 = Color3.new(1, 1, 1)
title.Font = Enum.Font.GothamBold
title.TextSize = 18
title.Parent = main

local function addToggle(name, y)
    local active = false
    local button = Instance.new("TextButton")
    button.Size = UDim2.new(1, -30, 0, 40)
    button.Position = UDim2.fromOffset(15, y)
    button.BackgroundColor3 = Color3.fromRGB(45, 45, 50)
    button.TextColor3 = Color3.new(1, 1, 1)
    button.Font = Enum.Font.GothamBold
    button.TextSize = 14
    button.Parent = main

    Instance.new("UICorner", button).CornerRadius =
        UDim.new(0, 8)

    local function refresh()
        button.Text = name .. ": " .. (active and "ON" or "OFF")
        button.BackgroundColor3 = active
            and Color3.fromRGB(190, 20, 40)
            or Color3.fromRGB(45, 45, 50)
    end

    button.Activated:Connect(function()
        active = not active
        refresh()
    end)

    refresh()
end

addToggle("Auto Farm (visual)", 65)
addToggle("Auto Chest (visual)", 115)
addToggle("Kill Aura (visual)", 165)
addToggle("Auto PvP (visual)", 215)

local credit = Instance.new("TextLabel")
credit.Size = UDim2.new(1, 0, 0, 25)
credit.Position = UDim2.fromOffset(0, 265)
credit.BackgroundTransparency = 1
credit.Text = "Script criado por Vn"
credit.TextColor3 = Color3.fromRGB(255, 80, 90)
credit.TextSize = 12
credit.Parent = main

main.Size = UDim2.fromOffset(0, 0)
TweenService:Create(
    main,
    TweenInfo.new(0.5, Enum.EasingStyle.Back),
    {Size = UDim2.fromOffset(300, 300)}
):Play()
