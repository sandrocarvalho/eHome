# Sistema de Criação de Planta Baixa de Casa com Agentes

Este projeto implementa um sistema simples para gerar uma planta baixa de casa com base em especificações do usuário, utilizando o Google AI Platform e o framework Google ADK (Agent Development Kit). O sistema é composto por uma cadeia de agentes que trabalham juntos para buscar informações, julgar os resultados e, potencialmente, gerar uma representação visual da planta.

## Visão Geral do Projeto

O objetivo deste projeto é demonstrar a capacidade de construir sistemas baseados em agentes que interagem e colaboram para alcançar um objetivo complexo. Neste caso, o sistema simula o processo de design de uma casa, desde a especificação inicial até a geração de uma descrição ou esboço da planta baixa.

O fluxo de trabalho geral é o seguinte:

1.  O **Usuário** fornece as especificações desejadas para a casa.
2.  O **Agente Buscador** utiliza uma ferramenta de busca (simulada neste código como `google_search` do Google ADK) para encontrar informações sobre plantas baixas que se aproximem das especificações.
3.  O **Agente Julgador** avalia as plantas baixas encontradas pelo Agente Buscador e seleciona a que melhor se adapta às especificações do usuário, fornecendo uma justificativa.
4.  (Opcional, dependendo da implementação completa) O **Agente Desenhista** (atualmente comentado no código principal) utilizaria um modelo de geração de imagem para criar um esboço visual da planta baixa selecionada.

## Tecnologias Utilizadas

*   **Python:** Linguagem de programação principal.
*   **Jupyter Notebook:** Ambiente de desenvolvimento interativo.
*   **Google AI Platform (Gemini Models):** Utilizado para os modelos de linguagem que alimentam os agentes.
*   **Google ADK (Agent Development Kit):** Framework para construção de agentes.
*   **`google-genai`:** Biblioteca Python para interagir com os modelos Gemini.
*   **`IPython.display` e `textwrap`:** Para formatar e exibir a saída no Jupyter Notebook.

## Pré-requisitos

Para executar este código, você precisará ter:

*   Uma conta Google Cloud.
*   Acesso aos modelos Google Gemini via API.
*   Uma API Key do Google Gemini configurada como uma "Secret" chamada `GOOGLE_API_KEY` no ambiente do Google Colab.

## Configuração

1.  **Obtenha uma API Key do Google Gemini:** Siga a documentação oficial do Google AI Platform para obter sua chave.
2.  **Configure a API Key no Google Colab:**
    *   No Google Colab, clique no ícone de chave (`🔑`) no menu lateral esquerdo.
    *   Clique em "Gerenciar secrets".
    *   Clique em "Novo secret".
    *   Defina o "Name" como `GOOGLE_API_KEY`.
    *   Cole sua API Key no campo "Value".
    *   Certifique-se de que a opção "Notebook access" esteja ativada para este notebook.
3.  **Clone o Repositório (se aplicável):** Se este código estiver em um repositório GitHub, clone-o para o seu ambiente local ou abra-o diretamente no Google Colab.
4.  **Execute as Células do Notebook:** Execute as células do Jupyter Notebook sequencialmente. As primeiras células instalarão as dependências necessárias e configurarão o acesso à API.

## Como Executar

1.  Abra o arquivo `.ipynb` em um ambiente Jupyter Notebook ou Google Colab.
2.  Execute todas as células do notebook em ordem.
3.  Quando solicitado, insira as especificações da casa dos seus sonhos no prompt de entrada.
4.  O notebook exibirá os resultados de cada agente na cadeia de execução.

## Estrutura do Código

O código está organizado nas seguintes partes principais:

*   **Instalação de Dependências:** Células iniciais para instalar `google-genai` e `google-adk`.
*   **Configuração da API e do Cliente:** Células para carregar a API Key e inicializar o cliente Google GenAI.
*   **Importações:** Importação das classes e módulos necessários do Google ADK, Google GenAI e bibliotecas padrão.
*   **Funções Auxiliares:**
    *   `call_agent(agent, message_text)`: Uma função para executar um agente e extrair sua resposta final.
    *   `to_markdown(text)`: Uma função para formatar texto em Markdown para melhor visualização no Colab.
*   **Definição dos Agentes:** Funções (`agente_buscador`, `agente_julgador`, `agente_desenhista`) que criam e configuram instâncias da classe `Agent` com instruções e ferramentas específicas.
*   **Lógica Principal de Execução:** A parte final do código que interage com o usuário, chama os agentes na sequência correta e exibe os resultados.

## Agentes

*   **Agente 1: Buscador de Plantas Baixas:**
    *   **Função:** Pesquisar descrições de plantas baixas que correspondam às especificações do usuário usando a ferramenta `google_search`.
    *   **Modelo:** `gemini-2.5-flash-preview-04-17-thinking`
*   **Agente 2: Julgador de Plantas:**
    *   **Função:** Avaliar as plantas encontradas pelo Agente Buscador e selecionar a melhor, fornecendo uma justificativa.
    *   **Modelo:** `gemini-2.5-flash-preview-04-17-thinking`
*   **Agente 3: Desenhista (Comentado):**
    *   **Função:** Gerar uma imagem de planta baixa com base na descrição da planta selecionada pelo Agente Julgador.
    *   **Modelo:** `imagen-3.0-generate-002`
    *   **Nota:** Este agente está atualmente comentado na lógica principal e não será executado por padrão.

## Contribuições

Contribuições são bem-vindas! Se você tiver ideias para melhorar este sistema (por exemplo, adicionar mais agentes, melhorar as instruções, habilitar o agente desenhista), sinta-se à vontade para abrir um "issue" ou enviar um "pull request".

## Licença

MIT

## Contato

[[sandrocarvalho]](https://github.com/sandrocarvalho)
