# Desafio Dio Criando um Simulador de Aventuras com Lua



**Código Completo e Abrangente para um Simulador de Aventuras com Lua**

lua



```lua
-- Define o jogador
jogador = {
  nome = "Aventureiro",
  saude = 100,
  ataque = 10,
  defesa = 5,
  inventario = {}
}

-- Define o monstro
monstro = {
  nome = "Goblin",
  saude = 50,
  ataque = 5,
  defesa = 2
}

-- Função para atacar
function atacar(atacante, defensor)
  dano = math.max(0, atacante.ataque - defensor.defesa)
  defensor.saude = defensor.saude - dano
end

-- Função para curar
function curar(alvo)
  alvo.saude = alvo.saude + 10
end

-- Função para imprimir o status
function imprimir_status(personagem)
  print(personagem.nome .. ":")
  print("  Saúde: " .. personagem.saude)
  print("  Ataque: " .. personagem.ataque)
  print("  Defesa: " .. personagem.defesa)
  print("  Inventário: " .. table.concat(personagem.inventario, ", "))
end

-- Função para obter a ação do jogador
function get_acao()
  print("O que você deseja fazer?")
  print("1. Atacar")
  print("2. Curar")
  print("3. Usar item")
  print("4. Sair")
  return io.read()
end

-- Função para usar um item
function usar_item(jogador, item)
  if item == "pocao_cura" then
    curar(jogador)
  elseif item == "espada" then
    jogador.ataque = jogador.ataque + 5
  elseif item == "escudo" then
    jogador.defesa = jogador.defesa + 2
  end
end

-- Loop principal do jogo
while true do
  -- Imprime o status do jogador e do monstro
  imprimir_status(jogador)
  imprimir_status(monstro)

  -- Obtém a ação do jogador
  acao = get_acao()

  -- Executa a ação do jogador
  if acao == 1 then
    atacar(jogador, monstro)
  elseif acao == 2 then
    curar(jogador)
  elseif acao == 3 then
    -- Obtém o item do jogador
    print("Qual item você deseja usar?")
    item = io.read()

    -- Usa o item
    usar_item(jogador, item)
  elseif acao == 4 then
    break
  end

  -- Verifica se o monstro está morto
  if monstro.saude <= 0 then
    print("Você derrotou o monstro!")
    break
  end

  -- O monstro ataca o jogador
  atacar(monstro, jogador)

  -- Verifica se o jogador está morto
  if jogador.saude <= 0 then
    print("Você foi derrotado pelo monstro!")
    break
  end
end
```



### **Aplicabilidade**

Este simulador de aventuras mais completo e abrangente pode ser usado para:

- Aprender conceitos de programação mais avançados em Lua, como gerenciamento de inventário e uso de itens
- Experimentar com diferentes estratégias de combate e uso de itens
- Criar jogos de aventura personalizados ainda mais envolventes



## **Conclusão**

Este código fornece uma base sólida para a criação de simuladores de aventuras complexos e divertidos usando Lua. Com um pouco de criatividade e imaginação, você pode usar Lua para criar seus próprios mundos de aventura únicos e envolventes.
