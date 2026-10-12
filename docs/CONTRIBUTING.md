# Como contribuir

Este é um guia geral de contribuição para todos os repositórios da [Poppinss](https://github.com/poppinss). Leia-o com atenção antes de contribuir com qualquer um deles. 🙏

## Como relatar problemas

Muitos relatos em projetos de código aberto são dúvidas ou problemas de configuração no ambiente de quem os reporta. Por isso, recomendamos investigar e tentar reproduzir o problema antes de abrir uma issue.

Ao relatar um bug, inclua o máximo possível de informações e exemplos de código. Bons relatos costumam:

- **Ser completos:** isole o bug, crie um teste que falhe no repositório e abra uma issue explicando o problema.
- **Ser reproduzíveis:** isole o bug e forneça uma reprodução mínima em um repositório GitHub. Leia o artigo [Por que reproduções são necessárias](https://antfu.me/posts/why-reproductions-are-required) (em inglês).
- **Ser claros:** descreva o problema, compartilhe o código que o provoca e inclua os arquivos de configuração relacionados e a versão do pacote usada.

Formate os blocos de código seguindo o [guia de sintaxe Markdown do GitHub](https://docs.github.com/en/get-started/writing-on-github/getting-started-with-writing-and-formatting-on-github/basic-writing-and-formatting-syntax).

Relatos sem informações suficientes para entender ou reproduzir o problema podem ser encerrados sem explicação adicional.

## Como criar pull requests

> **Nota pessoal:** em geral, sou mais cauteloso ao aceitar pull requests com novos recursos. A manutenção contínua e a adaptação desses recursos durante reescritas ficam sob minha responsabilidade.
>
> Não leve para o lado pessoal caso seu pull request seja recusado. Talvez eu não possa assumir esse trabalho no momento.

Não é agradável ter um pull request recusado depois de investir tempo e esforço na implementação. Por isso, recomendamos abrir uma issue explicando a mudança proposta antes de começar.

Crie uma issue para explicar como pretende contribuir:

- **Correção de bug:** pull requests para corrigir bugs geralmente são aceitos depois que o problema é confirmado.
- **Novo recurso:** explique por que ele é necessário e compartilhe materiais que ajudem a equipe a avaliar a proposta.

Se necessário, esteja disponível para abrir pull requests adicionais com documentação para o recurso ou melhoria.

## Configuração do repositório

1. Clone o repositório na sua máquina:

   ```sh
   git clone <URL_DO_REPOSITÓRIO>
   ```

2. Instale as dependências. Não atualize dependências junto com uma solicitação de recurso. Se encontrar dependências desatualizadas, abra um pull request separado para atualizá-las.

   Usamos `npm` para gerenciar dependências; não use `yarn` nem outra ferramenta.

   ```sh
   npm install
   ```

3. Execute os testes:

   ```sh
   npm test
   ```

## Ferramentas utilizadas

| Ferramenta | Uso |
| --- | --- |
| TypeScript | Os repositórios são escritos em TypeScript. O JavaScript compilado e as definições de tipos são publicados no npm. |
| TS Node | Usamos [ts-node](https://typestrong.org/ts-node/) para executar testes e scripts sem compilar o TypeScript, acelerando o ciclo de desenvolvimento. |
| SWC | [SWC](https://swc.rs/) é um compilador de TypeScript escrito em Rust. O ts-node oferece suporte integrado ao SWC, que usamos pela velocidade. |
| NP | Usamos [np](https://github.com/sindresorhus/np) para publicar pacotes no npm. Ele automatiza etapas da publicação e da criação de releases no GitHub. A configuração fica no `package.json`. |
| ESLint | Ajuda a manter um estilo de código consistente. Nossas regras são publicadas no pacote [eslint-plugin-adonis](https://github.com/adonisjs-community/eslint-plugin-adonis). |
| Prettier | Formata o código para manter uma apresentação consistente. Para entender a diferença entre ESLint e Prettier, consulte a documentação [Prettier vs. Linters](https://prettier.io/docs/en/comparison.html) (em inglês). |
| EditorConfig | O arquivo `.editorconfig` na raiz de cada projeto configura regras de indentação e espaços no editor. O Prettier formata o código depois; o EditorConfig ajuda a configurar o editor antes. |
| Conventional Changelog | Os commits seguem convenções verificadas pelo [commitlint](https://github.com/conventional-changelog/commitlint/#what-is-commitlint). |
| Husky | Usamos [Husky](https://typicode.github.io/husky/#/) para verificar as convenções de commit por meio de hooks do Git. |

## Comandos

| Comando | Descrição |
| --- | --- |
| `npm run test` | Executa os testes do projeto usando `ts-node`. |
| `npm run compile` | Compila o projeto TypeScript para JavaScript e grava os arquivos em `build`. |
| `npm run typecheck` | Verifica os tipos sem gerar os arquivos JavaScript. |
| `npm run release` | Inicia o processo de publicação usando `np`. |
| `npm run lint` | Analisa o código usando ESLint. |
| `npm run format` | Formata o código usando Prettier. |
| `npm run sync-labels` | Sincroniza com o GitHub os labels definidos em `.github/labels.json`. Esse comando é exclusivo para administradores do projeto. |

## Estilo de código

Os projetos de Harminder Virk são escritos em TypeScript, e a migração para ESM puro está acontecendo gradualmente.

- Saiba mais sobre o [estilo de código](https://github.com/thetutlage/meta/discussions/3) (em inglês).
- Consulte as configurações de [ESM e TypeScript](https://github.com/thetutlage/meta/discussions/2) (em inglês).

Antes de enviar o código, execute:

```sh
# Formata com Prettier
npm run format

# Analisa o código com ESLint
npm run lint
```

## Reconhecimento de contribuições

Usamos o GitHub para exibir as pessoas que contribuíram com cada repositório no painel lateral. Também usamos a geração automática de notas de release do GitHub, que inclui referências aos perfis de quem contribuiu.
