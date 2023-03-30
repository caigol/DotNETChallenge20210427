## Readme do Repositório

# DotNet Challenge 20210427
# Grupo Fácil
# Caique Silva Pereira - caigol10@hotmail.com - caique.pereiraphp@gmail.com

## Responda as questões sobre Back-end

1. Em certo serviço, foram alterados todos os métodos de acesso a dados para que fossem assíncronos,
utilizando _async/await no C#_. Foi dito que isso melhoraria a performance da aplicação. Faz sentido?
Justifique.

Sim, faz sentido que a alteração dos métodos de acesso a dados para serem assíncronos utilizando async/await no C# possa melhorar a performance da aplicação.
Quando um método é executado de forma síncrona, ele bloqueia a thread que o está executando até que a operação seja concluída. Isso significa que, se o método de acesso a dados for executado em uma thread principal da aplicação, outras operações que dependem dessa thread serão bloqueadas até que o método termine. Isso pode levar a uma diminuição na eficiência e no desempenho da aplicação, especialmente se houver muitas operações de acesso a dados que precisam ser executadas.
No entanto, ao utilizar async/await para tornar esses métodos de acesso a dados assíncronos, é possível executá-los em uma thread separada. Dessa forma, a thread principal da aplicação não é bloqueada, permitindo que outras operações possam continuar sendo executadas ao mesmo tempo. Isso pode levar a uma melhoria significativa na performance da aplicação, especialmente se houver muitas operações de acesso a dados ou se os dados estiverem sendo acessados de forma remota.


2. Considere os dois métodos abaixo, e as suas chamadas. Um desses métodos é executado de forma
assíncrona, liberando o thread para fazer outras operações. O outro é executado de forma síncrona,
onde não há liberação do thread. Qual é qual? Justifique.

```
async Task<string> RetornaOkAsync() => “ok”;
Task DelayAsync() => Task.Delay(1000);
...
await RetornaOkAsync();
await DelayAsync();

```

O método que é executado de forma assíncrona é o método "DelayAsync", enquanto o método "RetornaOkAsync" é executado de forma síncrona.
Isso ocorre porque o método "DelayAsync" usa o método "Task.Delay", que é uma operação assíncrona que suspende a execução do método por um determinado período de tempo, sem bloquear a thread que está executando o método. Enquanto isso, o método "RetornaOkAsync" não tem nenhuma operação assíncrona, e é executado de forma síncrona, sem liberar a thread.
Quando o código é executado, a primeira chamada "await RetornaOkAsync()" bloqueia a thread até que o método seja concluído, enquanto a segunda chamada "await DelayAsync()" libera a thread para fazer outras operações por um segundo antes de continuar com o restante do código.

3. Uma aplicação ASP.NET Core 3 padrão é executada em um container linux no docker, e há um arquivo
appsettings.json na pasta da aplicação, mas o endereço do banco de dados mudou. Dê ideias de como
podemos passar nova configuração para aplicação sem precisar recriar a imagem do docker.

A maneira que estou mais acostumado é utilizando variáveis de ambientes. Vou deixar aqui duas resoluções uma direta via docker e a mais comum pra mim que é utilizando variáveis de ambiente do Kubernetes.
Passar variáveis de ambiente via Docker: Uma maneira de passar a nova configuração para o aplicativo é definir variáveis de ambiente para o endereço do banco de dados e, em seguida, ler essas variáveis no código da aplicação. Isso pode ser feito com o comando "-e" ao executar o contêiner. Por exemplo: 'docker run -e "DATABASE_ADDRESS=meu_novo_endereco" minha_imagem'
Usar variáveis ​​de ambiente do Kubernetes: Se o aplicativo estiver sendo executado no Kubernetes, podemos usar as variáveis ​​de ambiente do Kubernetes para substituir as configurações do aplicativo. As variáveis ​​de ambiente podem ser definidas no arquivo de configuração do Kubernetes, e o aplicativo pode ser configurado para ler essas variáveis ​​em tempo de execução.

4. Há vários métodos de acesso ao banco de dados. Entre os mais utilizados no .NET, há o Entity
Framework da Microsoft. Do outro lado, há helpers para execução direta de SQL no banco, como
Dapper. Quando você utiliza um ou outro, e por quê?

O Entity Framework é mais adequado para projetos que requerem gerenciamento de banco de dados em grande escala, complexidade de relacionamento e persistência de dados avançada, como o uso de transações e procedimentos armazenados.
O Dapper é mais adequado para projetos que exigem desempenho e simplicidade em consultas SQL, como em projetos de microserviços e aplicações de alto desempenho.
Em resumo, se o projeto precisar de recursos avançados de mapeamento objeto-relacional e gerenciamento de banco de dados, o Entity Framework é a escolha ideal. Se o projeto precisa de desempenho e simplicidade na execução de consultas SQL, o Dapper pode ser a melhor opção.

5. Qual código você prefere? Justifique.

a. 
`List<T> list = new List<T>();`

b. 
`var list = new List<T>();`
 
Entre as opções apresentadas, eu prefiro a opção b: var list = new List<T>();
Isso porque, ao utilizar a palavra-chave var, estamos utilizando a inferência de tipo do compilador do C#. Nesse caso, o compilador infere o tipo da variável com base no tipo do objeto que está sendo atribuído a ela. Isso torna o código mais conciso e legível, evitando a redundância de ter que escrever o tipo duas vezes.

## Responda as questões sobre Modelagem de Dados:

1. Há uma tabela de log com muitos registros e uma query que retorna a data do último log de cada
cliente:

`SELECT IdCliente, MAX(DataLog) as UltimoLog FROM log GROUP BY IdCliente`

Já há um índice na tabela com os campos IdCliente, DataLog. A query ainda está lenta. Você tem
liberdade total para alterar o que quiser no sistema. O que você faria para obter este dado de forma
mais rápida?

A criação de índices otimizados para a consulta pode ajudar a melhorar o desempenho. Por exemplo, poderíamos criar um índice com a combinação dos campos IdCliente e DataLog na ordem inversa (ou seja, DataLog e IdCliente), que pode ser mais eficiente para essa consulta específica.

2. Cite um ou mais bancos de dados nosql que você já usou (ou gostaria de usar) e quais os casos de uso e
vantagens que você viu neles.

O banco nosql que mais trabalhei foi o MongoDB. Na minha última experiência utilizamos o MongoDB para armazenar tarifas de alugueis de veículos por loja/estado/cidade as grandes vantagens encontradas são a flexibilidade, desempenho e escalabilidade dos dados. Um chatbot desenvolvido na plataforma Blip (Take) fazia uma requisição no backend em .NET que consultada o MongoDB trazendo os valores de tarifas atualizados.


## Responda as questões sobre Front-end

1. Explique o conceito **"mobile-first"** e como ele se reflete em seu código CSS.

O mobile-first é um conceito de design que prioriza a criação de layouts e experiências de usuário para dispositivos móveis, antes de expandir para telas maiores, como desktops. Isso significa que o design e a experiência do usuário são pensados primeiro para dispositivos móveis, que geralmente possuem telas menores e recursos limitados, e depois adaptados para telas maiores.
No desenvolvimento do código CSS, o conceito mobile-first é refletido na escrita do código, onde a primeira abordagem é escrever CSS para dispositivos móveis, utilizando regras de estilo mais simples e que priorizam a eficiência e a simplicidade do código. A medida que o layout é expandido para telas maiores, regras mais complexas e específicas são adicionadas, para que o design possa ser adaptado à essas telas.

2. Qual código você prefere? Justifique.

a. 
```
.card {
background-color: #fff;
margin: 10px;
color: #0160d2;
padding: 10px;
}
```


b. 
```
.card {
display: block;
margin: 10px;
padding: 10px;
background-color: $white;
color: $blue;
}
```

Eu prefiro o código (b) pois contém definição das cores por meio de variáveis.

3. Qual o erro no HTML abaixo?

`<p><a href="/home"><div class="button">Voltar ao início</div></a></p>`

O erro no HTML apresentado é que o elemento `<a>` está aninhado dentro do elemento `<p>`, mas o elemento `<a>` é um elemento inline e o elemento `<p>` é um elemento de bloco. De acordo com a especificação HTML, elementos de bloco não podem ser filhos de elementos inline.
Além disso, o elemento `<a>` possui um elemento `<div>` dentro dele, mas isso não é permitido na sintaxe HTML. Elementos de bloco, como `<div>`, não podem ser filhos diretos de elementos inline, como `<a>`.


4. Em uma aplicação **_Angular_** podemos realizar a comunicação entre componentes fazendo com que
determinadas ações sejam refletidas onde for necessário. Considerando o cenário onde temos um
componente X responsável por uma ação que deve ser refletida tanto em componentes filhos quanto
em outros componentes distribuídos por toda a aplicação, como você realizaria essa comunicação?
Justifique.

Através do uso de um serviço de compartilhamento de dados injetado em todos os componentes que precisam compartilhar os dados. Esse serviço pode ter um método para atualizar os dados e outro para obtê-los. Os componentes podem chamar esses métodos para atualizar ou obter os dados compartilhados. Além disso devemos utilizar em conjunto o recurso observables do Angular. Por exemplo, o componente X pode atualizar um dado no serviço de compartilhamento de dados e, em seguida, notificar os outros componentes da aplicação por meio de um observable. Os componentes filhos e outros componentes que precisam ser atualizados podem se inscrever no observable para receber a notificação de atualização. Isso permite que a ação seja refletida em todos os componentes necessários, sem a necessidade de criar um grande número de inputs e outputs para passar dados entre os componentes ou emitir eventos manualmente. O serviço de compartilhamento de dados e observables fornecem uma solução mais escalável e gerenciável para a comunicação entre componentes em uma aplicação Angular.

## Responda as questões sobre Conhecimentos Gerais

1. Em que momentos e com que frequência você refatora seu código?

Procuro refatorar o código durante o desenvolvimento, antes de adicionar novas funcionalidades ou até mesmo quando utilizo ferramentas de análise de código (SonarQube por exemplo) e ele identifica oportunidades de refatoração.

2. Quando você se depara com um problema no desenvolvimento, onde não está claro como uma
biblioteca ou framework funciona, onde você procura informações (ex: blogs, artigos, github,
stackoveflow, etc)? 
Responda na ordem de importância que você dá pra cada fonte. Fique a vontade pra
detalhar ou especificar fontes que você usa.

Documentação da biblioteca ou framework - Através da documentação acabo encontrando várias informações e exemplos de utilização, quase sempre resolve o problema.
StackOverflow - Se através da documentação não encontrar a solução, procuro um fórum de um dev com problema semelhante no StackOverflow.
Outras fontes - Caso não consiga solucionar vou tentar utilizar sites de buscas (exemplo: Google) para encontrar outras fontes.
