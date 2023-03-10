Устанавливаем docker

apt install docker.io

Для установки docker compose скачиваем бинарный файлик и кладем его в /usr/local/bin

curl -L "https://github.com/docker/compose/releases/download/1.29.2/docker-compose-$(uname -s)-$(uname -m)" -o /usr/local/bin/docker-compose

Даем права на выполнение бинарного файла

chmod +x /usr/local/bin/docker-compose

Клонируем репозиторий заббикс-докера

git clone https://github.com/rtssv/grafana_node_exporter.git

Переходим в каталог репозитория

cd grafana_node_exporter/

Меняем имя сервера (ищем name_for_server) на нужное в файлах docker-compose.yml и prometheus/prometheus.yml

Также нужно указать данные для телеграма (bot_token и chat_id) в файле alertmanager/config.yml

Запускаем compose 

docker-compose up -d

Ждем пару минут и проверяем статус контейнеров 

docker ps

Если контейнеры запущены, то переходим в браузер по внешнему IP виртуалки по порту 3000. Логин и пароль admin. После первого входа попросят сменить.

Добавляем dashboard:

В левом боковом меню Dashboards -> Import. Указываем ID 1860 и нажимаем load (которая справа). Далее внизу указываем Prometheus. После создания dashboard нужно нажать на кнопку save (наверху вторая кнопка слева).

Также нужно добавить Dashboards с ID 193.
