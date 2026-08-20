# Git — Resumo Prático

Transcrição e explicação dos comandos do documento "Git Resumo Prático" (www.devmasterteam.com).

Clique em cada comando para expandir a explicação. O bloco de código dentro de cada item facilita copiar o comando (passe o mouse sobre ele para ver o botão de copiar, no GitHub/VS Code).

## Sumário

- [Configuração](#configuração)
- [Comandos diários](#comandos-diários)
- [Inspeção de alterações](#inspeção-de-alterações)
- [Remoção e restauração](#remoção-e-restauração)
- [Histórico](#histórico)
- [Alteração de commits](#alteração-de-commits)
- [Repositórios remotos](#repositórios-remotos)
- [Branches](#branches)
- [Mesclagem de branches](#mesclagem-de-branches)
- [Tags](#tags)
- [Modificação de histórico](#modificação-de-histórico)
- [Stash](#stash)
- [Bisect (bisseção)](#bisect-bisseção)
- [Fetch](#fetch)
- [Aplicação de commit](#aplicação-de-commit)
- [Alias](#alias)

## Configuração

<details>
<summary><code>git config --global user.name "nome_do_usuario"</code></summary>

```bash
git config --global user.name "nome_do_usuario"
```

Configura o nome do usuário que será usado nos commits.
</details>

<details>
<summary><code>git config --global user.email "email_do_usuario"</code></summary>

```bash
git config --global user.email "email_do_usuario"
```

Configura o email do usuário que será usado nos commits.
</details>

<details>
<summary><code>git config --list</code></summary>

```bash
git config --list
```

Lista todas as configurações e valores do Git.
</details>

## Comandos diários

<details>
<summary><code>git init</code></summary>

```bash
git init
```

Inicializa um repositório Git no diretório atual.
</details>

<details>
<summary><code>git status</code></summary>

```bash
git status
```

Exibe o estado atual do repositório: arquivos modificados, preparados (staged) e não rastreados.
</details>

<details>
<summary><code>git add &lt;arquivo&gt;</code></summary>

```bash
git add <arquivo>
```

Adiciona um arquivo específico à área de preparação (staging), deixando-o pronto para commit.
</details>

<details>
<summary><code>git add .</code></summary>

```bash
git add .
```

Adiciona todos os arquivos modificados/novos à área de preparação.
</details>

<details>
<summary><code>git commit -m "mensagem"</code></summary>

```bash
git commit -m "mensagem"
```

Registra as mudanças da área de preparação no repositório, com uma mensagem descritiva.
</details>

## Inspeção de alterações

<details>
<summary><code>git diff</code></summary>

```bash
git diff
```

Exibe as diferenças entre o diretório de trabalho e o último commit.
</details>

<details>
<summary><code>git diff --cached</code></summary>

```bash
git diff --cached
```

Mostra as diferenças entre os arquivos na área de preparação e o último commit.
</details>

<details>
<summary><code>git diff --staged</code></summary>

```bash
git diff --staged
```

Equivalente a `--cached`: mostra diferenças entre o staging e o último commit.
</details>

## Remoção e restauração

<details>
<summary><code>git rm --cached -r .</code></summary>

```bash
git rm --cached -r .
```

Remove arquivos e diretórios da área de preparação, mas mantém eles no diretório de trabalho.
</details>

<details>
<summary><code>git restore &lt;arquivo&gt;</code></summary>

```bash
git restore <arquivo>
```

Restaura um arquivo modificado para a versão do último commit.
</details>

<details>
<summary><code>git restore --staged &lt;arquivo&gt;</code></summary>

```bash
git restore --staged <arquivo>
```

Retira um arquivo da área de preparação (staging) sem perder as alterações feitas nele.
</details>

<details>
<summary><code>git checkout &lt;arquivo&gt;</code></summary>

```bash
git checkout <arquivo>
```

Restaura um arquivo para a versão do último commit (forma mais antiga, equivalente a `restore`).
</details>

<details>
<summary><code>git clean -f</code></summary>

```bash
git clean -f
```

Remove arquivos não rastreados (que nunca foram adicionados ao Git) do diretório de trabalho.
</details>

<details>
<summary><code>git reset --hard</code></summary>

```bash
git reset --hard
```

Descarta todas as alterações locais (staged e não staged) e volta ao estado do último commit. **Atenção: operação destrutiva.**
</details>

## Histórico

<details>
<summary><code>git log</code></summary>

```bash
git log
```

Mostra o histórico completo de commits.
</details>

<details>
<summary><code>git log --oneline</code></summary>

```bash
git log --oneline
```

Exibe um resumo dos commits, um por linha.
</details>

<details>
<summary><code>git log --patch</code></summary>

```bash
git log --patch
```

Mostra os detalhes (diffs) das mudanças feitas em cada commit.
</details>

<details>
<summary><code>git log --stat</code></summary>

```bash
git log --stat
```

Exibe estatísticas das alterações realizadas em cada commit (arquivos alterados, linhas adicionadas/removidas).
</details>

## Alteração de commits

<details>
<summary><code>git commit --amend</code></summary>

```bash
git commit --amend
```

Modifica o último commit, permitindo adicionar arquivos esquecidos ou alterar a mensagem.
</details>

<details>
<summary><code>git commit --amend --no-edit</code></summary>

```bash
git commit --amend --no-edit
```

Faz um amend no último commit sem alterar a mensagem existente.
</details>

## Repositórios remotos

<details>
<summary><code>git remote -v</code></summary>

```bash
git remote -v
```

Exibe as URLs dos repositórios remotos associados ao repositório local.
</details>

<details>
<summary><code>git remote add origin &lt;url&gt;</code></summary>

```bash
git remote add origin <url>
```

Adiciona um repositório remoto chamado `origin` com a URL especificada.
</details>

<details>
<summary><code>git remote set-url origin &lt;url&gt;</code></summary>

```bash
git remote set-url origin <url>
```

Modifica a URL de um repositório remoto já existente (`origin`).
</details>

<details>
<summary><code>git push</code></summary>

```bash
git push
```

Envia as alterações commitadas localmente para o repositório remoto.
</details>

<details>
<summary><code>git pull</code></summary>

```bash
git pull
```

Baixa e mescla as alterações do repositório remoto para o repositório local.
</details>

## Branches

<details>
<summary><code>git branch --list</code></summary>

```bash
git branch --list
```

Exibe a lista de branches locais no repositório.
</details>

<details>
<summary><code>git branch &lt;nova_branch&gt;</code></summary>

```bash
git branch <nova_branch>
```

Cria uma nova branch com o nome especificado, sem trocar para ela.
</details>

<details>
<summary><code>git checkout &lt;branch&gt;</code></summary>

```bash
git checkout <branch>
```

Muda para a branch especificada.
</details>

<details>
<summary><code>git checkout -b &lt;nova_branch&gt;</code></summary>

```bash
git checkout -b <nova_branch>
```

Cria uma nova branch e já muda para ela.
</details>

<details>
<summary><code>git checkout -f &lt;branch&gt;</code></summary>

```bash
git checkout -f <branch>
```

Força a troca para a branch especificada, descartando alterações não commitadas.
</details>

<details>
<summary><code>git switch &lt;branch&gt;</code></summary>

```bash
git switch <branch>
```

Alterna para a branch especificada (alternativa mais moderna ao `git checkout`).
</details>

<details>
<summary><code>git switch -</code></summary>

```bash
git switch -
```

Volta para a última branch em que se estava.
</details>

<details>
<summary><code>git switch -c &lt;nova_branch&gt;</code></summary>

```bash
git switch -c <nova_branch>
```

Cria uma nova branch e já muda para ela (equivalente a `git checkout -b`).
</details>

<details>
<summary><code>git branch -d &lt;nome_branch&gt;</code></summary>

```bash
git branch -d <nome_branch>
```

Exclui a branch local especificada, desde que já tenha sido mesclada.
</details>

<details>
<summary><code>git push --delete origin &lt;nome_branch&gt;</code></summary>

```bash
git push --delete origin <nome_branch>
```

Remove a branch especificada do repositório remoto.
</details>

<details>
<summary><code>git branch -m &lt;novo_nome&gt;</code></summary>

```bash
git branch -m <novo_nome>
```

Renomeia a branch atual para o novo nome.
</details>

<details>
<summary><code>git branch -m &lt;nome_antigo&gt; &lt;novo_nome&gt;</code></summary>

```bash
git branch -m <nome_antigo> <novo_nome>
```

Renomeia uma branch específica de `<nome_antigo>` para `<novo_nome>`.
</details>

<details>
<summary><code>git branch -a</code></summary>

```bash
git branch -a
```

Exibe todas as branches, locais e remotas.
</details>

## Mesclagem de branches

<details>
<summary><code>git merge &lt;branch&gt;</code></summary>

```bash
git merge <branch>
```

Mescla as alterações da branch especificada na branch atual.
</details>

<details>
<summary><code>git push --force</code></summary>

```bash
git push --force
```

Força o envio das alterações para o remoto, sobrescrevendo o histórico de commits lá. **Atenção: pode apagar trabalho de outras pessoas.**
</details>

<details>
<summary><code>git push --force-with-lease</code></summary>

```bash
git push --force-with-lease
```

Força o envio, mas verifica antes se o remoto não foi alterado por terceiros, evitando sobrescrever trabalho alheio sem perceber. Mais seguro que `--force`.
</details>

## Tags

<details>
<summary><code>git tag &lt;nome&gt;</code></summary>

```bash
git tag <nome>
```

Cria uma tag *lightweight* (sem metadados), associada ao commit atual (último commit).
</details>

<details>
<summary><code>git tag -a -m "mensagem" &lt;nome&gt;</code></summary>

```bash
git tag -a -m "mensagem" <nome>
```

Cria uma tag *annotated* (com metadados: autor, data, mensagem).
</details>

<details>
<summary><code>git show &lt;tag&gt;</code></summary>

```bash
git show <tag>
```

Exibe informações sobre uma tag específica, incluindo o commit ao qual está associada.
</details>

<details>
<summary><code>git tag --list</code></summary>

```bash
git tag --list
```

Exibe todas as tags do repositório.
</details>

<details>
<summary><code>git tag -n</code></summary>

```bash
git tag -n
```

Exibe todas as tags junto com suas mensagens (se houver).
</details>

<details>
<summary><code>git tag -d &lt;nome&gt;</code></summary>

```bash
git tag -d <nome>
```

Remove uma tag localmente.
</details>

<details>
<summary><code>git push --delete origin &lt;nome_tag&gt;</code></summary>

```bash
git push --delete origin <nome_tag>
```

Remove uma tag do repositório remoto.
</details>

## Modificação de histórico

<details>
<summary><code>git revert &lt;commit&gt;</code></summary>

```bash
git revert <commit>
```

Cria um **novo** commit que desfaz as alterações de um commit anterior (sem reescrever histórico).
</details>

<details>
<summary><code>git revert HEAD --no-edit</code></summary>

```bash
git revert HEAD --no-edit
```

Reverte o último commit sem abrir o editor para alterar a mensagem gerada.
</details>

<details>
<summary><code>git rebase &lt;branch&gt;</code></summary>

```bash
git rebase <branch>
```

Reaplica os commits da branch atual sobre a branch especificada, reescrevendo o histórico.
</details>

<details>
<summary><code>git rebase --abort</code></summary>

```bash
git rebase --abort
```

Aborta um rebase em andamento, retornando ao estado anterior ao início do rebase.
</details>

<details>
<summary><code>git rebase --continue</code></summary>

```bash
git rebase --continue
```

Continua o rebase após resolver os conflitos apontados.
</details>

## Stash

<details>
<summary><code>git stash</code></summary>

```bash
git stash
```

Guarda temporariamente as alterações não commitadas, deixando o diretório de trabalho limpo.
</details>

<details>
<summary><code>git stash list</code></summary>

```bash
git stash list
```

Exibe a lista de stashes armazenados.
</details>

<details>
<summary><code>git stash apply</code></summary>

```bash
git stash apply
```

Aplica o stash mais recente ao diretório de trabalho, sem removê-lo da lista.
</details>

<details>
<summary><code>git stash apply stash@&lt;posicao&gt;</code></summary>

```bash
git stash apply stash@<posicao>
```

Aplica um stash específico da lista, indicado pela posição.
</details>

<details>
<summary><code>git stash pop &lt;posicao&gt;</code></summary>

```bash
git stash pop <posicao>
```

Aplica **e remove** o stash especificado da lista.
</details>

<details>
<summary><code>git stash drop &lt;posicao&gt;</code></summary>

```bash
git stash drop <posicao>
```

Remove um stash específico da lista, sem aplicá-lo.
</details>

## Bisect (bisseção)

Usado para localizar, por busca binária, o commit que introduziu um bug.

<details>
<summary><code>git bisect start</code></summary>

```bash
git bisect start
```

Inicia uma sessão de bisseção.
</details>

<details>
<summary><code>git bisect good &lt;hash&gt;</code></summary>

```bash
git bisect good <hash>
```

Marca o commit especificado como "bom" (sem o bug).
</details>

<details>
<summary><code>git bisect bad &lt;hash&gt;</code></summary>

```bash
git bisect bad <hash>
```

Marca o commit especificado como "ruim" (com o bug).
</details>

<details>
<summary><code>git bisect good</code></summary>

```bash
git bisect good
```

Marca o commit atual (que está em checkout) como "bom".
</details>

<details>
<summary><code>git bisect bad</code></summary>

```bash
git bisect bad
```

Marca o commit atual como "ruim".
</details>

## Fetch

<details>
<summary><code>git fetch</code></summary>

```bash
git fetch
```

Baixa as atualizações dos repositórios remotos, mas **não** as mescla com a branch atual (diferente de `pull`).
</details>

## Aplicação de commit

<details>
<summary><code>git cherry-pick &lt;commit&gt;</code></summary>

```bash
git cherry-pick <commit>
```

Aplica as mudanças de um commit específico de outra branch na branch atual.
</details>

## Alias

<details>
<summary><code>git config --global alias.&lt;abreviacao&gt; &lt;comando&gt;</code></summary>

```bash
git config --global alias.<abreviacao> <comando>
```

Cria um alias global, permitindo usar `<abreviacao>` no lugar de `<comando>`.
</details>

<details>
<summary><code>git config --global --unset alias.&lt;abreviacao&gt;</code></summary>

```bash
git config --global --unset alias.<abreviacao>
```

Remove o alias global especificado.
</details>

---
Fonte: *Git Resumo Prático* — www.devmasterteam.com
