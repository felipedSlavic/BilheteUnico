# 🎫 BilheteUnico — Sistema de Transporte SP

<p>
  <img src="https://img.shields.io/badge/Java-ED8B00?style=for-the-badge&logo=openjdk&logoColor=white" />
  <img src="https://img.shields.io/badge/POO-Orientação%20a%20Objetos-blue?style=for-the-badge" />
  <img src="https://img.shields.io/badge/Status-Concluído-success?style=for-the-badge" />
</p>

Simulação do sistema de Bilhete Único do Metrô de São Paulo, desenvolvida em Java como exercício de **Programação Orientada a Objetos** (FIAP — 2° Ano SI).

---

## 📋 Funcionalidades

```
[1] Cadastrar bilhete
[2] Carregar bilhete
[3] Consultar saldo
[4] Passar na catraca
[5] Finalizar
```

| Opção | Descrição |
|-------|-----------|
| `[1]` Cadastrar | Registra um novo bilhete com número gerado automaticamente, vinculado a um usuário (nome, CPF e tipo de tarifa). |
| `[2]` Carregar | Busca o bilhete pelo CPF e adiciona créditos ao saldo. |
| `[3]` Consultar | Exibe o saldo atual do bilhete. |
| `[4]` Catraca | Calcula a tarifa conforme o perfil do usuário, debita do saldo e informa se há saldo insuficiente. |
| `[5]` Finalizar | Encerra o sistema. |

---

## 🏗️ Estrutura do Projeto

```
src/br/bilheteUnico/
├── Main.java          → Menu, fluxo principal e métodos estáticos
├── BilheteUnico.java  → Número, saldo, tarifa e lógica da catraca
└── Usuario.java       → Nome, CPF e tipo de tarifa
```

---

## 💡 Conceitos Aplicados

- **Múltiplas classes** — relacionamento entre `BilheteUnico` e `Usuario`
- **`final static`** — `tarifaBase` como constante de classe
- **`Random`** — geração automática do número do bilhete (1000–9999)
- **Tarifa diferenciada** — estudante e professor pagam metade do valor
- **Busca por CPF** — pesquisa linear no array de bilhetes
- **`boolean` como retorno** — `passarNaCatraca()` sinaliza saldo insuficiente

---

## 💰 Cálculo da Tarifa

```java
// BilheteUnico.java
public double calcularTarifa() {
    if (usuario.tipoTarifa.equals("comum")) {
        return tarifaBase;       // R$ 5,40
    }
    return tarifaBase / 2;       // R$ 2,70 → estudante ou professor
}
```

| Tipo de Tarifa | Valor |
|----------------|-------|
| `comum`        | R$ 5,40 |
| `estudante`    | R$ 2,70 |
| `professor`    | R$ 2,70 |

---

## ▶️ Como Executar

```bash
# Compile
javac src/br/bilheteUnico/*.java

# Execute
java -cp src br.bilheteUnico.Main
```

---

## 👨‍💻 Autor

**Felipe Slavic** · [github.com/felipedSlavic](https://github.com/felipedSlavic)
