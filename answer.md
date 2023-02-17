## Задача 1.   
###  Спрячьте сообщения с помощью делегирования  
**[код решения ](https://plnkr.co/edit/Y0qmbddm3XQ2iihq?p=preview&preview)**  
// Получаем элемент-контейнер  
`const container = document.getElementById('container');`  

// Добавляем обработчик событий на элемент-контейнер  
`container.addEventListener('click', function(event) {`  
  // Проверяем, что кликнули на кнопку удаления  
 ` if (event.target.classList.contains('remove-button')) {`  
    // Находим родительский элемент кнопки (элемент .pane)  
  `  const messagePane = event.target.parentNode;`  
    // Удаляем элемент .pane из DOM  
 `   messagePane.parentNode.removeChild(messagePane);`  
`  }`  
`}); `  



## Задача 2.   
### Поведение "подсказка"  
**[код решения ](https://plnkr.co/edit/1d0ftJwckrJZho0P?p=preview&preview)**  
`const tooltip = document.createElement('div');`  
`tooltip.classList.add('tooltip');`  
`document.body.append(tooltip);`  

`let lastTarget = null;`  

`document.addEventListener('mouseover', event => {`  
 ` const target = event.target.closest('[data-tooltip]');`  
 ` if (!target) return;`  

  `const tooltipText = target.dataset.tooltip;`  
  `if (!tooltipText) return;`  

  `tooltip.innerHTML = tooltipText;`  
  `tooltip.style.left = target.getBoundingClientRect().left + 'px';`  
  `tooltip.style.top = target.getBoundingClientRect().bottom + 'px';`  
  `tooltip.style.display = 'block';`  

  `lastTarget = target;`  
`});`

`document.addEventListener('mouseout', event => {`  
 ` if (lastTarget) {`  
  `  tooltip.style.display = 'none';`  
   ` lastTarget = null;`  
  `}`  
`});`  
