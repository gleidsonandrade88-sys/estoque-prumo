# Estoque Prumo — Via Permanente

Controle físico de materiais de via permanente: inventário do pátio, entradas, baixas e retornos por ativo, com fechamento de medição e relatórios em Excel.

**Aplicação:** https://gleidsonandrade88-sys.github.io/estoque-prumo/

## Como funciona

1. **Cadastro do estoque atual** — aba *Estoque*, botão **Inventário** em cada material: informe a quantidade contada no pátio e a data da contagem. Essa contagem é o marco zero do controle. Material que não está na lista pode ser cadastrado ali mesmo, com a unidade (UN, M³, TON).

2. **Movimentações** — aba *Lançar*:
   - **Entrada** — recebimento de material.
   - **Saída** — baixa por uso na área. Ativo e balizamento obrigatórios.
   - **Retorno** — material que voltou sem ser usado.

   O sistema avisa quando a saída é maior que o saldo e mantém responsável, matrícula e data preenchidos para lançar vários movimentos em sequência.

3. **Fechamento de medição** — aba *Medições*: informe o nome e a data de corte. O saldo de cada material é congelado naquela data e a planilha do período é baixada automaticamente, com saldo inicial, entradas, saídas, retornos, saldo final, consumo por ativo/balizamento e todos os lançamentos. Tudo que for lançado com data posterior ao corte já entra na medição seguinte.

## Relatórios

| Botão | Onde | Conteúdo |
|---|---|---|
| PDF do inventário | aba Estoque | Contagem por material, data, movimentos do período e saldo atual, com campos de assinatura |
| Folha de contagem | aba Estoque | Lista dos materiais com espaço em branco para anotar a contagem à caneta no pátio |
| PDF do período em aberto | aba Medições | Prévia da medição antes de fechar |
| PDF (por medição) | aba Medições | Relatório assinável do período fechado |
| Saldo atual (Excel) | aba Backup | Material, unidade e saldo atual |
| Histórico completo (Excel) | aba Backup | Todos os lançamentos, com ativo, balizamento e responsável |
| Excel (por medição) | aba Medições | Resumo do período, consumo por ativo e lançamentos |

Os PDFs saem pela impressão do navegador: em *Destino*, escolha **Salvar como PDF** (no celular, **Imprimir → Salvar como PDF**). Não depende de internet nem de programa instalado.

Os arquivos saem em CSV separado por ponto e vírgula, com acentuação preservada — abrem direto no Excel em português.

## Onde os dados ficam

Os dados ficam salvos no navegador do próprio aparelho (`localStorage`). Celular de campo e computador do escritório são bases separadas.

Para juntar ou transferir, use a aba **Backup**: *Baixar backup (.json)* no aparelho de origem e *Importar backup* no de destino. A importação substitui os dados do aparelho de destino, então faça o backup antes.

Rotina recomendada: baixar o backup ao fim de cada semana e no fechamento de cada medição.

## Estrutura

Página única, sem dependências externas e sem servidor — funciona offline depois de aberta uma vez.

```
index.html    aplicação completa (HTML, CSS e JavaScript)
```

---
Prumo Engenharia — uso interno.
