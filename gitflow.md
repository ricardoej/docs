# Gitflow - Documentação

## Introdução

O Gitflow é um modelo de branching para o Git que facilita o gerenciamento de projetos com um ciclo de vida de desenvolvimento mais complexo. Ele define um conjunto de regras e convenções para nomear branches e organizar o fluxo de trabalho.

## Principais Branches

### 1. Main

A branch `main` é a branch principal do projeto. É nela que estão as versões de produção estáveis.

### 2. Develop

A branch `develop` é a branch de desenvolvimento principal. Todas as novas features e bugfixes são mesclados nesta branch.

## Branches de Feature

### Criando uma Branch de Feature

Para criar uma nova feature, siga os passos abaixo:

```bash
git checkout develop  # Garante que você está na branch develop
git pull origin develop  # Atualiza a branch develop local
git checkout -b feature/nome-da-feature  # Cria e muda para a nova branch de feature
```

Exemplo:

```bash
git checkout develop
git pull origin develop
git checkout -b feature/nova-feature
```

## Branches de Bugfix

### Criando uma Branch de Bugfix

Para corrigir um bug, siga os passos abaixo:

```bash
git checkout develop  # Garante que você está na branch develop
git pull origin develop  # Atualiza a branch develop local
git checkout -b bugfix/nome-do-bug  # Cria e muda para a nova branch de bugfix
```

Exemplo:

```bash
git checkout develop
git pull origin develop
git checkout -b bugfix/correcao-bug
```

## Branches de Release

### Criando uma Branch de Release

Para preparar uma nova release, siga os passos abaixo:

```bash
git checkout develop  # Garante que você está na branch develop
git pull origin develop  # Atualiza a branch develop local
git checkout -b release/versao-da-release  # Cria e muda para a nova branch de release
```

Exemplo:

```bash
git checkout develop
git pull origin develop
git checkout -b release/1.0.0
```

## Exemplos Completos

### Exemplo de Ciclo de Feature

1. Criando uma branch de feature:

```bash
git checkout develop
git pull origin develop
git checkout -b feature/nova-feature
```

2. Trabalhando na feature e commitando as mudanças:

```bash
git add .
git commit -m "Implementação da nova feature"
```

3. Finalizando a feature e mesclando de volta para a develop:

```bash
git checkout develop
git pull origin develop
git merge feature/nova-feature
```

4. Removendo a branch de feature local:

```bash
git branch -d feature/nova-feature
```

5. Enviando a branch de feature para o repositório remoto:

```bash
git push origin develop
```

### Exemplo de Ciclo de Bugfix

1. Criando uma branch de bugfix:

```bash
git checkout develop
git pull origin develop
git checkout -b bugfix/correcao-bug
```

2. Trabalhando na correção do bug e commitando as mudanças:

```bash
git add .
git commit -m "Correção do bug"
```

3. Finalizando o bugfix e mesclando de volta para a develop:

```bash
git checkout develop
git pull origin develop
git merge bugfix/correcao-bug
```

4. Removendo a branch de bugfix local:

```bash
git branch -d bugfix/correcao-bug
```

5. Enviando a branch de bugfix para o repositório remoto:

```bash
git push origin develop
```

### Exemplo de Ciclo de Release

1. Criando uma branch de release:

```bash
git checkout develop
git pull origin develop
git checkout -b release/1.0.0
```

2. Realizando testes finais na branch de release.

3. Finalizando a release e mesclando de volta para a develop e main:

```bash
git checkout develop
git pull origin develop
git merge release/1.0.0

git checkout main
git pull origin main
git merge release/1.0.0
```

4. Criando uma tag para a versão da release:

```bash
git tag -a 1.0.0 -m "Versão 1.0.0"
```

5. Removendo a branch de release local:

```bash
git branch -d release/1.0.0
```

6. Enviando as alterações para o repositório remoto:

```bash
git push origin develop
git push origin main
git push origin --tags
```
