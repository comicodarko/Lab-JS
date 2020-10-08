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
