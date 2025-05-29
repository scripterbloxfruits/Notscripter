-- Chatmox Hub - Open Source Full Script for Blox Fruits -- Credits: Você (criador), comunidade open-source, base Rayfield UI

-- SERVICES local Players = game:GetService("Players") local ReplicatedStorage = game:GetService("ReplicatedStorage") local TeleportService = game:GetService("TeleportService") local HttpService = game:GetService("HttpService") local RunService = game:GetService("RunService") local LocalPlayer = Players.LocalPlayer local Character = LocalPlayer.Character or LocalPlayer.CharacterAdded:Wait()

-- LOAD RAYFIELD UI LIBRARY local Rayfield = loadstring(game:HttpGet('https://raw.githubusercontent.com/shlexware/Rayfield/main/source'))()

local Window = Rayfield:CreateWindow({ Name = "Chatmox Hub | Blox Fruits", LoadingTitle = "Chatmox Hub", LoadingSubtitle = "by Open Source Devs", ConfigurationSaving = { Enabled = true, FolderName = nil, FileName = "ChatmoxHub" }, Discord = { Enabled = false, Invite = "", RememberJoins = true }, KeySystem = false })

-- AUTO FARM TAB local AutoFarmTab = Window:CreateTab("Auto Farm", 4483362458) AutoFarmTab:CreateToggle({ Name = "Auto Farm NPC", CurrentValue = false, Flag = "AutoFarmNPC", Callback = function(Value) getgenv().AutoFarm = Value while getgenv().AutoFarm do task.wait()

