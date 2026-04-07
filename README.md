# 📦 FluxCD Home Cluster

Данный репозиторий содержит конфигурацию Kubernetes-кластера, управляемого через GitOps с использованием FluxCD.

## 🚀 Описание

Проект реализует подход GitOps, при котором состояние кластера полностью описано в Git-репозитории. FluxCD автоматически синхронизирует кластер с этим репозиторием.

---

## 🧱 Структура репозитория

```
.
├── apps/
│   ├── base/          # Базовые HelmRelease/Kustomize для приложений
│   ├── production/    # Патчи для production окружения
│   └── staging/       # Патчи для staging окружения
│
├── clusters/
│   ├── production/    # Конфигурация production кластера
│   └── staging/       # Конфигурация staging кластера (с bootstrap Flux)
│
├── infrastructure/
│   ├── dns/           # DNS сервер
│   ├── repositories/  # HelmRepository источники
│   └── monitoring/    # Мониторинг
│
└── README.md
```

## ⚙️ Используемые технологии

-   Kubernetes
-   FluxCD
-   Kustomize
-   Helm

## 🔄 Как это работает

1.  FluxCD установлен в кластер
2.  Подключён к Git-репозиторию
3.  Отслеживает изменения
4.  Автоматически применяет их

## 🛠 Установка FluxCD

```bash
curl -s https://fluxcd.io/install.sh \| sudo bash

flux --version

flux bootstrap github\
--owner=`<username>`{=html}\
--repository=fluxcd_home_cluster\
--branch=main\
--path=clusters/home\
--personal
```

## 🔐 Секреты

-   Kubernetes Secrets

## 📌 Преимущества

✔ Git как источник истины\
✔ История изменений\
✔ Автоматизация\
✔ Быстрый rollback

## 📚 Полезные команды

```bash
flux get all
flux get sources git
flux get kustomizations
```

## 🧠 Идея проекта

Home-lab Kubernetes кластер с GitOps управлением.

## 📎 Итог

Проект показывает, как организовать GitOps инфраструктуру с помощью FluxCD.

## 📝 Лицензия

MIT