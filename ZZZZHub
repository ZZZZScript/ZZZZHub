-- ============================================
-- BRAINROT DUELS SCRIPT
-- ============================================

local Players = game:GetService("Players")
local RunService = game:GetService("RunService")
local UserInputService = game:GetService("UserInputService")
local player = Players.LocalPlayer

-- ========== CONFIGURAÇÕES ==========
local config = {
    antiRagdoll = false,
    speedEnabled = false,
    speedValue = 50,
    autoGrab = false
}

-- ========== CRIAR GUI ==========
local gui = Instance.new("ScreenGui")
gui.Name = "BrainrotUI"
gui.ResetOnSpawn = false
gui.Parent = player:WaitForChild("PlayerGui")

local mainFrame = Instance.new("Frame")
mainFrame.Size = UDim2.new(0, 250, 0, 200)
mainFrame.Position = UDim2.new(0.5, -125, 0.5, -100)
mainFrame.BackgroundColor3 = Color3.fromRGB(20, 20, 25)
mainFrame.BackgroundTransparency = 0.1
mainFrame.Visible = true
mainFrame.Parent = gui
Instance.new("UICorner", mainFrame).CornerRadius = UDim.new(0, 12)

-- Título
local title = Instance.new("TextLabel")
title.Size = UDim2.new(1, 0, 0, 30)
title.Position = UDim2.new(0, 0, 0, 0)
title.Text = "🧠 BRAINROT DUELS"
title.TextColor3 = Color3.fromRGB(255, 255, 255)
title.BackgroundTransparency = 1
title.Font = Enum.Font.GothamBold
title.TextSize = 14
title.Parent = mainFrame

-- ========== ANTI RAGDOLL ==========
local antiRagdollBtn = Instance.new("TextButton")
antiRagdollBtn.Size = UDim2.new(0.9, 0, 0, 35)
antiRagdollBtn.Position = UDim2.new(0.05, 0, 0, 40)
antiRagdollBtn.Text = "🛡️ Anti Ragdoll: OFF"
antiRagdollBtn.TextColor3 = Color3.fromRGB(255, 255, 255)
antiRagdollBtn.BackgroundColor3 = Color3.fromRGB(40, 40, 50)
antiRagdollBtn.Font = Enum.Font.GothamBold
antiRagdollBtn.TextSize = 12
antiRagdollBtn.Parent = mainFrame
Instance.new("UICorner", antiRagdollBtn).CornerRadius = UDim.new(0, 6)

-- ========== SPEED ==========
local speedFrame = Instance.new("Frame")
speedFrame.Size = UDim2.new(0.9, 0, 0, 50)
speedFrame.Position = UDim2.new(0.05, 0, 0, 85)
speedFrame.BackgroundColor3 = Color3.fromRGB(40, 40, 50)
speedFrame.Parent = mainFrame
Instance.new("UICorner", speedFrame).CornerRadius = UDim.new(0, 6)

local speedLabel = Instance.new("TextLabel")
speedLabel.Size = UDim2.new(0.6, 0, 0, 20)
speedLabel.Position = UDim2.new(0.05, 0, 0.1, 0)
speedLabel.Text = "⚡ Speed: OFF"
speedLabel.TextColor3 = Color3.fromRGB(255, 255, 255)
speedLabel.BackgroundTransparency = 1
speedLabel.Font = Enum.Font.GothamBold
speedLabel.TextSize = 11
speedLabel.TextXAlignment = Enum.TextXAlignment.Left
speedLabel.Parent = speedFrame

local speedValue = Instance.new("TextLabel")
speedValue.Size = UDim2.new(0.3, 0, 0, 20)
speedValue.Position = UDim2.new(0.65, 0, 0.1, 0)
speedValue.Text = "50"
speedValue.TextColor3 = Color3.fromRGB(100, 200, 255)
speedValue.BackgroundTransparency = 1
speedValue.Font = Enum.Font.GothamBold
speedValue.TextSize = 11
speedValue.TextXAlignment = Enum.TextXAlignment.Right
speedValue.Parent = speedFrame

local speedSlider = Instance.new("Frame")
speedSlider.Size = UDim2.new(0.9, 0, 0, 4)
speedSlider.Position = UDim2.new(0.05, 0, 0.7, 0)
speedSlider.BackgroundColor3 = Color3.fromRGB(80, 80, 90)
speedSlider.Parent = speedFrame
Instance.new("UICorner", speedSlider).CornerRadius = UDim.new(1, 0)

local speedFill = Instance.new("Frame")
speedFill.Size = UDim2.new(0.2, 0, 1, 0)
speedFill.BackgroundColor3 = Color3.fromRGB(100, 150, 255)
speedFill.Parent = speedSlider
Instance.new("UICorner", speedFill).CornerRadius = UDim.new(1, 0)

local speedKnob = Instance.new("TextButton")
speedKnob.Size = UDim2.new(0, 12, 0, 12)
speedKnob.Position = UDim2.new(0.2, -6, 0.5, -6)
speedKnob.BackgroundColor3 = Color3.fromRGB(200, 200, 255)
speedKnob.Text = ""
speedKnob.Parent = speedSlider
Instance.new("UICorner", speedKnob).CornerRadius = UDim.new(1, 0)

local speedBtn = Instance.new("TextButton")
speedBtn.Size = UDim2.new(0.2, 0, 0, 22)
speedBtn.Position = UDim2.new(0.75, 0, 0.1, 20)
speedBtn.Text = "ON/OFF"
speedBtn.TextColor3 = Color3.fromRGB(255, 255, 255)
speedBtn.BackgroundColor3 = Color3.fromRGB(60, 60, 70)
speedBtn.Font = Enum.Font.GothamBold
speedBtn.TextSize = 10
speedBtn.Parent = speedFrame
Instance.new("UICorner", speedBtn).CornerRadius = UDim.new(0, 4)

-- ========== AUTO GRAB ==========
local autoGrabBtn = Instance.new("TextButton")
autoGrabBtn.Size = UDim2.new(0.9, 0, 0, 35)
autoGrabBtn.Position = UDim2.new(0.05, 0, 0, 145)
autoGrabBtn.Text = "🎯 Auto Grab: OFF"
autoGrabBtn.TextColor3 = Color3.fromRGB(255, 255, 255)
autoGrabBtn.BackgroundColor3 = Color3.fromRGB(40, 40, 50)
autoGrabBtn.Font = Enum.Font.GothamBold
autoGrabBtn.TextSize = 12
autoGrabBtn.Parent = mainFrame
Instance.new("UICorner", autoGrabBtn).CornerRadius = UDim.new(0, 6)

-- Fechar
local closeBtn = Instance.new("TextButton")
closeBtn.Size = UDim2.new(0, 25, 0, 25)
closeBtn.Position = UDim2.new(1, -30, 0, 5)
closeBtn.Text = "X"
closeBtn.TextColor3 = Color3.fromRGB(255, 255, 255)
closeBtn.BackgroundTransparency = 1
closeBtn.Font = Enum.Font.GothamBold
closeBtn.TextSize = 14
closeBtn.Parent = mainFrame

-- Botão flutuante para abrir/fechar
local toggleBtn = Instance.new("TextButton")
toggleBtn.Size = UDim2.new(0, 50, 0, 50)
toggleBtn.Position = UDim2.new(0, 10, 0.8, 0)
toggleBtn.Text = "🧠"
toggleBtn.TextScaled = true
toggleBtn.BackgroundColor3 = Color3.fromRGB(30, 30, 40)
toggleBtn.Parent = gui
Instance.new("UICorner", toggleBtn).CornerRadius = UDim.new(0, 25)

-- ========== FUNÇÕES ==========

-- Anti Ragdoll
local function aplicarAntiRagdoll()
    if config.antiRagdoll then
        local character = player.Character
        if character then
            local humanoid = character:FindFirstChildOfClass("Humanoid")
            if humanoid then
                -- Impede ragdoll (reverte estado)
                if humanoid.PlatformStand or humanoid.Sit then
                    humanoid.PlatformStand = false
                    humanoid.Sit = false
                end
                -- Força estado normal
                humanoid.AutoRotate = true
            end
        end
    end
end

-- Speed
local function aplicarSpeed()
    if config.speedEnabled then
        local character = player.Character
        if character then
            local humanoid = character:FindFirstChildOfClass("Humanoid")
            if humanoid then
                humanoid.WalkSpeed = config.speedValue
            end
        end
    end
end

-- Auto Grab Brainrot
local function autoGrabBrainrot()
    if not config.autoGrab then return end
    
    local character = player.Character
    if not character then return end
    
    local rootPart = character:FindFirstChild("HumanoidRootPart")
    if not rootPart then return end
    
    -- Procura pelo Brainrot (ajuste o nome conforme o jogo)
    for _, obj in pairs(workspace:GetDescendants()) do
        if obj:IsA("BasePart") and obj.Parent then
            local nome = obj.Name:lower()
            -- Possíveis nomes do brainrot no jogo
            if nome:find("brain") or nome:find("rot") or nome:find("pickup") or nome:find("orb") or nome:find("token") then
                -- Verifica se está perto
                local distance = (obj.Position - rootPart.Position).Magnitude
                if distance < 15 then
                    -- Move em direção ao item
                    local direction = (obj.Position - rootPart.Position).Unit
                    rootPart.Velocity = direction * 50
                    
                    -- Se estiver muito perto, toca no item
                    if distance < 5 then
                        firetouchinterest(rootPart, obj, 0)
                        firetouchinterest(rootPart, obj, 1)
                    end
                end
            end
        end
    end
end

-- Slider Speed
local dragging = false
local function updateSpeed(inputPos)
    local sliderPos = speedSlider.AbsolutePosition.X
    local sliderWidth = speedSlider.AbsoluteSize.X
    local percent = math.clamp((inputPos - sliderPos) / sliderWidth, 0, 1)
    local newValue = math.floor(26 + (200 - 26) * percent)
    
    speedFill.Size = UDim2.new(percent, 0, 1, 0)
    speedKnob.Position = UDim2.new(percent, -6, 0.5, -6)
    speedValue.Text = tostring(newValue)
    config.speedValue = newValue
    
    if config.speedEnabled then
        aplicarSpeed()
    end
end

speedKnob.MouseButton1Down:Connect(function()
    dragging = true
    local connection
    connection = UserInputService.InputChanged:Connect(function(input)
        if dragging and input.UserInputType == Enum.UserInputType.MouseMovement then
            updateSpeed(input.Position.X)
        end
    end)
    UserInputService.InputEnded:Connect(function(input)
        if input.UserInputType == Enum.UserInputType.MouseButton1 then
            dragging = false
            connection:Disconnect()
        end
    end)
end)

-- ========== EVENTOS DOS BOTÕES ==========

antiRagdollBtn.MouseButton1Click:Connect(function()
    config.antiRagdoll = not config.antiRagdoll
    antiRagdollBtn.Text = config.antiRagdoll and "🛡️ Anti Ragdoll: ON" or "🛡️ Anti Ragdoll: OFF"
    antiRagdollBtn.BackgroundColor3 = config.antiRagdoll and Color3.fromRGB(80, 120, 80) or Color3.fromRGB(40, 40, 50)
end)

speedBtn.MouseButton1Click:Connect(function()
    config.speedEnabled = not config.speedEnabled
    speedLabel.Text = config.speedEnabled and "⚡ Speed: ON" or "⚡ Speed: OFF"
    speedBtn.Text = config.speedEnabled and "ON ✅" or "OFF ❌"
    speedBtn.BackgroundColor3 = config.speedEnabled and Color3.fromRGB(80, 120, 80) or Color3.fromRGB(60, 60, 70)
    
    if not config.speedEnabled then
        local character = player.Character
        if character then
            local humanoid = character:FindFirstChildOfClass("Humanoid")
            if humanoid then
                humanoid.WalkSpeed = 16
            end
        end
    else
        aplicarSpeed()
    end
end)

autoGrabBtn.MouseButton1Click:Connect(function()
    config.autoGrab = not config.autoGrab
    autoGrabBtn.Text = config.autoGrab and "🎯 Auto Grab: ON" or "🎯 Auto Grab: OFF"
    autoGrabBtn.BackgroundColor3 = config.autoGrab and Color3.fromRGB(80, 120, 80) or Color3.fromRGB(40, 40, 50)
end)

-- Abrir/fechar menu
local menuAberto = true
toggleBtn.MouseButton1Click:Connect(function()
    menuAberto = not menuAberto
    mainFrame.Visible = menuAberto
end)

closeBtn.MouseButton1Click:Connect(function()
    mainFrame.Visible = false
    menuAberto = false
end)

-- Arrastar menu
local draggingMenu = false
local dragStart, menuStart

mainFrame.InputBegan:Connect(function(input)
    if input.UserInputType == Enum.UserInputType.MouseButton1 then
        draggingMenu = true
        dragStart = input.Position
        menuStart = mainFrame.Position
    end
end)

mainFrame.InputEnded:Connect(function(input)
    if input.UserInputType == Enum.UserInputType.MouseButton1 then
        draggingMenu = false
    end
end)

UserInputService.InputChanged:Connect(function(input)
    if draggingMenu and input.UserInputType == Enum.UserInputType.MouseMovement then
        local delta = input.Position - dragStart
        mainFrame.Position = UDim2.new(menuStart.X.Scale, menuStart.X.Offset + delta.X, menuStart.Y.Scale, menuStart.Y.Offset + delta.Y)
    end
end)

-- ========== LOOP PRINCIPAL ==========
spawn(function()
    while true do
        aplicarAntiRagdoll()
        aplicarSpeed()
        autoGrabBrainrot()
        task.wait(0.1)
    end
end)

-- Evento de personagem adicionado
player.CharacterAdded:Connect(function()
    task.wait(1)
    aplicarSpeed()
end)

print("✅ Brainrot Duels Script Carregado!")
print("⚡ Speed: 26-200 | 🛡️ Anti Ragdoll | 🎯 Auto Grab")