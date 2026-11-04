# Controle de Cargas

Aplicativo local para Windows, feito em Python e Tkinter, para controlar cargas, produtos, estoque, devoluções, relatórios e backups. Os dados ficam no próprio computador.

## Recursos

- Cargas com códigos automáticos no formato `C001`, `C002`… e produtos com códigos numéricos sequenciais (`001`, `002`…).
- Cadastro de destino e motorista durante a criação da carga, com opção para adicionar, editar ou excluir nomes. Ajudante é opcional.
- Status da carga alterável pelo botão que aparece na coluna **Status** após selecionar uma carga.
- Cadastro de cargas históricas sem nova movimentação de estoque.
- Estoque por produto. Salvar uma carga desconta as quantidades; registrar uma devolução devolve ao estoque.
- Histórico de ajustes de estoque com data (`DD-MM-AAAA`) e hora em colunas separadas. É possível selecionar e excluir vários registros do histórico sem alterar o saldo atual.
- Listas com fonte de 11 pt. Os detalhes da carga podem ser abertos com duplo clique.
- Relatórios de cargas em PDF ou Excel, com uma carga por linha, produtos agrupados e data e hora de geração.
- Relatório PDF do estoque sem código de produto, também com data e hora de geração.
- Filtros por destino, motorista, período, horário, status e produto.
- Backup e restauração, com frequência automática diária, semanal ou quinzenal.
- Atualizações pelo GitHub, com conferência SHA-256 e verificação de inicialização antes de substituir o executável.
- Abas carregadas sob demanda para reduzir o tempo de abertura.

## Arquivos do projeto

- `controle_cargas.py`: código-fonte do aplicativo.
- `requirements.txt`: dependências usadas na geração.
- `gerar_executavel.bat`: instalador das dependências e gerador do executável.
- `ImagemLogo.png`: logo do aplicativo; precisa ficar junto ao código e ao gerador.
- `.gitignore`: impede publicar banco de dados, backups e arquivos temporários de compilação.

## Gerar o executável no Windows

1. Instale Python 3.11 ou superior e marque a opção para adicioná-lo ao PATH.
2. Coloque `controle_cargas.py`, `gerar_executavel.bat`, `requirements.txt` e `ImagemLogo.png` na mesma pasta.
3. Execute `gerar_executavel.bat` com acesso à internet para instalar as dependências.
4. O executável será criado em `dist/ControleDeCargas.exe`.

O computador que usar o executável não precisa ter Python instalado. O gerador cria um arquivo executável único para Windows.

## Publicar uma atualização

1. Mantenha `APP_VERSION` no código igual à versão que será publicada.
2. Envie o código atualizado ao repositório público do GitHub.
3. Gere o executável com o `.bat` atualizado.
4. Crie uma Release com a tag correspondente à versão (por exemplo, `v1.0.4`) e anexe o arquivo chamado exatamente `ControleDeCargas.exe`.
5. Na aba **Atualizações**, clique em **Verificar atualizações** e depois confirme **Atualizar e reiniciar**.

O repositório `paulovictrr/ControleDeCargas` já vem preenchido. O atualizador confere a versão e o SHA-256 do arquivo e testa se o executável baixado consegue iniciar antes de instalá-lo.

## Dados locais

O banco fica em `%LOCALAPPDATA%\ControleDeCargas\cargas.db`; os erros são registrados em `%LOCALAPPDATA%\ControleDeCargas\erro.log`. O banco e os backups contêm dados de trabalho: mantenha-os fora do GitHub. Faça um backup antes de transferir os dados para outro computador.
