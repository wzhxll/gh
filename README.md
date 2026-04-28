-- 独立脚本：获取南瓜刀 (Jack-O-Sword)
local Players = game:GetService("Players")
local lp = Players.LocalPlayer

local function getPurchaseEvent()
    local rs = game:GetService("ReplicatedStorage")
    local events = rs:FindFirstChild("Events")
    if not events then return nil end
    local customize = events:FindFirstChild("Customize")
    if not customize then return nil end
    return customize:FindFirstChild("PurchaseEvent")
end

local purchase = getPurchaseEvent()
if purchase then
    -- 南瓜刀在游戏中的内部真实名称
    purchase:FireServer("Jack-O-Sword")
    game:GetService("StarterGui"):SetCore("SendNotification", {Title="获取", Text="已获取南瓜刀", Duration=2})
end
