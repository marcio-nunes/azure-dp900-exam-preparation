# Preparação para o exame Azure DP-900

- Todo conteúdo foi retirado dos módulos e paths do site Microsoft Learn e simulados realizados para fins de estudo.
- Criei o [Path de estudo para a certificação DP-900](https://docs.microsoft.com/en-us/users/marcio-nunes-silva/collections/jwmdi8nw8r3ze4) e vou atualizando conforme necessidade.
- Esse resumo não substitui os módulos completos. Recomendo fortemente estudar através dos módulos do MS Learn.
- Resumo baseado no [Study Guide](https://query.prod.cms.rt.microsoft.com/cms/api/am/binary/RE4wsKZ) oficial da Microsoft.
- [Microsoft Azure training and certifications](https://query.prod.cms.rt.microsoft.com/cms/api/am/binary/RE4J5ea)
- Façam simulados.
- Microsoft DP-900 practice test
- Na Udemy você também encontra alguns. Udemy Practice Test
- Agendamento do exame de certificação.
- Fiquem a vontade para ajudar a melhorar o conteúdo.

Icons: ☁️🔸

## Skills measured

- Describe core data concepts (25–30%)
- Identify considerations for relational data on Azure (20–25%)
- Describe considerations for working with non-relational data on Azure (15–20%)
- Describe an analytics workload on Azure (25–30%)

## ☁️ Describe core data concepts (25-30%)

### 🔸 Describe ways to represent data

Os dados são uma coleção de fatos, como números, descrições e observações usados para registrar informações. As estruturas de dados geralmente representam entidades que são importantes para uma organização (clientes, produtos, pedidos de vendas, etc). Normalmente, cada entidade tem um ou mais atributos ou características (um cliente pode ter um nome, um endereço, um número de telefone, etc).

Podemos classificar os dados como estruturados, semiestruturados ou não estruturados.

### Describe features of structured data

Dados estruturados obedecem a um esquema fixo, portanto, todos os dados têm os mesmos campos ou propriedades e  o esquema para entidades de dados estruturados é tabular. Em outras palavras, os dados são representados em uma ou mais tabelas que consistem em:

- linhas para representar cada instância de uma entidade de dados.
- colunas para representar os atributos da entidade.

Os dados estruturados geralmente são armazenados em um banco de dados no qual várias tabelas podem referenciar umas às outras usando valores de chave em um modelo relacional.

### Describe features of semi-structured

Dados semiestruturados são informações que têm alguma estrutura, mas que permitem alguma variação entre instâncias da entidade. Por exemplo, embora a maioria dos clientes possa ter um endereço de email, alguns podem ter vários endereços de email e outros podem não ter nenhum.

Um formato comum para dados semiestruturados é o JSON (JavaScript Object Notation).

> O JSON é apenas uma das muitas maneiras pelas quais os dados semiestruturados podem ser representados.

### Describe features of unstructured data

Nem todos os dados são estruturados ou até mesmo semiestruturados. Por exemplo, documentos, imagens, dados de áudio e vídeo e arquivos binários podem não ter uma estrutura específica. 

### 🔸 Identify options for data storage

As organizações normalmente armazenam dados em formato estruturado, semiestruturado ou não estruturado para registrar detalhes de entidades (por exemplo, clientes e produtos), eventos específicos (como transações de vendas) ou outras informações em documentos, imagens e outros formatos. Os dados armazenados podem ser recuperados para análise e relatórios posteriormente.

Há duas categorias amplas de armazenamento de dados comuns em uso:

- Armazenamentos de arquivos
- Bancos de dados

Na maioria das organizações, arquivos de dados importantes são armazenados de maneira centralizada em algum tipo de sistema de armazenamento de arquivos compartilhado. Cada vez mais, esse local de armazenamento central está sendo hospedado na nuvem.

### Describe common formats for data files

O formato de arquivo específico usado para armazenar dados depende de vários fatores, incluindo:

- O tipo de dados que está sendo armazenado (estruturado, semiestruturado ou não estruturado).
- Os aplicativos e serviços que precisarão ler, gravar e processar os dados.
- A necessidade de que os arquivos de dados sejam legíveis por seres humanos ou otimizados para armazenamento e processamento eficientes.

- Delimited text files - Geralmente, os dados são armazenados em formato de texto sem formatação com delimitadores de campo e terminadores de linha específicos. O formato mais comum para dados delimitados é CSV nos quais os campos são separados por vírgulas e as linhas terminam com um retorno de carriage return/new line. Opcionalmente, a primeira linha pode incluir os nomes de campo. Outros formatos comuns incluem 
    - TSV (tab-separated values) e space-delimited (em que as tabulações ou os espaços são usados para separar campos) 
    - Fixed-width data - Dados de largura fixa em que a cada campo é alocado um número fixo de caracteres. O texto delimitado é uma boa opção para dados estruturados que precisam ser acessados por uma ampla variedade de aplicativos e serviços em um formato legível.

### JavaScript Object Notation (JSON)

O JSON é um formato onipresente no qual um esquema de documento hierárquico é usado para definir entidades de dados (objetos) que têm vários atributos. Cada atributo pode ser um objeto (ou uma coleção de objetos), tornando o JSON um formato flexível que é bom para dados estruturados e semiestruturados.

Observe que os objetos estão entre chaves ({..}) e as coleções estão entre colchetes ([..]). Os atributos são representados por pares nome:valor e separados por vírgulas (,).

```JSON
{
  "customers":
  [
    {
      "firstName": "Joe",
      "lastName": "Jones",
      "contact":
      [
        {
          "type": "home",
          "number": "555 123-1234"
        },
        {
          "type": "email",
          "address": "joe@litware.com"
        }
      ]
    }
  ]
}
```

### Extensible Markup Language (XML)

O XML é um formato de dados legível que foi popular nos anos 90 e 2000. Ele tem sido substituído pelo formato JSON que é menos detalhado, mas ainda há alguns sistemas que usam XML para representar dados. O XML usa marcas delimitadas por colchetes angulares (../) para definir elementos e atributos

```XML
<Customers>
  <Customer name="Joe" lastName="Jones">
    <ContactDetails>
      <Contact type="home" number="555 123-1234"/>
      <Contact type="email" address="joe@litware.com"/>
    </ContactDetails>
  </Customer>
  <Customer name="Samir" lastName="Nadoy">
    <ContactDetails>
      <Contact type="email" address="samir@northwind.com"/>
    </ContactDetails>
  </Customer>
</Customers>
```

### Binary Large Object (BLOB)

Todos os arquivos são armazenados como dados binários, mas nos formatos legíveis descritos acima, os bytes de dados binários são mapeados em caracteres imprimíveis (ASCII). No entanto, alguns formatos de arquivo, particularmente para dados não estruturados, armazenam os dados como binários brutos que devem ser interpretados por aplicativos e renderizados.

Tipos comuns de dados armazenados como binários:

- Imagens
- Vídeo
- Documentos específicos de apps

### Formatos de arquivo otimizados

Embora os formatos legíveis para dados estruturados e semiestruturados possam ser úteis, normalmente eles não são otimizados para espaço de armazenamento ou processamento. 

Ao longo do tempo, alguns formatos de arquivo especializados que permitem a compactação, a indexação e o armazenamento e o processamento eficientes foram desenvolvidos.

- O Avro é um formato baseado em linha. Ele foi criado pelo Apache. Cada registro contém um cabeçalho que descreve a estrutura dos dados no registro. Esse cabeçalho é armazenado como JSON. Os dados são armazenados como informações binárias. Um aplicativo usa as informações no cabeçalho para analisar os dados binários e extrair os campos contidos neles. O Avro é um formato bom para compactar dados e minimizar os requisitos de armazenamento e largura de banda de rede.
- ORC (Optimized Row Columnar format) organiza os dados em colunas em vez de linhas. Ele foi desenvolvido pela HortonWorks para otimizar as operações de leitura e gravação no Apache Hive (o Hive é um sistema de data warehouse que dá suporte a resumos rápidos de dados e consultas em grandes conjuntos de dados). Um arquivo ORC contém faixas de dados. Cada faixa contém os dados de uma coluna ou conjunto de colunas. Uma faixa contém um índice nas linhas na faixa, os dados de cada linha e um rodapé que contém informações estatísticas (contagem, soma, máximo, mínimo e assim por diante) para cada coluna.
- O Parquet é outro formato de dados de coluna. Ele foi criado pela Cloudera e pelo Twitter. Um arquivo Parquet contém grupos de linhas. Os dados de cada coluna são armazenados juntos no mesmo grupo de linhas. Cada grupo de linhas contém uma ou mais partes de dados. Um arquivo Parquet inclui metadados que descrevem o conjunto de linhas encontrado em cada parte. Um aplicativo pode usar esses metadados para localizar rapidamente a parte correta de um determinado conjunto de linhas e recuperar os dados nas colunas especificadas para essas linhas. O Parquet é especialista em armazenar e processar tipos de dados aninhados com eficiência. Ele dá suporte a esquemas de codificação e compactação muito eficientes.

### 🔸 Describe types of databases

Um banco de dados é usado para definir um sistema central no qual dados podem ser armazenados e consultados.

### Bancos de dados relacionais

Os bancos de dados relacionais são comumente usados para armazenar e consultar dados estruturados. Os dados são armazenados em tabelas que representam entidades (clientes, produtos ou pedidos de venda). Cada instância de uma entidade recebe uma chave primária que a identifica de maneira exclusiva. Essas chaves são usadas para fazer referência à instância da entidade em outras tabelas. Esse uso de chaves para referenciar entidades de dados permite que um banco de dados relacional seja normalizado, o que, em parte, significa a eliminação de valores de dados duplicados. 

As tabelas são gerenciadas e consultadas usando SQL (linguagem SQL), que se baseia em um padrão ANSII e que, portanto, é semelhante entre vários sistemas de banco de dados.

### Bancos de dados não relacionais

Os bancos de dados não relacionais (NoSQL) são sistemas de gerenciamento de dados que não aplicam um esquema relacional aos dados.

- **Key-value databases** nos quais cada registro consiste em uma chave exclusiva e um valor associado, que pode estar em qualquer formato.

![key-value-store](https://docs.microsoft.com/pt-br/training/wwl-data-ai/explore-core-data-concepts/media/key-value-store.png)

- **Document databases**, que são uma forma específica de banco de dados de chave-valor na qual o valor é um documento JSON (em que o sistema é otimizado para análise e consulta).

![document-store](https://docs.microsoft.com/en-us/training/wwl-data-ai/explore-core-data-concepts/media/document-store.png)

- **Column family databases**, que podem armazenar dados tabulares que abrangem linhas e colunas; você também pode dividir as colunas em grupos conhecidos como famílias de colunas. Cada família de colunas contém um conjunto de colunas que estão logicamente relacionadas.

![column-family-store](https://docs.microsoft.com/pt-br/training/wwl-data-ai/explore-core-data-concepts/media/column-family-store.png)

- **Graph databases**, que armazenam entidades como nós com links para definir relações entre eles.

![graph](https://docs.microsoft.com/pt-br/training/wwl-data-ai/explore-core-data-concepts/media/graph.png)


### Describe common data workloads

Um sistema transacional registra transações que encapsulam eventos específicos que a organização deseja controlar. Uma transação pode ser financeira, como a movimentação de dinheiro entre contas em um sistema bancário, ou pode fazer parte de um sistema de varejo, controlando pagamentos de bens e serviços de clientes. Pense na transação como uma unidade de trabalho pequena e discreta.

### Describe features of transactional workloads

Os sistemas transacionais geralmente são de alto volume, às vezes manipulando muitos milhões de transações em um dia. Os dados que estão sendo processados têm que estar acessíveis com rapidez. O trabalho executado por sistemas transacionais é geralmente conhecido como OLTP (Online Transactional Processing).

As soluções OLTP (Online Transactional Processing) dependem de um sistema de banco de dados no qual o armazenamento de dados é otimizado para operações de leitura e gravação para dar suporte aos workloads transacionais nas quais os registros de dados são criados, recuperados, atualizados e excluídos (CRUD). Essas operações são aplicadas de maneira transacional para garantir a integridade dos dados armazenados no banco de dados. Para fazer isso, os sistemas OLTP impõem transações compatíveis com a semântica conhecida como ACID:

- Atomicity - cada transação é tratada como uma única unidade, que é totalmente bem-sucedida ou que falha completamente. Por exemplo, uma transação que envolve o débito de fundos de uma conta e o crédito do mesmo valor em outra conta deve concluir ambas as ações. Se uma das ações não puder ser concluída, a outra ação deverá falhar.
- Consistency - as transações só podem conduzir os dados do banco de dados de um estado válido para outro estado válido. Para continuar com o exemplo de débito e crédito acima, o estado concluído da transação deve refletir na transferência de fundos de uma conta para outra.
- Isolation - as transações simultâneas não podem interferir entre si e devem resultar em um estado consistente do banco de dados. Por exemplo, enquanto a transação para transferir fundos de uma conta para outra está em processo, outra transação que verifica o saldo dessas contas deve retornar resultados consistentes – a transação de verificação de saldo não pode recuperar um valor para uma conta que reflita o saldo antes da transferência e um valor para a outra conta que reflita o saldo após a transferência.
- Durability - quando uma transação tiver sido confirmada, ela permanecerá confirmada. Depois que a transação de transferência entre contas for concluída, os saldos de conta revisados serão persistidos para que, mesmo que o sistema do banco de dados seja desligado, a transação confirmada seja refletida quando ele for ligado novamente.

Os sistemas OLTP (Online Transactional Processing) normalmente são usados para dar suporte a aplicativos dinâmicos que processam dados de negócios, geralmente chamados de aplicativos de LOB (line of business).

### Describe features of analytical workloads

O processamento de dados analíticos normalmente usa sistemas somente leitura (ou read-mostly) que armazenam grandes volumes de dados históricos ou métricas de negócios. A análise pode ser baseada em um snapshot dos dados em um determinado momento ou em uma série de snapshots.

Uma arquitetura comum de análise de escala empresarial tem esta aparência:

![analytical-processing](https://docs.microsoft.com/pt-br/training/wwl-data-ai/explore-core-data-concepts/media/analytical-processing.png)

1. Os arquivos de dados podem ser armazenados em um data lake central para análise.
Um processo de ETL (extração, transformação e carregamento) copia dados de arquivos e bancos de dados OLTP para um data warehouse otimizado para atividade de leitura. Normalmente, o esquema de um data warehouse se baseia em tabelas de fatos que contêm valores numéricos que você deseja analisar (por exemplo, valores de vendas), com tabelas de dimensões relacionadas, que representam as entidades pelas quais você deseja medir (por exemplo, cliente ou produto).
- Os dados no data warehouse podem ser agregados e carregados em um modelo OLAP (processamento analítico online) ou cubo. Valores numéricos agregados (medidas) de tabelas de fatos são calculados para interseções de dimensões da tabelas de dimensões. Por exemplo, a receita de vendas pode ser totalizada por data, cliente e produto.
- Os dados no data lake, no data warehouse e no modelo analítico podem ser consultados para produzir relatórios, visualizações e painéis.

**Data lakes** são comuns em cenários de processamento analítico de dados em grande escala, em que um grande volume de dados baseados em arquivo precisa ser coletado e analisado.

**Data warehouses** são uma forma estabelecida de armazenar dados em um esquema relacional otimizado para operações de leitura – principalmente consultas para dar suporte a relatórios e à visualização de dados. O esquema do data warehouse pode exigir alguma desnormalização de dados em uma fonte de dados OLTP (apresentando algumas duplicações para fazer com que as consultas sejam executadas mais rapidamente).

Um **modelo OLAP** é um tipo agregado de armazenamento de dados que é otimizado para cargas de trabalho analíticas. As agregações de dados são feitas entre dimensões em diferentes níveis, permitindo que você faça drill up/down para exibir agregações em vários níveis hierárquicos; por exemplo, para localizar o total de vendas por região, por cidade ou por um endereço individual. Como os dados do OLAP são previamente agregados, as consultas para retornar os resumos que ele contém podem ser executadas rapidamente.

Tipos diferentes de usuários podem executar trabalhos de análise de dados em diferentes estágios da arquitetura geral. Por exemplo:

- Os cientistas de dados podem trabalhar diretamente com arquivos de dados em um data lake para explorar e modelar os dados.
- Os Analistas de Dados podem consultar tabelas diretamente no data warehouse para produzir relatórios e visualizações complexos.
- Os usuários empresariais podem consumir dados previamente agregados em um modelo analítico na forma de relatórios ou painéis.

### Identify roles and responsibilities for data workloads

- Describe responsibilities for database administrators
- Describe responsibilities for data engineers
- Describe responsibilities for data analysts

## ☁️ Identify considerations for relational data on Azure (20-25%) 

### 🔸 Describe relational concepts

- Identify features of relational data
- Describe normalization and why it is used
- Identify common structured query language (SQL) statements
- Identify common database objects

### 🔸 Describe relational Azure data services

- Describe the Azure SQL family of products including Azure SQL Database, Azure SQL
- Managed Instance, and SQL Server on Azure Virtual Machines
- Identify Azure database services for open-source database systems

## ☁️ Describe considerations for working with non-relational data on Azure (15-20%)

### 🔸 Describe capabilities of Azure storage

- Describe Azure Blob storage
- Describe Azure File storage
- Describe Azure Table storage

### 🔸 Describe capabilities and features of Azure Cosmos DB

- Identify use cases for Azure Cosmos DB
- Describe Azure Cosmos DB APIs

## ☁️ Describe an analytics workload on Azure (25-30%)

### 🔸 Describe common elements of large-scale analytics

- Describe considerations for data ingestion and processing
- Describe options for analytical data stores
- Describe Azure services for data warehousing, including Azure Synapse Analytics, Azure Databricks, Azure HDInsight, and Azure Data Factory

### 🔸 Describe consideration for real-time data analytics

- Describe the difference between batch and streaming data
- Describe technologies for real-time analytics including Azure Stream Analytics, Azure Synapse Data Explorer, and Spark structured streaming

### 🔸 Describe data visualization in Microsoft Power BI

- Identify capabilities of Power BI
- Describe features of data models in Power BI
- Identify appropriate visualizations for data