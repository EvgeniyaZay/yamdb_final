# yamdb_final
С использованием Continuous Integration и Continuous Deployment.
При пуше в ветку main автоматически отрабатывают сценарии:
1. Автоматический запуск тестов,
2. Обновление образов на Docker Hub,
3. Автоматический деплой на боевой сервер,
4. Отправка сообщения в телеграмм-бот в случае успеха.

## Начало работы

1. Клонируйте репозиторий на локальную машину.
```
git clone <адрес репозитория>
```
2. Для работы с проектом локально - установите вирутальное окружение и восстановите зависимости.
```
python -m venv venv
pip install -r requirements.txt 
```

### Подготовка удаленного сервера для развертывания приложения

Для работы с проектом на удаленном сервере должен быть установлен Docker и docker-compose.
Эта команда скачает скрипт для установки докера:
```
curl -fsSL https://get.docker.com -o get-docker.sh
```
Эта команда запустит его:
```
sh get-docker.sh
```
Установка docker-compose:
```
apt install docker-compose
```
```angular2html
https://github.com/github/docs/actions/workflows/yamdb_workflow.yml/badge.svg

```
