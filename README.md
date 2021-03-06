# Тестовое задание

## Задача № I.1
Каждый, говорящий правду, дает 1 утвердительный ответ и 2 отрицательных.  
Каждый, говорящий ложь, дает 2 утвердительных ответа и 1 отрицательный.  
Исходя из этого будем иметь 90 утвердительных ответов (т.к. каждый человек дает, как минимум один утвердительный ответ, плюс ещё некоторое количество (Х) утвердительных ответов от "лжецов".  
Согласно условиям, имеем 110 утвердительных ответ (45 + 35 + 30), следовательно:  
Х = 110 - 90 = 20.  

Как говорилось выше, каждый "лжец" дает 2 утвердительных ответа, значит 20 * 2 = 40 - утвердительных ответов дали "лжецы".  
110 - 40 = 70 - человек говорят правду.
> Время выполнения ~ 7 минут

## Задача № I.2

A B C  
D E F  
G H K  

A * B * C = _x_  
A * D * G = _x_  
Из этих двух выражений можно получить: B * C = D * G  

B * E * H = _y_  
D * E * F = _y_
Из этих двух выражений можно получить: B * H =  D * F

C * F * K = _z_  
G * H * K = _z_  
Из этих двух выражений можно получить: C * F = G * H  

Т.е. из чисел 3, 4, ... 11 нужно найти пары неповторяющихся чисел, произведения которых равны. Методом подбора получаем:  
3 * 8 = 6 * 4  
3 * 10 = 5 * 6  
4 * 10 = 5 * 8  

Таким образом числа 7, 9, 11 могут находиться на любой из позиций A, E, K.  
Далее, опять подбором была получена таблица:  
A 8 3  
4 E 10  
6 5 K  

С учетом ранее полученных выводов, получим один из вариантов ответа:  
7 8 3  
4 9 10   
6 5 11
> Время выполнения ~ 20 минут

## Задача № I.3
Если достоверно известно, что с 5000м предмет точно разбивается и не надо проверять эту границу, то решени следующее.  
1. Фиксируем начальные границы тестируемого отрезка (0 и 5000м)
2. Вычисляем середину тестируемого отрезка - высота для сбрасывания предмета (изначально она равна 2500м, далее при получении дробного значения округляем его до меньшего значения)
3. Первый предмет сбрасываем с высоты полученной на шаге 2.
4. Если предмет разбился, то
5. |  Берем второй предмет и начинаем сбрасывать его с нижней границы текущего отрезка с шагом 1м  
   |  до тех пор,пока второй предмет не разобьется
6. |  Если при очередном сбрасывании второй предмет разбился, то считаем высоту прошлого сбрасывания результатом
7. Иначе
8. |  Изменяем тестируемый отрезок (высоту, с которой сбросили предмет на шаге 2,  
   |  принимаем за нижнюю границу отрезка, верхняя граница остается неизменной)
9. |  Переходим на шаг 2
> Время выполнения ~ 10 минут

<hr />

## Задача № II.1
```javascript
function joinCities(arr) {
  return `${arr.join(',')}.`;
}

function joinCitiesAlt(arr) {
  let result = arr[0];
  for (let i = 1; i < arr.length; i++) {
    result += `,${arr[i]}`;
  }
  return `${result}.`
}
```
> Время выполнения ~ 3 минут

## Задача № II.2
```javascript
function round(number) {
  return Math.round(number / 5) * 5;
}
```
> Время выполнения ~ 3 минут

## Задача № II.3
```javascript
function getGenitive(count) {
  let result = `${count} компьютеров`;
  if (count % 100 < 5 || count % 100 > 20) {
    if (count % 10 === 1) {
      result = `${count} компьютер`;
    }
    if (count % 10 > 1 && count % 10 < 5) {
      result = `${count} компьютера`;
    }
  }
  return result;
}
```
> Время выполнения ~ 8 минут

## Задача № II.4
```javascript
function isSimple(number) {
  for (let i = 2; i < number; i++) {
    if (number % i === 0) {
      return `Число ${number} - составное`;
    }
  }
  return `Число ${number} - простое`;
}
```
> Время выполнения ~ 5 минут

## Задача № II.4
```javascript
function doubleHelper(arr) {
  const objFromArr = {};
  for (let i = 0; i < arr.length; i++) {
    if (objFromArr[arr[i]]) {
      objFromArr[arr[i]] += 1;
    } else {
      objFromArr[arr[i]] = 1;
    }
  }
  return Object.entries(objFromArr).filter(item => item[1] > 1).map(item => +item[0]);
}

function doubles(arr1, arr2) {
  const boudlesArr1 = doubleHelper(arr1);
  const boudlesArr2 = doubleHelper(arr2);
  const result = boudlesArr1.filter(item => boudlesArr2.includes(item));
  return result;
}
```
> Время выполнения ~ 11 минут