# Controle de Cargas

Aplicativo local para Windows, feito em Python e Tkinter, para acompanhar cargas, produtos, estoque, devoluções, relatórios e backups.

## Arquivos do projeto

- `ControleCargas.py`: código-fonte.
- `requirements.txt`: bibliotecas necessárias para gerar o executável.
- `gerar_executavel.bat`: prepara o executável Windows.
- `ImagemLogo.png`: logo usada no aplicativo e no executável; mantenha este arquivo junto dos demais.
- `.gitignore`: evita publicar banco de dados, backups e arquivos temporários de build.

## Gerar no Windows

1. Instale Python 3.11 ou superior e marque a opção para adicionar Python ao PATH.
2. Deixe `controle_cargas.py`, `gerar_executavel.bat`, `requirements.txt` e `ImagemLogo.png` na mesma pasta.
3. Execute `gerar_executavel.bat` com acesso à internet.
4. O executável será criado em `dist/ControleDeCargas.exe`.

O computador que usar o executável não precisa ter Python instalado. Os dados ficam em `%LOCALAPPDATA%\ControleDeCargas`.

## Publicar atualizações

1. Mantenha `APP_VERSION` no código alinhada à versão publicada.
2. Publique o código em um repositório público do GitHub.
3. Crie uma Release com uma tag de versão, como `v1.0.1`, e anexe o executável com o nome exato `ControleDeCargas.exe`.
4. No programa, abra **Atualizações**. O repositório `paulovictrr/ControleDeCargas` já vem preenchido; clique em **Verificar atualizações**.

O programa confere a versão e o SHA-256 informado pelo GitHub. Após sua confirmação, fecha, substitui o executável atual e reinicia. O banco local permanece no computador.

## Dados locais

O banco e os backups contêm dados de trabalho. Mantenha-os fora do repositório GitHub. O `.gitignore` do projeto já exclui os bancos SQLite, os backups e as pastas de build.
