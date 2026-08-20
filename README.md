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
<pre><code>git config --global user.name "nome_do_usuario"</code></pre>

Configura o nome do usuário que será usado nos commits.
</details>

<details>
<summary><code>git config --global user.email "email_do_usuario"</code></summary>
<pre><code>git config --global user.email "email_do_usuario"</code></pre>

Configura o email do usuário que será usado nos commits.
</details>

<details>
<summary><code>git config --list</code></summary>
<pre><code>git config --list</code></pre>

Lista todas as configurações e valores do Git.
</details>

## Comandos diários

<details>
<summary><code>git init</code></summary>
<pre><code>git init</code></pre>

Inicializa um repositório Git no diretório atual.
</details>

<details>
<summary><code>git status</code></summary>
<pre><code>git status</code></pre>

Exibe o estado atual do repositório: arquivos modificados, preparados (staged) e não rastreados.
</details>

<details>
<summary><code>git add &lt;arquivo&gt;</code></summary>
<pre><code>git add &lt;arquivo&gt;</code></pre>

Adiciona um arquivo específico à área de preparação (staging), deixando-o pronto para commit.
</details>

<details>
<summary><code>git add .</code></summary>
<pre><code>git add .</code></pre>

Adiciona todos os arquivos modificados/novos à área de preparação.
</details>

<details>
<summary><code>git commit -m "mensagem"</code></summary>
<pre><code>git commit -m "mensagem"</code></pre>

Registra as mudanças da área de preparação no repositório, com uma mensagem descritiva.
</details>

## Inspeção de alterações

<details>
<summary><code>git diff</code></summary>
<pre><code>git diff</code></pre>

Exibe as diferenças entre o diretório de trabalho e o último commit.
</details>

<details>
<summary><code>git diff --cached</code></summary>
<pre><code>git diff --cached</code></pre>

Mostra as diferenças entre os arquivos na área de preparação e o último commit.
</details>

<details>
<summary><code>git diff --staged</code></summary>
<pre><code>git diff --staged</code></pre>

Equivalente a `--cached`: mostra diferenças entre o staging e o último commit.
</details>

## Remoção e restauração

<details>
<summary><code>git rm --cached -r .</code></summary>
<pre><code>git rm --cached -r .</code></pre>

Remove arquivos e diretórios da área de preparação, mas mantém eles no diretório de trabalho.
</details>

<details>
<summary><code>git restore &lt;arquivo&gt;</code></summary>
<pre><code>git restore &lt;arquivo&gt;</code></pre>

Restaura um arquivo modificado para a versão do último commit.
</details>

<details>
<summary><code>git restore --staged &lt;arquivo&gt;</code></summary>
<pre><code>git restore --staged &lt;arquivo&gt;</code></pre>

Retira um arquivo da área de preparação (staging) sem perder as alterações feitas nele.
</details>

<details>
<summary><code>git checkout &lt;arquivo&gt;</code></summary>
<pre><code>git checkout &lt;arquivo&gt;</code></pre>

Restaura um arquivo para a versão do último commit (forma mais antiga, equivalente a `restore`).
</details>

<details>
<summary><code>git clean -f</code></summary>
<pre><code>git clean -f</code></pre>

Remove arquivos não rastreados (que nunca foram adicionados ao Git) do diretório de trabalho.
</details>

<details>
<summary><code>git reset --hard</code></summary>
<pre><code>git reset --hard</code></pre>

Descarta todas as alterações locais (staged e não staged) e volta ao estado do último commit. **Atenção: operação destrutiva.**
</details>

## Histórico

<details>
<summary><code>git log</code></summary>
<pre><code>git log</code></pre>

Mostra o histórico completo de commits.
</details>

<details>
<summary><code>git log --oneline</code></summary>
<pre><code>git log --oneline</code></pre>

Exibe um resumo dos commits, um por linha.
</details>

<details>
<summary><code>git log --patch</code></summary>
<pre><code>git log --patch</code></pre>

Mostra os detalhes (diffs) das mudanças feitas em cada commit.
</details>

<details>
<summary><code>git log --stat</code></summary>
<pre><code>git log --stat</code></pre>

Exibe estatísticas das alterações realizadas em cada commit (arquivos alterados, linhas adicionadas/removidas).
</details>

## Alteração de commits

<details>
<summary><code>git commit --amend</code></summary>
<pre><code>git commit --amend</code></pre>

Modifica o último commit, permitindo adicionar arquivos esquecidos ou alterar a mensagem.
</details>

<details>
<summary><code>git commit --amend --no-edit</code></summary>
<pre><code>git commit --amend --no-edit</code></pre>

Faz um amend no último commit sem alterar a mensagem existente.
</details>

## Repositórios remotos

<details>
<summary><code>git remote -v</code></summary>
<pre><code>git remote -v</code></pre>

Exibe as URLs dos repositórios remotos associados ao repositório local.
</details>

<details>
<summary><code>git remote add origin &lt;url&gt;</code></summary>
<pre><code>git remote add origin &lt;url&gt;</code></pre>

Adiciona um repositório remoto chamado `origin` com a URL especificada.
</details>

<details>
<summary><code>git remote set-url origin &lt;url&gt;</code></summary>
<pre><code>git remote set-url origin &lt;url&gt;</code></pre>

Modifica a URL de um repositório remoto já existente (`origin`).
</details>

<details>
<summary><code>git push</code></summary>
<pre><code>git push</code></pre>

Envia as alterações commitadas localmente para o repositório remoto.
</details>

<details>
<summary><code>git pull</code></summary>
<pre><code>git pull</code></pre>

Baixa e mescla as alterações do repositório remoto para o repositório local.
</details>

## Branches

<details>
<summary><code>git branch --list</code></summary>
<pre><code>git branch --list</code></pre>

Exibe a lista de branches locais no repositório.
</details>

<details>
<summary><code>git branch &lt;nova_branch&gt;</code></summary>
<pre><code>git branch &lt;nova_branch&gt;</code></pre>

Cria uma nova branch com o nome especificado, sem trocar para ela.
</details>

<details>
<summary><code>git checkout &lt;branch&gt;</code></summary>
<pre><code>git checkout &lt;branch&gt;</code></pre>

Muda para a branch especificada.
</details>

<details>
<summary><code>git checkout -b &lt;nova_branch&gt;</code></summary>
<pre><code>git checkout -b &lt;nova_branch&gt;</code></pre>

Cria uma nova branch e já muda para ela.
</details>

<details>
<summary><code>git checkout -f &lt;branch&gt;</code></summary>
<pre><code>git checkout -f &lt;branch&gt;</code></pre>

Força a troca para a branch especificada, descartando alterações não commitadas.
</details>

<details>
<summary><code>git switch &lt;branch&gt;</code></summary>
<pre><code>git switch &lt;branch&gt;</code></pre>

Alterna para a branch especificada (alternativa mais moderna ao `git checkout`).
</details>

<details>
<summary><code>git switch -</code></summary>
<pre><code>git switch -</code></pre>

Volta para a última branch em que se estava.
</details>

<details>
<summary><code>git switch -c &lt;nova_branch&gt;</code></summary>
<pre><code>git switch -c &lt;nova_branch&gt;</code></pre>

Cria uma nova branch e já muda para ela (equivalente a `git checkout -b`).
</details>

<details>
<summary><code>git branch -d &lt;nome_branch&gt;</code></summary>
<pre><code>git branch -d &lt;nome_branch&gt;</code></pre>

Exclui a branch local especificada, desde que já tenha sido mesclada.
</details>

<details>
<summary><code>git push --delete origin &lt;nome_branch&gt;</code></summary>
<pre><code>git push --delete origin &lt;nome_branch&gt;</code></pre>

Remove a branch especificada do repositório remoto.
</details>

<details>
<summary><code>git branch -m &lt;novo_nome&gt;</code></summary>
<pre><code>git branch -m &lt;novo_nome&gt;</code></pre>

Renomeia a branch atual para o novo nome.
</details>

<details>
<summary><code>git branch -m &lt;nome_antigo&gt; &lt;novo_nome&gt;</code></summary>
<pre><code>git branch -m &lt;nome_antigo&gt; &lt;novo_nome&gt;</code></pre>

Renomeia uma branch específica de `<nome_antigo>` para `<novo_nome>`.
</details>

<details>
<summary><code>git branch -a</code></summary>
<pre><code>git branch -a</code></pre>

Exibe todas as branches, locais e remotas.
</details>

## Mesclagem de branches

<details>
<summary><code>git merge &lt;branch&gt;</code></summary>
<pre><code>git merge &lt;branch&gt;</code></pre>

Mescla as alterações da branch especificada na branch atual.
</details>

<details>
<summary><code>git push --force</code></summary>
<pre><code>git push --force</code></pre>

Força o envio das alterações para o remoto, sobrescrevendo o histórico de commits lá. **Atenção: pode apagar trabalho de outras pessoas.**
</details>

<details>
<summary><code>git push --force-with-lease</code></summary>
<pre><code>git push --force-with-lease</code></pre>

Força o envio, mas verifica antes se o remoto não foi alterado por terceiros, evitando sobrescrever trabalho alheio sem perceber. Mais seguro que `--force`.
</details>

## Tags

<details>
<summary><code>git tag &lt;nome&gt;</code></summary>
<pre><code>git tag &lt;nome&gt;</code></pre>

Cria uma tag *lightweight* (sem metadados), associada ao commit atual (último commit).
</details>

<details>
<summary><code>git tag -a -m "mensagem" &lt;nome&gt;</code></summary>
<pre><code>git tag -a -m "mensagem" &lt;nome&gt;</code></pre>

Cria uma tag *annotated* (com metadados: autor, data, mensagem).
</details>

<details>
<summary><code>git show &lt;tag&gt;</code></summary>
<pre><code>git show &lt;tag&gt;</code></pre>

Exibe informações sobre uma tag específica, incluindo o commit ao qual está associada.
</details>

<details>
<summary><code>git tag --list</code></summary>
<pre><code>git tag --list</code></pre>

Exibe todas as tags do repositório.
</details>

<details>
<summary><code>git tag -n</code></summary>
<pre><code>git tag -n</code></pre>

Exibe todas as tags junto com suas mensagens (se houver).
</details>

<details>
<summary><code>git tag -d &lt;nome&gt;</code></summary>
<pre><code>git tag -d &lt;nome&gt;</code></pre>

Remove uma tag localmente.
</details>

<details>
<summary><code>git push --delete origin &lt;nome_tag&gt;</code></summary>
<pre><code>git push --delete origin &lt;nome_tag&gt;</code></pre>

Remove uma tag do repositório remoto.
</details>

## Modificação de histórico

<details>
<summary><code>git revert &lt;commit&gt;</code></summary>
<pre><code>git revert &lt;commit&gt;</code></pre>

Cria um **novo** commit que desfaz as alterações de um commit anterior (sem reescrever histórico).
</details>

<details>
<summary><code>git revert HEAD --no-edit</code></summary>
<pre><code>git revert HEAD --no-edit</code></pre>

Reverte o último commit sem abrir o editor para alterar a mensagem gerada.
</details>

<details>
<summary><code>git rebase &lt;branch&gt;</code></summary>
<pre><code>git rebase &lt;branch&gt;</code></pre>

Reaplica os commits da branch atual sobre a branch especificada, reescrevendo o histórico.
</details>

<details>
<summary><code>git rebase --abort</code></summary>
<pre><code>git rebase --abort</code></pre>

Aborta um rebase em andamento, retornando ao estado anterior ao início do rebase.
</details>

<details>
<summary><code>git rebase --continue</code></summary>
<pre><code>git rebase --continue</code></pre>

Continua o rebase após resolver os conflitos apontados.
</details>

## Stash

<details>
<summary><code>git stash</code></summary>
<pre><code>git stash</code></pre>

Guarda temporariamente as alterações não commitadas, deixando o diretório de trabalho limpo.
</details>

<details>
<summary><code>git stash list</code></summary>
<pre><code>git stash list</code></pre>

Exibe a lista de stashes armazenados.
</details>

<details>
<summary><code>git stash apply</code></summary>
<pre><code>git stash apply</code></pre>

Aplica o stash mais recente ao diretório de trabalho, sem removê-lo da lista de stashes.
</details>

<details>
<summary><code>git stash apply stash@&lt;posicao&gt;</code></summary>
<pre><code>git stash apply stash@&lt;posicao&gt;</code></pre>

Aplica um stash específico da lista, indicado pela posição.
</details>

<details>
<summary><code>git stash pop &lt;posicao&gt;</code></summary>
<pre><code>git stash pop &lt;posicao&gt;</code></pre>

Aplica **e remove** o stash especificado da lista.
</details>

<details>
<summary><code>git stash drop &lt;posicao&gt;</code></summary>
<pre><code>git stash drop &lt;posicao&gt;</code></pre>

Remove um stash específico da lista, sem aplicá-lo.
</details>

## Bisect (bisseção)

Usado para localizar, por busca binária, o commit que introduziu um bug.

<details>
<summary><code>git bisect start</code></summary>
<pre><code>git bisect start</code></pre>

Inicia uma sessão de bisseção.
</details>

<details>
<summary><code>git bisect good &lt;hash&gt;</code></summary>
<pre><code>git bisect good &lt;hash&gt;</code></pre>

Marca o commit especificado como "bom" (sem o bug).
</details>

<details>
<summary><code>git bisect bad &lt;hash&gt;</code></summary>
<pre><code>git bisect bad &lt;hash&gt;</code></pre>

Marca o commit especificado como "ruim" (com o bug).
</details>

<details>
<summary><code>git bisect good</code></summary>
<pre><code>git bisect good</code></pre>

Marca o commit atual (que está em checkout) como "bom".
</details>

<details>
<summary><code>git bisect bad</code></summary>
<pre><code>git bisect bad</code></pre>

Marca o commit atual como "ruim".
</details>

## Fetch

<details>
<summary><code>git fetch</code></summary>
<pre><code>git fetch</code></pre>

Baixa as atualizações dos repositórios remotos, mas **não** as mescla com a branch atual (diferente de `pull`).
</details>

## Aplicação de commit

<details>
<summary><code>git cherry-pick &lt;commit&gt;</code></summary>
<pre><code>git cherry-pick &lt;commit&gt;</code></pre>

Aplica as mudanças de um commit específico de outra branch na branch atual.
</details>

## Alias

<details>
<summary><code>git config --global alias.&lt;abreviacao&gt; &lt;comando&gt;</code></summary>
<pre><code>git config --global alias.&lt;abreviacao&gt; &lt;comando&gt;</code></pre>

Cria um alias global, permitindo usar `<abreviacao>` no lugar de `<comando>`.
</details>

<details>
<summary><code>git config --global --unset alias.&lt;abreviacao&gt;</code></summary>
<pre><code>git config --global --unset alias.&lt;abreviacao&gt;</code></pre>

Remove o alias global especificado.
</details>

---
Fonte: *Git Resumo Prático* — www.devmasterteam.com
