A Todo simple application implemented by containerizing the three parts.
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

[4] - First time you have to generate MongoDB container
```bash
   $ docker run --name mongodb --network todo-net -d -v data:/data/db mongo
   $ docker stop mongodb
```

[5] - To start Todo second and other times
```bash
    $ cd ./230706-todo
    $ ./start
```
`The explanation:`
```bash
docker container start mongodb
docker run --network todo-net --rm --name uh-node-ip -d\
    -p 8000:8000 uh-todoapp-ip:mon1
docker run --name uh-react-todo -it --rm -p 3000:3000\
    -v $(pwd)/frontend/src:/app/src uh-frontend
```

[6] - To stop Todo
```bash
    $ cd ./230706-todo
    $ ./stop
```
`The explanation:`
```bash
echo "List of stopped containers:"
docker stop uh-react-todo
docker stop uh-node-ip
docker stop mongodb
echo "--------------------------------------------"
echo "Check of all available containers:"
docker ps -a
```

[7] - Launch a web-application Todo in developmen mode in a browser

# http://localhost:3000
