# yamdb_final
С использованием Continuous Integration и Continuous Deployment.
При пуше в ветку main автоматически отрабатывают сценарии:
1. Автоматический запуск тестов,
2. Обновление образов на Docker Hub,
3. Автоматический деплой на боевой сервер,
4. Отправка сообщения в телеграмм-бот в случае успеха.

# Как запустить проект:
### Клонировать репозиторий и перейти в него в командной строке
```angular2html
git clone 
```
```angular2html
cd api_yamdb
```
### Создать и активировать виртуальное окружение:
```angular2html
python3 -m venv venv
```
```angular2html
source/bin/activate
```
### Установить зависимости из файла requiremens.txt:
```angular2html
python3 -m pip install --upgrade pip
```
```angular2html
pip install -r requirements.txt
```

### Подготовка удаленного сервера для развертывания приложения

Для работы с проектом на удаленном сервере должен быть установлен Docker и docker-compose.
Эта команда скачает скрипт для установки докера:
```
sudo apt install docker.io
sudo curl -L "https://github.com/docker/compose/releases/download/1.29.2/docker-compose-$(uname -s)-$(uname -m)" -o /usr/local/bin/docker-compose
sudo chmod +x /usr/local/bin/docker-compose
```
Проверьте корректность установки Docker-compose:
```
sudo  docker-compose --version
```

```angular2html
https://github.com/github/docs/actions/workflows/yamdb_workflow.yml/badge.svg
```
### После успешного деплоя:
Соберите статические файлы (статику):
```
docker-compose exec web python manage.py collectstatic --no-input
```
Примените миграции:
```
docker-compose exec web python manage.py makemigrations
docker-compose exec web python manage.py migrate --noinput
```
Создайте суперпользователя:
```
docker-compose exec web python manage.py createsuperuser

```

### Документация к API:
```angular2html
http://127.0.0.1:8000/redoc/
```
### Над проектом работали
- Дементьев Александр
- Зайцева Евгения
- Денисов Максим