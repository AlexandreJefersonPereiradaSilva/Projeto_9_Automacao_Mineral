# Projeto 9: Robô de Monitoramento de Processos Minerários (RPA) 🤖⛏️
---
## O Cenário 👨‍💼

Você é analista em uma consultoria de geoprocessamento e sua equipe precisa monitorar todos os processos minerários ativos no estado de São Paulo para um cliente importante. A fonte oficial desses dados é o SIGMINE (Sistema de Informações Geográficas da Mineração), disponibilizado pelo Governo Federal.

A tarefa é repetitiva: toda semana, você precisa entrar no Portal de Dados Abertos, navegar até o conjunto de dados do SIGMINE, baixar o pacote completo de dados do Brasil e verificar se há atualizações.

Sua missão é automatizar 100% deste processo. Você vai construir um "robô" (script RPA) com `pyautogui` que fará o trabalho pesado, garantindo que sua equipe sempre tenha os dados mais recentes sem gastar tempo com tarefas manuais.


## 📋 Requisitos da Missão

O robô precisa ser um assistente digital confiável. Ele deve seguir os passos de forma precisa para baixar o conjunto de dados correto.

1.  **Acessar a Fonte de Dados:** O script deve abrir um navegador e ir diretamente para a página do SIGMINE no Portal de Dados Abertos.
      * **URL:** `https://dados.gov.br/dados/conjuntos-dados/sistema-de-informacoes-geograficas-da-mineracao-sigmine`
2.  **Navegar até os Dados:** O robô deve localizar e clicar no botão principal para acessar a página de download dos recursos.
3.  **Baixar o Pacote de Dados:** Na página de recursos, o script deve identificar o link para o download do arquivo compactado (geralmente um `.zip`) que contém todos os processos minerários do Brasil e iniciar o download.
4.  **Confirmar o Download:** O robô deve aguardar tempo suficiente para que o download do arquivo (que pode ser grande) seja concluído antes de encerrar sua execução.

## 💡 Roteiro Sugerido para o Sucesso

A chave para um robô RPA de sucesso é mapear os cliques e usar pausas para esperar o carregamento das páginas.

1.  **Instale e importe as bibliotecas**: `pip install pyautogui`. No seu script, comece com `import pyautogui` e `import time`.
2.  **Abra o Navegador e Acesse o Site**:
    ```python

    pyautogui.write('https://dados.gov.br/dados/conjuntos-dados/sistema-de-informacoes-geograficas-da-mineracao-sigmine')
    pyautogui.press('enter')
    ```
3.  **Encontre e Clique no Botão "Acessar o recurso"**:
      * Navegue até a área necessária (Recursos) com `pyautogui`.
      * Programe o robô para esperar e clicar neste botão:
    <!-- end list -->
    
4.  **Encontre e Clique no Link de Download**:
      * Após clicar, o navegador irá para uma nova página. Nela, tire um screenshot do link de download do arquivo principal (geralmente um arquivo `.zip`).
5.  **Aguarde o Fim do Download**: Dê um tempo generoso para o download, já que o arquivo pode ser grande.
    ```python
    time.sleep(n)
    print("Processo finalizado!")
    ```
