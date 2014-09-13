Docker Registry Test
====================

Run Private Docker Registry
---------------------------

```shell
$ vagrant up
```

Check [http://localhost:5000/](http://localhost:5000/).

Push and Pull from Private Docker Registry
------------------------------------------

```shell
$ docker build -t sample/nginx sample
```

Tag with **Server Host and Port**.

```shell
$ docker tag sample/nginx localhost:5000/sample/nginx
```

Push!

```shell
$ docker push localhost:5000/sample/nginx
```

Check [http://localhost:5000/v1/repositories/sample/nginx/tags](http://localhost:5000/v1/repositories/sample/nginx/tags).

Delete and Pull!

```shell
$ docker rmi sample/nginx localhost:5000/sample/nginx
$ docker pull localhost:5000/sample/nginx
```

Good!
