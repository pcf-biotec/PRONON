# PRONON - Automatization strategies for HTS methods
---

# Projeto de Análise de Heatmaps

## Descrição

Este projeto realiza a análise e visualização de dados de múltiplos arquivos Excel. O objetivo é processar dados, calcular médias e desvios padrão, e gerar heatmaps personalizados. Os arquivos resultantes são exportados para diretórios específicos para facilitar a análise e a visualização.

## Funcionalidades

- **Leitura e Processamento de Arquivos Excel:** Processa múltiplos arquivos e folhas, calcula estatísticas básicas (médias e desvios padrão).
- **Geração de Heatmaps:** Cria heatmaps utilizando paletas de cores personalizadas e métodos de escalonamento.
- **Exportação de Resultados:** Exporta os resultados processados e os heatmaps para diretórios específicos.

## Estrutura do Projeto

- `patients/`: Pasta contendo os arquivos Excel a serem processados.
- `results/`: Pasta onde os resultados serão exportados.
  - `results_heatmaps/`: Subpasta dentro de `results/` onde os heatmaps serão salvos.
- `COMPOUNDS.txt`: Arquivo de texto contendo compostos utilizados na análise de heatmaps.

## Dependências

Este projeto requer os seguintes pacotes R:

- `dplyr`
- `openxlsx`
- `readxl`
- `pheatmap`
- `RColorBrewer`
- `viridis`

Instale as dependências usando:

```r
install.packages(c("dplyr", "openxlsx", "readxl", "pheatmap", "RColorBrewer", "viridis"))
```

## Scripts

### `heatmap_analysis.R`

O script principal que realiza as seguintes operações:

1. **Importação das Bibliotecas Necessárias**
2. **Definição das Funções:**
   - **`split_and_process(df, cols1, cols2)`**: Divide o dataframe em dois com base nas colunas fornecidas e calcula as médias e desvios padrão.
   - **`read_all_sheets(file_path, cols1, cols2)`**: Lê todas as folhas de um arquivo Excel e processa os dados.
   - **`read_all_files(folder_path, cols1, cols2)`**: Lê todos os arquivos Excel na pasta `patients`.
   - **`export_results(results, export_path, base_filename)`**: Exporta os resultados calculados para arquivos Excel.
   - **`export_combined_results(all_sheets, export_path)`**: Cria um arquivo Excel combinado para cada arquivo na pasta `patients`.
   - **`create_heatmap_data_for_file(file_name, all_sheets, compounds)`**: Cria um dataframe combinado para geração de heatmaps.
   - **`plot_and_export_heatmap(heatmap_data, file_name, plot_type)`**: Gera e exporta heatmaps com base nos dados fornecidos.

3. **Execução do Script:**
   - Processa arquivos Excel na pasta `patients`.
   - Calcula médias e desvios padrão.
   - Exporta os resultados para arquivos Excel.
   - Gera e exporta heatmaps.

## Como Usar

1. **Preparar o Ambiente:**
   - Instale o R e as bibliotecas necessárias.
   - Coloque os arquivos Excel que deseja processar na pasta `patients/`.
   - Crie o arquivo `COMPOUNDS.txt` com a lista de compostos.

2. **Executar o Script:**
   - Abra o R ou RStudio.
   - Execute o script `heatmap_analysis.R` no seu ambiente.

3. **Resultados:**
   - Os arquivos de resultados serão salvos na pasta `results/`:
     - `*_mean.xlsx`: Contém as médias calculadas.
     - `*_sd.xlsx`: Contém os desvios padrão calculados.
   - Os heatmaps serão salvos na subpasta `results/results_heatmaps/`.

## Exemplo

Aqui está um exemplo de execução do script:

```r
source("heatmap_analysis.R")
```

Certifique-se de ajustar o caminho dos arquivos e pastas conforme necessário.

## Contribuição

Sinta-se à vontade para contribuir com melhorias ou correções. Por favor, siga as diretrizes padrão para contribuições em projetos de código aberto.

1. Faça um fork deste repositório.
2. Crie uma branch para suas alterações (`git checkout -b minha-nova-feature`).
3. Faça suas alterações e teste-as.
4. Envie suas alterações (`git push origin minha-nova-feature`).
5. Abra um pull request no GitHub.

## Licença

Este projeto está licenciado sob a Licença MIT - veja o arquivo [LICENSE](LICENSE) para mais detalhes.

---

Espero que essa documentação ajude a entender e usar o projeto de forma mais eficiente! Se precisar de mais alguma coisa, é só avisar.
