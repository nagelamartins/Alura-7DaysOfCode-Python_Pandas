# 7 Days of Code - Alura | Python com Pandas - Anotações 📝


Este documento reúne meus principais aprendizados técnicos e desafios enfrentados durante o desafio **7 Days of Code – Python com Pandas, da Alura**.  

---
## 📌 Aprendizados Gerais:
1. **Nomeação de variáveis importa**: Ao longo do desafio, percebi que usar nomes genéricos dificulta o raciocínio conforme a análise cresce.
   Nomear DataFrames de forma descritiva melhora clareza, reduz erros e facilita revisões futuras.
   
2. **Entender o problema vem antes do código**: O desafio vinha em formato de e-mail, com texto corrido e sem etapas explícitas.
   Por isso, era necessário:
   * Identificar o objetivo principal;
   * Extrair tarefas implícitas;
   * Dividir em partes menores.
---
## 📌 Dia 1: 
* Diferença entre `.concat()` e `.merge()`:
  * `.concat()`: É usado quando os dados têm a mesma estrutura.  
    Une DataFrames empilhando:
      * Linhas (uma abaixo da outra)
      * Ou colunas (uma ao lado da outra)
  * `.merge()`: Mescla DataFrames com base em uma chave comum (como um JOIN em SQL). É usado quando queremos combinar informações complementares.
  
* Arquivo `.parquet`: O formato Parquet é um tipo de arquivo colunar otimizado para desempenho e armazenamento eficiente, muito utilizado em contextos de Big Data.
  Foi meu primeiro contato prático com esse formato.

---
## 📌 Dia 2:
Pratiquei:
* Estruturas `if-elif-else`;
* Laço `for`;
* Criação de listas para gerar novas colunas.

**Aprendizado importante:**
Criar uma nova coluna a partir de regras condicionais permite transformar dados brutos em categorias interpretáveis.

---
## 📌 Dia 3:
* Utilizei funções da biblioteca `datetime` para extrair partes específicas das datas (como mês e ano): fundamental para trabalhar com séries temporais;

* Visualização com Seaborn e Matplotlib:
  * Customizar temas;
  * Ajustar títulos e rótulos;
  * Interpretar padrões visuais.

 ---
 ## 📌 Dia 4:
 * Definição de funções (`def`): Criar funções permite:
   * Reutilizar código;
   * Organizar lógica;
   * Tornar o notebook mais limpo;
   * Melhorar legibilidade e manutenção.
   
* Distribuições categóricas: Entender a distribuição de variáveis categóricas ajuda a:
    * Identificar predominâncias;
    * Detectar desbalanceamentos;
    * Entender comportamento do conjunto de dados.
 
---
## 📌 Dia 5:
* Erro inicial:  Agrupei valores por mês, ignorando o ano. Isso somava todos os “janeiros” de diferentes anos.
  * Consequência: O boxplot não representava corretamente a variação temporal.
  * Correção: Usar o método `to_period('M')` para transformar datas em períodos mensais, respeitando o ano.
  
* Boxplot: Foi meu primeiro contato mais aprofundado com interpretação visual de dispersão.
  * O boxplot representa:
    * Mediana (linha central)
    * Intervalo interquartil (50% central dos dados)
    * Valores mínimos e máximos dentro de um limite aceitável
    * Outliers (valores fora do padrão)
  * Aprendizado:
    * Caixa curta → baixa variabilidade
    * Caixa longa → alta variabilidade
    * Bigodes longos → grande amplitude
    * Pontos isolados → possíveis eventos atípicos

---
## 📌 Dia 6:
* JSON aninhado: O arquivo JSON continha estruturas internas (dicionários dentro de dicionários).
  Foi necessário acessar os índices internos corretamente para extrair as informações desejadas.
  * Aprendizado: Entender a estrutura hierárquica é essencial ao trabalhar com dados semi-estruturados.
  
* Tipagem de um campo: Ao converter a tipagem da 'matricula_ou_siape' do arquivo JSON diretamente para `string`, seus caracteres ficaram diferentes do arquivo em
   Excel, que já era `float` nativamente. Por conta disso, ao usar o `.merge()`, eles não foram mesclados corretamente e informações foram perdidas.
  * Aprendizado: Antes de mesclar dados, é necessário garantir que as chaves estejam no mesmo tipo `(dtype)`.
  
* Uso incorreto do `dropna()`: Removi todos os valores nulos, quando o correto era remover apenas os nulos da coluna 'matrícula_ou_siape'.
  * Correção: Utilizar o parâmetro `subset`.
 
---
## 📌 Dia 7: 
* Diferenças percentuais: O desafio propunha comparar 2019 e 2022. Por isso, decidi:
  * Não incluir 2020 por ausência de dados completos;
  * Calcular diretamente a variação entre 2019 e 2022.
  * Isso causou divergências com os valores comparativos entre 2019 e 2022 do instrutor, uma vez que ele parece ter usado os dados de 2020.
  
* Pandas Styler: permite formatar DataFrames para visualização:
  * Aplicar cores;
  * Formatar registros;
  * Destacar valores
  * Melhorar a comunicação de resultados.
  
* Exportação para `.html`: Exportei o DataFrame formatado para `.html`. Foi meu primeiro contato com essa etapa de apresentação de resultados fora do ambiente do
  notebook.

---
## 📌 Conclusão:
Este desafio consolidou:
* Integração de múltiplas fontes de dados;
* Tratamento de inconsistências;
* Agrupamentos temporais;
* Interpretação de boxplot;
* Importância da tipagem correta;
* Apresentação visual de resultados.  

Mais do que aprender funções específicas, foi um exercício de:
* Estruturar problemas;
* Identificar erros;
* Corrigir decisões;
* Pensar criticamente sobre os resultados.
