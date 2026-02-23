Perfeito! Com o link direto do código fonte, consigo te dar exatamente a documentação que você quer, apenas com os nomes e os modelos prontos. Baseado no arquivo source.lua.txt da sua branch específica, aqui estão os principais elementos para criar sua UI.

📦 Modelos da Luna Interface Suite (Branch: TERCEIRO-COMANDO-DA-CAPITAL)

Aqui estão os modelos de código para os elementos principais que encontrei na análise do código fonte. Use-os como template nos seus scripts.

---

# Janela Principal (CreateWindow)

```lua
local Window = Luna:CreateWindow({
    Name = "Título da Janela",
    Subtitle = "Subtítulo",
    LogoID = "ID_DA_IMAGEM_AQUI",
    LoadingEnabled = true,
    LoadingTitle = "Carregando...",
    LoadingSubtitle = "Aguarde",
    ConfigSettings = {
        RootFolder = nil,
        ConfigFolder = "NomeDaPasta"
    },
    KeySystem = false,
    KeySettings = {
        Title = "Sistema de Chave",
        Subtitle = "Insira sua chave",
        Note = "Nota sobre a chave",
        SaveInRoot = false,
        SaveKey = true,
        Key = {"chave123"}
    }
})
```

# Aba (CreateTab)

```lua
local Tab = Window:CreateTab({
    Name = "Nome da Aba",
    Icon = "home", -- Nome do ícone (Material)
    ImageSource = "Material", -- "Material" ou "Lucide"
    ShowTitle = true
})
```

# Seção (CreateSection)

```lua
Tab:CreateSection("Nome da Seção")
```

# Divisor (CreateDivider)

```lua
Tab:CreateDivider()
```

# Botão (CreateButton)

```lua
Tab:CreateButton({
    Name = "Texto do Botão",
    Description = "Descrição opcional",
    Callback = function()
        -- Código a ser executado ao clicar
        print("Botão clicado!")
    end
})
```

# Toggle (CreateToggle)

```lua
local Toggle = Tab:CreateToggle({
    Name = "Texto do Toggle",
    Description = "Descrição opcional",
    CurrentValue = false, -- Valor inicial (true/false)
    Callback = function(Value)
        -- Value é booleano (true/false)
        print("Toggle:", Value)
    end
}, "FlagUnicaParaSalvar")
```

# Slider (CreateSlider)

```lua
local Slider = Tab:CreateSlider({
    Name = "Texto do Slider",
    Range = {0, 100}, -- {Valor Mínimo, Valor Máximo}
    Increment = 1,
    CurrentValue = 50,
    Callback = function(Value)
        print("Slider:", Value)
    end
}, "FlagUnicaParaSalvar")
```

# Dropdown (CreateDropdown)

```lua
local Dropdown = Tab:CreateDropdown({
    Name = "Texto do Dropdown",
    Options = {"Opção 1", "Opção 2", "Opção 3"},
    Default = 1, -- Índice da opção padrão (começa em 1)
    Callback = function(Value)
        print("Opção selecionada:", Value)
    end
}, "FlagUnicaParaSalvar")
```

# Color Picker (CreateColorPicker)

```lua
local ColorPicker = Tab:CreateColorPicker({
    Name = "Seletor de Cor",
    Color = Color3.fromRGB(255, 0, 0), -- Cor inicial (Vermelho)
    Flag = "FlagUnica",
    Callback = function(Value)
        -- Value é um Color3
        print("Cor selecionada:", Value)
    end
}, "FlagUnicaParaSalvar")
```

# Label (CreateLabel)

```lua
Tab:CreateLabel({
    Text = "Texto informativo",
    Style = 1 -- 1=normal, 2=sucesso(verde), 3=aviso(vermelho)
})
```

# Notificação (Notification)

```lua
Luna:Notification({
    Title = "Título",
    Icon = "check_circle",
    ImageSource = "Material",
    Content = "Conteúdo da notificação"
})
```

# Carregar Configurações (Final do Script)

```lua
Luna:LoadAutoloadConfig()
```

⚠️ Importante

· Flags: Use flags únicas para cada Toggle, Slider, Dropdown e ColorPicker para que as configurações sejam salvas corretamente.
· Luna:LoadAutoloadConfig(): Sempre coloque esta linha no final do seu script para carregar as configurações salvas pelos usuários.
· Ícones: Use nomes de ícones do Material Icons (como "home", "settings", "person") quando ImageSource for "Material".

Com esses modelos, você consegue construir qualquer interface completa usando essa versão da Luna. Se precisar de um exemplo de script completo ou tiver dúvidas sobre algum parâmetro, é só falar.
