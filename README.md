Для подключения к серверу внутренней сети в одну команду из локального рабочего места, используя внешний сервер bastion-host, необходимо использовать следующий метод:

ssh -i <путь к ключу> -t -A <пользователь>@<внешний IP сервера bastion-host> ssh <IP конечного сервера внутренней сети>

Например:

ssh -i ~/.ssh/appuser -t -A appuser@34.76.5.251 ssh 10.132.0.5

Предварительно нужно добавить приватный ключ в ssh агент авторизации командой:

ssh-add <путь к ключу>

Для подключения к серверу внутренней сети по алиасу из локального рабочего места, сначала нужно создать алиас:

alias <имя алиаса>="<команда>"

Например:

alias someinternalhost="ssh -i ~/.ssh/appuser -t -A appuser@34.76.5.251 ssh 10.132.0.5"

Подключение осуществляется посредством ввода имени алиаса:

someinternalhost
