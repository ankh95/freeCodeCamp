---
id: 587d8257367417b2b2512c7e
title: Use Depth First Search in a Binary Search Tree
challengeType: 1
videoUrl: ''
localeTitle: Использовать глубину первого поиска в двоичном дереве поиска
---

## Description
<section id="description"> Мы знаем, как искать двоичное дерево поиска для определенного значения. Но что, если мы просто хотим исследовать все дерево? Или что, если у нас нет упорядоченного дерева, и нам нужно просто искать значение? Здесь мы представим некоторые методы обхода дерева, которые можно использовать для изучения структур древовидных данных. Сначала - поиск по глубине. При поиске по глубине, заданное поддерево рассматривается как можно глубже, прежде чем поиск продолжит переход к другому поддереву. Это можно сделать тремя способами: In-order: Начать поиск на самом левом узле и завершить на самом правом узле. Предварительный порядок: исследуйте все корни перед листьями. Post-order: Исследуйте все листья перед корнями. Как вы можете догадаться, вы можете выбрать различные методы поиска в зависимости от того, какие данные хранят ваше дерево и что вы ищете. Для двоичного дерева поиска обход ордера возвращает узлы в отсортированном порядке. Инструкции: Здесь мы создадим эти три метода поиска в нашем двоичном дереве поиска. Поиск по глубине - это неотъемлемая рекурсивная операция, которая продолжает исследовать дальнейшие поддеревья, пока присутствуют дочерние узлы. Как только вы поймете эту базовую концепцию, вы можете просто изменить порядок, в котором вы исследуете узлы и поддеревья, чтобы произвести любой из трех поисков выше. Например, в post-order search мы хотели бы перечислить весь путь до листового узла, прежде чем мы начнем возвращать любой из самих узлов, тогда как в предварительном поиске мы хотели бы сначала вернуть узлы, а затем продолжить рекурсию вниз по дереву. Определение <code>inorder</code> , <code>preorder</code> , и <code>postorder</code> метода на нашем дереве. Каждый из этих методов должен возвращать массив элементов, которые представляют обход дерева. Обязательно верните целые значения в каждом узле массива, а не сами узлы. Наконец, возвращаем значение <code>null</code> если дерево пусто. </section>

## Instructions
<section id="instructions">
</section>

## Tests
<section id='tests'>

```yml
tests:
  - text: Существует структура данных <code>BinarySearchTree</code> .
    testString: 'assert((function() { var test = false; if (typeof BinarySearchTree !== "undefined") { test = new BinarySearchTree() }; return (typeof test == "object")})(), "The <code>BinarySearchTree</code> data structure exists.");'
  - text: 'Двоичное дерево поиска имеет метод, называемый <code>inorder</code> .'
    testString: 'assert((function() { var test = false; if (typeof BinarySearchTree !== "undefined") { test = new BinarySearchTree() } else { return false; }; return (typeof test.inorder == "function")})(), "The binary search tree has a method called <code>inorder</code>.");'
  - text: 'Двоичное дерево поиска имеет метод, называемый <code>preorder</code> .'
    testString: 'assert((function() { var test = false; if (typeof BinarySearchTree !== "undefined") { test = new BinarySearchTree() } else { return false; }; return (typeof test.preorder == "function")})(), "The binary search tree has a method called <code>preorder</code>.");'
  - text: 'Двоичное дерево поиска имеет метод, называемый <code>postorder</code> .'
    testString: 'assert((function() { var test = false; if (typeof BinarySearchTree !== "undefined") { test = new BinarySearchTree() } else { return false; }; return (typeof test.postorder == "function")})(), "The binary search tree has a method called <code>postorder</code>.");'
  - text: 'Метод <code>inorder</code> возвращает массив значений узла, которые являются результатом обхода порядка.'
    testString: 'assert((function() { var test = false; if (typeof BinarySearchTree !== "undefined") { test = new BinarySearchTree() } else { return false; }; if (typeof test.inorder !== "function") { return false; }; test.add(7); test.add(1); test.add(9); test.add(0); test.add(3); test.add(8); test.add(10); test.add(2); test.add(5); test.add(4); test.add(6); return (test.inorder().join("") == "012345678910"); })(), "The <code>inorder</code> method returns an array of the node values that result from an inorder traversal.");'
  - text: 'Метод <code>preorder</code> возвращает массив значений узлов, которые являются результатом обхода предзаказов.'
    testString: 'assert((function() { var test = false; if (typeof BinarySearchTree !== "undefined") { test = new BinarySearchTree() } else { return false; }; if (typeof test.preorder !== "function") { return false; }; test.add(7); test.add(1); test.add(9); test.add(0); test.add(3); test.add(8); test.add(10); test.add(2); test.add(5); test.add(4); test.add(6); return (test.preorder().join("") == "710325469810"); })(), "The <code>preorder</code> method returns an array of the node values that result from a preorder traversal.");'
  - text: 'Метод <code>postorder</code> возвращает массив значений узлов, которые являются результатом обхода порядка после расписания.'
    testString: 'assert((function() { var test = false; if (typeof BinarySearchTree !== "undefined") { test = new BinarySearchTree() } else { return false; }; if (typeof test.postorder !== "function") { return false; }; test.add(7); test.add(1); test.add(9); test.add(0); test.add(3); test.add(8); test.add(10); test.add(2); test.add(5); test.add(4); test.add(6); return (test.postorder().join("") == "024653181097"); })(), "The <code>postorder</code> method returns an array of the node values that result from a postorder traversal.");'
  - text: Метод <code>inorder</code> возвращает <code>null</code> для пустого дерева.
    testString: 'assert((function() { var test = false; if (typeof BinarySearchTree !== "undefined") { test = new BinarySearchTree() } else { return false; }; if (typeof test.inorder !== "function") { return false; }; return (test.inorder() == null); })(), "The <code>inorder</code> method returns <code>null</code> for an empty tree.");'
  - text: Метод <code>preorder</code> возвращает <code>null</code> для пустого дерева.
    testString: 'assert((function() { var test = false; if (typeof BinarySearchTree !== "undefined") { test = new BinarySearchTree() } else { return false; }; if (typeof test.preorder !== "function") { return false; }; return (test.preorder() == null); })(), "The <code>preorder</code> method returns <code>null</code> for an empty tree.");'
  - text: Метод <code>postorder</code> возвращает значение <code>null</code> для пустого дерева.
    testString: 'assert((function() { var test = false; if (typeof BinarySearchTree !== "undefined") { test = new BinarySearchTree() } else { return false; }; if (typeof test.postorder !== "function") { return false; }; return (test.postorder() == null); })(), "The <code>postorder</code> method returns <code>null</code> for an empty tree.");'

```

</section>

## Challenge Seed
<section id='challengeSeed'>

<div id='js-seed'>

```js
var displayTree = (tree) => console.log(JSON.stringify(tree, null, 2));
function Node(value) {
    this.value = value;
    this.left = null;
    this.right = null;
}
function BinarySearchTree() {
    this.root = null;
    // change code below this line
    // change code above this line
}

```

</div>


### After Test
<div id='js-teardown'>

```js
console.info('after the test');
```

</div>

</section>

## Solution
<section id='solution'>

```js
// solution required
```
</section>
