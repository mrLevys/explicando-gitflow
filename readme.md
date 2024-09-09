# Gitflow para Pequenos Times de Desenvolvimento

O Gitflow é um modelo de ramificação para Git que oferece uma estrutura robusta para gerenciar o desenvolvimento de software. Ele organiza o fluxo de trabalho e facilita o controle de versões.

## 1. Principais Ramificações do Gitflow

### a) `main`
- **Propósito**: Contém o código de produção.
- **Uso**: Apenas versões estáveis e prontas para produção são mescladas aqui.
- **Como usar**: Mesclar apenas a partir da branch `release` ou `hotfix`, após aprovação e testes.

### b) `develop`
- **Propósito**: Armazena o código de desenvolvimento para a próxima versão.
- **Uso**: Reflete o trabalho em andamento. Todas as novas funcionalidades são mescladas aqui.
- **Como usar**: Funcionalidades são desenvolvidas em ramificações derivadas de `develop` e, ao final, mescladas de volta.

## 2. Ramificações de Suporte

### a) `feature/*`
- **Propósito**: Contém o desenvolvimento de uma nova funcionalidade ou melhoria.
- **Uso**: Criada a partir de `develop`. Ao terminar a funcionalidade, é mesclada de volta em `develop`.
- **Como usar**: O desenvolvedor trabalha em sua própria `feature` e, ao finalizar, abre um pull request para revisão e mescla em `develop`.

### b) `release/*`
- **Propósito**: Prepara o código para uma nova versão de produção.
- **Uso**: Criada a partir de `develop` quando as funcionalidades estão prontas. Passa por ajustes finais.
- **Como usar**: Após finalizada, a branch é mesclada em `main` e `develop`.

### c) `hotfix/*`
- **Propósito**: Para corrigir problemas críticos em produção.
- **Uso**: Criada a partir de `main` para corrigir bugs urgentes na produção. Após a correção, é mesclada em `main` e `develop`.
- **Como usar**: Após a resolução e testes, a branch `hotfix` é mesclada em `main` e `develop`.

## 3. Fluxo de Trabalho Prático

1. **Criar uma nova funcionalidade**:
   - Criar uma branch `feature` a partir de `develop`.
   - Trabalhar na funcionalidade até estar completa.
   - Abrir um pull request para mesclar a `feature` em `develop`.
   
2. **Preparar uma versão para produção**:
   - Quando as funcionalidades estiverem completas, criar uma branch `release` a partir de `develop`.
   - Fazer ajustes finais e correções de bugs.
   - Mesclar a branch `release` em `main` e `develop`.

3. **Lidar com problemas críticos em produção**:
   - Criar uma branch `hotfix` a partir de `main`.
   - Corrigir o bug.
   - Mesclar a branch `hotfix` em `main` e `develop`.

## Vantagens:
- **Colaboração organizada**: Cada desenvolvedor trabalha em sua própria `feature`.
- **Controle sobre o ciclo de lançamentos**: As branches de `release` garantem uma preparação cuidadosa antes de cada lançamento.
- **Correções rápidas**: `Hotfix` permite corrigir rapidamente problemas críticos em produção.

## Exemplo Prático
Em um pequeno time de 3 desenvolvedores:
- Cada um trabalha em suas próprias branches `feature`.
- Antes de cada release, cria-se uma branch `release` para correções finais.
- Problemas críticos em produção são tratados em `hotfix` para correção rápida.

Esse fluxo promove colaboração eficiente e um processo de lançamento confiável.
