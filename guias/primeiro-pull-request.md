# Seu primeiro pull request

Antes de editar, leia as instruções do projeto e confira se a mudança já está sendo feita por outra pessoa. Para funcionalidades novas ou decisões de produto, converse com os mantenedores primeiro.

## 1. Crie um fork e baixe sua cópia

No GitHub, use o botão **Fork** do projeto. Nos comandos abaixo, substitua `SEU_USUARIO`, `PROJETO` e `ORGANIZACAO` pelos nomes reais. Eles são marcadores, não nomes prontos para executar.

```sh
git clone https://github.com/SEU_USUARIO/PROJETO.git
cd PROJETO
git remote add upstream https://github.com/ORGANIZACAO/PROJETO.git
git remote -v
```

`origin` aponta para seu fork; `upstream` aponta para o projeto original. Não coloque tokens ou senhas nessas URLs.

## 2. Crie uma branch com um objetivo

O exemplo começa na branch padrão que acabou de ser clonada. Se o projeto exigir outra branch de destino, siga o `CONTRIBUTING.md`.

```sh
git switch -c docs/clarificar-instalacao
```

Escolha um problema pequeno: uma instrução incompleta, um exemplo quebrado ou um bug reproduzível. Evite misturar correções de comportamento, reorganização de arquivos e formatação numa única PR.

## 3. Confira o resultado

Execute os comandos de instalação, teste e build indicados pelo projeto. Eles variam: não presuma que todo repositório usa npm ou tem `npm test`.

Para um bug, registre o caso que falha antes da alteração e confira que ele passa depois. Para documentação, execute os passos descritos quando for possível.

```sh
git status
git diff
```

Leia o diff e confira se ele contém apenas o que você pretende enviar. Faça também a [revisão de privacidade](privacidade-antes-do-push.md).

## 4. Registre somente os arquivos desejados

Substitua `caminho/do/arquivo` pelo arquivo que você revisou. Repita o comando para os demais arquivos necessários.

```sh
git add caminho/do/arquivo
git diff --cached
git commit -m "docs: clarify installation steps"
git push -u origin docs/clarificar-instalacao
```

O commit precisa de nome e e-mail configurados no Git. Para preservar seu e-mail pessoal, use o endereço noreply fornecido nas configurações do GitHub. Não copie o endereço de outra pessoa.

## 5. Abra a pull request

No GitHub, abra a comparação do seu fork com o projeto original. Confira o repositório e a branch de destino antes de enviar.

Uma boa descrição responde:

- Qual problema concreto esta mudança resolve?
- Como alguém consegue reproduzi-lo?
- O que mudou e por quê?
- Quais verificações foram executadas e com qual resultado?
- Há limitações ou assistência de IA a informar?

Não marque uma issue como resolvida se você implementou apenas parte do pedido. Use uma referência à issue quando a relação existir, sem inventar vínculos.

Depois de abrir, acompanhe o retorno e faça os ajustes na mesma branch. A PR pode depender de revisão ou de autorização do mantenedor para rodar verificações externas; isso não é motivo para contornar controles do projeto.

[Voltar ao início](../README.md)
