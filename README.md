# Raf Console Studio - Official Strapi Demo

Наш стэк:
Strapi 5, Next.js 14, Node v 20.14.0, npm, Yarn

## Начнём

# 🛠 Подготовка

## 1. Clone Raf Console Studio

Копируем в подготовленную папку наш код проекта удобным нам способом
- Мы запускаем бэкенд (Strapi) и фронтенд (Next.js) в разных командных строках, запускать их с одной - совсем другие действия

# Правильные переменные окружения для каждой части:

Strapi (example in `./strapi/.env.example`):
  - `STRAPI_ADMIN_CLIENT_URL=<url-of-nextjs>`
  - `STRAPI_ADMIN_CLIENT_PREVIEW_SECRET=<a-random-token>` <br />
    ***То есть, в директории /strapi мы копируем .env.example и вставляем в то же место, где он находится, только меняем название на .env***

- У нас создан `./strapi/.env` файл

Next.js (example in `./next/.env.sample`):
  - `NEXT_PUBLIC_API_URL=<url-of-strapi>` (mandatory)
  - `PREVIEW_SECRET=<the-same-random-token-as-for-strapi>`<br />
    ***То есть, в директории /next мы копируем .env.example и вставляем в то же место, где он находится, только меняем название на .env***

- У нас создан `./next/.env` файл

## 2. Запускаем Strapi CMS

Переходим в `./my-projects/Raf-Console-Studio/strapi` папку и запускаем следющую команду:

```
yarn && yarn build && yarn develop
```

- Всё, у нас запустился проект админ-панели) Но кончено же это произойдёт не моментально

## 3. Запускаем Next.js 14

Переходим в `./my-projects/Raf-Console-Studio/next` папку и запускаем следющую команду:

```
yarn && yarn build && yarn start
```

- Всё, у нас запустился проект админ-панели) Но кончено же это произойдёт не моментально

# Последующий ЛОКАЛЬНЫЙ запуск ранее задеплоенного проекта 

## Strapi

- Открываем директорию ./strapi/
- Прописываем команду:

```
yarn develop
```
- У нас запущен проект Strapi CMS

## Next.js

- Открываем директорию ./next/
- Прописываем команду:

```
yarn develop
```
- У нас запущен проект Next.js

## Разное, но нужное ✨

### Yarn

<br />

**yarn** Устанавливает указанные ранее библиотеки, без которых ничего не установится.<br />
**yarn build** Билдит проект, тут могут вылезать ошибки и это к лучшему, если нет никаких ошибок, то версия нормальная и рабочая.<br />
**yarn start** Запускает проект, но не надо забывать, что если мы заранее не сбилдили проект, то будет версия последнего билда.<br />
**yarn develop** Запускает проект в режими разработчика, в этом режими ЗАПРЕЩЕНО хостить проект в интернет, только запускать локально. В этом режиме всё будет работать и применяться моментально, без надобности **yarn build**.<br />

### Global

<br />

[Customizable API](https://strapi.io/features/customizable-api): Automatically build out the schema, models, controllers for your API from the editor. Get REST or GraphQL API out of the box without writing a single line of code.<br />
[Media Library](https://strapi.io/features/media-library): The media library allows you to store your images, videos and files in your Strapi admin panel with many ways to visualize and manage them.<br />
[Role-Based Access Control (RBAC)](https://strapi.io/features/custom-roles-and-permissions): Role-Based Access Control is a feature available in the Administration Panel settings that let your team members have access rights only to the information they need.<br />
[Internationalization (i18n)](https://strapi.io/features/internationalization): Internationalization (i18n) lets you create many content versions, also called locales, in different languages and for different countries.<br />
[Audit Logs](https://strapi.io/blog/reasons-and-best-practices-for-using-audit-logs-in-your-application)The Audit Logs section provides a searchable and filterable display of all activities performed by users of the Strapi application<br />
[Data transfer](https://strapi.io/blog/importing-exporting-and-transferring-data-with-the-strapi-cli) Streams your data from one Strapi instance to another Strapi instance.<br />
[Review Worfklows](https://docs.strapi.io/user-docs/settings/review-workflows) Create and manage any desired review stages for your content, enabling your team to collaborate in the content creation flow from draft to publication. <br />


## Resources

[Docs](https://docs.strapi.io) • [Demo](https://strapi.io/demo) • [Forum](https://forum.strapi.io/) • [Discord](https://discord.strapi.io) • [Youtube](https://www.youtube.com/c/Strapi/featured) • [Strapi Design System](https://design-system.strapi.io/) • [Marketplace](https://market.strapi.io/) • [Clou Free Trial](https://cloud.strapi.io) 


## Customization

- The Strapi application contains a custom population middleware in order to populate more data than what it is set by default. You can find it in the `./strapi/src/middlewares/deepPopulate.ts` file.

- The Strapi application contains a postinstall script that will regenerate an uuid for the project in order to get some anonymous usage information concerning this demo. You can disable it by removing the uuid inside the `./strapi/packages.json` file.

- The Strapi application contains a patch for the @strapi/admin package. It is only necessary for the hosted demos since we automatically create the Super Admin users for them when they request this demo on our website.
