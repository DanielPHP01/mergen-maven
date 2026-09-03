# Mergen SDK — Maven repository

Публичный maven-репозиторий Android SDK **Mergen** (сканирование ID-карт КР).
Аутентификация не требуется.

## Подключение

`settings.gradle.kts`:

```kotlin
dependencyResolutionManagement {
    repositories {
        maven {
            url = uri("https://danielphp01.github.io/mergen-maven/")
            content { includeGroup("com.mergen") }
        }
    }
}
```

`build.gradle`:

```groovy
implementation 'com.mergen:mergen-sdk:2.6.1'
```

`content { includeGroup("com.mergen") }` не обязателен, но избавляет Gradle от
лишних запросов к этому репозиторию за чужими артефактами.

## Версии

| Версия | Дата | Что нового |
|---|---|---|
| 2.6.1 | 2026-08-28 | `frontOcclusion` / `backOcclusion` в `VerifyResult` — причина отказа галерейного фото (палец/тень) |

Документация публичного API обеих платформ: см. сайт клиентской документации SDK.

## Зеркало

Те же артефакты публикуются в GitHub Packages
(`maven.pkg.github.com/DanielPHP01/MergenSDK-Android`), но тот реестр требует
classic PAT даже для публичных пакетов — этот репозиторий существует, чтобы
интеграторам не нужны были токены.
