Visão geral
Portais AET é um app web leve que reúne, em seis botões, os portais de Autorização Especial de Trânsito (AET) de cargas e veículos especiais, e traz um assistente de IA para tirar dúvidas. Serve a quem precisa acessar portais de AET de órgãos diferentes e quer chegar ao certo com um toque.
A tela tem só três partes: o título, a grade de botões e o assistente. Cada botão abre o portal em uma nova aba.
Portais incluídos
O app tem seis botões, na ordem abaixo, e cada um abre o endereço exatamente como foi informado.
Órgão
UF
Portal
Endereço
DNIT
Federal
SIAET
https://siaet.dnit.gov.br
DER-PE
PE
Plug
https://plug.der.pe.gov.br/?next=/
DER-SP
SP
Via Digital
https://app.der.sp.gov.br/viadigital/
DETRAN-CE
CE
AET Especial
https://aetespecial.detran.ce.gov.br/
Infraestrutura BA
BA
SIDER
https://sider.infraestrutura.ba.gov.br/aet/efetuarLogout.do
Goinfra
GO
Portal AET
https://portalaet.goinfra.go.gov.br/portalaet/abrirConRequerimento.do
O endereço da Bahia termina em efetuarLogout.do, que é uma página de saída. Se ela não levar à tela de entrada, troque pelo endereço de login do SIDER.
Assistente de IA
O assistente responde dúvidas sobre AET e indica qual portal usar conforme o trecho da rota. Ele roda dentro do próprio app, na capacidade de IA nativa das páginas publicadas no Claude, sem chave de API nem servidor próprio.
• Entrada: campo de texto com envio por botão ou Enter (Shift+Enter quebra a linha). Três perguntas de exemplo aparecem como atalhos até a primeira pergunta.
• Contexto: ele conhece os seis portais do app e sabe a que órgão e UF cada um pertence.
• Regras de resposta: português do Brasil, no máximo seis linhas, e indicação do portal quando fizer sentido (federal ou estadual).
• Limites: não deve inventar prazos, valores, artigos de lei ou números de resolução. Quando não tiver certeza, diz isso e orienta a confirmar no portal do órgão ou na resolução vigente do CONTRAN.
• Consentimento: na primeira pergunta o Claude pede a permissão do usuário. Se for negada, o assistente é desativado e os botões continuam funcionando.
• Memória: a conversa vale só enquanto a página está aberta. Nada é salvo.
Como usar
O app abre por um link e funciona no computador e no celular.
1.  Abra o link do app no navegador.
2.  Toque no botão do órgão desejado. O portal abre em uma nova aba.
3.  Para tirar uma dúvida, escreva no campo do assistente ou toque em uma das perguntas de exemplo.
4.  Autorize o assistente quando o Claude pedir permissão, na primeira pergunta.
No celular: use a opção "Adicionar à tela inicial" do navegador para ter um ícone de acesso rápido.
Compartilhamento: a página está privada, e só quem criou consegue abri-la. Para outras pessoas usarem, compartilhe pelo menu Share da página.
Tema: o visual acompanha o modo claro ou escuro do aparelho.
Estrutura técnica e manutenção
O app é uma única página HTML, sem servidor e sem dependências de código. Só as fontes Inter e Space Grotesk vêm do Google Fonts, com fonte do sistema como alternativa.
Parte
Como funciona
Botões
Links <a> comuns com target="_blank", em grade de duas colunas
Assistente
Capacidade sample do Claude, com modelo rápido e resposta exibida em tempo real
Tema
Cores definidas em variáveis, com versões clara e escura
Armazenamento
Nenhum. A conversa fica só na memória da página
Trocar o endereço de um portal: edite o href do botão correspondente na seção de navegação da página.
Incluir um portal: copie um bloco <a class="site">, ajuste sigla, nome e endereço, e acrescente a linha do portal na lista PORTAIS do script, para o assistente conhecê-lo.
Republicar: depois de editar o arquivo, publique de novo no mesmo endereço. O link do app não muda.
Limitações e próximos passos
O app só direciona para os portais: não faz login, não guarda dados e não emite nem acompanha AETs.
• O assistente dá orientação geral e pode errar. Confirme regras, prazos e documentos no portal do órgão.
• O assistente só funciona onde a página roda com IA nativa do Claude e depende da permissão de quem a abre.
• Os endereços podem mudar. Se um botão deixar de funcionar, atualize o href.
Próximos passos possíveis:
[ ] Incluir outros estados e órgãos
[ ] Adicionar favoritos ou ordem personalizada dos botões
[ ] Confirmar o endereço de entrada do SIDER (Bahia)
