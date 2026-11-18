## MongoDB (NoSQL)

> **Это задание лучше выполнять в WSL или в другом полноценном Linux!**

Выполните все этапы работы с проектом по примеру с [Nginx](/content/Docker/ImageLibrary/Nginx.md)

- > Никогда в разработке не используйте русские имена файлов и каталогов!
- > Никогда в разработке не используйте пробелы и спец.символы в именах файлов и каталогов!
- > Перед созданием проекта убедитесь, что порт 8084 не занят другим приложением!
- > Создание проекта лучше начать с "чистого листа", предварительно остановив и удалив все другие контейнеры и образы!

1. Запуск **MongoDB**

в **Windows Powershell**
```shell
docker run -d `
  --name my-mongo `
  -p 27017:27017 `
  mongo:latest
```

![alt text](/Dockers/img/MongoDB%201.png)

> Если эта команда в Powershell не работает, то удалите из кода апострофы `

в **Git-Bash/Linux/WSL 2.0/Mac**
```shell
docker run -d \
  --name my-mongo \
  -p 27017:27017 \
  mongo:latest
```

![alt text](/Dockers/img/MongoDB%202.png)

2. Подключиться через shell
```shell
docker exec -it my-mongo mongosh
```

![alt text](/Dockers/img/MongoDB%203.png)

Повыполняйте какие-нибудь команды в этой БД для проверки и пришлите скрины

Посмотреть базы данных
```shell
show dbs
```

![alt text](/Dockers/img/MongoDB%204.png)

Создать/переключиться на базу
```shell
use myapp
```

![alt text](/Dockers/img/MongoDB%205.png)

Создать коллекцию и вставить документ
```shell
db.users.insertOne({ name: "Иван", age: 30, city: "Москва" })
```

![alt text](/Dockers/img/MongoDB%206.png)

Найти документы
```shell
db.users.find()
```

![alt text](/Dockers/img/MongoDB%207.png)

Найти с фильтром
```shell
db.users.find({ age: { $gt: 25 } })
```

![alt text](/Dockers/img/MongoDB%208.png)

Обновить документ
```shell
db.users.updateOne({ name: "Иван" }, { $set: { age: 31 } })
```

![alt text](/Dockers/img/MongoDB%209.png)

Удалить документ
```shell
db.users.deleteOne({ name: "Иван" })
```

![alt text](/Dockers/img/MongoDB%2010.png)

Посмотреть коллекции
```shell
show collections
```

![alt text](/Dockers/img/MongoDB%2011.png)

Выйти
```shell
exit
```

![alt text](/Dockers/img/MongoDB%2012.png)

> Если вы обнаружили ошибку в этом тексте - сообщите пожалуйста автору!