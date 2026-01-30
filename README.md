# 🤖 AI Multi-Translator: Azure, Google & Groq
Este repositório foi desenvolvido para o Bootcamp de IA da DIO, focado em extração de conteúdo técnico de URLs e tradução de documentos. O projeto destaca-se pela versatilidade, utilizando três provedores de IA diferentes para contornar limitações de cota e explorar diferentes capacidades de processamento.

## 📂 Estrutura do Repositório

O projeto é composto por dois notebooks principais, cada um explorando uma abordagem de integração:

* **`dio-azure-openai.ipynb`**: Tradução de Artigos Técnicos (Web Scraping)
Localizado no arquivo que utiliza Google Gemini e Groq. Este fluxo captura artigos do portal Dev.to, limpa o conteúdo e o traduz mantendo a formatação original. Google Gemini 1.5/2.0 Flash: Utilizado via SDK google-genai para traduções contextuais profundas. Groq (Llama-3.3-70b): Utilizado via langchain-groq para traduções ultra-rápidas. BeautifulSoup4: Responsável por extrair o texto limpo, removendo scripts e estilos HTML.

* **`dio-azure-translator.ipynb`**: Tradução de Documentos (Azure Translator)
Localizado no notebook que utiliza os serviços cognitivos da Microsoft para processar arquivos locais.

Azure AI Translator: API oficial para tradução de textos com alta fidelidade.

Python-Docx: Utilizado para ler arquivos .docx, traduzir parágrafo por parágrafo e gerar um novo arquivo traduzido.

## 🛠️ Tecnologias e Dependências
Bash
pip install -U google-genai langchain-groq beautifulsoup4 requests python-docx

🔑 Configuração de Chaves
Para rodar este projeto, você precisará configurar as seguintes variáveis:

GOOGLE_API_KEY: Obtida no Google AI Studio.

GROQ_API_KEY: Obtida no Groq Console.

subscription_key (Azure): Obtida no portal do Azure para o serviço Translator.

Este projeto demonstra a capacidade de integrar múltiplas nuvens e SDKs para resolver problemas reais de tradução e processamento de dados.

Dica de mestre: No seu GitHub, lembre-se de que os notebooks salvam o estado da última execução. Como você usou o gemini-2.5-flash no código, certifique-se de que a biblioteca google-genai está na versão mais atual para evitar erros de modelo não encontrado!

## 🚀 Como Começar

### 1. Requisitos
Instale as dependências necessárias no seu ambiente:

```bash
pip install -U google-genai beautifulsoup4 requests

2. Configuração de API
Para rodar os notebooks, você precisará de uma chave de API do Google AI Studio. No código, configure sua chave como variável de ambiente ou diretamente no script:

Python
import os
os.environ["GOOGLE_API_KEY"] = "SUA_CHAVE_AQUI"
3. Execução
O fluxo principal do projeto segue estes passos:

Extração: O script acessa a URL fornecida e remove tags HTML desnecessárias (scripts, menus, rodapés).

Processamento: O texto limpo é enviado para a IA.

Tradução: O modelo (Gemini 1.5 Flash) traduz o conteúdo técnico respeitando o contexto e a formatação Markdown.

⚠️ Observações sobre Limites de Cota (Rate Limit)
Este projeto utiliza a camada gratuita da API do Gemini. Caso receba o erro 429 RESOURCE_EXHAUSTED, aguarde cerca de 60 segundos para que a cota de requisições por minuto seja resetada.

Desenvolvido por [Seu Nome] durante o Bootcamp Microsoft Azure AI Fundamentals.

