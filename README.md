# Modelo Lógico para Banco de Dados - Clínica Médica

Este repositório contém as instruções para a criação do modelo lógico do banco de dados de uma clínica médica, incluindo a modelagem e manipulação de dados utilizando SQL.

## Ferramentas Utilizadas

- [brModelo Web](https://www.brmodeloweb.com/lang/pt-br/index.html) (versão online) ou [brModelo Desktop](https://sourceforge.net/projects/brmodelo) (versão offline)
- Alternativamente, é possível utilizar o [draw.io](https://app.diagrams.net/)
- Microsoft SQL Server Management Studio (SSMS)

## Passo a Passo

### 1. Criando o Modelo Lógico

1. Abra o brModelo ou acesse via site.
2. Selecione a opção **Modelo Lógico**.
3. No menu **Artefatos**, clique em **Tabela** e insira a primeira tabela do modelo.
4. Renomeie a tabela para **cliente** e adicione os seguintes campos:
   - `codigo` (INTEGER, Chave Primária)
   - `nome` (VARCHAR(40))
   - `nascimento` (DATE)
5. Utilize o mesmo procedimento para criar as demais tabelas.
6. Posicione as tabelas e crie os seguintes relacionamentos:
   - Um paciente pode agendar várias consultas.
   - Um médico pode atender vários pacientes por dia.
   - Cada consulta pode ou não ter exames associados.
   - Um pedido de exame só pode conter um tipo de exame.
   - Cada exame pode ser solicitado por vários pedidos de exame.

### 2. Criando e Manipulando o Banco de Dados no SQL Server

1. Abra o **Microsoft SQL Server Management Studio (SSMS)**.
2. Baixe o arquivo `tb_clinica_medica.sql` e abra no SSMS.
3. Execute os seguintes comandos:
   - Criar o banco de dados:
     ```sql
     CREATE DATABASE clinica_medica;
     ```
   - Criar tabelas conforme o modelo lógico.
   - Adicionar chaves primárias e estrangeiras.
   - Inserir dados nas tabelas:
     ```sql
     INSERT INTO paciente (codigo, nome, nascimento) VALUES (1, 'João Silva', '1985-06-20');
     ```
   - Atualizar e deletar registros:
     ```sql
     UPDATE paciente SET nome = 'João Souza' WHERE codigo = 1;
     DELETE FROM medico WHERE crm = 12345;
     ```
4. Execute `SELECT * FROM` para verificar os dados.

## Considerações Finais

- Utilize boas práticas ao nomear tabelas e campos (sem acentos, espaços ou caracteres especiais).
- Sempre revise o modelo lógico antes de criar as tabelas no SQL.
- Teste os comandos SQL antes de executar em um ambiente de produção.

