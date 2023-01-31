## Descrição:

 Este projeto tem como finalidade executar um robô de forma assistida utilizando o UiPath Studio.
 
 - Efetua login em um sistema web;
 - Baixa todos os relatórios mensais de um fornecedor específico;
 - Gera um relatório anual;
 - Armazena os dados gerados;
 - Efetua logout do sistema;
 
 
## Instruções:

Criar um fluxo de trabalho que: 
 - Efetua login no sistema web Acme;
 - Reseta os dados de teste do sistema;
 - Navega até a página "Work Items";
 - Extrai dados e filtra por coluna (Type=WI4,Status=Open)
 - Insere os dados filtrados em fila do Orquestrador;
 - Para cada atividade do tipo WI4 executa os seguintes passos:
  - Abre a página 'Detalhes' da atividade selecionada para recuperar o ID fiscal do fornecedor;
  - Volta para o Dashboard e acessa a seção 'Download Monthly Report' no menu 'Reports';
  - Preenche o ID fiscal do fornecedor, baixa todos os relatórios mensais correspondentes para 2022;
  - Agrupa todos os relatórios mensais baixados em um único relatório anual do Excel;
  - Carrega o relatório anual do Excel resultante na seção "Carregar relatório anual" no menu Relatórios;
  - Preenche o Vendor TaxID, define o ano como 2022 e seleciona o arquivo em seu disco rígido. Isso retornará um ID de upload exclusivo;
  - Volta para a página 'Detalhes do item' de trabalho e seleciona 'Atualizar item de trabalho';
  - Define o status como "Concluído";    
  - Continua com a próxima atividade WI4;    
 - Encerra o sistema web Acme;

## Requisitos:

 Os requisitos para a execução deste robô são:

- Ter o navegador Google Chrome instalado; 
- Ter a extensão UiPath Automation para guias anônimas ativada;
- Ajustar arquivo de configuração 'Data\Config.xlsx' conforme os parâmetros do usuário;
