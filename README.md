# Gerenciador de Espaçonaves Star Wars

Este repositório contém os scripts SQL para criar um banco de dados que gerencia espaçonaves do universo Star Wars. O banco de dados foi modelado no SQL Server e inclui tabelas para planetas, naves, pilotos, associações entre pilotos e naves, e histórico de viagens.

## Estrutura do Banco de Dados

O banco de dados é composto pelas seguintes tabelas:

1. **Planetas**
   - Armazena informações sobre os planetas do universo Star Wars.
   - Colunas: `IdPlaneta`, `Nome`, `Rotacao`, `Orbita`, `Diametro`, `Clima`, `Populacao`.

2. **Naves**
   - Armazena informações sobre as espaçonaves.
   - Colunas: `IdNave`, `Nome`, `Modelo`, `Passageiros`, `Carga`, `Classe`.

3. **Pilotos**
   - Armazena informações sobre os pilotos.
   - Colunas: `IdPiloto`, `Nome`, `AnoNascimento`, `IdPlaneta`.
   - Relacionamento: `IdPlaneta` faz referência à tabela `Planetas`.

4. **PilotosNaves**
   - Associa pilotos às naves que eles podem pilotar.
   - Colunas: `IdPiloto`, `IdNave`, `FlagAutorizado`.
   - Relacionamentos:
     - `IdPiloto` faz referência à tabela `Pilotos`.
     - `IdNave` faz referência à tabela `Naves`.

5. **HistoricoViagens**
   - Registra as viagens realizadas por pilotos em naves.
   - Colunas: `IdNave`, `IdPiloto`, `DtSaida`, `DtChegada`.
   - Relacionamento: `IdPiloto` e `IdNave` fazem referência à tabela `PilotosNaves`.

## Scripts Disponíveis

- **`script_tables_star.sql`**: Cria as tabelas e define as chaves primárias e estrangeiras.
- **`insert_data_star.sql`**: Insere dados iniciais nas tabelas (opcional).
- **`constraints_star.sql`**: Adiciona restrições adicionais, se necessário.

## Como Usar

1. Clone este repositório.
2. Execute o script `script_tables_star.sql` no SQL Server Management Studio (SSMS) ou outra ferramenta compatível.
3. Opcionalmente, execute o script `insert_data_star.sql` para popular as tabelas com dados iniciais.
4. O banco de dados estará pronto para uso.

## Contribuições

Contribuições são bem-vindas! Se você encontrar algum problema ou tiver sugestões para melhorar o projeto, abra uma issue ou envie um pull request.

## Licença

Este projeto está licenciado sob a MIT License. Consulte o arquivo [LICENSE](LICENSE) para mais detalhes
