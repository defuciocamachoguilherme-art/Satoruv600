local Libary = local redzlib = loadstring(game:HttpGet("https://pastefy.app/JoaoaDi1/raw"))()




game:GetService("ReplicatedStorage").RE["1RPNam1eTex1t"]:FireServer(table.unpack({
                [1] = "RolePlayName",
                [2] = "[ Satoru Hub User ]"
                }))
                
                -- Define a bio do jogador
                game:GetService("ReplicatedStorage").RE["1RPNam1eTex1t"]:FireServer(table.unpack({
                    [1] = "RolePlayBio",
                    [2] = "Criador:Rei gui_official_007",
                }))
                
                
local Window = Libary:MakeWindow({
    Title = "Satoru Hub| Brookhaven RP🇧🇷 ",
    SubTitle = "by gui_official",
    LoadText = "Carregando Hub",
    Flags = "Hub_Broookhaven"
})
Window:AddMinimizeButton({
    Button = { Image = "rbxassetid://122623627187728", BackgroundTransparency = 0 },
    Corner = { CornerRadius = UDim.new(35, 1) },
})

-- =========================================================
-- INFORMAÇÕES E CRÉDITOS - Satoru HUB BROOKHAVEN RP
-- =========================================================

local InfoTab = Window:MakeTab({ "Info", "info" })

-- =========================================================
-- SEÇÃO: INFORMAÇÕES PRINCIPAIS
-- =========================================================
InfoTab:AddSection({ "Informações Principais" })

InfoTab:AddParagraph({ "Nome do Hub:", "Satoru Hub | Brookhaven Edition" })
InfoTab:AddParagraph({ "Desenvolvedores:", " gui_official & black" })
InfoTab:AddParagraph({ "Versão:", "3.6.0 - Novembro de 2025" })
InfoTab:AddParagraph({ "Idioma:", "Português (Brasil)" })
InfoTab:AddParagraph({ "Jogo Principal:", "Brookhaven RP 🏡" })
InfoTab:AddParagraph({ "Compatibilidade:", " PC | 📱 Celular | 💊 Tablet" })

-- =========================================================
-- SEÇÃO: CRÉDITOS
-- =========================================================
InfoTab:AddSection({ "Créditos" })

InfoTab:AddParagraph({ "Projeto:", "Satoru Hub © 2026" })
InfoTab:AddParagraph({ "Design e Scripts:", "Gui_official" })
InfoTab:AddParagraph({ "Efeitos e Visual:", "denolk" })
InfoTab:AddParagraph({ "Equipe:", "Satoru Hub Dev Team" })

-- =========================================================
-- SEÇÃO: REDES OFICIAIS
-- =========================================================
InfoTab:AddSection({ "Redes Oficiais" })

InfoTab:AddDiscordInvite({
    Name = "Servidor satoru Hub",
    Description = "Entre na nossa comunidade no Discord 💬",
    Logo = "rbxassetid://122623627187728",
    Invite = "https://discord.gg/mRpVDmUAH"
})

InfoTab:AddDiscordInvite({
    Name = "Gui_official",
    Description = "TikTok Oficial 🎥",
    Logo = "rbxassetid://122623627187728",
    Invite = "https://www.tiktok.com/@gui_official_007?_r=1&_t=ZM-91ImhLXFpEa"
})

-- =========================================================
-- SEÇÃO: INFORMAÇÕES DO JOGADOR
-- =========================================================
InfoTab:AddSection({ "Informações do Jogador" })

local Players = game:GetService("Players")
local Stats = game:GetService("Stats")
local player = Players.LocalPlayer

local function getStatValue(parent, name)
    if parent then
        local obj = parent:FindFirstChild(name)
        if obj and obj.GetValue then
            local sucesso, valor = pcall(function() return obj:GetValue() end)
            if sucesso then
                return math.floor(valor)
            end
        end
    end
    return "Não identificado"
end

local info = {}

info["Usuário:"] = player.Name or "Não identificado"
info["Nome de Exibição:"] = player.DisplayName or "Não identificado"
info["ID do Usuário:"] = player.UserId or "Não identificado"
info["Idade da Conta:"] = player.AccountAge or "Não identificado"

local netStats = Stats:FindFirstChild("Network")
local serverStats = netStats and netStats:FindFirstChild("ServerStatsItem")
info["Ping:"] = (serverStats and getStatValue(serverStats, "Data Ping") .. " ms") or "Não identificado"

if identifyexecutor then
    local sucesso, nome, versao = pcall(function() return identifyexecutor() end)
    info["Executor:"] = sucesso and (nome .. (versao and (" v" .. versao) or "")) or "Não identificado"
else
    info["Executor:"] = "Não identificado"
end

for chave, valor in pairs(info) do
    InfoTab:AddParagraph({ chave, tostring(valor) })
end

InfoTab:AddParagraph({ "Idioma:", "Português" })
InfoTab:AddParagraph({ "Jogo:", "Brookhaven RP 🏡" })
InfoTab:AddParagraph({ "Hub Ativo:", "Satoru Hub" })
InfoTab:AddParagraph({ "Versão do Hub:", "5.6.0" })

-- =========================================================
-- SEÇÃO: MENSAGENS
-- =========================================================
InfoTab:AddSection({ "Mensagens" })
InfoTab:AddParagraph({ "Mensagem:", "Mostre seu estilo e aproveite o xexo Hub com classe! 😎🔥" })
InfoTab:AddParagraph({ "Nota:", "Criado para diversão, criatividade e estilo — Satoru Hub BR 💜" })

-- =========================================================
-- SEÇÃO: OUTROS + ANIMAÇÃO VISUAL COM SOM
-- =========================================================
InfoTab:AddSection({ "Outros" })

InfoTab:AddButton({
    Name = "🔁 Reentrar no Servidor",
    Callback = function()
        local TeleportService = game:GetService("TeleportService")
        TeleportService:TeleportToPlaceInstance(game.PlaceId, game.JobId, game.Players.LocalPlayer)
    end
})

InfoTab:AddButton({
    Name = "💫 Créditos Visuais",
    Callback = function()
        game:GetService("StarterGui"):SetCore("SendNotification", {
            Title = "Saroru Hub - Créditos ",
            Text = "Feito com estilo por Gui_official & black",
            Duration = 5
        })
    end
})

-- =========================================================
-- ✨ ANIMAÇÃO VISUAL + SOM AO ABRIR A ABA INFO
-- =========================================================
task.spawn(function()
    local player = game.Players.LocalPlayer
    local char = player.Character or player.CharacterAdded:Wait()
    local hrp = char:WaitForChild("HumanoidRootPart")

    local part = Instance.new("Part")
    part.Size = Vector3.new(1, 1, 1)
    part.Anchored = true
    part.CanCollide = false
    part.Transparency = 1
    part.Position = hrp.Position + Vector3.new(0, 3, 0)
    part.Parent = workspace

    local particles = Instance.new("ParticleEmitter", part)
    particles.Texture = "rbxassetid://243660364"
    particles.Color = ColorSequence.new{
        ColorSequenceKeypoint.new(0, Color3.fromRGB(140, 0, 255)),
        ColorSequenceKeypoint.new(1, Color3.fromRGB(0, 200, 255))
    }
    particles.Size = NumberSequence.new({NumberSequenceKeypoint.new(0, 1), NumberSequenceKeypoint.new(1, 3)})
    particles.Transparency = NumberSequence.new(0.2)
    particles.Lifetime = NumberRange.new(2)
    particles.Rate = 80
    particles.Speed = NumberRange.new(0.5)
    particles.LightEmission = 1
    particles.Rotation = NumberRange.new(0, 360)
    particles.SpreadAngle = Vector2.new(180, 180)

    local logo = Instance.new("BillboardGui", part)
    logo.Size = UDim2.new(5, 0, 5, 0)
    logo.AlwaysOnTop = true
    logo.StudsOffset = Vector3.new(0, 4, 0)
    logo.Enabled = true

    local img = Instance.new("ImageLabel", logo)
    img.Image = "rbxassetid://122623627187728"
    img.Size = UDim2.new(1, 0, 1, 0)
    img.BackgroundTransparency = 1
    img.ImageTransparency = 0.2

    -- Som de energia suave
    local som = Instance.new("Sound", part)
    som.SoundId = "rbxassetid://9120219474"
    som.Volume = 1
    som:Play()

    -- Desaparecimento suave
    task.spawn(function()
        for i = 0.2, 1, 0.02 do
            img.ImageTransparency = i
            task.wait(0.05)
        end
        part:Destroy()
    end)
end)



local TrollTab = Window:MakeTab({ Title = "Scripts Trolls", Icon = "rbxasset dps coloca})


TrollTab:AddSection({ "Black Hole" })
TrollTab:AddButton({
    Name = "Black Hole",
    Description = " Ativando isso você puxa Parts até o seu personagem",
    Callback = function()
        local Players = game:GetService("Players")
local RunService = game:GetService("RunService")
local LocalPlayer = Players.LocalPlayer
local Workspace = game:GetService("Workspace")

local angle = 1
local radius = 10
local blackHoleActive = false

local function setupPlayer()
    local character = LocalPlayer.Character or LocalPlayer.CharacterAdded:Wait()
    local humanoidRootPart = character:WaitForChild("HumanoidRootPart")

    local Folder = Instance.new("Folder", Workspace)
    local Part = Instance.new("Part", Folder)
    local Attachment1 = Instance.new("Attachment", Part)
    Part.Anchored = true
    Part.CanCollide = false
    Part.Transparency = 1

    return humanoidRootPart, Attachment1
end

local humanoidRootPart, Attachment1 = setupPlayer()

if not getgenv().Network then
    getgenv().Network = {
        BaseParts = {},
        Velocity = Vector3.new(14.46262424, 14.46262424, 14.46262424)
    }

    Network.RetainPart = function(part)
        if typeof(part) == "Instance" and part:IsA("BasePart") and part:IsDescendantOf(Workspace) then
            table.insert(Network.BaseParts, part)
            part.CustomPhysicalProperties = PhysicalProperties.new(0, 0, 0, 0, 0)
            part.CanCollide = false
        end
    end

    local function EnablePartControl()
        LocalPlayer.ReplicationFocus = Workspace
        RunService.Heartbeat:Connect(function()
            sethiddenproperty(LocalPlayer, "SimulationRadius", math.huge)
            for _, part in pairs(Network.BaseParts) do
                if part:IsDescendantOf(Workspace) then
                    part.Velocity = Network.Velocity
                end
            end
        end)
    end

    EnablePartControl()
end

local function ForcePart(v)
    if v:IsA("Part") and not v.Anchored and not v.Parent:FindFirstChild("Humanoid") and not v.Parent:FindFirstChild("Head") and v.Name ~= "Handle" then
        for _, x in next, v:GetChildren() do
            if x:IsA("BodyAngularVelocity") or x:IsA("BodyForce") or x:IsA("BodyGyro") or x:IsA("BodyPosition") or x:IsA("BodyThrust") or x:IsA("BodyVelocity") or x:IsA("RocketPropulsion") then
                x:Destroy()
            end
        end
        if v:FindFirstChild("Attachment") then
            v:FindFirstChild("Attachment"):Destroy()
        end
        if v:FindFirstChild("AlignPosition") then
            v:FindFirstChild("AlignPosition"):Destroy()
        end
        if v:FindFirstChild("Torque") then
            v:FindFirstChild("Torque"):Destroy()
        end
        v.CanCollide = false
        
        local Torque = Instance.new("Torque", v)
        Torque.Torque = Vector3.new(1000000, 1000000, 1000000)
        local AlignPosition = Instance.new("AlignPosition", v)
        local Attachment2 = Instance.new("Attachment", v)
        Torque.Attachment0 = Attachment2
        AlignPosition.MaxForce = math.huge
        AlignPosition.MaxVelocity = math.huge
        AlignPosition.Responsiveness = 500
        AlignPosition.Attachment0 = Attachment2
        AlignPosition.Attachment1 = Attachment1
    end
end

local function toggleBlackHole()
    blackHoleActive = not blackHoleActive
    if blackHoleActive then
        for _, v in next, Workspace:GetDescendants() do
            ForcePart(v)
        end

        Workspace.DescendantAdded:Connect(function(v)
            if blackHoleActive then
                ForcePart(v)
            end
        end)

        spawn(function()
            while blackHoleActive and RunService.RenderStepped:Wait() do
                angle = angle + math.rad(2)

                local offsetX = math.cos(angle) * radius
                local offsetZ = math.sin(angle) * radius

                Attachment1.WorldCFrame = humanoidRootPart.CFrame * CFrame.new(offsetX, 0, offsetZ)
            end
        end)
    else
        Attachment1.WorldCFrame = CFrame.new(0, -1000, 0)
    end
end

LocalPlayer.CharacterAdded:Connect(function()
    humanoidRootPart, Attachment1 = setupPlayer()
    if blackHoleActive then
        toggleBlackHole()
    end
end)

local library = loadstring(game:HttpGet("https://raw.githubusercontent.com/miroeramaa/TurtleLib/main/TurtleUiLib.lua"))()
local window = library:Window("Projeto LKB")

window:Slider("Radius Blackhole",1,100,10, function(Value)
   radius = Value
end)

window:Toggle("Blackhole", true, function(Value)
       if Value then
            toggleBlackHole()
        else
            blackHoleActive = false
        end
end)

spawn(function()
    while true do
        RunService.RenderStepped:Wait()
        if blackHoleActive then
            angle = angle + math.rad(angleSpeed)
        end
    end
end)

toggleBlackHole()
    end
})


TrollTab:AddSection({ "Puxar Parts" })
TrollTab:AddButton({
    Name = "Puxar Parts",
    Description = "Para usar, chegue perto do Player Selecionado",
    Callback = function()
        -- Gui to Lua
-- Version: 3.2

-- Instances:

local Gui = Instance.new("ScreenGui")
local Main = Instance.new("Frame")
local Box = Instance.new("TextBox")
local UITextSizeConstraint = Instance.new("UITextSizeConstraint")
local Label = Instance.new("TextLabel")
local UITextSizeConstraint_2 = Instance.new("UITextSizeConstraint")
local Button = Instance.new("TextButton")
local UITextSizeConstraint_3 = Instance.new("UITextSizeConstraint")

--Properties:

Gui.Name = "Gui"
Gui.Parent = gethui()
Gui.ZIndexBehavior = Enum.ZIndexBehavior.Sibling

Main.Name = "Main"
Main.Parent = Gui
Main.BackgroundColor3 = Color3.fromRGB(75, 75, 75)
Main.BorderColor3 = Color3.fromRGB(0, 0, 0)
Main.BorderSizePixel = 0
Main.Position = UDim2.new(0.335954279, 0, 0.542361975, 0)
Main.Size = UDim2.new(0.240350261, 0, 0.166880623, 0)
Main.Active = true
Main.Draggable = true

Box.Name = "Box"
Box.Parent = Main
Box.BackgroundColor3 = Color3.fromRGB(95, 95, 95)
Box.BorderColor3 = Color3.fromRGB(0, 0, 0)
Box.BorderSizePixel = 0
Box.Position = UDim2.new(0.0980926454, 0, 0.218712583, 0)
Box.Size = UDim2.new(0.801089942, 0, 0.364963502, 0)
Box.FontFace = Font.new("rbxasset://fonts/families/SourceSansSemibold.json", Enum.FontWeight.Bold, Enum.FontStyle.Normal)
Box.PlaceholderText = "Player here"
Box.Text = ""
Box.TextColor3 = Color3.fromRGB(255, 255, 255)
Box.TextScaled = true
Box.TextSize = 31.000
Box.TextWrapped = true

UITextSizeConstraint.Parent = Box
UITextSizeConstraint.MaxTextSize = 31

Label.Name = "Label"
Label.Parent = Main
Label.BackgroundColor3 = Color3.fromRGB(95, 95, 95)
Label.BorderColor3 = Color3.fromRGB(0, 0, 0)
Label.BorderSizePixel = 0
Label.Size = UDim2.new(1, 0, 0.160583943, 0)
Label.FontFace = Font.new("rbxasset://fonts/families/Nunito.json", Enum.FontWeight.Bold, Enum.FontStyle.Normal)
Label.Text = "Bring Parts | Made by: Lusquinha_067"
Label.TextColor3 = Color3.fromRGB(255, 255, 255)
Label.TextScaled = true
Label.TextSize = 14.000
Label.TextWrapped = true

UITextSizeConstraint_2.Parent = Label
UITextSizeConstraint_2.MaxTextSize = 21

Button.Name = "Button"
Button.Parent = Main
Button.BackgroundColor3 = Color3.fromRGB(95, 95, 95)
Button.BorderColor3 = Color3.fromRGB(0, 0, 0)
Button.BorderSizePixel = 0
Button.Position = UDim2.new(0.183284417, 0, 0.656760991, 0)
Button.Size = UDim2.new(0.629427791, 0, 0.277372271, 0)
Button.Font = Enum.Font.Nunito
Button.Text = "Bring | Off"
Button.TextColor3 = Color3.fromRGB(255, 255, 255)
Button.TextScaled = true
Button.TextSize = 28.000
Button.TextWrapped = true

UITextSizeConstraint_3.Parent = Button
UITextSizeConstraint_3.MaxTextSize = 28

-- Scripts:

local Players = game:GetService("Players")
local RunService = game:GetService("RunService")
local LocalPlayer = Players.LocalPlayer
local UserInputService = game:GetService("UserInputService")
local Workspace = game:GetService("Workspace")

local character
local humanoidRootPart

mainStatus = true
UserInputService.InputBegan:Connect(function(input, gameProcessedEvent)
	if input.KeyCode == Enum.KeyCode.RightControl and not gameProcessedEvent then
		mainStatus = not mainStatus
		Main.Visible = mainStatus
	end
end)

local Folder = Instance.new("Folder", Workspace)
local Part = Instance.new("Part", Folder)
local Attachment1 = Instance.new("Attachment", Part)
Part.Anchored = true
Part.CanCollide = false
Part.Transparency = 1

if not getgenv().Network then
	getgenv().Network = {
		BaseParts = {},
		Velocity = Vector3.new(14.46262424, 14.46262424, 14.46262424)
	}

	Network.RetainPart = function(Part)
		if Part:IsA("BasePart") and Part:IsDescendantOf(Workspace) then
			table.insert(Network.BaseParts, Part)
			Part.CustomPhysicalProperties = PhysicalProperties.new(0, 0, 0, 0, 0)
			Part.CanCollide = false
		end
	end

	local function EnablePartControl()
		LocalPlayer.ReplicationFocus = Workspace
		RunService.Heartbeat:Connect(function()
			sethiddenproperty(LocalPlayer, "SimulationRadius", math.huge)
			for _, Part in pairs(Network.BaseParts) do
				if Part:IsDescendantOf(Workspace) then
					Part.Velocity = Network.Velocity
				end
			end
		end)
	end

	EnablePartControl()
end

local function ForcePart(v)
	if v:IsA("BasePart") and not v.Anchored and not v.Parent:FindFirstChildOfClass("Humanoid") and not v.Parent:FindFirstChild("Head") and v.Name ~= "Handle" then
		for _, x in ipairs(v:GetChildren()) do
			if x:IsA("BodyMover") or x:IsA("RocketPropulsion") then
				x:Destroy()
			end
		end
		if v:FindFirstChild("Attachment") then
			v:FindFirstChild("Attachment"):Destroy()
		end
		if v:FindFirstChild("AlignPosition") then
			v:FindFirstChild("AlignPosition"):Destroy()
		end
		if v:FindFirstChild("Torque") then
			v:FindFirstChild("Torque"):Destroy()
		end
		v.CanCollide = false
		local Torque = Instance.new("Torque", v)
		Torque.Torque = Vector3.new(100000, 100000, 100000)
		local AlignPosition = Instance.new("AlignPosition", v)
		local Attachment2 = Instance.new("Attachment", v)
		Torque.Attachment0 = Attachment2
		AlignPosition.MaxForce = math.huge
		AlignPosition.MaxVelocity = math.huge
		AlignPosition.Responsiveness = 200
		AlignPosition.Attachment0 = Attachment2
		AlignPosition.Attachment1 = Attachment1
	end
end

local blackHoleActive = false
local DescendantAddedConnection

local function toggleBlackHole()
	blackHoleActive = not blackHoleActive
	if blackHoleActive then
		Button.Text = "Bring Parts | On"
		for _, v in ipairs(Workspace:GetDescendants()) do
			ForcePart(v)
		end

		DescendantAddedConnection = Workspace.DescendantAdded:Connect(function(v)
			if blackHoleActive then
				ForcePart(v)
			end
		end)

		spawn(function()
			while blackHoleActive and RunService.RenderStepped:Wait() do
				Attachment1.WorldCFrame = humanoidRootPart.CFrame
			end
		end)
	else
		Button.Text = "Bring Parts | Off"
		if DescendantAddedConnection then
			DescendantAddedConnection:Disconnect()
		end
	end
end

local function getPlayer(name)
	local lowerName = string.lower(name)
	for _, p in pairs(Players:GetPlayers()) do
		local lowerPlayer = string.lower(p.Name)
		if string.find(lowerPlayer, lowerName) then
			return p
		elseif string.find(string.lower(p.DisplayName), lowerName) then
			return p
		end
	end
end

local player = nil

local function VDOYZQL_fake_script() -- Box.Script 
	local script = Instance.new('Script', Box)

	script.Parent.FocusLost:Connect(function(enterPressed)
		if enterPressed then
			player = getPlayer(Box.Text)
			if player then
				Box.Text = player.Name
				print("Player found:", player.Name)
			else
				print("Player not found")
			end
		end
	end)
end
coroutine.wrap(VDOYZQL_fake_script)()
local function JUBNQKI_fake_script() -- Button.Script 
	local script = Instance.new('Script', Button)

	script.Parent.MouseButton1Click:Connect(function()
		if player then
			character = player.Character or player.CharacterAdded:Wait()
			humanoidRootPart = character:WaitForChild("HumanoidRootPart")
			toggleBlackHole()
		else
			print("Player is not selected")
		end
	end)
end
coroutine.wrap(JUBNQKI_fake_script)()
    end
})

TrollTab:AddSection({ "Invisível" })

TrollTab:AddButton({
    Name = "Ficar Invisível
