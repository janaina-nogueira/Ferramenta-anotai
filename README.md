# 1. Visão Geral do Projeto

O AnotAÍ! é uma plataforma digital desenvolvida para realizar anotação humana de sentenças, com foco em fenômenos linguísticos sensíveis, como descrições de identidade, papéis sociais, características atribuídas a pessoas e polaridade semântica.
O sistema foi implementado em Python utilizando Streamlit, permitindo acesso web, autenticação por usuário e salvamento seguro e incremental das anotações.

O objetivo central é construir um corpus padrão-ouro, anotado de forma controlada por múltiplos avaliadores, seguindo um esquema de categorias definido teoricamente.

# 2. Funcionalidades Principais
Autenticação individual
Cada anotador recebe um nome de usuário e senha.
A autenticação é validada por hash SHA-256, garantindo segurança.

Atribuição personalizada de sentenças
Cada usuário recebe apenas as sentenças designadas no arquivo de assignments.

Interface limpa e intuitiva

A plataforma apresenta:
- sentença atual
- categorias para marcação (multilabel)
- campo de polaridade (positiva/negativa/neutra)
- barra de progresso
- botões para navegação e salto para sentenças não anotadas

Autosave inteligente
O sistema salva automaticamente:
a cada N mudanças (default: 10)
ou após S segundos desde o último salvamento (default: 15s)

Compatibilidade retroativa
Se o arquivo do usuário não tiver coluna de polaridade, o sistema adiciona automaticamente.

Persistência segura
Cada anotador possui seu próprio arquivo.

# 3. Arquitetura do Sistema

A plataforma utiliza os seguintes arquivos externos

O backend é construído sobre:
pandas (carregamento eficiente de CSV e Parquet)
hashlib (segurança das senhas)
Streamlit (frontend interativo)
JSON para serializar múltiplos rótulos por sentença

# 4. Fluxo de Uso do Anotador

Login: o usuário insere seu nome e senha.
Carregamento: o sistema mostra apenas as sentenças atribuídas àquele anotador.
Anotação


# 5. Objetivos Metodológicos do Sistema

A ferramenta foi criada para:
Padronizar a anotação humana, reduzindo ruído e inconsistência.
Permitir comparação entre anotadores e cálculos de concordância.
Gerar um corpus padrão-ouro para análises linguísticas e experimentos supervisionados em PLN.
Criar documentação reprodutível de todo o pipeline: seleção, anotação e consolidação.
Dar suporte à detecção de vieses linguísticos e categorias sensíveis em textos brasileiros.


# 9. Contatos
Desenvolvimento e pesquisa: Prof.ª Dr.ª Valéria Quadros dos Reis
Instituição: Universidade Federal de Mato Grosso do Sul – FACOM
E-mail: valeria.reis@ufms.br
