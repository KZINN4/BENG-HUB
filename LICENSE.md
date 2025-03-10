local Players = game:GetService("Players")
local ReplicatedStorage = game:GetService("ReplicatedStorage")

local player = Players.LocalPlayer

-- Função para puxar o peixe instantaneamente
local function InstantCatch()
    local fishingEvent = ReplicatedStorage:FindFirstChild("FishingEvent") -- Ajuste conforme necessário
    if fishingEvent then
        fishingEvent:FireServer("CatchInstant") 
    end
end

-- Função para encantar qualquer relíquia automaticamente
local function EnchantRelic()
    local enchantEvent = ReplicatedStorage:FindFirstChild("EnchantRelicEvent") -- Ajuste conforme necessário
    if enchantEvent then
        enchantEvent:FireServer("MaxEnchant") 
    end
end

-- Conectando a eventos para ativar as funções
while wait(0.1) do
    InstantCatch() -- Puxa o peixe instantaneamente
    EnchantRelic() -- Encanta qualquer relíquia automaticamente
end
