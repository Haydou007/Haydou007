-- Script para teletransportar até as Esferas do Dragão em Dragon Ball Rage

local player = game.Players.LocalPlayer
local character = player.Character or player.CharacterAdded:Wait()

local function teleportToEsfera()
    for _, esfera in ipairs(workspace:GetChildren()) do
        if esfera.Name == "DragonBall" and esfera:IsA("Part") then
            character.HumanoidRootPart.CFrame = esfera.CFrame
            print("Teleportado para a Esfera do Dragão!")
            return
        end
    end
    print("Nenhuma Esfera do Dragão encontrada.")
end

-- Executa a função de teletransporte
teleportToEsfera()
