# Como instalar o Planejador de Rotas

Você recebeu 3 arquivos:
- `Planejador_de_Rotas.xlsx` — a planilha (layout de entrada e resultado)
- `modJSON.bas` — código auxiliar (leitor de JSON)
- `modRota.bas` — código principal (busca a rota)

## Passo 1 — Habilitar a aba Desenvolvedor (só na primeira vez)
No Excel: **Arquivo > Opções > Personalizar Faixa de Opções** → marque **Desenvolvedor** → OK.

## Passo 2 — Abrir o Editor VBA
Abra `Planejador_de_Rotas.xlsx` e pressione **Alt + F11**.

## Passo 3 — Importar os dois módulos
No Editor VBA: **Arquivo > Importar Arquivo...**
- Selecione `modJSON.bas` → Abrir
- Repita: **Arquivo > Importar Arquivo...** → selecione `modRota.bas` → Abrir

Você verá os dois módulos aparecerem em "Módulos", na árvore à esquerda.

## Passo 4 — Salvar como planilha habilitada para macro
**Arquivo > Salvar Como** → escolha o tipo **Pasta de Trabalho Habilitada para Macro do Excel (*.xlsm)**.
(Isso é obrigatório — um .xlsx comum não guarda macros.)

## Passo 5 — Preencher e rodar
1. Volte para a aba "Rota" na planilha.
2. Preencha **Origem**, até 4 **Pontos de passagem** (opcionais) e **Destino** nas células amarelas.
3. Rode a macro: aba **Desenvolvedor > Macros** → selecione `BuscarRota` → **Executar**.
   (Ou aperte **Alt+F8**, selecione `BuscarRota`, Executar.)
4. Se aparecer aviso de segurança/macro ao abrir o arquivo, clique em **Habilitar Conteúdo**.

O resultado (distância, tempo estimado, sequência de cidades e rodovias percorridas) aparece
automaticamente nas células abaixo.

## Observações importantes
- **Precisa de internet** — a macro consulta dois serviços gratuitos: Nominatim (converte
  cidade em coordenadas) e OSRM (calcula a rota).
- **Sem chave de API** — nenhum cadastro é necessário, mas por isso o serviço é gratuito e
  pode ser mais lento ou instável em horários de pico. Se der erro de conexão, tente de novo.
- **Nomes de rodovias**: o OSRM traz o nome/número da via como está mapeado no OpenStreetMap
  (ex: "BR-101", "Rodovia Régis Bittencourt"). Trechos sem nome mapeado aparecem como
  "(via sem nome / trecho local)".
- **Cidades no caminho**: a lista de cidades é exatamente a Origem + Pontos de passagem +
  Destino que você digitou — o sistema não "descobre" cidades intermediárias que você não
  informou. Se quiser isso (detectar automaticamente todas as cidades que a rota atravessa),
  me avise — dá pra adicionar uma segunda etapa que faz geocodificação reversa ao longo do
  trajeto.
- Seja específico nos endereços (ex: "Caruaru, PE" em vez de só "Caruaru") para evitar
  ambiguidade com cidades de mesmo nome em outros estados.
