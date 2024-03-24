# Template: c++ with vcpkg
Проект-шаблон на c++ с настроенным менеджером зависимостей.

## Синхронизация зависимостей
Из корневой папки проекта:
```bash
cmake build
```
**Синхронизация обязательна при любом изменении *cmake.toml***

> [!WARNING]  
> Обратите внимание на версию vcpkg в `cmake.toml`, возможно в данный момент времени она уже неактуальна и требует обновления. Следите за релизами [вот здесь](https://github.com/microsoft/vcpkg/releases).

## Сборка проекта
Находясь в папке `build`:
```bash
make
```
Скомпилированая программа будет находится в `build/app`

## Добавление зависимостей

Чтобы добавить библиотеку в проект, необходимо модифицировать `cmake.toml`:

1. Найти название библиотеки в [реестре vcpkg](https://vcpkg.io/en/packages)
2. Добавить в `vckpkg.packages` название библиотеки
3. Указать версию в `find-package` (либо `*` если любая версия подойдёт`)
4. Добавить имя зависимости в `target.app.link-libraries`


--------
Позаимствовано: https://github.com/build-cpp/vcpkg_template
