# Pit Lane — App de Trackday

Aplicativo Android para entusiastas de automobilismo acompanharem trackdays, consultarem os detalhes dos eventos, salvarem datas de interesse e organizarem o histórico de participações, tempos de volta e gastos.

## Objetivo do projeto

Desenvolver um aplicativo Android em Kotlin com Jetpack Compose, reunindo consumo de API, autenticação local, persistência de dados e navegação entre telas. O design das telas foi elaborado previamente e será utilizado como referência para a implementação das funcionalidades.

## Funcionalidades planejadas

- Cadastro e login de usuários, com validação dos campos.
- Manutenção da sessão após fechar e reabrir o aplicativo.
- Consulta à agenda de trackdays por meio de uma API REST pública.
- Exibição dos detalhes de cada evento, incluindo data, horário, categoria, vagas e valor.
- Salvamento de trackdays favoritos para cada usuário.
- Histórico de participações, incluindo veículo, tempos de volta e gastos.
- Perfil do usuário e opção de sair da conta.
- Estados visuais de carregamento, sucesso, erro e falta de conexão.
- Navegação inferior com pelo menos três abas e acesso à tela de detalhes do evento.

> As funcionalidades acima são objetivos de implementação. Marque-as como concluídas somente depois de testar o comportamento no aplicativo.

## Tecnologias e arquitetura

- **Kotlin**
- **Jetpack Compose** para a interface.
- **Navigation Compose** para a navegação.
- **Retrofit** e **coroutines** para o consumo da API REST.
- **Room** para persistência local.
- **Repository** para intermediar o acesso aos dados.
- **ViewModel** para estados e lógica de apresentação.

A API pública será escolhida e testada antes da integração. Registre nesta seção o nome, o endereço-base e os dados efetivamente utilizados assim que a escolha estiver confirmada.

## Cronograma de desenvolvimento

O cronograma parte do princípio de que o design das telas já está concluído. As semanas são uma sugestão de organização e podem ser ajustadas ao prazo definido pela equipe e pelo professor.

| Etapa | Atividades | Entrega / critério de conclusão | Previsão |
|---|---|---|---|
| 1. Planejamento técnico | Revisar o design, definir o fluxo de navegação, escolher e testar a API pública e combinar a divisão de tarefas. | Escopo, API e responsabilidades definidos. | Semana 1 |
| 2. Configuração do projeto | Criar o projeto Kotlin com Jetpack Compose, configurar dependências, namespace, permissões de internet e pacotes. | Aplicativo abre no emulador sem travar e estrutura inicial organizada. | Semana 1 |
| 3. Integração com a API | Criar a interface Retrofit, os modelos de dados e o Repository; fazer requisições usando coroutines. | Dados recebidos e exibidos na agenda, com estados de carregamento, sucesso e erro. | Semana 2 |
| 4. Banco de dados local | Implementar Room: Entity, DAO e Database; criar o acesso aos dados por meio do Repository. | Dados locais podem ser gravados, consultados e mantidos após fechar e reabrir o app. | Semana 2 |
| 5. Cadastro, login e sessão | Implementar usuários no Room, validação de e-mail e senha, e-mail único, hash da senha, mensagens de erro e persistência da sessão. | Cadastro e login funcionam; senha incorreta é recusada; sessão é mantida após reiniciar o app; opção Sair retorna ao login. | Semana 3 |
| 6. Navegação e telas | Conectar login à área principal, implementar a barra inferior com pelo menos três abas, rotas type-safe e tela de detalhes. | Fluxo entre telas funciona e o detalhe recebe o evento selecionado corretamente. | Semana 3 |
| 7. Favoritos e histórico | Associar os itens salvos ao usuário conectado e implementar a consulta e exibição do histórico previsto no projeto. | Dados salvos persistem e não se misturam entre contas diferentes. | Semana 4 |
| 8. Integração e acabamento | Conectar as telas ao ViewModel e ao Repository, revisar textos e estados de erro, conferir o visual com o design aprovado. | Telas integradas e comportamento consistente em situações normais e de falha. | Semana 4 |
| 9. Testes e correções | Testar cadastro, login válido e inválido, navegação, API, Room, modo avião, sessão persistente e troca de usuários. | Checklist de testes executada e problemas encontrados corrigidos. | Semana 5 |
| 10. Documentação e entrega | Adicionar 4 a 6 prints, registrar API, divisão de tarefas e aprendizados no README; conferir os commits de todos os integrantes e o repositório GitHub. | Repositório pronto para envio ao professor. | Semana 5 |

## API utilizada

**A definir / confirmar durante a implementação.**

- **Nome:** [nome da API]
- **Endereço-base:** [URL base]
- **Dados utilizados:** [descrever quais informações são exibidas no aplicativo]
- **Observações:** priorizar uma API pública que não exija cadastro nem chave, conforme o enunciado da atividade.

## Estrutura de pacotes

A estrutura deve respeitar as responsabilidades indicadas no enunciado. Ajuste os nomes conforme os pacotes realmente criados no projeto.

```text
com.seuapp
├── network
│   └── Interface e configuração do Retrofit
├── data
│   ├── Modelos de dados
│   ├── Room: Entity, DAO e Database
│   └── Repository
├── viewmodel
│   └── ViewModels e estados das telas
└── userinterface
    ├── Telas Compose
    ├── Componentes visuais
    └── Navegação
```

As telas não devem chamar Retrofit nem DAO diretamente. O acesso a esses recursos deve passar pelo Repository, e o ViewModel não deve depender da camada `userinterface`.

## Prints do aplicativo

Adicione de 4 a 6 imagens reais do aplicativo implementado. Sugestão de seleção:

1. Tela de login.
2. Tela de cadastro.
3. Agenda/lista de trackdays.
4. Detalhes de um trackday.
5. Tela de salvos ou histórico.
6. Estado de erro ou falta de conexão.

Exemplo de organização dos arquivos de imagem:

```text
README.md
docs/
└── prints/
    ├── login.png
    ├── cadastro.png
    ├── agenda.png
    ├── detalhes.png
    ├── salvos.png
    └── sem-conexao.png
```

Depois de adicionar as imagens ao repositório, você pode exibi-las aqui usando, por exemplo, `![Tela de login](docs/prints/login.png)`.

## Divisão de tarefas

Preencha a tabela com os nomes dos integrantes e as atividades que cada um realmente realizou.

| Integrante | O que fez |
|---|---|
| [Nome do integrante 1] | [Atividades realizadas] |
| [Nome do integrante 2] | [Atividades realizadas] |
| [Nome do integrante 3, se houver] | [Atividades realizadas] |

Todos os integrantes devem contribuir com commits no repositório.

## O que aprendemos

Cada integrante deve escrever uma frase sobre o que aprendeu durante o desenvolvimento.

- **[Nome do integrante 1]:** [Uma frase sobre o que aprendeu.]
- **[Nome do integrante 2]:** [Uma frase sobre o que aprendeu.]
- **[Nome do integrante 3, se houver]:** [Uma frase sobre o que aprendeu.]

## Checklist antes da entrega

- [ ] O aplicativo abre no emulador sem travar.
- [ ] A API funciona e a interface apresenta carregamento, sucesso e erro.
- [ ] O cadastro valida os dados e impede e-mails duplicados.
- [ ] A senha é armazenada como hash, não em texto puro.
- [ ] O login aceita credenciais corretas e rejeita incorretas com mensagem clara.
- [ ] A sessão continua ativa depois de fechar e reabrir o aplicativo.
- [ ] O botão Sair retorna ao login.
- [ ] Os dados locais persistem após reiniciar o aplicativo.
- [ ] Os dados de usuários diferentes não se misturam.
- [ ] A navegação possui pelo menos três abas e a tela de detalhes recebe o item correto.
- [ ] As dependências entre `network`, `data`, `viewmodel` e `userinterface` respeitam a arquitetura solicitada.
- [ ] O README contém 4 a 6 prints, API utilizada, divisão de tarefas e aprendizados.
- [ ] Todos os integrantes possuem commits no GitHub.
- [ ] Cada integrante preencheu individualmente o formulário de feedback solicitado pelo professor.

## Repositório

[Adicione aqui o link do repositório no GitHub.]
