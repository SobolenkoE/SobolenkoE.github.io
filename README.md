# Публичный сайт ToDeskAI

Статический сайт продукта и документы для пользователей. Планируемый адрес:
<https://sobolenkoe.github.io/>. Отдельный репозиторий:
`SobolenkoE/SobolenkoE.github.io`.

## Состав

- `index.html` — продукт, загрузка, размещение данных и контакты;
- `privacy/index.html` — конфиденциальность, почтовый OAuth, ИИ и журналы;
- `terms/index.html` — условия использования;
- `assets/style.css`, `assets/icon.png` — стили и публичная иконка приложения;
- `.nojekyll`, `robots.txt`, `sitemap.xml` — статическая публикация и индексация.

Сайт не содержит JavaScript, сборщика, зависимостей, аналитики, форм, cookies
или внешних шрифтов. Шрифты системные. Политики описывают отдельные границы
обработки сайта, приложения, настроенного сервера и поставщиков ИИ.

## Локальный просмотр

Из корня этого репозитория:

```sh
python3 -m http.server 8080 --bind 127.0.0.1
```

Открыть <http://127.0.0.1:8080/>, `/privacy/` и `/terms/`. Проверить ширины
320, 768, 1024 и 1440 px, клавиатурную навигацию, skip link, переходы по
якорям и отсутствие горизонтального скролла. Все внутренние ссылки идут от
корня: сайт рассчитан на пользовательский GitHub Pages, а не подпапку проекта.

## Публикация на GitHub Pages

1. Создать публичный репозиторий `SobolenkoE/SobolenkoE.github.io` и поместить
   эти файлы в ветку `main`. Не добавлять `.env`, OAuth-реквизиты, токены,
   приватные исходники или рабочие данные.
2. В **Settings → Pages → Build and deployment** выбрать **Deploy from a
   branch**, ветку `main` и каталог `/(root)`; сохранить настройки.
3. Дождаться завершения Pages deployment и проверить HTTPS-адреса главной,
   политики и условий. Значок `.nojekyll` отключает обработку Jekyll.
4. Проверить ссылку на последний релиз. Сейчас доступны Windows и Linux;
   наличие сборки macOS не обещается без опубликованного артефакта.

Считать сайт опубликованным после успешного Pages deployment и проверки
этих адресов по HTTPS. Локальная готовность файлов не означает публикацию.

## Google OAuth Branding и подтверждение сайта

В Google Auth Platform → **Branding** использовать:

| Поле | Адрес |
| --- | --- |
| Application home page | `https://sobolenkoe.github.io/` |
| Privacy policy | `https://sobolenkoe.github.io/privacy/` |
| Terms of service | `https://sobolenkoe.github.io/terms/` |

Контакт проекта: `sobolenkoy@gmail.com`. Название продукта: `ToDeskAI`.
Сайт не утверждает, что Google уже проверил приложение.

GitHub Pages предоставляет хостинг, но публикация на `sobolenkoe.github.io`
не закрывает подтверждение домена для Google OAuth. На дату документа
[инструкция Google](https://support.google.com/cloud/answer/13804266?hl=en)
требует **Domain Property** в Search Console с DNS-подтверждением. Проверка
URL-prefix через HTML-файл или метатег для этого недостаточна. У владельца
сайта нет управления DNS домена `github.io`.

Для подтверждения домена потребуется:

1. Приобрести собственный домен и получить доступ к его DNS.
2. Подключить его к GitHub Pages по
   [инструкции GitHub](https://docs.github.com/en/pages/configuring-a-custom-domain-for-your-github-pages-site).
3. Под аккаунтом владельца Google Cloud проекта добавить **Domain Property**
   в [Search Console](https://search.google.com/search-console/), разместить
   выданную Google TXT-запись в DNS и пройти проверку.
4. После запуска HTTPS обновить canonical-адреса, sitemap, ссылки Branding
   и список разрешённых доменов в Google Auth Platform.

До появления собственного домена не добавлять `CNAME`, выдуманные TXT-токены
или метатеги подтверждения. Не указывать чужой `github.io` как собственный
домен. Сайт на Pages можно использовать для информации о продукте, но
подтверждение домена и одобрение OAuth остаются отдельными незавершёнными шагами.

Для Gmail область `https://mail.google.com/` требует отдельной проверки
запрашиваемого доступа при публичном распространении. До этого использовать
тестовую аудиторию OAuth-проекта и проверять ограничения в Google Console.

## Поддержка содержания

Дата текущих политик: **12.11.2026**. При изменении обработки данных обновить
текст, дату и `lastmod` в sitemap. Проверять соответствие аудита агента,
хранения токенов, ИИ-интеграций и настроек развёртывания реальному приложению.
Заявление Limited Use — обязательство проекта, а не знак сертификации Google.

Официальные материалы:

- [Создание пользовательского сайта GitHub Pages](https://docs.github.com/en/pages/getting-started-with-github-pages/creating-a-github-pages-site);
- [Требования к подтверждению домена Google OAuth](https://support.google.com/cloud/answer/13804266?hl=en);
- [Google OAuth: проверка бренда](https://developers.google.com/identity/protocols/oauth2/production-readiness/brand-verification);
- [Google API Services User Data Policy](https://developers.google.com/terms/api-services-user-data-policy).
