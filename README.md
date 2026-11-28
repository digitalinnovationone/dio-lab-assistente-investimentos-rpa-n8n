<p align="center">
  <img
    src="./cover_840x560.gif"
    alt="Assistente de Investimentos com RPA e IA Generativa"
    width="100%"
  >
</p>

<h1 align="center">Assistente de Investimentos com RPA e IA Generativa</h1>

<p align="center">
  <a href="https://www.python.org/">
    <img src="https://img.shields.io/badge/Python-3.10%2B-3776AB?style=for-the-badge&amp;logo=python&amp;logoColor=white" alt="Python 3.10+">
  </a>
  <a href="https://n8n.io/">
    <img src="https://img.shields.io/badge/n8n-orchestration-EA4B71?style=for-the-badge&amp;logo=n8n&amp;logoColor=white" alt="Orquestração n8n">
  </a>
  <a href="https://platform.openai.com/docs/">
    <img src="https://img.shields.io/badge/OpenAI-GPT--4%20(opcional)-412991?style=for-the-badge&amp;logo=openai&amp;logoColor=white" alt="OpenAI GPT-4 opcional, não configurado no workflow atual">
  </a>
  <a href="https://ai.google.dev/">
    <img src="https://img.shields.io/badge/Google-Gemini%201.5%20Flash-8E75B2?style=for-the-badge&amp;logo=googlegemini&amp;logoColor=white" alt="Google Gemini 1.5 Flash">
  </a>
  <a href="https://jupyter.org/">
    <img src="https://img.shields.io/badge/Jupyter-Notebook-F37626?style=for-the-badge&amp;logo=jupyter&amp;logoColor=white" alt="Jupyter Notebook">
  </a>
  <a href="https://opensource.org/licenses/MIT">
    <img src="https://img.shields.io/badge/License-MIT-yellow?style=for-the-badge" alt="Licença MIT, conforme declaração do projeto">
  </a>
  <a href="https://codeql.github.com/">
    <img src="https://img.shields.io/badge/CodeQL-security%20analysis-0F80C1?style=for-the-badge&amp;logo=github&amp;logoColor=white" alt="CodeQL — análise de segurança">
  </a>
  <img src="https://img.shields.io/badge/Quality-ISO%209001-0078D4?style=for-the-badge" alt="Referência de qualidade ISO 9001">
  <img src="https://img.shields.io/badge/Lean%20Six%20Sigma-Green%20Belt-6A1B9A?style=for-the-badge" alt="Lean Six Sigma Green Belt">
</p>

## Sobre o Projeto

Este projeto educacional demonstra como combinar **RPA em Python**, **orquestração de workflows no n8n** e **IA generativa** em um cenário de atendimento relacionado ao mercado financeiro.

O notebook extrai dados de uma página de demonstração, organiza informações de clientes — como nome, saldo e perfil de investidor — e prevê o envio desses dados a um webhook do n8n. O workflow processa cada cliente e usa um agente de IA para gerar uma mensagem informativa e personalizada de acordo com o perfil e o saldo.

O projeto não executa transações nem acessa contas financeiras. As mensagens geradas são demonstrativas e não constituem recomendação de investimento.

> **Estado atual da integração:** o notebook ainda contém um TODO para enviar os dados ao webhook, e o workflow exportado está inativo. Para executar o pipeline de ponta a ponta, configure o webhook e as credenciais no n8n e ative o workflow.

## Fluxo de Funcionamento (Pipeline de Dados)

1. **Extração de dados — Web Scraping/RPA**  
   O notebook usa `requests` e `BeautifulSoup` para buscar e interpretar a tabela de clientes da [página de demonstração da DIO](https://digitalinnovationone.github.io/dio-lab-assistente-investimentos-rpa-n8n/).

2. **Processamento e tratamento**  
   Cada linha da tabela é convertida em um dicionário Python com os campos `nome`, `email`, `saldo` e `perfil`. O notebook atual não usa Pandas; a transformação é feita com estruturas nativas do Python.

3. **Orquestração no n8n**  
   O arquivo `n8n/workflow.json` define um webhook POST chamado `clientes`, seguido pelo nó **Split Out**, que separa os dados em itens individuais. O notebook ainda precisa ser conectado ao webhook para enviar a lista de clientes.

4. **IA Generativa**  
   O agente de IA recebe o perfil e o saldo do cliente. O workflow atual está configurado para usar **Google Gemini 1.5 Flash** e inclui opções ilustrativas de investimento no prompt. **OpenAI GPT-4 não está conectado no workflow atual**; pode ser considerado como alternativa mediante configuração de um nó e de credenciais apropriadas.

5. **Resultado Final**  
   Quando o workflow estiver ativo e configurado, o nó **Responder Webhook** devolve o texto gerado pelo agente. A resposta pode então ser apresentada ou utilizada pelo sistema que chamou o webhook.

## Tecno-Stack e Ferramentas

- **Python 3.10+:** linguagem recomendada para executar o notebook.
- **Requests e BeautifulSoup:** dependências usadas atualmente para buscar e interpretar o HTML.
- **Pandas:** não é usado no notebook atual; pode ser adicionado se o processamento tabular evoluir.
- **Jupyter Notebook:** ambiente para executar `rpa/extrair_clientes.ipynb`.
- **n8n:** workflow exportado em `n8n/workflow.json`; requer importação, configuração das credenciais e ativação.
- **Google Gemini 1.5 Flash:** modelo configurado no workflow atual.
- **OpenAI GPT-4:** alternativa possível, ainda não configurada neste repositório.
- **Qualidade e Governança 4.0:** referências a ISO 9001 e Lean Six Sigma Green Belt relacionadas a práticas de qualidade e melhoria contínua; os selos não representam certificação deste projeto.
- **CodeQL:** selo informativo sobre a ferramenta. Não há workflow CodeQL configurado no repositório.
- **Licença MIT:** selo incluído conforme solicitado. O repositório ainda não contém um arquivo `LICENSE`; adicione-o na raiz para formalizar a licença.

## Como Executar o Projeto Localmente

Requer Python 3.10 ou superior. O repositório ainda não possui `requirements.txt`, então as dependências são instaladas diretamente com `pip`.

1. Clone o repositório e entre na pasta do projeto:

   ```bash
   git clone [https://github.com/Rafael-TOZATO/dio-lab-assistente-investimentos-rpa-n8n.git](https://github.com/Rafael-TOZATO/dio-lab-assistente-investimentos-rpa-n8n.git)
   cd dio-lab-assistente-investimentos-rpa-n8n

## 📬 CONTATOS E PERFIS

💻 **PROJECTS & PORTFOLIOS**
* **App Ecosystem / Dev Hub:**<br>https://tozato-ai-core.vercel.app
* **H-Folio Professional:**<br>https://h-folio-I0.vercel.app

🧩 **AGENSI.IO**
* **Creator:**<br>https://www.agensi.io/creators/rafael-ornelas-tozato

🐙 **CODES & REPOSITORIES**
* **GitHub:**<br>https://github.com/Rafael-TOZATO

✍️ **ARTICLES & PUBLICATIONS**
* **Medium:**<br>https://medium.com/@ornelas.tozato
* **DEV Community:**<br>https://dev.to/rafaeltozato

🪟 **MICROSOFT LEARN**
* **Perfil:**<br>https://learn.microsoft.com/pt-br/users/rafaelornelastozato-2209

💼 **LINKEDIN**
* **Perfil Profissional:**<br>https://www.linkedin.com/in/rafaeltozato81

📬 **CONTACT**
* **E-mail:**<br>ornelas.tozato@gmail.com
