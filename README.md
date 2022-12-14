# PROJETO MAGIC CARDS

# ESTE É UM PROJETO FEITO EM REACT

Neste aplicativo, voce será capaz de criar sua própria carta.

⚠️ Passo a passo da aplicação ⚠️

### 1.[X] - Criar o formulário para adicionar as cartas
### 2.[X] - Colocar as props necessárias
### 3.[X] - Criar e renderizar o componente Card com as props necessárias
 **Utilizei a renderização condicional do React nesse requisito.**
### 4.[X] - Criar o preview da carta
### 5.[X] - Validando o botao de salvar no formulário
#### Regras de validação:

#### O botão só deve estar habilitado se todas as informações do formulário estiverem preenchidas;

- Os campos Nome, Descrição, Imagem e Raridade devem conter alguma informação (os inputs não podem estar vazios).

- A soma dos valores dos 3 atributos (attr1-input, attr2-input e attr3-input) não pode ultrapassar o valor 210.

- Cada um dos três atributos pode ter no máximo 90 pontos cada.

- Os atributos não podem receber valores negativos.

* Será validado se o botão salvar está desabilitado quando a página é renderizada pela primeira vez.
* Será validado se o botão salvar está desabilitado se o campo nome estiver vazio.
* Será validado se o botão salvar está desabilitado se o campo imagem estiver vazio.
* Será validado se o botão salvar está desabilitado se o campo descrição estiver vazio.
* Será validado se o botão salvar está desabilitado se o campo do atributo 1 for maior que 90.
* Será validado se o botão salvar está desabilitado se o campo do atributo 1 for menor que 0.
* Será validado se o botão salvar está desabilitado se o campo do atributo 2 for maior que 90.
* Será validado se o botão salvar está desabilitado se o campo do atributo 2 for menor que 0.
* Será validado se o botão salvar está desabilitado se o campo do atributo 3 for maior que 90.
* Será validado se o botão salvar está desabilitado se o campo do atributo 3 for menor que 0.
* Será validado se o botão salvar está desabilitado se a somatória dos campos de atributos for maior que 210.
* Será validado se o botão salvar é habilitado ao preencher todos os campos do formulário corretamente.

### 6. [X] - Criar a função do botao salvar

#### Criar um novo estado na aplicação para salvar a lista de cartas existentes no seu baralho. Salvar cada carta em um formato de objeto e ter um array com esses objetos no seu estado.

- Ao clicar no botão as informações que foram preenchidas no formulário deverão ser salvas no estado da sua aplicação.

- Após salvar as informações, os inputs do formulário Nome, Descrição e Imagem e o conteúdo do preview da carta deverão ser limpos.

- Após salvar as informações, os três campos de atributos devem ter valor 0.

- Após salvar as informações, o campo Raridade deve conter o valor selecione.

### 7. [X] - Criar a validação das cartas TRUNFO

#### Só pode existir apenas uma carta TRUNFO. Validação para que somente 1 carta TRUNFO seja salva no seu baralho.

* Para que tenha apenas uma carta salva como TRUNFO é preciso que o input do TRUNFO esteja checked na hora de salvar a carta. Fiz a validação no próprio input do TRUNFO com prop hasTrunfo do componente Form.

* Caso já exista uma carta Super TRUNFO em seu baralho, o formulário de criação de carta não deverá exibir mais o checkbox. No seu lugar deve ser renderizada a frase: "Você já tem um TRUNFO em seu baralho".

 **Utilizei a renderização condicional do React nesse requisito.**
 Se hasTrunfo for true, irá renderizar uma mensagem, senão renderiza o input TRUNFO.

 #### No componente APP, dentro da função onSavedButtonClick, ao clicar ele faz uma conferencia, se cardTrunfo for true ao clicar, o estado hasTrunfo fica verdadeiro(impedindo de se criar outra carta TRUNFO).

* Será validado se o checkbox do TRUNFO é redenderizado ao carregar a página, e se o texto "Você já tem um TRUNFO em seu baralho" é renderizado caso já exista uma carta TRUNFO.

### 8. [X] - Exibir as cartas salvas no estado
  #### Já possuo cartas criadas que estao salvas no estado allCards(um array de obejtos).

  - Renderizei o conjunto delas dentro do componente App. (Lista com todos as cartas salvas no estado allCards)
  - Conforme vou colocando cartas novas, ele é atualizado automaticamente.
  - Usei o componente Card para fazer isso.
  - Criei o componente AllCards, fiz um map do componente Cards dentro dele percorrendo o estado allCards, que eu passei via props.

  *** ERROS PARA CORRIGIR AINDA *** : CORRIGIR A RENDERIZAÇÃO DA CARTA
  
### 9. [] - Criar o botao de remover carta do baralho (INCOMPLETO)

#### CRIADO A FUNÇÃO;  

```js
removeCard = ({target}) => {
    this.setState((prev) => ({
      savedCards: prev.savedCards.filter((element) => (target.cardName !== element.name)),
    }));
  }
```
  *** ESTA FUNÇÃO é uma HOF que filtra o elementos que ao clicar no botao excluir(que possui o cardName) retorna um array sem o elemento com aquele nome ***
#### AINDA NÃO FUNCIONA

### 10.[] - Criar o filtro pelo nome da carta (INCOMPLETO)

Para filtro do nome, você deverá criar um campo do tipo text e adicionar o atributo data-testid="name-filter".

Este campo deve ser renderizado sempre, mesmo se não existir cartas salvas no baralho.

Ao digitar neste campo, deve ser renderizado na página apenas as cartas que contenham no nome o texto digitado.



### 11.[] - Criar o filtro pela raridade da carta (INCOMPLETO)

  Para filtrar por raridade, você deverá criar um campo do tipo select e adicionar o atributo data-testid="rare-filter";

Este select deve possuir as seguintes options: todas, normal, raro e muito raro. Por padrão, a opção todas já deverá estar selecionada;

Ao selecionar uma das opções, apenas as cartas que possuem a raridade especificada deverão ser renderizadas. Caso esteja selecionada todas, não deve ter filtro de raridade aplicado na lista.

Se o campo do filtro Nome estiver preenchido, os dois filtros (por nome e por raridade) devem funcionar em conjunto.

### 12.[X] - Criar o filtro de carta TRUNFO

* Foi criado um input tipo checkbox, que ao mudar, filtra a carta TRUNFO
* Foi criado a função para filtrar o trunfo.

``` js
  filtraTrunfo = () => {
    this.setState((prev) => ({
      savedCards: prev.savedCards.filter((element) => element.cardTrunfo === true)
    }))
  }
```

