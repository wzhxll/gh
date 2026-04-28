-- 独立脚本：只获取铁桩（原样提取）
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
    purchase:FireServer("Iron Stake")
    game:GetService("StarterGui"):SetCore("SendNotification", {Title="获取", Text="已获取铁桩", Duration=2})
end
