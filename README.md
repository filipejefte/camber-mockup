# Camber — mockup do MVP

> A sua oficina no alinhamento perfeito.

Mockup navegável do Camber, sistema de gestão simples para o mecânico autônomo. Ele junta a operação do dia (agenda e ordens de serviço) com o controle financeiro e fiscal. É um arquivo só (`index.html`), sem build e sem dependências. Os dados são fictícios e tudo é simulado no navegador: nenhum Pix, nota fiscal ou mensagem de WhatsApp é enviado de verdade.

## O que tem

| Parte | O que faz |
|---|---|
| **Início** | Quanto entrou hoje e quanto falta receber, as **pendências** (cada uma com o botão que resolve: Confirmar, Receber, Paguei, Anexar, Repor) e a agenda do dia |
| **Agenda** | Seis dias à frente, horários marcados, entregas previstas e **Abrir OS** direto do horário |
| **OS** | Lista em aberto ou todas. Cada OS tem dois status: **Serviço** (pendente/finalizado) e **Pagamento** (pendente/pago, com Pix, dinheiro ou cartão) |
| **Nova OS** | Três passos: carro (placa), itens (tabela de serviços + peças do estoque) e envio pelo WhatsApp. Carro novo entra no cadastro na hora |
| **Comprovante** | Prévia em papel claro, com a logo da oficina e o selo "Gerado via Camber — Histórico Protegido" |
| **Caixa** | Saldo do mês (entradas e saídas), valores a receber, conferência de cada Pix com a OS, contas a pagar, movimentações e o resumo "Pronto para o Leão" |
| **Cadastros** | Clientes, carros (ficha com especificações e prontuário), estoque (com aviso de estoque baixo e de peça sem nota) e tabela de serviços |
| **Configurações** | Tema **claro** (padrão), **escuro** ou **padrão do sistema**; dados da oficina; cenários da demonstração |

## Roteiro de 60 segundos

1. **Início:** duas pendências, um Pix de R$ 620 para conferir e o Onix pronto sem pagamento.
2. **Agenda de hoje › Abrir OS** do Gol (08:00): toque em *Troca de pastilhas*, *Alinhamento* e *Pastilha dianteira*.
3. **Revisar › Enviar pelo WhatsApp**, e depois **Compartilhar** o comprovante.
4. **Início:** toque em **Confirmar** no Pix, depois em **Receber** no Onix, **Receber pagamento** e **Pix**.
5. As pendências zeram e aparece **Tudo em dia**.

## Cenários de demonstração

Na engrenagem, em **Demonstração**. Trocar de cenário apaga o que foi feito na demo, mas não mexe no tema.

| Cenário | O que aparece |
|---|---|
| Tudo em dia | Nenhuma pendência |
| Dia comum | Pix para conferir e um carro pronto sem pagamento (é o estado inicial) |
| Dia cheio de pendências | Conta vencida, peça sem nota no estoque, entrega atrasada, Pix sem OS (para ligar à OS certa), estoque baixo |

Endereços das telas: `#/inicio`, `#/agenda`, `#/os`, `#/os/nova`, `#/caixa`, `#/cadastros`, `#/ajustes`. No computador, o app aparece numa moldura de celular com o roteiro ao lado. No celular, ocupa a tela toda.

## Estrutura

```
index.html   o app inteiro (HTML, CSS e JS em seções comentadas)
README.md    este arquivo
.nojekyll    faz o GitHub Pages servir os arquivos como estão
.gitignore   deixa de fora a pasta de cache da ferramenta de design
```

## Publicar no GitHub Pages

1. No GitHub, crie um repositório público, por exemplo `camber-mockup`.
2. Suba os três arquivos na branch `main`, pela web (**Add file › Upload files**) ou pelo terminal:
   ```bash
   git add index.html README.md .nojekyll
   git commit -m "Mockup do MVP do Camber"
   git remote add origin https://github.com/<usuario>/camber-mockup.git
   git push -u origin main
   ```
3. Em **Settings › Pages**, escolha **Deploy from a branch**, depois **main** e a pasta **/ (root)**, e salve.
4. Em um ou dois minutos o mockup fica no ar em `https://<usuario>.github.io/camber-mockup/`.

As fontes (Inter, JetBrains Mono e Material Symbols Rounded) vêm do Google Fonts. Sem internet o app funciona igual, mas usa a fonte do sistema e os ícones viram letras. Nomes, placas e telefones são fictícios.
