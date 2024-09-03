# Urban_09

Практическая работа по модулю "Некоторые интересные и (крайне) полезные инструменты"

Часть 1: ESLint

1. Инициализируйте новый проект npm: npm init -y
2. Установите ESLint: npm install eslint --save-dev
3. Инициализируйте конфигурацию ESLint: npm init @eslint/config@latest
4. Проверка кода с помощью ESLint: npx eslint index.js

Часть 2: Prettier

1. Установите Prettier: npm install --save-dev prettier
2. Создайте файл .prettierrc с базовой конфигурацией:
   {
   "singleQuote": true,
   "semi": true
   }
3. Установите необходимые пакеты: npm install --save-dev eslint-config-prettier eslint-plugin-prettier
4. Обновите ваш .eslintrc для использования Prettier:
   {
   "extends": [
   "eslint:recommended",
   "plugin:prettier/recommended"
   ]
   }
5. Запустите Prettier для форматирования кода: npx prettier --write index.js

Часть 3: Lighthouse

1. Установите Lighthouse глобально: npm install -g lighthouse
2. Запустите локальный сервер: npx http-server
3. Запустите Lighthouse для анализа локального сервера: lighthouse http://127.0.0.1:8080 --output html --output-path ./report.html

Часть 4: Sentry

1. Добавить в index.html:
<script src="https://js-de.sentry-cdn.com/de6f0a294e741e3f17333f61f1c63366.min.js" crossorigin="anonymous"></script>
2. Добавить скрип конфигурации Sentry index.html:
   <script>
   Sentry.onLoad(function () {
   Sentry.init({
   // Tracing
   tracesSampleRate: 1.0,
   // Session Replay
   replaysSessionSampleRate: 0.1,
   replaysOnErrorSampleRate: 1.0,
   });
   });
   </script>
3. Создайте намеренную ошибку в вашем коде. Ошибка создана в файле index.js -> myUndefinedFunction is not defined.
