# 🤖 AI Article Translator - DIO Bootcamp Azure

Este repositório contém ferramentas de processamento de linguagem natural desenvolvidas para o Bootcamp de IA da [DIO](https://www.dio.me/). O projeto foca em extrair conteúdo técnico de URLs (como o Dev.to) e realizar traduções automáticas de alta qualidade utilizando serviços de IA de ponta.

## 📂 Estrutura do Repositório

O projeto é composto por dois notebooks principais, cada um explorando uma abordagem de integração:

* **`dio-azure-openai.ipynb`**: Notebook principal que realiza o fluxo completo de *Web Scraping* e tradução. Originalmente desenvolvido para Azure OpenAI e adaptado para suportar o **Google Gemini 1.5 Flash**.
* **`dio-azure-translator.ipynb`**: Exploração de serviços de tradução específicos e manipulação de textos para diferentes idiomas.

## 🛠️ Tecnologias e Bibliotecas

* **Python 3.12**
* **[Google GenAI SDK](https://github.com/google/generative-ai-python)**: Utilizado para a tradução com o modelo Gemini.
* **BeautifulSoup4**: Para extração e limpeza de dados de páginas web.
* **Requests**: Para requisições HTTP.
* **Markdown**: Formato de saída para garantir que o artigo mantenha a legibilidade.

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

📝 Exemplo de Uso
Python
url = '[https://dev.to/exemplo-de-artigo](https://dev.to/exemplo-de-artigo)'
text = extract_text_from_url(url)
article = translate_article(text, "pt-br")
print(article)
⚠️ Observações sobre Limites de Cota (Rate Limit)
Este projeto utiliza a camada gratuita da API do Gemini. Caso receba o erro 429 RESOURCE_EXHAUSTED, aguarde cerca de 60 segundos para que a cota de requisições por minuto seja resetada.

Desenvolvido por [Seu Nome] durante o Bootcamp Microsoft Azure AI Fundamentals.


---

### Dica para o seu GitHub:
Para deixar o projeto ainda mais profissional, você pode criar um arquivo chamado `.gitignore` e escrever apenas isso dentro dele:
```text
.env
__pycache__/
.ipynb_checkpoints/
