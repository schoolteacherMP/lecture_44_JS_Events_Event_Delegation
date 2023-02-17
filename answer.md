## Задача 1.   
###  Спрячьте сообщения с помощью делегирования  

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
