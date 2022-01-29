# development

```sh
ip_address=$(python -c 'import socket; print(socket.gethostbyname(socket.gethostname()))')
echo "http://${ip_address}:8080/"
hugo server --bind="0.0.0.0" --baseURL="http://${ip_address}" --port=8080
```

```sh
ip_address=127.0.0.1
hugo server --bind="${ip_address}" --baseURL="http://${ip_address}" --port=8080
```

```sh
ip_address=0.0.0.0
hugo server --bind="${ip_address}" --baseURL="http://${ip_address}" --port=8080
```