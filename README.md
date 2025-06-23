
```lua
local function criarCasa(posicao)
    -- Criar a base da casa
    local base = Instance.new("Part")
    base.Size = Vector3.new(10, 1, 10) -- Tamanho da base
    base.Position = posicao
    base.Anchored = true
    base.BrickColor = BrickColor.new("Brown") -- Cor da base
    base.Parent = workspace

    -- Criar as paredes
    local paredeFrente = Instance.new("Part")
    paredeFrente.Size = Vector3.new(10, 5, 1)
    paredeFrente.Position = posicao + Vector3.new(0, 2.5, -5)
    paredeFrente.Anchored = true
    paredeFrente.BrickColor = BrickColor.new("Dark stone grey")
    paredeFrente.Parent = workspace

    local paredeTraseira = Instance.new("Part")
    paredeTraseira.Size = Vector3.new(10, 5, 1)
    paredeTraseira.Position = posicao + Vector3.new(0, 2.5, 5)
    paredeTraseira.Anchored = true
    paredeTraseira.BrickColor = BrickColor.new("Dark stone grey")
    paredeTraseira.Parent = workspace

    local paredeEsquerda = Instance.new("Part")
    paredeEsquerda.Size = Vector3.new(1, 5, 10)
    paredeEsquerda.Position = posicao + Vector3.new(-5, 2.5, 0)
    paredeEsquerda.Anchored = true
    paredeEsquerda.BrickColor = BrickColor.new("Dark stone grey")
    paredeEsquerda.Parent = workspace

    local paredeDireita = Instance.new("Part")
    paredeDireita.Size = Vector3.new(1, 5, 10)
    paredeDireita.Position = posicao + Vector3.new(5, 2.5, 0)
    paredeDireita.Anchored = true
    paredeDireita.BrickColor = BrickColor.new("Dark stone grey")
    paredeDireita.Parent = workspace

    -- Criar o telhado
    local telhado = Instance.new("WedgePart")
    telhado.Size = Vector3.new(11, 1, 11)
    telhado.Position = posicao + Vector3.new(0, 6, 0)
    telhado.Anchored = true
    telhado.BrickColor = BrickColor.new("Bright red") -- Cor do telhado
    telhado.Parent = workspace
end

-- Função para ativar a criação da casa
local function ativarCriacao()
    local posicaoCasa = Vector3.new(0, 0, 0) -- Altere para a posição desejada
    criarCasa(posicaoCasa)
end

-- Conectar a função ao evento de um jogador entrar no jogo
game.Players.PlayerAdded:Connect(function(player)
    player.CharacterAdded:Connect(function(character)
        -- Aqui você pode ativar a criação da casa quando o jogador entrar
        ativarCriacao()
    end)
end)
```
