A Todo sample application implemented by containerizing the three parts.
The backend is implemented using Mongo DBMS v6 and Node.js v18.
The frontend - with React.js v18.

[1] - To generate and start a container with MongoDB DBMS
```bash
    $ docker run --network todo-net --rm --name mongodb -d mongo
```

[2] - To containerize Node.js backend
```bash
    $ cd ./230706-todo/backend
    $ docker build -t uh-todoapp-ip:mon1 .
```

[3] - To containerize React.js v18 frontend
```bash
    $ cd ./230706-todo/frontend
    $ docker build -t uh-frontend:ls37 .

```

[4] - To start Todo
```bash
    $ cd ./230706-todo
    $ ./start37
```
`The explanation:`

docker run --network todo-net --rm --name mongodb -d mongo
docker run --network todo-net --rm --name uh-node-ip -d\
    -p 8000:8000 uh-todoapp-ip:mon1
docker run --rm -p 3000:3000 --name uh-frontend-todo\
    -it uh-frontend:ls37


[5] - To stop Todo
```bash
    $ cd ./230706-todo
    $ ./stop
```
`The explanation:`

echo "List of stopped containers:"
docker stop uh-frontend-todo
docker stop uh-node-ip
docker stop mongodb
echo "--------------------------------------------"
echo "Check of all available containers:"
docker ps -a