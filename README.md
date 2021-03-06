Certified Scrum Developer - Módulo de Testes
=========

Durante esse módulo, criaremos um pequeno simulador de cotidiano de um desenvolvedor. Em cada etapa, você terá algumas opções que podem deixar seu dia mais leve ou mais estressante. O seu nível de stress pode variar de 0 a 10 e esse coeficiente influenciará a probabilidade de você se envolver em determinados eventos durante o dia.

- Acordar
- Café da Manhã
- Ida ao Trabalho
- Almoço
- Fim do Expediente
- Volta do Trabalho
- Filme pra relaxar

O módulo de testes do CSD se dividirá em 4 etapas:


## Testes

#### Gerenciamento de dependências

Para escrever e rodar testes é necessário adicionar algum *framework* de testes ao seu classpath. Mas vamos fazer isso de uma maneira mais profissional: usando o [Gradle][1].

O **Gradle** é uma ferramenta de automação de *builds* que faz o trabalho dos conhecidos [Maven][2] e [Ant][3] de uma maneira mais sucinta e auto-explicativa. Sua sintaxe é menos verbosa e de fácil compreensão, e por esse motivo o utilizaremos bastante no decorrer do curso.

O arquivo `build.gradle` é onde declaramos as dependências e tarefas de nossa aplicação. Para esse repositório, utilizamos também alguns plugins para facilitar a execução da aplicação.

Vamos utilizar o [JUnit][4] para executar os testes. Para incluí-lo no projeto basta descomentar a seguinte linha no arquivo `build.gradle`:

```groovy
testCompile group: 'junit', name: 'junit', version: '4.11'
```

Essa linha informa ao gradle que nossos testes dependem da biblioteca Junit. Com isso, qualquer tarefa que execute testes verificará se o JUnit está presente e o baixará automaticamente do repositório Maven caso seja necessário.

Embora não seja um assunto ligado diretamente ao TDD, o gerenciamento de dependências é extremamente importante para que possamos garantir a uniformidade entre os ambientes de desenvolvimento. Se você desenvolver sempre dessa forma, fica fácil garantir que o servidor de CI e as máquinas de todo o time estão trabalhando com as mesmas dependências.

#### Escrevendo seu primeiro teste

Tente digitar `gradle tasks` na linha de comando. O Gradle listará todas as tarefas que podem ser executadas em nosso projeto atual. Vamos focar agora em duas tarefas principais:

* `gradle run`

Esse comando executa nossa aplicação diretamente na linha de comando. E como o primeiro acontecimento já está implementado, podemos ver o que acontece se escolhemos acordar cedo ou tarde.

O plugin *application* foi incluído no `build.gradle` para que o Gradle soubesse que nosso projeto se trata de uma aplicação. Além disso, também informamos nesse arquivo onde estão nossas classes Java e qual delas é o ponto de entrada de nossa aplicação.

* `gradle test`

Com esse comando rodamos os testes existentes para nosso projeto. Assim como as classes da aplicação, o diretório onde nossos testes ficam é configurado no arquivo `build.gradle`. No momento, temos apenas um teste para a classe `Despertar.java`. Dê uma olhada no arquivo `DespertarTests.java` e tente implementar seu primeiro teste para o método `getOpcoes` da classe `Despertar`.

[1]: http://www.gradle.org/
[2]: http://maven.apache.org/
[3]: http://ant.apache.org/
[4]: http://junit.org/