📊 Desafio Telecom X - Análise de Churn e ETL
Fala pessoal! Este é o repositório do meu projeto para o Desafio Telecom X, desenvolvido como parte da formação em Data Science do Oracle Next Education (ONE) em parceria com a Alura.

O principal objetivo deste projeto foi colocar a mão na massa em um cenário real de negócios: pegar uma base de dados bruta, realizar todo o processo de ETL (Extração, Transformação e Carga) e, em seguida, fazer uma Análise Exploratória (EDA) para entender os motivos que levam os clientes a cancelarem seus serviços (o famoso Customer Churn).

🛠️ Tecnologias Utilizadas
Python (Linguagem principal)

Pandas (Para manipulação e limpeza dos dados)

Matplotlib & Seaborn (Para a criação dos gráficos e visualizações)

Jupyter Notebook (Ambiente de desenvolvimento)

🔍 O Processo (Como o problema foi resolvido)
1. Extração (O problema do JSON aninhado)
Os dados foram fornecidos em um arquivo JSON (TelecomX_Data.json), mas não era uma tabela simples. As informações financeiras, de internet e de telefone estavam "escondidas" em dicionários dentro das colunas (dados aninhados). Para resolver isso, utilizei a função pd.json_normalize do Pandas, que "achatou" esses dados e transformou tudo em uma tabela estruturada.

2. Transformação (A faxina)
Com os dados extraídos, fiz a limpeza da base:

Removi os prefixos estranhos que ficaram nos nomes das colunas.

Tratei valores em branco na coluna de Gasto Total (Total), forçando a conversão para numérico (usando coerce) e removendo os registros de clientes novos que ainda não tinham faturas fechadas.

Removi dados duplicados para garantir a integridade da análise.

3. Carga e Análise (Gerando valor)
Gerei um arquivo telecomx_dados_limpos.csv pronto para ser usado em dashboards (como Power BI) e criei gráficos com o Seaborn para cruzar a variável de cancelamento (Churn) com o perfil do cliente.

💡 Principais Descobertas (Insights)
O perigo do Cheque Eletrônico: A análise mostrou claramente que a maior taxa de evasão acontece com clientes que utilizam o "Electronic Check" como forma de pagamento. Clientes com débito automático ou cartão de crédito são muito mais fiéis.

Preço importa: O boxplot gerado na análise revelou que clientes com planos mais caros (mensalidades próximas a $80) cancelam muito mais do que os clientes de planos básicos (abaixo de $65).

Recomendação para a empresa: Criar campanhas de incentivo para migração de método de pagamento (tirar a galera do cheque eletrônico) e revisar a entrega de valor dos planos mais caros.

🚀 Como rodar o projeto
Clone este repositório.

Certifique-se de ter o Python e as bibliotecas listadas instaladas (pip install pandas matplotlib seaborn).

Abra o arquivo TelecomX_BR.ipynb no Jupyter Notebook ou Google Colab.

Rode as células sequencialmente (o arquivo TelecomX_Data.json precisa estar na mesma pasta).
