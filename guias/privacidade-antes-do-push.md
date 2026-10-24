# Revisão de privacidade antes do envio

Confira exatamente o conteúdo que será publicado, inclusive capturas de tela e arquivos anexados.

## Arquivos que merecem atenção

- `.env`, `.env.local` e configurações com valores de produção.
- Chaves de API, tokens, senhas, certificados e chaves privadas.
- Bancos locais, cópias de segurança, exportações e dados de clientes.
- Logs, relatórios internos e imagens de painéis autenticados.
- URLs que funcionam como credenciais ou incluem tokens.

Um `.env.example` pode ser útil quando contém apenas nomes de variáveis e valores fictícios claramente identificados.

## Comandos de conferência

```sh
git status
git diff --cached --name-only
git diff --cached
git ls-files '.env*'
```

Leia os resultados antes do push. Um arquivo listado por `git ls-files` já está sendo rastreado; acrescentá-lo ao `.gitignore` não o remove automaticamente do histórico.

O `.gitignore` reduz inclusões acidentais, mas não substitui a revisão. Não execute `git add -f` em arquivos ignorados sem entender por que foram excluídos.

Se um segredo real já tiver sido publicado, apagar a linha em um commit posterior não é suficiente. Consulte a [orientação oficial do GitHub sobre dados sensíveis](https://docs.github.com/en/authentication/keeping-your-account-and-data-secure/removing-sensitive-data-from-a-repository) e trate a credencial exposta com o serviço que a emitiu.

[Voltar ao início](../README.md)
