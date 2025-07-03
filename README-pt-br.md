<!-- |||||||||||||||||||| EN - PT |||||||||||||||||||| -->
<p align='center'>
  <a href="https://github.com/dev-ggomes/Branches-Complete-Guide4-Repositories/blob/main/README.md">🇺🇸 English</a> | 
  <a href="https://github.com/dev-ggomes/Branches-Complete-Guide4-Repositories/blob/main/README-pt-pt.md">ᴘᴛ Português</a> | 
  <a href="https://github.com/dev-ggomes/Branches-Complete-Guide4-Repositories/blob/main/README-pt-br.md">🇧🇷 Português</a>
</p>

<!-- |||||||||||||||||||| TITLE |||||||||||||||||||| -->

<div align="center">
  
  # Guia sobre Branches
  
  :octocat: Guia completo e intuitivo para dominar branches no Git e GitHub

</div> 

<!-- |||||||||||||||||||| STARS |||||||||||||||||||| -->
<p align="center">
  ⭐  Se gostou deste repositório, me ajuda contribuindo com uma estrelinha
</p>

<!-- |||||||||||||||||||| SPONSORS & STARS |||||||||||||||||||| -->
<p align='center'>
  <a href="https://github.com/sponsors/dev-ggomes"><img alt="Sponsor" src="https://img.shields.io/badge/sponsor-30363D?style=for-the-badge&logo=GitHub-Sponsors&logoColor=#white" /></a>
  &nbsp;
  <a href="#"><img alt="GitHub Repo stars" src="https://img.shields.io/github/stars/dev-ggomes/Branches-Complete-Guide4-Repositories?style=for-the-badge" /></a>
</p>

<!-- |||||||||||||||||||| CONTENT |||||||||||||||||||| -->

## 📖 Índice

1. [Sobre](#-sobre)
2. [⚙️ Glossário](#️-glossário)
3. [🚀 Quickstart](#-quickstart)
4. [🌳 Conceitos de Branch](#-conceitos-de-branch)
5. [🗂️ Tipos de Branches](#️-tipos-de-branches)
6. [⚙️ Fluxo de Trabalho (Workflow)](#️-fluxo-de-trabalho-workflow)

   * [GitHub Flow](#github-flow)
   * [Git Flow](#git-flow)
7. [🔧 Operações Essenciais](#-operações-essenciais)

   * [Criar Branch](#criar-branch)
   * [Atualizar Branch](#atualizar-branch)
   * [Publicar Branch](#publicar-branch)
   * [PR & Merge](#pr--merge)
8. [⏰ Quando Usar Cada Branch](#-quando-usar-cada-branch)
9. [👍 Boas Práticas](#-boas-práticas)
10. [🚀 Próximos Passos](#-próximos-passos)

---

## 📌 Sobre

Este repositório é um guia visual e passo a passo para iniciantes e profissionais entenderem e aplicarem estratégias de branching no Git e GitHub. Inclui definições claras, fluxos de trabalho e exemplos práticos.

---

## ⚙️ Glossário

| Termo            | Descrição breve                                                       |
| ---------------- | --------------------------------------------------------------------- |
| **branch** ou **branches**       | Ramo de desenvolvimento independente.                                 |
| **commit** ou **commits**       | Snapshot de alterações no repositório.                                |
| **pull request** ou **PR** | Proposta de integração de um branch em outro, com revisão.            |
| **merge** ou **merges**        | Ação de combinar alterações de diferentes branches.                   |
| **main**         | Branch principal e estável (produção).                                |
| **develop**      | Branch de integração de novas funcionalidades.                        |
| **feature/**     | Prefixo para desenvolvimento de novas funcionalidades.                |
| **bugfix/**      | Prefixo para correções de bugs durante o desenvolvimento.             |
| **hotfix/**      | Prefixo para correções críticas em produção.                          |
| **release/**     | Prefixo para preparar uma nova versão de software.                    |
| **experiment/**  | Prefixo para protótipos e testes sem garantia de merge.               |
| **squash**       | Combina múltiplos commits em um único commit.                         |
| **rebase**       | Reaplica commits de uma branch sobre outra, gerando histórico linear. |

---

## 🚀 Quickstart

1. **Criar Branch**

   ```bash
   git switch -c feature/nome-da-feature
   ```
2. **Fazer Commits**

   ```bash
   git add . && git commit -m "Descrição clara da mudança"
   ```
3. **Publicar no GitHub**

   ```bash
   git push -u origin feature/nome-da-feature
   ```
4. **Abrir Pull Request**

   * No GitHub, selecione seu branch e clique em **New Pull Request**.
5. **Revisão e Merge**

   * Após aprovação, mescle e delete seu branch:

     ```bash
     git switch main && git pull
     git branch -d feature/nome-da-feature
     git push origin --delete feature/nome-da-feature
     ```

---

## 🌳 Conceitos de Branch

Cada branch funciona como um espaço isolado para suas alterações. Imagine o histórico do projeto como um tronco de árvore (`main`), e cada branch é um ramo onde você pode trabalhar sem afetar o tronco.

---

## 🗂️ Tipos de Branches

| Prefixo         | Exemplo               | Propósito                           |
| --------------- | --------------------- | ----------------------------------- |
| **main**        | `main`                | Código em produção                  |
| **develop**     | `develop`             | Integração de novas funcionalidades |
| **feature/**    | `feature/login`       | Desenvolvimento de uma nova feature |
| **bugfix/**     | `bugfix/erro-404`     | Correção de bugs                    |
| **hotfix/**     | `hotfix/patch-1.0.1`  | Correções críticas em produção      |
| **release/**    | `release/2.0.0`       | Preparação de versão                |
| **experiment/** | `experiment/a-b-test` | Protótipos e testes                 |

---

## ⚙️ Fluxo de Trabalho (Workflow)

### GitHub Flow

1. Trabalhe sempre a partir de `main`.
2. Crie um branch de feature.
3. Faça commits frequentes.
4. Publique e abra um PR.
5. Após aprovação, mescle em `main` e realize o deploy.

```bash
gitGraph
git checkout main
commit id:"v1.0.0 deploy"
branch feature/a
checkout feature/a
commit id:"Implementa A"
checkout main
merge feature/a
```

### Git Flow

1. **main**: produção
2. **develop**: integração contínua
3. **feature**\*: branches criadas de `develop`
4. **release**\*: branches de preparação de versão
5. **hotfix**\*: branches de correções urgentes

```bash
gitGraph
git checkout -b develop main
commit id:"Início Sprint"
branch feature/b
checkout feature/b
commit id:"Nova funcionalidade B"
checkout develop
merge feature/b
branch release/1.0.0
checkout release/1.0.0
commit id:"Ajustes & Docs"
checkout main
merge release/1.0.0
 tag v1.0.0
checkout develop
merge release/1.0.0
```

---

## 🔧 Operações Essenciais

### Criar Branch

```bash
git switch -c prefixo/nome
```

### Atualizar Branch

```bash
git fetch origin
# Rebase para sincronizar com a base
git rebase origin/main
```

### Publicar Branch

```bash
git push -u origin prefixo/nome
```

### PR & Merge

> [!NOTE]\
> **Notas de Merge**
> * **Merge Commit**: preserva histórico completo. Use para features longas.
> * **Squash and Merge**: consolida commits em um só. Use para simplificar.
> * **Rebase and Merge**: cria histórico linear. Use para commits atômicos.

---

## ⏰ Quando Usar Cada Branch

* **feature/**: novas funcionalidades.
* **bugfix/**: correções antes do release.
* **hotfix/**: correções críticas em produção.
* **release/**: preparação de versão.
* **experiment/**: protótipos e testes.

---

## 👍 Boas Práticas

* Use **nomes claros** e consistentes.
* Faça **commits pequenos** e descritivos.
* Abra **PRs detalhados** com contexto.
* Proteja branches: exija revisão antes do merge.
* Delete branches mescladas para manter o repositório limpo.

---

## 🚀 Próximos Passos

1. Clone o repositório:

   ```bash
   git clone https://github.com/seu-nome-de-usuario/Branches-Complete-Guide4-Repositories.git
   ```


2. Siga o **Quickstart**.
3. Experimente os **fluxos de trabalho**.
4. Contribua com sugestões via **PR** ou **Issue**.


---

<p align="center">
  
  Feito com ❤️ & Markdown por [dev-ggomes](https://github.com/dev-ggomes) com a contribuição de [LeoSilva91](https://github.com/LeoSilva91)
  
</p>
