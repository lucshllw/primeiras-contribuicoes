# Três exemplos reais de contribuição

Registrados em 24/10/2026. Os três são pull requests propostos; a abertura não significa que os mantenedores aceitaram ou publicaram a mudança. Consulte os links para o estado atual.

## OGL: declarar chamadas que o runtime já aceita

**Proposta:** [oframe/ogl #265](https://github.com/oframe/ogl/pull/265).

O JavaScript de `Mat3.set` e `Mat4.set` aceita uma matriz ou tupla em um único argumento. As declarações TypeScript exigiam todos os argumentos escalares, então uma chamada válida falhava na compilação.

O trabalho começou com uma fixture TypeScript que falhava com TS2554 e um teste de runtime que confirmava o comportamento já existente. A correção acrescenta sobrecargas, sem alterar o JavaScript. A fixture passou depois da alteração e os dois testes de runtime passaram.

**Lição:** uma contribuição pequena pode tornar uma API existente utilizável sem criar uma funcionalidade nova.

## Lenis: descrever precisamente um bloqueio de interação

**Proposta:** [darkroomengineering/lenis #562](https://github.com/darkroomengineering/lenis/pull/562), relacionada à [issue #552](https://github.com/darkroomengineering/lenis/issues/552).

Na branch v2, `lock()` bloqueia os gestos tratados pelo Lenis, mas não toda rolagem nativa. Em uma reprodução no Chromium, Page Down ainda moveu a página enquanto `isLocked` era verdadeiro.

A documentação proposta diferencia os dois comportamentos e mostra como ocultar/restaurar o overflow do elemento de rolagem quando uma integração de modal precisar disso. O comportamento foi conferido no navegador e no código, sem mudar o runtime.

**Lição:** documentação é uma contribuição técnica quando corrige uma expectativa incorreta com evidência reproduzível.

## OGL: remover apenas o callback responsável pelo descarte

**Proposta:** [oframe/ogl #266](https://github.com/oframe/ogl/pull/266).

`InstancedMesh.removeFrustumCull()` chamava `offBeforeRender`, um método inexistente na classe `Mesh`. A chamada falhava antes de restaurar as instâncias que haviam sido descartadas da renderização.

A correção remove o callback específico da lista existente e preserva outros callbacks. Três testes passaram depois de reproduzir a falha: restauração das matrizes e contagem, remoção repetida sem afetar outros callbacks e restauração dos dados de lightmap. São testes de lógica em Node, sem renderização WebGL.

**Lição:** um bug encontrado durante uma investigação pode merecer uma correção própria. Esta proposta não afirma resolver a discussão mais ampla sobre o descarte global do renderer.

## O que foi evitado

- Duplicar PRs que já resolviam outros problemas encontrados na pesquisa.
- Publicar comentários genéricos sem informação nova.
- Declarar que as propostas foram aprovadas antes do retorno dos mantenedores.
- Omitir o uso de assistência de IA nas descrições das contribuições.

[Voltar ao início](../README.md)
