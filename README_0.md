# База чтоб не косячить
![id](https://images.universe.com/3ec98038-5c4f-4c14-9f38-3975ea9027af/-/progressive/yes/-/inline/yes/)
* суть в том что здесь пропишим что устанавливаем зачем и как

## Базовые пакеты которые устанавливаем 1 раз.
1. Установка node.js нужен чтоб потягивать зависимости быстро устанавливать пакеты
> Переходим на [сайт node.js](https://nodejs.org/en/) скачиваем актуальную версию
>  все базово устанавливаем, утановка долгая особенно в терминале
> * Все это делаеться для такой вещи как NPM. 
> NPM — это менеджер пакетов JavaScript, который:
> 1. помогает публиковать проекты на Node.js, распространяемые с открытым исходным кодом;
> 2. помогает взаимодействовать с сервером, браузером и онлайн-площадками при помощи командной строки;
> 3. помогает устанавливать, удалять и управлять пакетами, используемыми для запуска проекта;
> 4. мное другое в зависимости от задач.
2. Установка vue.js
> 1. Переходим на [сайт vue.js](https://ru.vuejs.org/v2/guide/installation.html) здесь прописаны все базовые способы запуска vue через CDN
> 2. Для установки [через CLI](https://cli.vuejs.org/ru/guide/installation.html) это установка для реального проекта и более простая и надежная
> * Нам нужно по очереди вводить команды в терминал
```
 npm install -g @vue/cli
# ИЛИ
 yarn global add @vue/cli
# так мы устанавливаем глобальный пакет vue cli иеперь появиться команда vue  чрез терминал
 vue 
# покажет все базовые команды
```
>> все это делаеться на уровне администратора есть щанс на блокировку со стороны системы
>> пути решения проблемы вбить на уровне админа в PowerShell следующую строку 
```
Set-ExecutionPolicy -ExecutionPolicy Bypass
```
>> или перед командой npm прописывать sudo тоже утановка и запуск от имени администратора
### С этого момента установка идет идет на уровне проекта и все потягиваеться именнок к проекту

## Создаем проект

команда через терминал  для базового vue 
```
 vue create (название проекта маленькими буквами или ставим точку если терминал в теле проекта).

vue create "project name"
vue create .
```
при вводе vue create .
```
Generate project in current directory? (Y/n)
Спрашивает хотим ли мы сгенерировать сдеся (вероятно да, хотя кто нас проказников знает)
```
---

## первая настройка 
после запуска -- vue create 
```
? Please pick a preset: (Use arrow keys) // какого присета надо
> Default ([Vue 2] babel, eslint) // дефолтный 2 версия
  Default (Vue 3) ([Vue 3] babel, eslint) // дефолтный 3 версия
  Manually select features // сам настраивай
```
> дальше выбираем настройки defalt 1, defalt 2, или собственые, если один раз настроил видимо лучше потом не трогать.

### Manually select features
1. В здесь ставим галочки в зависимости от необходимости:
```
? Check the features needed for your project: (Press <space> to select, <a> to toggle all, <i> to invert selection)
// выбирите функции которые нужны для проекта, жми пробел для выбора
>(*) Choose Vue version
 (*) Babel
 ( ) TypeScript
 ( ) Progressive Web App (PWA) Support
 ( ) Router
 ( ) Vuex
 ( ) CSS Pre-processors
 (*) Linter / Formatter
 ( ) Unit Testing
 ( ) E2E Testing
```
> Очень посредственно представляю что они делают
1. 1. Стартовый набор более чем: Choose Vue version, Babel, Linter / Formatter (можно отключить он задолбает ошибками);
1. 2. Добавляем из необходимого новичку по мнению автора: Router, Vuex,  CSS Pre-processors (может понадобиться вешь полезная).

2. Выбираем версию vue. Это окно может не появиться первым видимо это зависит от сборок и настроения разрабов.
```
? Choose a version of Vue.js that you want to start the project with 
  2.x
> 3.x
```
3. Подключаем history mode "Y" 
```
? Use history mode for router? (Requires proper server setup for index fallback in production) (Y/n) 
```
>(Опция при создании экземпляра маршрутизатора позволяет нам выбирать между различными режимами)
>> звучит почти как АБРА-КАДАБРА, притворимся что понятно.
4. Выберите препроцессор CSS, (with dart-sass) или (with node-sass) основной выбор: 2 больше подходит для понимания кода (субъективно)
```
? Pick a CSS pre-processor (PostCSS, Autoprefixer and CSS Modules are supported by default): 
  Sass/SCSS (with dart-sass)
> Sass/SCSS (with node-sass)
  Less
  Stylus
```
> SASS и SCSS это типа помошник стилизации кода CSS работающий на руби и добавляющий капельку мозгов к рутиному процессу
>> SCSS диалект SASS и по стилю чуть больше напоминает CSS, базовый SASS ближе к питону или руби
5. Выбор линтера, без понимания особо выбирать не приходиться лазеем по форумам и жмякаем рекомендованое
```
? Pick a linter / formatter config: 
  ESLint with error prevention only 
> ESLint + Airbnb config
  ESLint + Standard config
  ESLint + Prettier
```
>ESLint + Airbnb или ESLint + Prettier. жеребьевкой выиграл 1.
6. Выбор когда должен включаться линтер при сохранении или при комите, при сохранении показалось логичнее
```
? Pick additional lint features: (Press <space> to select, <a> to toggle all, <i> to invert selection)
>(*) Lint on save
 ( ) Lint and fix on commit
```
7. Где мы хотим хранить конфигурации в файле конфиг, или json. Оба устраивают выбираем 2
```
? Where do you prefer placing config for Babel, ESLint, etc.? (Use arrow keys)
> In dedicated config files 
  In package.json          
```
8. Последнее хотим ли сохранить настроки, пока нет но в будущем ДА. Нет потому что нет уверености в отсутсвии косяков
```
? Save this as a preset for future projects? (y/N)
```
### На этом заканчиваеться базовая подготовка проекта 

## Подтягиваем пакеты и зависимости
```
npm install
```

### Запускает то что прописано в разделе script файла package.json
```
npm run serve
```

### создает скрипт, который запускает ваше приложение - скажем, сервер.js
```
npm run build
```

### Для ознакомления и познания идем сюда [Vue](https://cli.vuejs.org/config/).
