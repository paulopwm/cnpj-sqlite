# CNPJ-SQLITE
Script em python para converter os arquivos de dados públicos de CNPJs para o formato SQLITE. O código é compatível com o layout das tabelas disponibilizadas pela Receita Federal a partir de 2021.

## Dados públicos de CNPJs no site da Receita:
Os arquivos csv zipados com os dados de CNPJs estão disponíveis em https://www.gov.br/receitafederal/pt-br/assuntos/orientacao-tributaria/cadastros/consultas/dados-publicos-cnpj ou http://200.152.38.155/CNPJ/ (aqui os arquivos aparecem primeiro). 

## Pré-requisitos:
Python 3.8;<br>
Bibliotecas pandas, dask e sqlalchemy.<br>

## Utilizando o script:
Este projeto não baixa os arquivos do site da Receita. Sugiro utilizar um gerenciador de downloads. Obtenha uma relação dos arquivos disponíveis pelo comando<br>
python dados_cnpj_lista_url.py<br>

Baixe todos os arquivos zipados do site da Receita e salve na pasta "dados-publicos-zip".<br>
O download no site da Receita é lento, pode demorar várias horas. <br><br>
Crie uma pasta com o nome "dados-publicos".<br>

Para iniciar a conversão dos arquivos para o formato sqlite, digite em um console DOS<br>
python dados_cnpj_para_sqlite.py<br>

O processamento durou cerca de 2hs em um notebook i7 de oitava geração.

Ao final, será gerado um arquivo cnpj.db, no formato sqlite, que pode ser aberto no DB Browser for SQLITE (https://sqlitebrowser.org/).<br>

O arquivo cnpj.db poderá ser usado no meu projeto rede-cnpj (https://github.com/rictom/rede-cnpj), que permite visualização gráfica de relacionamentos entre empresas e sócios. Este projeto está rodando online em https://www.redecnpj.com.br.<br>
O projeto https://github.com/rictom/cnpj_consulta utiliza o arquivo cnpj.db para visualizar os dados de cnpj em formato de tabela.<br>

## Arquivo sqlite já tratado:<a id="arquivo_sqlite"></a>
O banco de dados no formato sqlite, referência 9/4/2022 (.D20409.), está disponível em  https://www.mediafire.com/folder/1vdqoa2mk0fu9/cnpj-sqlite.
Baixe o arquivo cnpj.7z e utilize o 7-zip (https://www.7-zip.org/download.html) para descompactar.<br>

![image](https://user-images.githubusercontent.com/71139693/154585662-8c38c206-cb80-492e-8413-47699c79b4fd.png)<br>
Lista das tabelas do arquivo cnpj.db no DBBrowser for SQLITE.

## Conversão para mysql:
O script em https://github.com/rictom/cnpj-mysql faz o carregamento dos dados para o banco de dados em MYSQL.<br>

## Histórico de versões
versão 0.2 (janeiro/2022)
- removido código não utilizado

versão 0.1 (julho/2021)
- primeira versão

