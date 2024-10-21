-- Script para encontrar Esferas do Dragão em Dragon Ball Rage

local locais = {
    Vector3.new(100, 0, 100), -- Ajuste as coordenadas conforme necessário
    Vector3.new(-100, 0, -100),
    Vector3.new(200, 0, 200),
    Vector3.new(-200, 0, 200),
}

local player = game.Players.LocalPlayer
local character = player.Character or player.CharacterAdded:Wait()

local function verificarEsferas()
    for _, localizacao in ipairs(locais) do
        local esfera = workspace:FindFirstChild("DragonBall") -- Nome do objeto da esfera
        if esfera and (esfera.Position - character.HumanoidRootPart.Position).magnitude < 50 then
            print("Esfera do Dragão encontrada em: " .. tostring(localizacao))
            -- Aqui você pode adicionar código para coletar a esfera, se necessário
        end
    end
end

while wait(5) do -- Verifica a cada 5 segundos
    verificarEsferas()
end
