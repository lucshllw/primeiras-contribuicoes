# Ideias de contribuições em interfaces web

Escolha um comportamento que você consiga observar, reproduzir e explicar. Os exemplos abaixo são pontos de investigação, não afirmações de que algum projeto específico tenha esses problemas.

## Documentação e exemplos

- Uma instrução de instalação que deixa de fora uma dependência necessária.
- Um exemplo que descreve um comportamento diferente do código atual.
- Uma opção cujo valor padrão não está claro.
- Um trecho de código que não compila na configuração documentada.

## Acessibilidade

- Um controle que não funciona pelo teclado.
- Foco que desaparece ao abrir ou fechar uma interface.
- Um componente animado que ignora a preferência por movimento reduzido.
- Uma interação que só existe no hover e não tem alternativa no toque.

Teste o comportamento e consulte os padrões adotados pelo projeto. Uma alteração isolada não comprova acessibilidade completa.

## TypeScript

- Uma declaração que rejeita uma chamada aceita e documentada pelo runtime.
- Uma propriedade opcional marcada como obrigatória por engano.
- Um retorno declarado incorretamente que impede encadear métodos.

Inclua um exemplo mínimo de compilação. Se possível, verifique também o comportamento do JavaScript para confirmar a intenção da API.

## Desempenho e ciclo de vida

- Um temporizador que continua ativo depois de desmontar o componente.
- Um evento registrado várias vezes sem limpeza.
- Uma mídia que baixa sem necessidade antes de aparecer.

Meça antes e depois sob as mesmas condições. Não prometa melhora universal com base em um único dispositivo ou apenas na leitura do código.

## Antes de propor a alteração

Confira se há solução em andamento, siga as convenções do projeto e limite a mudança ao problema demonstrado. Para decisões de produto ou novos recursos, alinhe a proposta com os mantenedores antes de implementar.

[Voltar ao início](../README.md)
