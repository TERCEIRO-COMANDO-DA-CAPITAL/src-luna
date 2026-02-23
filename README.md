📚 Luna Interface Suite - Documentação de Modelos

Abaixo estão todos os modelos de código para a Luna Interface Suite. Basta copiar e colar no seu script.

---

📦 Carregamento da Biblioteca

```lua
local Luna = loadstring(game:HttpGet("https://raw.githubusercontent.com/TERCEIRO-COMANDO-DA-CAPITAL/src-luna/refs/heads/main/source.lua.txt"))()
```

---

🪟 Janela Principal (CreateWindow)

```lua
local Window = Luna:CreateWindow({
    Name = "Título da Janela",
    Subtitle = "Subtítulo Aqui",
    LogoID = "1234567890",
    LoadingEnabled = true,
    LoadingTitle = "Carregando...",
    LoadingSubtitle = "Aguarde",
    ConfigSettings = {
        RootFolder = nil,
        ConfigFolder = "PastaConfig"
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

---

📌 Aba (CreateTab)

```lua
local Tab = Window:CreateTab({
    Name = "Nome da Aba",
    Icon = "home",              -- Nome do ícone (Material)
    ImageSource = "Material",    -- "Material" ou "Lucide"
    ShowTitle = true
})
```

---

🔹 Seção (CreateSection)

```lua
Tab:CreateSection("Nome da Seção")
```

---

➖ Divisor (CreateDivider)

```lua
Tab:CreateDivider()
```

---

🔘 Botão (CreateButton)

```lua
Tab:CreateButton({
    Name = "Texto do Botão",
    Description = "Descrição opcional",
    Callback = function()
        -- Código ao clicar
        print("Botão clicado!")
    end
})
```

---

🔄 Toggle (CreateToggle)

```lua
local Toggle = Tab:CreateToggle({
    Name = "Texto do Toggle",
    Description = "Descrição opcional",
    CurrentValue = false,
    Callback = function(Value)
        print("Toggle:", Value)
    end
}, "FlagUnicaParaSalvar")
```

---

📊 Slider (CreateSlider)

```lua
local Slider = Tab:CreateSlider({
    Name = "Texto do Slider",
    Range = {0, 100},
    Increment = 1,
    CurrentValue = 50,
    Callback = function(Value)
        print("Slider:", Value)
    end
}, "FlagUnicaParaSalvar")
```

---

🔽 Dropdown (CreateDropdown)

```lua
local Dropdown = Tab:CreateDropdown({
    Name = "Texto do Dropdown",
    Options = {"Opção 1", "Opção 2", "Opção 3"},
    Default = 1,
    Callback = function(Value)
        print("Opção selecionada:", Value)
    end
}, "FlagUnicaParaSalvar")
```

---

🎨 Color Picker (CreateColorPicker)

```lua
local ColorPicker = Tab:CreateColorPicker({
    Name = "Seletor de Cor",
    Color = Color3.fromRGB(255, 0, 0),
    Flag = "FlagUnica",
    Callback = function(Value)
        print("Cor selecionada:", Value)
    end
}, "FlagUnicaParaSalvar")
```

---

🏷️ Label (CreateLabel)

```lua
Tab:CreateLabel({
    Text = "Texto informativo",
    Style = 1  -- 1=normal, 2=sucesso, 3=aviso
})
```

---

🔔 Notificação (Notification)

```lua
Luna:Notification({
    Title = "Título",
    Icon = "check_circle",
    ImageSource = "Material",
    Content = "Conteúdo da notificação"
})
```

---

💾 Carregar Configurações (Final do Script)

```lua
Luna:LoadAutoloadConfig()
```

---

✅ Exemplo Completo Mínimo

```lua
local Luna = loadstring(game:HttpGet("https://raw.githubusercontent.com/TERCEIRO-COMANDO-DA-CAPITAL/src-luna/refs/heads/main/source.lua.txt"))()

local Window = Luna:CreateWindow({
    Name = "Minha UI",
    Subtitle = "by Eu",
    LoadingEnabled = false,
    KeySystem = false
})

local Tab = Window:CreateTab({
    Name = "Principal",
    Icon = "home",
    ImageSource = "Material"
})

Tab:CreateSection("Controles")

Tab:CreateButton({
    Name = "Clique Aqui",
    Callback = function()
        print("Funcionou!")
    end
})

Luna:LoadAutoloadConfig()
```
