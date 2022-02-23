# База чтоб не косячить раздел 2.
![id](https://images.universe.com/3ec98038-5c4f-4c14-9f38-3975ea9027af/-/progressive/yes/-/inline/yes/)
* суть в том что здесь пропишим что и чем являеться поможет понимать процессы

## Переходим к созданию базового Vue проекта
> 1. В начале сделаем голый проект именно с целью тренировки закрепления навыков
> 2. Многое удаляеться с целью прописать руками и закрепить знания и материал

### Шаг 1. Подготовка.
подразумеваеться что базовая установка была проведена
1. Открываем терминал и создаем проект
```
vue create . 
# или
vue create name_projek (название с маленькой буквы это важно)
```
2. Проходим в настройки и выбираем только базовые вещи а именно
```
? Check the features needed for your project: (Press <space> to select, <a> to toggle all, <i> to invert selection)
>(*) Choose Vue version
 (*) Babel
 ( ) TypeScript
 ( ) Progressive Web App (PWA) Support
 ( ) Router
 ( ) Vuex
 ( ) CSS Pre-processors
 ( ) Linter / Formatter
 ( ) Unit Testing
 ( ) E2E Testing
```
линтер хорошая вешь и может помочь подсказками но чаще просто раздражает, а в базисных настройках он по умолчанию включен

3. Сохранять или не сохранять настройки не важно
4. проект создан запускаем его через терминал
```
npm run serve
```
Должна появиться ссылка на переход на локальный сервер где отразица базовая страница vue
> Возможна ошибка прав доступа решаеться:
>> 1. пути решения проблемы вбить на уровне админа в PowerShell следующую строку Set-ExecutionPolicy -ExecutionPolicy Bypass 
>> 2. перед командой npm прописывать sudo тоже утановка и запуск от имени администратора

### Шаг 2. Создание собственного проекта
1. Убираем из проекта лишее не трогаем паку node_modules с отсальными будем работать
2. В папке public оставляем фаил index.html осстальное удаляем открваем фаил и удаляем лишнее должно получиться
```html
<!DOCTYPE html>
<html lang="ru">
  <head>
    <meta charset="utf-8">
    <meta http-equiv="X-UA-Compatible" content="IE=edge">
    <meta name="viewport" content="width=device-width,initial-scale=1.0">
    <title>title</title>
  </head>
  <body>
    <div id="app"></div>
    <!-- здесь будет наш проект -->
  </body>
</html>
```
2. Переходим в папку scr оставляем только два файла App.vue и main.js
* 1. Открываем App.vue опять удаляем лишнее отавляем только
```js
<template>
  <div id="app">
  </div>
</template>

<script>


export default {
  name: 'App',
  components: {
  }
}
</script>
<style>
</style>
```
* 2. Открываем main.js удаляем лишнее отавляем только
```js
import Vue from 'vue'
import App from './App.vue'

Vue.config.productionTip = false

new Vue({
  render: h => h(App),
}).$mount('#app')
```
### Получаем голую площадку для работы и творчества интересует нас App.vue
Разбираем все что там есть по частям
```html
<template>
  <div id="app">
      <!--здесь будет все что мы хотим видеть на сайте-->
  </div>
</template>

<script>
//тут может быть js код в меру разумного

//это объект vue c которым мы работаем
export default {
  name: 'App',
}
</script>

<style>
    // здесь стили можно прописывать как простой css и подключать классами
</style>
```
* В разделе пропиваем желаемую нами html страницу и закидываем ее в тело блока div
```html
<div id="app">
      <h1>Привет Мир!!!</h1>
  </div>
```
стоит поэксперементировать и попробовать запускаем через терминал
```
npm run serve
```


### На этом заканчиваеться базовое знакомство с Vue

### Для ознакомления и познания идем сюда [Vue](https://cli.vuejs.org/config/).
