# Modelos de Bancos de Dados #

## Base de Dados Hierárquicas ##
As estruturas hierárquicas foram muito usadas em sistemas mainframe. Sua estrutura era baseada em relações de arvores. Sendo as relações apenas se baseando em Um-para-um ou um-para-muitos. Essencialmente uma relação de pai e filho(s).

## Base de Dados em Rede ##
A organização dos bancos de dados em rede herdaram da dos bancos de dados hierárquicos ja existentes onde existiam registro filho poderia ter mais de um pai. Sendo assim um pouco mais completo do que o modelo antigo. Os modelos sempre eram criados interligados previamente possibilitando uma navegação entre o sistema.

## Bancos de Dados em Memória Principal##

Os bancos de dados de memória principal tem como foco grande velocidade de acesso a dados. Como por exemplo centrais telefônicas. os acessos a dados contidos na memória é mais rápido do que acessos em disco rígido por conta de menos etapas e menor espera para o retorno dos dados. Mas tornando inviável para quantidades maiores de dados pelo grande custo de expandir servidores no modo vertical ( processamento e memoria ) do que expansões horizontais ( discos rígidos ).

## Bancos de Dados Relacional ##
Bancos de dados relacionais foram feitos para um melhor relacionamento entre os dados de locais diferentes.
Isso trouxe mais versalidade aos softwares para uma epoca. A linguagem padrão das databases relacionais é a SQL.
A principal utilidade de databases Relacionais é evitar redundancia de dados e garantir que as relações façam sentido.

## Bancos de Dados Orientados a Objetos ##
Mesmo com o desenvolvmento avançado de alguns modelos de databases como os relacionais. Algums nichos de negocio precisam de algo tratar os dados como um tipo diferente de dados em que não era possivel trabalhar nos modelos relacionais.

Com isso surgiu os Bancos de dados Orientados a Objetos. COm necessidades de salvar tipos diferntes de modelos de arquivos como por exmeplo simulações, textos, e graficos.

## SGDB ##
A manipulação de dados em uma database pura é muito complexo tornando impossivel fazer o mesmo de forma 'manual' então surgiram os SGDBs sao softwares encarregados de trabalhar com as databases em si. O que tira a responsabilidade do desenvolvedor de trabalhar com as mesmas e as deixar menos suceptiveis a erros.

Algumas regras sao definidas para ser considerado um SGDB
Atomicidade: A execução de uma transação deve ser atômica, ou todas as ações são executadas, ou nenhuma é; 
Consistência: Cada transação executada isoladamente deve preservar a consistência do banco de dados; 
Isolamento: Cada transação deve ser isolada dos efeitos da execução concorrente de outras transações; 
Durabilidade: Toda transação que for finalizada de forma bem-sucedida deve persistir seus resultados em banco mesmo na presença de falhas no sistema.
