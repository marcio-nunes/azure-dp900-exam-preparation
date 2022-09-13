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

Os profissionais de dados executam funções distintas na criação e no gerenciamento de soluções de software e trabalham com várias tecnologias e serviços para realizar isso.

Há uma ampla variedade de funções que envolvem gerenciamento, controle e uso de dados. Algumas funções são orientadas aos negócios, outras envolvem mais engenharia e as demais focam na pesquisa, já outras são funções híbridas que combinam diferentes aspectos de gerenciamento de dados. 

As três funções de trabalho importantes que lidam com os dados na maioria das organizações são:

- **Administradores de Banco de Dados**, que gerenciam bancos de dados, atribuindo permissões aos usuários, armazenando cópias de backup de dados e restaurando dados em caso de falhas.
- **Engenheiros de dados**, que gerenciam a infraestrutura e os processos de integração de dados em toda a organização, aplicando rotinas de limpeza de dados, identificando regras de governança de dados e implementando pipelines para transferir e transformar dados entre sistemas.
- Analistas de Dados, que exploram e analisam dados para criar visualizações e gráficos que permitem que as organizações tomem decisões informadas.

> Em algumas organizações, a mesma pessoa pode executar várias funções

### Describe responsibilities for database administrators

Um Administrador de Banco de Dados do Azure é responsável pelos aspectos de design, implementação, manutenção e operação de sistemas de bancos de dados locais e baseados em nuvem. Eles são responsáveis pela disponibilidade geral e pelo desempenho e otimizações consistentes dos bancos de dados. Eles trabalham com os stakeholders para implementar políticas e ferramentas, além de processos de backup e planos de recuperação para serem usados após um desastre natural ou erro humano.

O Administrador de Banco de Dados também é responsável por gerenciar a segurança dos dados nos bancos de dados, conceder privilégios sobre os dados, além de conceder ou negar acesso aos usuários conforme apropriado.

### Describe responsibilities for data engineers

Um Engenheiro de Dados colabora com os stakeholders para projetar e implementar cargas de trabalho relacionadas a dados, incluindo pipelines de ingestão de dados, atividades de limpeza e transformação e armazenamentos de dados para cargas de trabalho analíticas. Eles usam uma ampla variedade de tecnologias de plataforma de dados, incluindo bancos de dados relacionais e não relacionais, repositórios de arquivos e fluxos de dados.

Eles também são responsáveis por garantir que a privacidade dos dados seja mantida dentro da nuvem, abrangendo armazenamentos de dados locais e na nuvem. Eles são responsáveis por gerenciar e monitorar pipelines de dados para garantir que as cargas de dados tenham o desempenho esperado.

### Describe responsibilities for data analysts

Um analista de dados permite que as empresas maximizem o valor dos ativos de dados. Eles são responsáveis por explorar dados para identificar tendências e relações, projetar e criar modelos analíticos e favorecer capacidades avançadas de análise por meio de relatórios e visualizações.

Um Analista de Dados processa dados brutos e, com base em requisitos empresariais identificados, os transforma para fornecer insights relevantes.

> Há outras funções relacionadas a dados não mencionadas aqui, como cientista de dados e arquiteto de dados, e há outros profissionais técnicos que trabalham com os dados, incluindo desenvolvedores de aplicativos e engenheiros de software.

## ☁️ Identify considerations for relational data on Azure (20-25%) 

### 🔸 Describe relational concepts

- Identify features of relational data
- Describe normalization and why it is used
- Identify common structured query language (SQL) statements
- Identify common database objects

### 🔸 Describe relational Azure data services

### Describe the Azure SQL family of products including Azure SQL Database, Azure SQL

### Azure SQL 

Azure SQL é o nome coletivo de uma família de soluções de banco de dados relacional com base no mecanismo de banco de dados do Microsoft SQL Server. 

- **Azure SQL Database** - um banco de dados de PaaS (plataforma como serviço) totalmente gerenciado hospedado no Azure.
- **Azure SQL Managed Instance** - uma instância hospedada do SQL Server com manutenção automatizada, que permite uma configuração mais flexível do que o Azure SQL DB, mas com mais responsabilidade administrativa para o proprietário.
- **Azure SQL VM** - uma máquina virtual com uma instalação do SQL Server, permitindo a máxima capacidade de configuração com total responsabilidade de gerenciamento.

Os administradores de banco de dados normalmente provisionam e gerenciam os sistemas de banco de dados Azure SQL para dar suporte a aplicativos de LOB (linha de negócios) que precisam armazenar dados transacionais.

Os engenheiros de dados podem usar os sistemas de banco de dados SQL do Azure como fontes para pipelines de dados que executam operações de ETL (extração, transformação e carregamento) para ingerir os dados transacionais em um sistema analítico.

Os analistas de dados podem consultar os bancos de dados SQL do Azure diretamente para criar relatórios, no entanto, em grandes organizações, os dados geralmente são combinados com os dados de outras fontes em um armazenamento de dados analíticos para dar suporte às análises empresariais.

### Azure Database for open-source relational databases

O Azure inclui serviços gerenciados para sistemas de banco de dados relacionais populares de código aberto, incluindo:

- **Azure Database for MySQL** - um sistema de gerenciamento de banco de dados de código aberto fácil de usar que é comumente usado em aplicativos da pilha LAMP (Linux, Apache, MySQL e PHP).
- **Azure Database for MariaDB** - um sistema de gerenciamento de banco de dados mais recente, criado pelos desenvolvedores originais do MySQL. Desde então, o mecanismo de banco de dados foi reescrito e otimizado para aprimorar o desempenho. O MariaDB tem compatibilidade com o Oracle Database.
- **Azure Database for PostgreSQL** - um banco de dados híbrido relacional-objeto. É possível armazenar dados em tabelas relacionais, também permite que você armazene tipos de dados personalizados, com propriedades não relacionais próprias.

Assim como acontece com os sistemas de banco de dados SQL do Azure, os bancos de dados relacionais de código aberto são gerenciados por administradores de banco de dados para dar suporte a aplicativos transacionais e fornecem uma fonte de dados para engenheiros de dados, criando pipelines para soluções analíticas e analistas de dados que criam relatórios.

### Azure Cosmos DB

O Azure Cosmos DB é um sistema de banco de dados não relacional (NoSQL) de escala global que dá suporte a várias APIs (interfaces de programação de aplicativo), permitindo que você armazene e gerencie dados como documentos JSON, pares chave-valor, famílias de colunas e grafos.

Em algumas organizações, instâncias do Cosmos DB podem ser provisionadas e gerenciadas por um administrador de banco de dados, embora os desenvolvedores de software tenham o costume de gerenciar o armazenamento de dados NoSQL como parte da arquitetura geral do aplicativo. Os engenheiros de dados geralmente precisam integrar fontes de dados do Cosmos DB a soluções analíticas corporativas que dão suporte à modelagem e geração de relatórios por analistas de dados.

### Azure Storage

 O Armazenamento do Azure é um serviço principal do Azure que permite armazenar dados em:

- **Blob containers** - armazenamento escalonável e econômico para arquivos binários.
- **File shares** - compartilhamentos de arquivos de rede, semelhante ao que normalmente é encontrado nas redes corporativas.
- **Tables** - armazenamento de chave-valor para aplicativos que precisam ler e gravar valores de dados rapidamente.

Os engenheiros de dados usam o Armazenamento do Azure para hospedar data lakes – armazenamentos de blobs com um namespace hierárquico que permite que os arquivos sejam organizados em pastas em um sistema de arquivos distribuído.

### Azure Data Factory

O Azure Data Factory é um serviço do Azure que permite definir e agendar pipelines de dados para transferir e transformar dados. Você pode integrar seus pipelines a outros serviços do Azure, possibilitando a ingestão de dados de armazenamentos de dados na nuvem, o processamento dos dados usando a computação baseada em nuvem e a manutenção dos resultados em outro armazenamento de dados.

O Azure Data Factory é usado por engenheiros de dados para criar soluções de ETL (extração, transformação e carregamento) que preenchem os armazenamentos de dados analíticos com os dados de sistemas transacionais na organização.

### Azure Synapse Analytics

O Azure Synapse Analytics é uma solução de análise de dados abrangente e unificada que oferece uma interface de serviço única para vários recursos analíticos, incluindo:

- **Pipelines** - baseado na mesma tecnologia do Azure Data Factory.
- **SQL** - um mecanismo de banco de dados SQL altamente escalonável, otimizado para cargas de trabalho de data warehouse.
- **Apache Spark** - um sistema de processamento de dados distribuído de código aberto que dá suporte a várias linguagens de programação e APIs, incluindo Java, Scala, Python e SQL.
- **Azure Synapse Data Explorer** - uma solução de análise de dados de alto desempenho que é otimizada para consultas em tempo real de dados de log e telemetria usando a KQL (Kusto Query Language).

Os engenheiros de dados podem usar o Azure Synapse Analytics para criar uma solução de análise de dados unificada que combina pipelines de ingestão de dados, armazenamento de data warehouse e armazenamento do data lake em um único serviço.

Os analistas de dados podem usar pools de SQL e do Spark por meio de notebooks interativos para explorar e analisar dados e aproveitar a integração com serviços como Azure Machine Learning e Microsoft Power BI para criar modelos de dados e extrair insights dos dados.

### Azure Databricks

O Azure Databricks é uma versão integrada do Azure da plataforma popular do Databricks, que combina a plataforma de processamento de dados Apache Spark com a semântica de banco de dados SQL e uma interface de gerenciamento integrada para permitir a análise de dados em larga escala.

Os engenheiros de dados podem usar as habilidades que já têm do Databricks e do Spark para criar armazenamentos de dados analíticos no Azure Databricks.

Os analistas de dados podem usar o suporte nativo ao notebook no Azure Databricks para consultar e visualizar dados em uma interface baseada na Web fácil de usar.

### Azure HDInsight

O Azure HDInsight é um serviço do Azure que fornece clusters hospedados no Azure para tecnologias populares de código aberto de processamento de Big Data do Apache, incluindo:

- **Apache Spark** - um sistema de processamento de dados distribuído que dá suporte a várias linguagens de programação e APIs, incluindo Java, Scala, Python e SQL.
- **Apache Hadoop** - um sistema distribuído que usa trabalhos MapReduce para processar grandes volumes de dados com eficiência em vários nós de cluster. Os trabalhos MapReduce podem ser escritos em Java ou abstraídos por interfaces como Apache Hive, uma API baseada em SQL que é executada no Hadoop.
- **Apache HBase** - um sistema de código aberto para armazenamento e consulta de dados NoSQL em larga escala.
- **Apache Kafka** - um agente de mensagens para processamento de fluxo de dados.
- **Apache Storm** - um sistema de código aberto para processamento de dados em tempo real por meio de uma topologia de spouts e bolts.

Os engenheiros de dados podem usar o Azure HDInsight para dar suporte a cargas de trabalho de análise de Big Data que dependem de várias tecnologias de código aberto.

### Azure Stream Analytics

O Azure Stream Analytics é um mecanismo de processamento de fluxo em tempo real que captura um fluxo de dados de uma entrada, aplica uma consulta para extrair e manipular os dados do fluxo de entrada e grava os resultados em uma saída para análise ou processamento adicional.

Os engenheiros de dados podem incorporar o Azure Stream Analytics em arquiteturas de análise de dados que capturam fluxos dados para ingestão em um armazenamento de dados analíticos ou para visualização em tempo real.

### Azure Data Explorer

O Azure Data Explorer é um serviço autônomo que oferece a mesma consulta de alto desempenho de dados de log e telemetria que o runtime do Azure Synapse Data Explorer no Azure Synapse Analytics.

Os analistas de dados podem usar o Azure Data Explorer para consultar e analisar dados que incluem um atributo de carimbo de data/hora, como normalmente é encontrado em arquivos de log e dados de telemetria da IoT (Internet das Coisas).

### Microsoft Purview

O Microsoft Purview fornece uma solução para governança e descoberta de dados de toda a empresa. Use o Microsoft Purview para criar um mapa de seus dados e acompanhar a linhagem de dados em várias fontes de dados e sistemas, permitindo encontrar dados confiáveis para análise e relatórios.

Os engenheiros de dados podem usar o Microsoft Purview para impor a governança de dados em toda a empresa e garantir a integridade dos dados usados para dar suporte a cargas de trabalho analíticas.

### Microsoft Power BI

O Microsoft Power BI é uma plataforma para modelagem de dados analíticos e relatórios que os analistas de dados podem usar para criar e compartilhar visualizações de dados interativas. Os relatórios do Power BI podem ser criados por meio do aplicativo Power BI Desktop e, em seguida, publicados e fornecidos por meio de relatórios e aplicativos baseados na Web no serviço do Power BI, bem como no aplicativo móvel do Power BI.

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