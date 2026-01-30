# 🤖 AI Multi-Translator: Azure, Google & Groq

Este repositório foi desenvolvido para o Bootcamp de IA da **DIO**.  
O projeto foca na extração de conteúdo técnico de URLs e na tradução automatizada de documentos e artigos.

O grande diferencial deste projeto é a sua **versatilidade**, integrando três provedores de IA diferentes para contornar limitações de cota e explorar o melhor de cada tecnologia.

## 📂 Estrutura do Repositório

O projeto é composto por dois notebooks principais com abordagens distintas:

### 1. `dio-azure-openai.ipynb`: Tradução de Artigos (Web Scraping)

Originalmente planejado para Azure, este notebook foi adaptado para usar **Google Gemini** e **Groq** devido à disponibilidade de cotas gratuitas.

- **Fluxo**: Captura artigos de portais como Dev.to, limpa o HTML e traduz preservando a formatação original.
- **Google Gemini 1.5/2.5 Flash**: Utilizado via SDK `google-genai` para traduções contextuais.
- **Groq (Llama-3.3-70b)**: Utilizado via `langchain-groq` para processamento ultra-rápido.
- **BeautifulSoup4**: Extração de texto limpo, removendo scripts e estilos desnecessários.

### 2. `dio-azure-translator.ipynb`: Tradução de Documentos (Azure)

Focado no uso dos serviços cognitivos da Microsoft para processar arquivos locais.

- **Azure AI Translator**: API oficial para tradução de textos com alta fidelidade.
- **Python-Docx**: Biblioteca para manipulação de arquivos `.docx`, permitindo a tradução parágrafo por parágrafo e geração de um novo arquivo traduzido.

## 🚀 Como Começar

### Instalação das Dependências

Instale todos os pacotes necessários de uma só vez:

```bash
pip install -U google-genai langchain-groq beautifulsoup4 requests python-docx
```

### Configuração de chaves

Para rodar os notebooks, você precisará configurar suas chaves de API.  
No código, você pode definir como variáveis de ambiente ou diretamente nas variáveis:

- **GOOGLE_API_KEY**: Obtida no Google AI Studio.
- **GROQ_API_KEY**: Obtida no Groq Console.
- **subscription_key**: Obtida no portal do Azure para o serviço Translator.

### Execução do Fluxo

- **Extração**: O script acessa a URL e remove tags desnecessárias (menus, rodapés).
- **Processamento**: O texto limpo é enviado para a IA escolhida.
- **Saída**: O conteúdo é entregue em Markdown (para artigos) ou em um novo arquivo `.docx` traduzido.

## ⚠️ Observações sobre Limites (Rate Limit)

Este projeto utiliza camadas gratuitas.  
Caso receba o erro `429 RESOURCE_EXHAUSTED`, aguarde cerca de **60 segundos** para que a cota de requisições por minuto seja resetada pelos provedores.

## 💡 Dica de mestre

Certifique-se de que a biblioteca `google-genai` está na versão mais atual para evitar erros ao chamar o modelo **gemini-2.5-flash**.

---

Desenvolvido por **Franciso Rabelo** durante o *Bootcamp Microsoft Azure AI Fundamentals*.
