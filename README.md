local Plr = game.Players.LocalPlayer
local ReplicatedStorage = game:GetService("ReplicatedStorage")
local Workspace = game:GetService("Workspace")
local TweenService = game:GetService("TweenService")

-- Utilidades
function TweenTo(pos)
    local char = Plr.Character
    if char and char:FindFirstChild("HumanoidRootPart") then
        local tween = TweenService:Create(char.HumanoidRootPart, TweenInfo.new((char.HumanoidRootPart.Position - pos).Magnitude/300, Enum.EasingStyle.Linear), {CFrame = CFrame.new(pos)})
        tween:Play()
        tween.Completed:Wait()
    end
end

function GetEnemy()
    for _, mob in pairs(Workspace.Enemies:GetChildren()) do
        if mob:FindFirstChild("HumanoidRootPart") and mob:FindFirstChild("Humanoid") and mob.Humanoid.Health > 0 then
            return mob
        end
    end
    return nil
end

function EquipWeapon()
    for i,v in pairs(Plr.Backpack:GetChildren()) do
        if v:IsA("Tool") and string.find(v.Name, "Katana")
