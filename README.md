# Preparação para o exame Azure DP-900

- Todo conteúdo foi retirado dos módulos e paths do site Microsoft Learn e simulados realizados para fins de estudo.
- Criei o [Path de estudo para a certificação DP-900](https://docs.microsoft.com/en-us/users/marcio-nunes-silva/collections/jwmdi8nw8r3ze4) e vou atualizando conforme necessidade.
- Esse resumo não substitui os módulos completos. Recomendo fortemente estudar através dos módulos do MS Learn.
- Resumo baseado no [Study Guide](https://query.prod.cms.rt.microsoft.com/cms/api/am/binary/RE4wsKZ) oficial da Microsoft.
- [Microsoft Azure training and certifications](https://query.prod.cms.rt.microsoft.com/cms/api/am/binary/RE4J5ea)
- Façam simulados.
- Microsoft DP-900 practice test
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

- **Atomicity** - cada transação é tratada como uma única unidade, que é totalmente bem-sucedida ou que falha completamente. Por exemplo, uma transação que envolve o débito de fundos de uma conta e o crédito do mesmo valor em outra conta deve concluir ambas as ações. Se uma das ações não puder ser concluída, a outra ação deverá falhar.
- **Consistency** - as transações só podem conduzir os dados do banco de dados de um estado válido para outro estado válido. Para continuar com o exemplo de débito e crédito acima, o estado concluído da transação deve refletir na transferência de fundos de uma conta para outra.
- **Isolation** - as transações simultâneas não podem interferir entre si e devem resultar em um estado consistente do banco de dados. Por exemplo, enquanto a transação para transferir fundos de uma conta para outra está em processo, outra transação que verifica o saldo dessas contas deve retornar resultados consistentes – a transação de verificação de saldo não pode recuperar um valor para uma conta que reflita o saldo antes da transferência e um valor para a outra conta que reflita o saldo após a transferência.
- **Durability** - quando uma transação tiver sido confirmada, ela permanecerá confirmada. Depois que a transação de transferência entre contas for concluída, os saldos de conta revisados serão persistidos para que, mesmo que o sistema do banco de dados seja desligado, a transação confirmada seja refletida quando ele for ligado novamente.

Os sistemas OLTP (Online Transactional Processing) normalmente são usados para dar suporte a aplicativos dinâmicos que processam dados de negócios, geralmente chamados de aplicativos de LOB (line of business).

### Describe features of analytical workloads

O processamento de dados analíticos normalmente usa sistemas somente leitura (ou read-mostly) que armazenam grandes volumes de dados históricos ou métricas de negócios. A análise pode ser baseada em um snapshot dos dados em um determinado momento ou em uma série de snapshots.

Uma arquitetura comum de análise de escala empresarial tem esta aparência:

![analytical-processing](https://docs.microsoft.com/pt-br/training/wwl-data-ai/explore-core-data-concepts/media/analytical-processing.png)

1. Os arquivos de dados podem ser armazenados em um data lake central para análise.
2. Um processo de ETL (extração, transformação e carregamento) copia dados de arquivos e bancos de dados OLTP para um data warehouse otimizado para atividade de leitura. Normalmente, o esquema de um data warehouse se baseia em tabelas de fatos que contêm valores numéricos que você deseja analisar (por exemplo, valores de vendas), com tabelas de dimensões relacionadas, que representam as entidades pelas quais você deseja medir (por exemplo, cliente ou produto).
3. Os dados no data warehouse podem ser agregados e carregados em um modelo OLAP (processamento analítico online) ou cubo. Valores numéricos agregados (medidas) de tabelas de fatos são calculados para interseções de dimensões da tabelas de dimensões. Por exemplo, a receita de vendas pode ser totalizada por data, cliente e produto.
4. Os dados no data lake, no data warehouse e no modelo analítico podem ser consultados para produzir relatórios, visualizações e painéis.

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

### Explorar funções e serviços de dados

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

## ☁️ Identify considerations for relational data on Azure (20-25%) 

### 🔸 Describe relational concepts

Em um banco de dados relacional, você modelará coleções de entidades do mundo real na forma de tabelas. Uma entidade pode ser qualquer coisa para a qual você deseja registrar informações; geralmente objetos e eventos importantes. Uma tabela contém linhas e cada linha representa uma instância de uma entidade. As tabelas relacionais são um formato para dados estruturados e cada linha de uma tabela tem as mesmas colunas. Cada coluna armazena dados de um tipo de dados específico (texto, datas, números inteiros e decimais). 

### Identify features of relational data

### Describe normalization and why it is used

A normalização é um termo usado por profissionais de banco de dados para um processo de design de esquema que minimiza a duplicação de dados e impõe a integridade dos dados.

- Separar cada entidade em sua própria tabela.
- Separar cada atributo discreto em sua própria coluna.
- Identificar exclusivamente cada instância de entidade (linha) usando uma chave primária.
- Usar colunas de chave estrangeira para vincular entidades relacionadas.

Cada entidade que é representada nos dados (cliente, produto, pedido de venda e item) é armazenada em sua própria tabela e cada atributo discreto dessas entidades está em sua própria coluna.

O registro de cada instância de uma entidade como uma linha em uma tabela específica da entidade remove a duplicação dos dados. 

A decomposição de atributos em colunas individuais garante que cada valor seja restrito a um tipo de dados apropriado e fornece um nível útil de granularidade nos dados para consulta.

As instâncias de cada entidade são identificadas exclusivamente por uma ID ou outro valor de chave, conhecido como chave primária; e quando uma entidade faz referência a outra (por exemplo, um pedido tem um cliente associado), a chave primária da entidade relacionada é armazenada como uma chave estrangeira.

Normalmente, um RDBMS (sistema de gerenciamento de banco de dados relacional) pode impor a integridade referencial para garantir que um valor inserido em um campo de chave estrangeira tenha uma chave primária correspondente existente na tabela relacionada, por exemplo, impedindo pedidos de clientes inexistentes.

Em alguns casos, uma chave (primária ou estrangeira) pode ser definida como uma chave composta com base em uma combinação exclusiva de várias colunas.

### Identify common structured query language (SQL) statements

SQL (Structured Query Language) é usada para se comunicar com um banco de dados relacional. Ela é a linguagem padrão para sistemas de gerenciamento de banco de dados relacional. As instruções SQL são usadas para executar tarefas como atualizar dados em um banco de dados ou recuperar dados de um banco de dados. 

> O SQL foi originalmente padronizado pelo ANSI (American National Standards Institute) em 1986 e pela ISO (Organização Internacional de Normalização) em 1987. Desde então, o padrão foi estendido várias vezes, pois os fornecedores de banco de dados relacional adicionaram novos recursos aos sistemas que não fazem parte do padrão, o que resultou em uma variedade de dialetos do SQL. 

Alguns dialetos populares do SQL incluem:

- T-SQL (Transact-SQL). Essa versão do SQL é usada pelo Microsoft SQL Server e pelos serviços de SQL do Azure.
- pgSQL. Esse é o dialeto que tem extensões implementadas no PostgreSQL.
- PL/SQL. Esse é o dialeto usado pela Oracle. PL/SQL significa Procedural Language/SQL.

### Tipos de instrução SQL

Instruções SQL são agrupadas em três grupos lógicos principais:

- **DDL (linguagem de definição de dados)** - Você usa instruções DDL para criar, modificar e remover tabelas e outros objetos em um banco de dados (tabela, procedimentos armazenados, exibições, entre outros). As instruções DDL mais comuns são: 
  - CREATE - Cria um objeto no banco de dados, como uma tabela ou uma view.
  - ALTER - Modifica a estrutura de um objeto. Por exemplo, alterar uma tabela para adicionar uma nova coluna.
  - DROP - Remova um objeto do banco de dados.
  - RENAME - Renomeia um objeto existente.

- **DCL (linguagem de controle de dados)** - Os administradores de banco de dados geralmente usam instruções DCL para gerenciar o acesso a objetos em um banco de dados, concedendo, negando ou revogando permissões a usuários ou grupos específicos. As três instruções DCL principais são:
  - GRANT - Conceder permissão para executar ações específicas
  - DENY - Negar permissão para executar ações específicas
  - REVOKE - Remover uma permissão concedida anteriormente

- **DML (linguagem de manipulação de dados)** - Você usa instruções DML para manipular as linhas em tabelas. Essas instruções permitem recuperar (consultar) dados, inserir novas linhas ou modificar linhas existentes. Você também poderá excluir linhas se não precisar mais delas.
  - SELECT - Ler linhas de uma tabela
  - INSERT - Inserir novas linhas em uma tabela
  - UPDATE - Modificar dados em linhas existentes
  - DELETE - Excluir linhas existentes

A forma básica de uma instrução INSERT insere uma linha por vez. Por padrão, as instruções SELECT, UPDATE e DELETE são aplicadas a todas as linhas em uma tabela. Normalmente, você aplica uma cláusula WHERE com essas instruções para especificar critérios. Somente as linhas que correspondem a esses critérios serão selecionadas, atualizadas ou excluídas.

Você também pode executar instruções SELECT que recuperam dados de várias tabelas usando uma cláusula JOIN. As junções indicam como as linhas em uma tabela são conectadas com as linhas em outra tabela a fim de determinar quais dados retornar. Uma condição de junção típica corresponde a uma chave estrangeira de uma tabela e a chave primária associada na outra tabela.

A instrução INSERT tem um formato um pouco diferente. Você especifica uma tabela e as colunas em uma cláusula INTO e uma lista de valores a serem armazenados nessas colunas. O SQL Standard dá suporte apenas à inserção de uma linha por vez. Alguns dialetos permitem que você especifique várias cláusulas VALUES para adicionar várias linhas por vez.

### Identify common database objects

Além das tabelas, um banco de dados relacional pode conter outras estruturas que ajudam a otimizar a organização dos dados, encapsular ações programáticas e aprimorar a velocidade de acesso.

### View 

Uma view é uma tabela virtual com base no conjunto de resultados de uma consulta SELECT. Você pode considerar uma view como uma janela em linhas especificadas de uma ou mais tabelas subjacentes. É possível consultar a view e filtrar os dados de maneira muito semelhante à de uma tabela.

### Stored procedure 

Define instruções SQL que podem ser executadas sob comando. Os procedimentos armazenados são usados para encapsular lógica programática de ações em um banco de dados que os aplicativos precisam executar ao trabalhar com os dados. Você pode definir um stored procedure com parâmetros para criar uma solução flexível para ações comuns que talvez precisem ser aplicadas aos dados com base em uma chave ou em critérios específicos. Por exemplo, o procedimento armazenado a seguir pode ser definido para alterar o nome de um produto com base na ID do produto especificada.

```SQL
CREATE PROCEDURE RenameProduct
	@ProductID INT,
	@NewName VARCHAR(20)
AS
UPDATE Product
SET Name = @NewName
WHERE ID = @ProductID;
```

Quando um produto precisa ser renomeado, você pode executar o procedimento armazenado, passando a ID do produto e o novo nome a ser atribuído:

```SQL
EXEC RenameProduct 201, 'Spanner';
```

### Index

Um índice ajuda a pesquisar dados em uma tabela. Imagine um índice em uma tabela como um índice no final de um livro. Um índice de livro contém um conjunto classificado de referências, com as páginas nas quais cada referência ocorre. Quando você deseja encontrar uma referência a um item no livro, procura por ela no índice. Você pode usar os números de página no índice para ir diretamente para as páginas corretas no livro. Sem um índice, talvez seja necessário ler todo o livro para localizar as referências que você está procurando.

Quando você cria um índice em um banco de dados, especifica uma coluna da tabela e o índice contém uma cópia desses dados em uma ordem classificada, com ponteiros para as linhas correspondentes na tabela. Quando o usuário executa uma consulta que especifica essa coluna na cláusula WHERE, o sistema de gerenciamento de banco de dados pode usar esse índice para buscar os dados mais rapidamente do que se precisasse examinar toda a tabela, linha por linha.

```SQL
CREATE INDEX idx_ProductName
ON Product(Name);
```

O índice cria uma estrutura baseada em árvore que o otimizador de consulta do sistema do banco de dados pode usar para localizar rapidamente linhas na tabela.

![index](https://docs.microsoft.com/pt-br/training/wwl-data-ai/explore-relational-data-offerings/media/index.png)

Em uma tabela que contém poucas linhas, o uso do índice provavelmente não será mais eficiente do que simplesmente ler a tabela inteira e localizar as linhas solicitadas pela consulta. No entanto, quando uma tabela tem muitas linhas, os índices podem melhorar drasticamente o desempenho das consultas.

É possível criar vários índices em uma tabela. No entanto, os índices não são gratuitos. Um índice consome espaço de armazenamento e sempre que você insere, atualiza ou exclui dados em uma tabela, é necessário haver manutenção nos índices dessa tabela. Esse trabalho adicional pode causar lentidão nas operações de inserção, atualização e exclusão. Você precisa ter um equilíbrio entre o uso índices que aceleram suas consultas e o custo de executar outras operações.

### 🔸 Describe relational Azure data services

O Azure dá suporte a vários serviços de banco de dados, permitindo que você execute sistemas de gerenciamento de banco de dados relacionais populares, como SQL Server, PostgreSQL e MySQL na nuvem.

A maioria dos serviços de banco de dados do Azure é totalmente gerenciada, liberando um tempo valioso que você gastaria gerenciando seu banco de dados.

O desempenho de nível empresarial com alta disponibilidade interna significa que você pode escalar rapidamente e alcançar distribuição global sem se preocupar com o tempo de inatividade dispendioso. Os desenvolvedores podem aproveitar as inovações líderes do setor, como segurança interna com monitoramento automático e detecção de ameaças, além de ajuste automático para aprimorar o desempenho. Além de todos esses recursos, você tem a disponibilidade garantida. 

### Describe the Azure SQL family of products including Azure SQL Database, Azure SQL

### Managed Instance, and SQL Server on Azure Virtual Machines

Azure SQL é um termo coletivo para uma família de serviços de banco de dados baseados no Microsoft SQL Server no Azure. Os serviços específicos de SQL do Azure incluem:

### SQL Server em VMs (Máquinas Virtuais) do Azure 

Uma máquina virtual em execução no Azure com uma instalação do SQL Server. O uso de uma VM torna essa opção uma solução de IaaS (infraestrutura como serviço) que virtualiza a infraestrutura de hardware para computação, armazenamento e rede no Azure, tornando-a uma ótima opção para migração **"lift-and-shift"** de instalações locais existentes do SQL Server para a nuvem.

- **Compatibilidade** - Totalmente compatível com instalações físicas locais e virtualizadas. 
- **Arquitetura** - Instâncias do SQL Server são instaladas em uma máquina virtual. Cada instância pode dar suporte a vários bancos de dados.
- **Disponibilidade**	- 99,99%
- **Gerenciamento**	- Você deve gerenciar todos os aspectos do servidor, incluindo o sistema operacional e as atualizações, a configuração, os backups e outras tarefas de manutenção do SQL Server.
- **Casos de uso** - Use essa opção quando precisar migrar ou estender uma solução de SQL Server local e manter o controle total sobre todos os aspectos da configuração do servidor e do banco de dados.

Migrar do sistema em execução no local para uma máquina virtual do Azure não é diferente de mover um banco de dados de um servidor local para outro.

Essa abordagem é adequada para migrações e aplicativos que exigem acesso a recursos do sistema operacional que podem não ser compatíveis no nível de PaaS. 

As máquinas virtuais do SQL são prontas para o lift-and-shift de aplicativos existentes que exigem migração rápida para a nuvem com alterações mínimas. 

Você também pode usar o SQL Server em VMs do Azure para estender aplicativos locais existentes para a nuvem em implantações híbridas.

É possível usar o SQL Server em uma máquina virtual para desenvolver e testar aplicativos SQL Server tradicionais. Com uma máquina virtual, você tem os direitos administrativos completos sobre o DBMS e o sistema operacional. É uma opção perfeita quando uma organização já tem recursos de TI disponíveis para manter as máquinas virtuais.

- Criar cenários rápidos de desenvolvimento e teste quando você não quiser comprar hardware do SQL Server local que não seja de produção.
- Preparar o lift-and-shift para os aplicativos existentes que exigem migração rápida para a nuvem com poucas ou nenhuma alteração.
- Escalar verticalmente a plataforma em que o SQL Server é executado alocando mais memória, capacidade de CPU e espaço em disco à máquina virtual. É possível redimensionar rapidamente uma máquina virtual do Azure sem a necessidade de reinstalar o software que está sendo executado nela.

### Azure SQL Managed Instance** 

Uma opção de PaaS (plataforma como serviço) que fornece quase 100% de compatibilidade com instâncias de SQL Server locais, abstraindo o hardware e o sistema operacional subjacentes. O serviço inclui gerenciamento automatizado de atualizações de software, backups e outras tarefas de manutenção, reduzindo a carga administrativa do suporte a uma instância de servidor de banco de dados. 

- **Compatibilidade** - Quase 100% de compatibilidade com SQL Server. A maioria dos bancos de dados locais pode ser migrada com alterações mínimas no código, usando o serviço Azure Database Migration.
- **Arquitetura** - Cada instância gerenciada pode dar suporte a vários bancos de dados. Além disso, os pools de instâncias podem ser usados para compartilhar recursos com eficiência em instâncias menores.
- **Disponibilidade**	- 99,99%
- **Gerenciamento**	- Atualizações, backups e recuperação totalmente automatizados.
- **Casos de uso** - Use essa opção para a maioria dos cenários de migração na nuvem, especialmente quando você precisar de alterações mínimas nos aplicativos existentes.

A Instância Gerenciada de SQL automatiza backups, aplicação de patch de software, monitoramento de banco de dados e outras tarefas gerais, mas você tem controle total sobre a segurança e a alocação de recursos para os seus bancos de dados. 

As instâncias gerenciadas dependem de outros serviços do Azure, como o Azure Storage para backups, o Azure Event Hubs para telemetria, o Azure Active Directory para autenticação, o Azure Key Vault para TDE (Transparent Data Encryption) e alguns serviços da plataforma Azure que fornecem recursos de segurança e compatibilidade.

Todas as comunicações são criptografadas e assinadas usando certificados. Para verificar a confiabilidade das partes que se comunicam, as instâncias gerenciadas verificam constantemente esses certificados por meio de listas de certificados revogados. Se os certificados forem revogados, a instância gerenciada fechará as conexões para proteger os dados.

Considere a Instância Gerenciada de SQL do Azure se você quiser fazer o lift-and-shift de uma instância do SQL Server local e todos os seus bancos de dados para a nuvem, sem incorrer na sobrecarga de gerenciamento da execução do SQL Server em uma máquina virtual.

A Instância Gerenciada de SQL do Azure fornece recursos que não estão disponíveis no Banco de Dados SQL do Azure. Se o sistema usar recursos como servidores vinculados, Service Broker (um sistema de processamento de mensagens que pode ser usado para distribuir o trabalho entre servidores) ou Database Mail (que permite ao seu banco de dados enviar mensagens de email para os usuários), use a instância gerenciada. Para verificar a compatibilidade com um sistema local existente, instale o AMD (Assistente de Migração de Dados). Essa ferramenta analisa seus bancos de dados no SQL Server e relata problemas que possam bloquear a migração para uma instância gerenciada.

A Instância Gerenciada de SQL do Azure permite que um administrador do sistema gaste menos tempo em tarefas administrativas. As tarefas automatizadas incluem 
- instalação e aplicação de patches do software do sistema operacional e do sistema de gerenciamento de banco de dados
- redimensionamento e configuração de instâncias dinâmicas
- backups
- replicação de banco de dados (incluindo banco de dados do sistema)
- configuração de alta disponibilidade e de fluxo de dados de monitoramento de desempenho e integridade.

A Instância Gerenciada de SQL do Azure tem quase 100% de compatibilidade com a Edição do SQL Server Enterprise em execução local.

A Instância Gerenciada de SQL do Azure dá suporte a logons do Mecanismo de banco de dados do SQL Server e logons integrados ao Azure AD (Active Directory). Os logons do Mecanismo de banco de dados do SQL Server incluem um nome de usuário e uma senha. Você deve inserir suas credenciais sempre que se conectar ao servidor. Os logons do Azure AD usam as credenciais associadas à sua entrada atual do computador e você não precisa fornecê-las sempre que se conectar ao servidor.

### **Azure SQL Database** - um serviço de banco de dados de PaaS totalmente gerenciado e altamente escalonável projetado para a nuvem. Esse serviço inclui os principais recursos de nível de banco de dados do SQL Server local e é uma boa opção se você precisa criar um aplicativo na nuvem.
  - **Compatibilidade** - Dá suporte à maioria dos principais recursos de nível de banco de dados do SQL Server. Alguns recursos que dependem de um aplicativo local podem não estar disponíveis.
  - **Arquitetura** - Você pode provisionar um banco de dados individual em um servidor dedicado e gerenciado (lógico) ou você pode usar um pool elástico para compartilhar recursos entre vários bancos de dados para aproveitar a escalabilidade sob demanda.
  - **Disponibilidade**	- 99,995%
  - **Gerenciamento**	- Atualizações, backups e recuperação totalmente automatizados.
  - **Casos de uso** - Use essa opção para novas soluções de nuvem ou para migrar aplicativos que têm dependências mínimas no nível da instância.

O Banco de Dados SQL do Azure está disponível como um Banco de Dados Individual ou um Pool Elástico.

> O Servidor do Banco de Dados SQL é um constructo lógico que atua como um ponto administrativo central para um banco de dados individual ou em pool, logons, regras de firewall, regras de auditoria, políticas de detecção de ameaças e grupos de failover.

- **Single Database** - Você cria e executa um servidor de banco de dados na nuvem e acessa o banco de dados por meio desse servidor. 
  - A Microsoft gerencia o servidor, de modo que tudo o que você precisa fazer é configurar o banco de dados, criar suas tabelas e preenchê-las com os seus dados. 
  - Você pode escalar o banco de dados se precisar de mais recursos. Por padrão, os recursos são alocados previamente e você é cobrado por hora pelos recursos que solicitou. 
  - Também é possível especificar uma configuração sem servidor. Nessa configuração é criado um servidor próprio, que pode ser compartilhado por bancos de dados pertencentes a outros assinantes do Azure. A Microsoft garante a privacidade do seu banco de dados. 
  - O banco de dados é dimensionado automaticamente e os recursos são alocados ou desalocados conforme necessário.

- **Elastic Pool** - Essa opção é semelhante ao Banco de Dados Individual. No entanto, por padrão, vários bancos de dados podem compartilhar os mesmos recursos por meio de multilocação. Os recursos são chamados de pool. Você cria o pool e somente seus bancos de dados podem usá-lo. Esse modelo será útil se você tiver bancos de dados com requisitos de recursos que variam ao longo do tempo. Além disso, ajuda a economizar. O Pool Elástico permite usar os recursos disponíveis no pool e liberá-los após a conclusão do processamento.

O Banco de Dados SQL do Azure oferece a melhor opção de baixo custo com administração mínima. Não é totalmente compatível com as instalações locais do SQL Server. Geralmente, é usada em novos projetos de nuvem em que o design do aplicativo pode acomodar as alterações necessárias em seus aplicativos.

O Banco de Dados SQL do Azure é muito usado para:

- Aplicativos de nuvem modernos que precisam usar os recursos estáveis de SQL Server mais recentes.
- Aplicativos que exigem alta disponibilidade.
- Sistemas com uma carga variável que precisam do servidor de banco de dados para escalar e reduzir verticalmente de modo rápido.

O Banco de Dados SQL do Azure é compatível com a restauração pontual, o que permite recuperar um banco de dados para o estado em que estava em qualquer ponto no passado. É possível replicar bancos de dados para regiões diferentes para fornecer mais resiliência e recuperação de desastre.

A proteção avançada contra ameaças (Advanced threat protection) fornece recursos de segurança avançados:

- Avaliações de vulnerabilidade, para ajudar a detectar e corrigir possíveis problemas de segurança com seus bancos de dados. 
- Proteção contra ameaças detecta atividades anômalas que indicam tentativas incomuns e potencialmente prejudiciais de acessar ou explorar seu banco de dados. 
- Monitora continuamente o banco de dados com relação a atividades suspeitas e fornece alertas de segurança imediatos sobre possíveis vulnerabilidades, ataques de injeção de SQL e padrões de acesso anormal do banco de dados. 
- Os alertas da proteção contra ameaças fornecem detalhes de atividades suspeitas e recomendam ações para investigar e atenuar a ameaça.

A auditoria rastreia eventos de banco de dados e os grava em um log de auditoria na Azure storage account. A auditoria pode ajudar você a manter uma conformidade regulatória, a entender a atividade do banco de dados e a obter informações sobre discrepâncias e anomalias que poderiam indicar preocupações de negócios ou suspeitas de violações de segurança.

O Banco de Dados SQL ajuda a proteger seus dados, fornecendo criptografia que protege os dados armazenados no banco de dados (em repouso) e enquanto está sendo transferido pela rede (em movimento).

- **Azure SQL Edge** - um mecanismo SQL que é otimizado para cenários de IoT (Internet das Coisas) que precisam trabalhar com transmissão de dados de séries temporais.

### Identify Azure database services for open-source database systems

Além dos serviços de SQL do Azure, há serviços de dados do Azure disponíveis para outros sistemas de bancos de dados relacionais populares, incluindo MySQL, MariaDB e PostgreSQL. O propósito desses serviços é permitir que as organizações que os usam em aplicativos locais migrem para o Azure rapidamente, sem fazer alterações significativas em seus aplicativos.

MySQL, MariaDB e PostgreSQL são sistemas de gerenciamento de banco de dados relacionais personalizados para diferentes especializações.

### Azure Database for MySQL

O Banco de Dados do Azure para MySQL é uma implementação de PaaS do MySQL na nuvem do Azure baseada na Community Edition do MySQL.

O serviço do Banco de Dados do Azure para MySQL inclui alta disponibilidade sem custo adicional e escalabilidade de acordo com a necessidade. Você paga apenas pelo que usa. É possível fazer backups automáticos com restauração pontual.

O servidor fornece segurança de conexão para impor regras de firewall e, opcionalmente, exigir conexões SSL. Muitos parâmetros de servidor permitem definir as configurações do servidor, como modos de bloqueio, número máximo de conexões e tempos limite.

Determinadas operações não estão disponíveis no Banco de Dados do Azure para MySQL. Essas funções se encarregam principalmente da segurança e da administração. O Azure gerencia esses aspectos do próprio servidor de banco de dados.

O Banco de Dados do Azure para MySQL tem duas opções de implantação: 

- **Azure Database for MySQL Flexible Server** - é uma oferta de banco de dados como serviço totalmente gerenciado com desempenho previsível e escalabilidade dinâmica. O servidor flexível oferece controle mais granular e maior flexibilidade para configuração e funções de gerenciamento de banco de dados. O servidor flexível é a opção de implantação recomendada para todos os novos desenvolvimentos ou migrações.
- **Azure Database for MySQL Single Server** - Servidores únicos são mais adequados para aplicativos existentes que já utilizam um servidor único.

Os seguintes recursos estão disponíveis no Banco de Dados do Azure para MySQL:

- Recursos internos de alta disponibilidade.
- Desempenho previsível.
- Dimensionamento fácil que responde rapidamente à demanda.
- Proteção dos dados, em repouso e em movimento.
- Backups automáticos e restauração pontual dos últimos 35 dias.
- Segurança de nível empresarial e conformidade com a legislação.

O sistema usa o pay-as-you-go para que você pague apenas pelo que usar.

Os servidores do Banco de Dados do Azure para MySQL oferecem recursos de monitoramento para adicionar alertas e ver métricas e logs.

### Azure Database for MariaDB

É uma implementação do sistema de gerenciamento de banco de dados MariaDB adaptado para execução no Azure. Baseia-se na Community Edition do MariaDB.

O banco de dados é totalmente gerenciado e controlado pelo Azure. Depois de provisionar o serviço e transferir seus dados, o sistema não requer quase nenhuma administração adicional.

O Banco de Dados do Azure para MariaDB oferece:

- Alta disponibilidade interna sem nenhum custo adicional.
- Desempenho previsível, com preços pré-pagos inclusivos.
- Dimensionamento em segundos, conforme o necessário.
- Proteção para dados confidenciais em repouso e em movimento.
- Backups automáticos e restauração pontual por até 35 dias.
- Segurança e conformidade de nível empresarial.

### Azure Database for PostgreSQL

Você poderá escolher Banco de Dados do Azure para PostgreSQL para executar uma implementação de PaaS do PostgreSQL na nuvem do Azure. Esse serviço fornece os mesmos benefícios de disponibilidade, desempenho, dimensionamento, segurança e administração que o MySQL.

Alguns recursos dos bancos de dados PostgreSQL locais não estão disponíveis no Banco de Dados do Azure para PostgreSQL, extensões que os usuários podem adicionar a um banco de dados para executar tarefas especializadas, como escrever stored procedures em várias linguagens de programação (além de pgsql, que está disponível) e interagir diretamente com o sistema operacional. Há compatibilidade com um conjunto básico de extensões usadas com mais frequência e a lista de extensões disponíveis está sob análise contínua.

O Banco de Dados do Azure para PostgreSQL tem três opções de implantação:

- **Azure Database for PostgreSQL Single Server** - Você escolhe entre três tipos de preço: Básico, Uso Geral e Otimizado para Memória. Cada tipo é compatível com diferentes números de CPUs, memória e tamanhos de armazenamento – você seleciona uma com base na carga que espera processar.
- **Azure Database for PostgreSQL Flexible Server** - A opção de implantação de servidor flexível para PostgreSQL é um serviço de banco de dados totalmente gerenciado. Ele fornece mais controle e personalizações de configuração do servidor e tem melhores controles de otimização de custo.
- **Azure Database for PostgreSQL Hyperscale (Citus)** - é uma opção de implantação que dimensiona consultas em vários nós de servidor para processar grandes cargas de banco de dados. Seu banco de dados é dividido entre nós. Os dados são divididos em partes com base no valor de uma partition key ou sharding key. Considere usar essa opção de implantação para as maiores implantações de banco de dados do PostgreSQL na nuvem do Azure.

O Banco de Dados do Azure para PostgreSQL é um serviço altamente disponível. Ele contém mecanismos internos de detecção de falha e failover.

Os usuários do PostgreSQL conhecerão a ferramenta pgAdmin, que você pode usar para gerenciar e monitorar um banco de dados PostgreSQL. No entanto, alguns recursos voltados para o servidor, como executar backup e restauração do servidor, não estão disponíveis porque o servidor é gerenciado e mantido pela Microsoft.

O Banco de Dados do Azure para PostgreSQL registra informações sobre as consultas executadas em bancos de dados no servidor e as salva em um banco de dados chamado azure_sys. Consulte a exibição query_store.qs_view para ver essas informações e usá-las para monitorar as consultas que os usuários estão executando. Essas informações podem se mostrar valiosas se você precisa ajustar as consultas executadas por seus aplicativos.

## ☁️ Describe considerations for working with non-relational data on Azure (15-20%)

### 🔸 Describe capabilities of Azure storage

### Describe Azure Blob storage

Azure Blob Storage é um serviço que permite armazenar grandes quantidades de dados não estruturados como objetos grandes binários, ou blobs, na nuvem. Os blobs são uma maneira eficiente de armazenar arquivos de dados em um formato otimizado para armazenamento baseado em nuvem, e os aplicativos podem lê-los e gravá-los usando a Azure blob storage API.

![azure-blob-storage](https://docs.microsoft.com/pt-br/training/wwl-data-ai/explore-provision-deploy-non-relational-data-services-azure/media/azure-blob-storage.png)

Em uma Azure storage account  você armazena blobs em contêineres. Um contêiner oferece uma maneira prática de agrupar blobs relacionados. Você controla quem pode ler e gravar blobs dentro de um contêiner no nível do contêiner. 

Dentro de um contêiner, você pode organizar blobs em uma hierarquia de pastas virtuais. As pastas são puramente virtuais, e você não pode executar operações no nível da pasta para controlar o acesso ou executar operações em massa.

O Armazenamento de Blobs do Azure é compatível com três tipos diferentes de blob:

- **Block blobs** - Um blob de blocos é tratado como um conjunto de blocos. Cada bloco pode variar em tamanho, até 100 MB. Um blob de blocos pode conter até 50 mil blocos, fornecendo um tamanho máximo de mais de 4,7 TB. O bloco é a menor quantidade de dados que podem ser lidos ou gravados como uma unidade individual. Os blobs de blocos são mais bem usados para armazenar objetos binários, grandes e discretos que são alterados com pouca frequência.

- **Page blobs** - Um blob de páginas é organizado como uma coleção de páginas de tamanho fixo de 512 bytes. Um blob de páginas é otimizado para dar suporte a operações de leitura e gravação aleatórias; você pode buscar e armazenar dados para uma página, se necessário. Um blob de páginas pode conter até 8 TB de dados. O Azure usa blobs de páginas para implementar o armazenamento em disco virtual para máquinas virtuais.

- **Append blobs** - Um blob de acréscimo é um blob de blocos otimizado para dar suporte a operações de acréscimo. Você só pode adicionar blocos ao final de um blob de acréscimo; não há suporte à atualização ou à exclusão de blocos existentes. Cada bloco pode variar em tamanho, até 4 MB. O tamanho máximo de um blob de acréscimo é de mais de 195 GB.

Blob storage fornece três camadas de acesso, que ajudam a balancear a latência de acesso e o custo de armazenamento:

- Hot tier - é a padrão. Você usa essa camada para blobs que são acessados com frequência. Os dados de blob são armazenados em mídia de alto desempenho.
- Cool tier - A camada de acesso esporádico tem desempenho inferior e incorre em custos de armazenamento reduzidos em comparação a camada Hot. Use a camada Fria para dados que são acessados com pouca frequência. Você pode migrar um blob da camada Fria de volta para a camada Quente.

- Archive - oferece o menor custo de armazenamento, mas com maior latência. A camada Arquivos se destina a dados históricos que não devem ser perdidos, mas é necessária apenas raramente. Os blobs na camada Arquivos são efetivamente armazenados em um estado offline. A latência de leitura para a camada Arquivos, pode levar horas para que os dados fiquem disponíveis. Para recuperar um blob da camada Arquivos, você precisa alterar a camada de acesso para Quente ou Fria. Em seguida, o blob será reidratado.

Uma política de gerenciamento do ciclo de vida pode migrar automaticamente um blob da camada Quente para a Fria e para a camada Arquivos e também pode ser organizada para excluir blobs desatualizados.

### Describe Azure DataLake Storage Gen2



### Describe Azure File storage
- Describe Azure Table storage

### 🔸 Describe capabilities and features of Azure Cosmos DB

O Azure Cosmos DB é um sistema de banco de dados não relacional (NoSQL) de escala global que dá suporte a várias APIs (interfaces de programação de aplicativo), permitindo que você armazene e gerencie dados como documentos JSON, pares chave-valor, famílias de colunas e grafos.

O Azure Cosmos DB dá suporte a várias APIs que permitem aos desenvolvedores usar a semântica de programação de muitos tipos comuns de armazenamento de dados para trabalhar com os dados no Cosmos DB. A estrutura de dados interna é abstrata, permitindo que os desenvolvedores usem o Cosmos DB para armazenar e consultar dados usando APIs com as quais já estão familiarizados.

O Cosmos DB usa índices e particionamento para fornecer desempenho rápido de leitura e gravação e pode ser dimensionado para grandes volumes de dados. 

O Cosmos DB é um sistema de gerenciamento de banco de dados altamente escalonável. O Cosmos DB aloca automaticamente espaço em um contêiner para suas partições, e cada partição pode crescer até 10 GB em tamanho. Os índices são criados e mantidos automaticamente. Praticamente, não há nenhuma sobrecarga administrativa.

### Identify use cases for Azure Cosmos DB

O Cosmos DB é altamente adequado para os seguintes cenários:

- IoT e telemática. Normalmente, esses sistemas ingerem grandes quantidades de dados em picos de atividade frequentes. O Cosmos DB pode aceitar e armazenar essas informações rapidamente. Os dados podem ser usados pelos serviços de análise, como o Azure Machine Learning, o Azure HDInsight e o Microsoft Power BI. Além disso, é possível processar os dados em tempo real usando o Azure Functions, disparado à medida que os dados chegam ao banco de dados.
- Varejo e marketing. A Microsoft usa o Cosmos DB para as próprias plataformas de comércio eletrônico que são executadas como parte da Microsoft Store e do Xbox Live. Ele também é usado no setor de varejo para armazenar dados de catálogo e para fornecimento de eventos em pipelines de processamento de pedidos.
- Jogos. A camada de banco de dados é um componente crucial dos aplicativos de jogos. Os jogos modernos executam o processamento gráfico em clientes móveis/console, mas dependem da nuvem para fornecer conteúdo personalizado, como estatísticas de jogos, integração em mídia social e tabelas com as melhores pontuações. Os jogos geralmente exigem latências de um milissegundo para leituras e gravações a fim de fornecer uma experiência envolvente no jogo. Um banco de dados de jogo deve ser rápido e ser capaz de lidar com grandes picos de taxas de solicitação durante novos lançamentos de jogos e atualizações de recursos.
- Aplicativos Web e móveis. O Azure Cosmos DB é normalmente usado em aplicativos Web e móveis e é bastante adequado para modelagem de interações sociais, integração com serviços de terceiros e desenvolvimento de experiências personalizadas avançadas. Os SDKs do Cosmos DB podem ser usados para criar aplicativos iOS e Android avançados usando a estrutura popular do Xamarin.

### Describe Azure Cosmos DB APIs

O Azure Cosmos DB dá suporte a várias APIs, permitindo que os desenvolvedores migrem facilmente os dados de repositórios NoSQL usados com frequência e apliquem as próprias habilidades de programação existentes. Ao provisionar uma nova instância do Cosmos DB, você seleciona a API que deseja usar. A escolha da API depende de vários fatores, incluindo o tipo de dados a ser armazenado, a necessidade de oferecer suporte a aplicativos existentes e as habilidades de API dos desenvolvedores que trabalharão com o armazenamento de dados.

- **Core (SQL) API** - A API nativa no Cosmos DB gerencia dados no formato de documento JSON e, apesar de ser uma solução de armazenamento de dados NoSQL, usa a sintaxe SQL para trabalhar com os dados.

- **MongoDB API** - O MongoDB é um banco de dados de software livre conhecido no qual são armazenados no formato JSON binário (BSON). A API do Azure Cosmos DB para MongoDB permite que os desenvolvedores usem bibliotecas de cliente do MongoDB e código para trabalhar com os dados no Azure Cosmos DB. A MQL (linguagem de consulta do MongoDB) usa uma sintaxe compacta orientada a objeto na qual os desenvolvedores usam objetos para chamar métodos. Por exemplo, a seguinte consulta usa o método find para consultar a coleção products no objeto db:

```
db.products.find({id: 123})

# resultado
{
   "id": 123,
   "name": "Hammer",
   "price": 2.99
}
```

- **Table API** - é usada para trabalhar com os dados em tabelas de chave-valor, semelhante ao Azure Table Storage. A Azure Cosmos DB Table API oferece maior escalabilidade e desempenho do que o Azure Table Storage. Abaixo uma consulta ao endpoint da tabela Customer.

```URL
https://endpoint/Customers(PartitionKey='1',RowKey='124')
```

- **Cassandra API** - O API do Cassandra é compatível com o Apache Cassandra, que é um banco de dados de software livre popular que usa uma estrutura de armazenamento de famílias de colunas. As famílias de colunas são tabelas, semelhantes àquelas em um banco de dados relacional, com a exceção de que não é obrigatório que cada linha tenha as mesmas colunas. O Cassandra dá suporte a uma sintaxe baseada em SQL.

- **Gremlin API** - A API do Gremlin é usada com os dados em uma estrutura de grafo, na qual as entidades são definidas como vértices que formam nós (nodes) no grafo conectado. Os nós são conectados por bordas (edges) que representam relações, desta forma:

![graph](https://docs.microsoft.com/pt-br/training/wwl-data-ai/explore-non-relational-data-stores-azure/media/graph.png)

A sintaxe do Gremlin inclui funções para operar em vértices e bordas, permitindo que você insira, atualize, exclua e consulte dados no grafo. Por exemplo, você pode usar o código a seguir para adicionar um novo funcionário chamado Alice que relata ao funcionário com a ID 1 (Suzana).

```
g.addV('employee').property('id', '3').property('firstName', 'Alice')
g.V('3').addE('reports to').to(g.V('1'))

# resultado
g.V().hasLabel('employee').order().by('id')
```

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