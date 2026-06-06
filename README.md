# Лабораторная работа 6

[![CI](https://github.com/justtavinay-coder/lab06/actions/workflows/cicd.yml/badge.svg)](https://github.com/justtavinay-coder/lab06/actions/workflows/cicd.yml)

Данная лабораторная работа посвящена изучению средств пакетирования на примере CPack.

## Задание

Настроить сборку пакетов для приложения `solver`.

Каждый релиз содержит:

- архивы с исходным кодом;
- пакеты с бинарным файлом `solver`.

## Build

```sh
cmake -S . -B _build
cmake --build _build
```

## Package

```sh
cmake -S . -B _build -DCPACK_GENERATOR="TGZ;ZIP;DEB;RPM"
cmake --build _build --target package
```

## CI

GitHub Actions собирает проект и пакеты. Если commit помечен тегом `v*`, workflow создает GitHub Release и загружает собранные пакеты.
