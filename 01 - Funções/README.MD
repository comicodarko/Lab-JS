<h1 align="center">
  Lab <img src="https://camo.githubusercontent.com/15db4280f306a50d7f567cc5eb67c38c476097e0/68747470733a2f2f692e6962622e636f2f636766623730622f617364642e706e67" width=35>
</h1>


<h2 align="center">  
  
  :memo:
  
  Funções
</h2>

## <a name="i">:robot: Índice</a>

- 1 -   [JS - Funções](#1-1)
  - 1.1 [Maneiras de declarar funções](#1-1)
  - 1.2 [Parâmetros da Função](#1-2)
  - 1.3 [Retorno da Função](#1-3)
  - 1.4 [Escopo Léxico](#1-4)
- 2 -   [JS - Arrays]()
- 3 -   [JS - Objetos e proptypes]()
- 4 -   [JS - Classes]()
- 5 -   [JS - Assíncrono]()
- 6 -   [JS - Tooling e ES6 Modules]()
- 7 -   [JS - Node]()
- 8 -   [Linux - Deploy de aplicação]()
- 9 -   [JS - API REST - Express e MongoDB]()
- 10 -  [JS - React]()
- 11 -  [JS - Redux e Redux Saga]()
- 12 -  [JS - Expressões regulares]()
  
****

## <a name="1-1">Maneiras de declarar funções</a>

### **Funções Literais:**

```js
function sayHello() {
  console.log('Hello!');
}

sayHello();
```
> Em funções literais ocorre o **Function Hoisting**, onde o JavaScript elevará a função para o topo (como se fosse global).

### **Função de Expressão:**

Funções no JavaScript são como Objetos de primeira classe e podem ser tratadas como dado.

```js
const sayHello = function() {
  console.log('Hello!');
}

sayHello();
```
> Agora é possível jogar essa variável como parâmetro de outra função e fazer a mesma executar a função a cima.

```js
function execute(func) {
  func();
}

execute(sayHello);
```

### **Arrow Function:**

```js
const sayHello = () => {
  console.log('Hello!');
}

sayHello();
```

### **Funções dentro de Objetos:**

```js
const obj = {
  say: function() {
    console.log('Hello!');
  }
}

obj.say();
```

### **Uma versão atualizada:**

```js
const obj = {
  say() {
    console.log('Hello!');
  }
}

obj.say();
```
> O JavaScript já reconhece say como um método.

[Voltar para o índice](#i)
****

## <a name="1-2">Parâmetros da Função</a>

### Arguments:

```js
function test() {
  let total = 0;
  for (let argumento of arguments) {
    total += argumento;
  }
}

test(1, 2, 3, 4);
```
> 1, 2 , 3, 4 foram para o array **arguments**.  
> Nesse caso teremos a soma total dos números passado sem utilizar de parâmetros na função.  
> Vale lembra que esse tipo de feito não funciona em arrow functions. 

### Parâmetros sobrando:

```js
function test(a, b, c, d) {
  console.log(a, b, c, d);
}

test(1, 2);
```
> **c** e **d** terão o valor de *undefined*.

### Valores padrões para parâmetros:

```js
function test(a, b = 2) {
  console.log(a + b);
}

test(1);
```

### Pulando definição de valores de parâmetros:

```js
function test(a, b = 2, c) {
  console.log(a + b + c);
}

test(1, undefined, 1);
```
> **b** receberá o valor padrão de 2.  
> Esse é o único jeito de "pular". Null será lido como 0. 

### Rest Operator como parâmetros

```js
function test(operador, ...numeros) {
  console.log(a + b);
}

test('+', 10, 15, 20);
```
> Todo o resto após '+' será atribuído a um array.

[Voltar para o índice](#i)
****

## <a name="1-3">Retorno da Função</a>

**return** - Retorna um valor - Termina a função.  

```js
  function createPerson(name, age) {
    return { name, age }
  }

  const p1 = createPerson('Fábio', 20);
  const p2 = {
    name: 'Fábio2',
    age: 20
  }
```


Funções sem retorno (alert(), por exemplo), retornam undefined.

### **Retornando uma função (sem executar)**

```js
function func1(bla1) {
  function func2(bla2) {
    return bla1 + bla2;
  }
  return func2
}

const soma = func1(1);
// soma guarda uma função e não um retorno.
soma(2);
// 1+2=3
```
> Sim, o parâmetro da função 1 está sendo usado na função 2...   

### **Onde isso é util?** 

duplicar, triplicar, quadriplicar...

```js
function duplica(n) {
  return n * 2;
}

function triplica(n) {
  return n * 3;
}

function quadriplica(n) {
  return n * 4;
}
```

Facilitando:

```js
function createMultiplier(multiplier) {
  return function(n) {
    return n * multiplier;
  }
}
const duplica = createMultiplier(2);
const triplica = createMultiplier(3);
const quadriplica = createMultiplier(4);
```

### **Escopo Léxico**

A função conhece: 
- local onde ela foi declarada
- tudo declarado dentro dela
- vizinhos

```js
const name = 'José';

function sayName() {
  const name = 'Fábio';
  console.log(name);
}

sayName();
```
> Nesse caso será falado "Fábio", caso não existisse, seria falado "José".

### **Porém:**

```js
const name = 'José';

function sayName() {
  console.log(name);
}

function useSayName() {
  const name = 'Fábio';
  sayName();
}

useSayName();
```

> Será falado 'José' por conta do contexto léxico.

[Voltar para o índice](#i)
****

[Voltar para o índice](#i)
****