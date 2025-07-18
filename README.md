-- Dupe-Script✨
local player = game.Players.LocalPlayer
local char = player.Character or player.CharacterAdded:Wait()
local heldItem = nil

-- UI Setup
local screenGui = Instance.new("ScreenGui", game.CoreGui)
screenGui.Name = "DupeGUI"
local btn = Instance.new("TextButton", screenGui)
btn.Text = "Dupe"
btn.Size = UDim2.new(0, 120, 0, 40)
btn.Position = UDim2.new(0.5, -60, 0.8, 0)
btn.BackgroundColor3 = Color3.fromRGB(255, 153, 255)
btn.TextColor3 = Color3.fromRGB(255, 255, 255)
btn.TextSize = 25
btn.Font = Enum.Font.GothamBold
btn.Active = true
btn.Draggable = true
btn.BorderSizePixel = 0
btn.BackgroundTransparency = 0.1
btn.ZIndex = 10

-- Dupe Function
btn.MouseButton1Click:Connect(function()
    heldItem = char:FindFirstChildOfClass("Tool") or player.Backpack:FindFirstChildOfClass("Tool")
    if heldItem then
        local clone = heldItem:Clone()
        clone.Parent = player.Backpack
    end
end)
