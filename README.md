local player = game.Players.LocalPlayer
local userInputService = game:GetService("UserInputService")

-- Criação da interface
local screenGui = Instance.new("ScreenGui")
screenGui.Parent = player:WaitForChild("PlayerGui")

local frame = Instance.new("Frame")
frame.Size = UDim2.new(0, 200, 1, 0) -- Largura de 200 pixels e altura total da tela
frame.Position = UDim2.new(0, 0, 0, 0) -- Lado esquerdo da tela
frame.BackgroundColor3 = Color3.fromRGB(50, 50, 50) -- Cor de fundo
frame.Visible = false -- Inicialmente invisível
frame.Parent = screenGui

local textLabel = Instance.new("TextLabel")
textLabel.Size = UDim2.new(1, 0, 0, 50) -- Texto ocupa toda a largura do frame
textLabel.Position = UDim2.new(0, 0, 0, 0)
textLabel.Text = "Opções de Espancar"
textLabel.TextColor3 = Color3.new(1, 1, 1) -- Cor do texto
textLabel.BackgroundTransparency = 1 -- Fundo transparente
textLabel.Parent = frame

-- Função para adicionar botões de espancamento
local function addButton(text, position)
    local button = Instance.new("TextButton")
    button.Size = UDim2.new(1, 0, 0, 50) -- Tamanho do botão
    button.Position = position
    button.Text = text
    button.TextColor3 = Color3.new(1, 1, 1) -- Cor do texto
    button.BackgroundColor3 = Color3.fromRGB(100, 100, 100) -- Cor do botão
    button.Parent = frame

    button.MouseButton1Click:Connect(function()
        -- Aqui você pode adicionar a lógica para "espancar" jogadores
        print(text .. " ativado!")
    end)
end

-- Adicionando botões de exemplo
addButton("Espancar Jogador 1", UDim2.new(0, 0, 0, 50))
addButton("Espancar Jogador 2", UDim2.new(0, 0, 0, 100))

-- Função para alternar a visibilidade da interface
local function toggleFrame()
    frame.Visible = not frame.Visible
end

-- Conectar a função ao clique
userInputService.InputBegan:Connect(function(input, gameProcessedEvent)
    if input.UserInputType == Enum.UserInputType.MouseButton1 and not gameProcessedEvent then
        toggleFrame()
    end
end)
