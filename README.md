🎬 LocaFlex — Locadora de Filmes Online

"Sua locadora dos seus filmes favoritos no precinho!"

O LocaFlex é uma aplicação web front-end que simula uma locadora de filmes digital com estética retrô e navegação intuitiva. O sistema permite explorar títulos em destaque, filtrar um catálogo dinâmico, realizar cadastro de clientes e simular o pagamento de aluguéis com regras de desconto e cupons promocionais.

📁 Estrutura do Projeto

O projeto é organizado em páginas HTML independentes conectadas entre si via navegação e parâmetros de URL (Query Strings), acompanhadas por folhas de estilo CSS dedicadas:

locaflex/
├── index.html                  # Página inicial (Home) com filmes em destaque
├── catalogo.html               # Catálogo completo com busca e filtros dinâmicos
├── cadastrocliente.html        # Formulário de cadastro de novos clientes
├── simuladorpagamentos.html    # Calculadora e simulador de checkout/aluguel
├── sobre.html                  # Página institucional com a história da locadora
├── indexStyle.css              # Folha de estilos principal (Home, Catálogo e Cadastro)
├── simuladorpagamentoStyle.css # Folha de estilos específica do simulador de pagamentos
├── sobreStyle.css              # Folha de estilos específica da página Sobre
└── README.md                   # Documentação do projeto


🚀 Funcionalidades por Página

1. Página Inicial (index.html)

Apresenta a identidade visual da LocaFlex e o menu de navegação principal.

Exibe uma vitrine com 4 filmes em destaque (A voz do silêncio, Jovens Bruxas, Festa no céu e Edward mãos de tesoura), incluindo gênero, classificação indicativa e pôster.

Botões de "Alugar" que redirecionam diretamente para o simulador de pagamento já com o filme selecionado via parâmetro na URL (?filme=id-do-filme).

2. Catálogo Completo (catalogo.html)

Renderização Dinâmica: Os 10 títulos do acervo são armazenados em um array de objetos JavaScript e renderizados automaticamente na tela.

Busca em Tempo Real: Campo de pesquisa por nome do filme (oninput).

Filtros por Gênero: Botões interativos para filtrar entre Todos, Animação, Drama, Comédia, Aventura / Ficção e Suspense / Terror.

Barra de Resumo: Calcula e exibe em tempo real a quantidade de filmes filtrados e a soma total dos valores dos itens exibidos.

3. Cadastro de Cliente (cadastrocliente.html)

Formulário completo com validação nativa HTML5 (required) para:

Nome Completo

E-mail

Telefone / WhatsApp

Data de Nascimento

Senha

Intercepta o envio (submit) via JavaScript para exibir confirmação imediata e limpar os campos.

4. Simulador de Pagamentos (simuladorpagamentos.html)

Integração via URL: Lê o parâmetro ?filme= enviado pela Home ou pelo Catálogo para pré-selecionar o título no formulário.

Configuração do Aluguel:

Seleção de filme (valores entre R$ 3,90 e R$ 5,90).

Quantidade de dias ou unidades (1 a 30).

Formato de mídia: Digital / Streaming (sem custo extra) ou DVD / Blu-ray Físico (+ R$ 4,00 de taxa única).

Regras de Desconto:

Combo Maratona: Alugando 3 ou mais dias/unidades, aplica-se automaticamente 15% de desconto.

Cupom Promocional: Inserindo o código TELE20, aplica-se +20% de desconto acumulativo (podendo chegar a 35% off no total).

Exibe o resumo detalhado (Subtotal, Desconto aplicado e Total a Pagar) formatado em Real (R$).

5. Sobre a Locadora (sobre.html)

Conta a história fictícia e a proposta retrô da locadora, destacando números do acervo, pilares de atendimento (Curadoria, Comunidade, Nostalgia) e links de chamada para ação (CTA).

🛠️ Tecnologias Utilizadas

HTML5: Estruturação semântica das páginas e formulários.

CSS3: Estilização modularizada com variáveis CSS, layouts responsivos e badges de classificação indicativa.

JavaScript (Vanilla): Manipulação do DOM, filtragem de arrays, leitura de URLSearchParams, cálculos financeiros e formatação de moeda (toLocaleString('pt-BR')).

💻 Como Executar o Projeto

Por ser um projeto front-end estático, não há necessidade de instalar dependências ou configurar servidores complexos:

Baixe ou clone os arquivos do repositório em uma mesma pasta.

Certifique-se de que os arquivos .css (indexStyle.css, simuladorpagamentoStyle.css e sobreStyle.css) estejam no mesmo diretório dos arquivos .html.

Abra o arquivo index.html em qualquer navegador moderno (Chrome, Edge, Firefox, Safari).

(Opcional) Para desenvolvimento, utilize a extensão Live Server no VS Code para recarregamento automático.

⚠️ Observações de Manutenção (Pontos de Atenção no Código)

Durante a revisão da estrutura atual, foram identificados pequenos detalhes de integração entre páginas que podem ser ajustados futuramente:

Links de navegação em sobre.html: O menu superior aponta para cadastro.html, enquanto o arquivo existente é cadastrocliente.html (como já está correto no botão do rodapé da mesma página).

IDs de filmes entre catalogo.html e simuladorpagamentos.html: Alguns valores do <select> no simulador (ex.: coraline-e-o-mundo-secreto, a-viagem-de-chihiro, 10-coisas-que-eu-odeio-em-voce) diferem ligeiramente dos ids definidos no array do catálogo (coraline, viagem-chihiro, 10-coisas). Padronizar esses slugs garantirá que a pré-seleção automática funcione para 100% dos filmes.

📄 Licença

Projeto desenvolvido para fins educacionais e de portfólio. © 2026 LocaFlex.
