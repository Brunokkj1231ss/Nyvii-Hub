local Rayfield = loadstring(game:HttpGet('https://sirius.menu/rayfield'))()

local Window = Rayfield:CreateWindow({
   Name = "Script DC Nyvii🎶",
   Icon = 0, -- Icon in Topbar. Can use Lucide Icons (string) or Roblox Image (number). 0 to use no icon (default).
   LoadingTitle = "🎶Mapa ID Nyvii🎶",
   LoadingSubtitle = "Feito por Bruno🪐",
   Theme = "Default", -- Check https://docs.sirius.menu/rayfield/configuration/themes

   DisableRayfieldPrompts = false,
   DisableBuildWarnings = false, -- Prevents Rayfield from warning when the script has a version mismatch with the interface

   ConfigurationSaving = {
      Enabled = true,
      FolderName = nil, -- Create a custom folder for your hub/game
      FileName = "Big Hub"
   },

   Discord = {
      Enabled = false, -- Prompt the user to join your Discord server if their executor supports it
      Invite = "noinvitelink", -- The Discord invite code, do not include discord.gg/. E.g. discord.gg/ ABCD would be ABCD
      RememberJoins = true -- Set this to false to make them join the discord every time they load it up
   },

   KeySystem = false, -- Set this to true to use our key system
   KeySettings = {
      Title = "Script Staff DC",
      Subtitle = "Key System",
      Note = "No method of obtaining the key is provided", -- Use this to tell the user how to get a key
      FileName = "Key", -- It is recommended to use something unique as other scripts using Rayfield may overwrite your key file
      SaveKey = true, -- The user's key will be saved, but if you change the key, they will be unable to use your script
      GrabKeyFromSite = false, -- If this is true, set Key below to the RAW site you would like Rayfield to get the key from
      Key = {"Hello"} -- List of keys that will be accepted by the system, can be RAW file links (pastebin, github etc) or simple strings ("hello","key22")
   }
})

local Tab = Window:CreateTab("Detectar Scripts", 4483362458) -- Title, Image

local Button = Tab:CreateButton({
   Name = "Click Para Detectar",
   Callback = function()
   loadstring(game:HttpGet("https://rawscripts.net/raw/Universal-Script-Roblox-Anticheat-finder-30874"))()
   end,
})

local Button = Tab:CreateButton({
   Name = "ESP",
   Callback = function()
   local espEnabled = false -- Estado inicial

local function createESP(player)
    if player.Character and not player.Character:FindFirstChild("ESP") then
        local billboardGui = Instance.new("BillboardGui")
        billboardGui.Name = "ESP"
        billboardGui.Adornee = player.Character:FindFirstChild("HumanoidRootPart")
        billboardGui.Size = UDim2.new(0, 200, 0, 50)
        billboardGui.AlwaysOnTop = true

        local nameLabel = Instance.new("TextLabel")
        nameLabel.Size = UDim2.new(1, 0, 1, 0)
        nameLabel.Text = player.Name
        nameLabel.TextColor3 = Color3.new(1, 0, 0) -- Cor vermelha
        nameLabel.BackgroundTransparency = 1
        nameLabel.Font = Enum.Font.SourceSansBold
        nameLabel.TextSize = 14
        nameLabel.Parent = billboardGui

        billboardGui.Parent = player.Character
    end
end

local function removeESP(player)
    if player.Character and player.Character:FindFirstChild("ESP") then
        player.Character.ESP:Destroy()
    end
end

local function toggleESP()
    espEnabled = not espEnabled
    for _, player in pairs(game.Players:GetPlayers()) do
        if espEnabled then
            createESP(player)
        else
            removeESP(player)
        end
    end
end

-- Escuta a tecla "E" para alternar o ESP
game:GetService("UserInputService").InputBegan:Connect(function(input, gameProcessed)
    if not gameProcessed and input.KeyCode == Enum.KeyCode.E then
        toggleESP()
    end
end)

-- Atualiza ESP para jogadores novos
game.Players.PlayerAdded:Connect(function(player)
    player.CharacterAdded:Connect(function()
        if espEnabled then
            createESP(player)
        end
    end)
end)

-- Remove ESP quando o jogador sair
game.Players.PlayerRemoving:Connect(function(player)
    removeESP(player)
end)

   end,

   Rayfield:Notify({
   Title = "Ativar ou Desativar ESP",
   Content = "Tecla (E)",
   Duration = 7.5,
   Image = 4483362458,
})
})





















































local Button = Tab:CreateButton({
   Name = "Pulo Infito",
   Callback = function()
local player = game.Players.LocalPlayer
local character = player.Character or player.CharacterAdded:Wait()
local humanoid = character:WaitForChild("Humanoid")

local UserInputService = game:GetService("UserInputService")
local RunService = game:GetService("RunService")

local jumpEnabled = false -- Pulo infinito desativado inicialmente
local holdingJump = false -- Detecta se o jogador está segurando a tecla de pulo
local jumpTimer = 30 -- Duração do pulo infinito em segundos

-- Função para ativar o pulo infinito por 30 segundos
local function activateJump()
    jumpEnabled = true
    print("Pulo infinito ativado por 30 segundos")
    task.delay(jumpTimer, function()
        jumpEnabled = false
        print("Pulo infinito desativado automaticamente após 30 segundos")
    end)
end

-- Detecta quando o botão de pulo é pressionado
UserInputService.InputBegan:Connect(function(input, gameProcessed)
    if not gameProcessed and input.KeyCode == Enum.KeyCode.Space then
        if not holdingJump then
            holdingJump = true -- Começa a segurar o botão
            if not jumpEnabled then
                activateJump() -- Ativa o pulo infinito
            end
        end
    end
end)

-- Detecta quando o botão de pulo é solto
UserInputService.InputEnded:Connect(function(input, gameProcessed)
    if input.KeyCode == Enum.KeyCode.Space then
        holdingJump = false -- Solta o botão
    end
end)

-- Escuta as solicitações de salto enquanto o botão está sendo segurado
RunService.RenderStepped:Connect(function()
    if jumpEnabled and holdingJump then
        humanoid:ChangeState(Enum.HumanoidStateType.Jumping)
    end
end)

   end,
})

local Tab = Window:CreateTab("GHosT HUB👻", 4483362458) -- Title, Image

local Button = Tab:CreateButton({
   Name = "Ghost Hub",
   Callback = function()
   -- Variáveis para controlar o estado
local texturasRemovidas = false
        loadstring(game:HttpGet('https://raw.githubusercontent.com/GhostPlayer352/Test4/main/GhostHub'))()
   end,
})























































































































Rayfield:Notify({
   Title = "Abrir o Script",
   Content = "Tecla (k)",
   Duration = 6.5,
   Image = 4483362458,
})
