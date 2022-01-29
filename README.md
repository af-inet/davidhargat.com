# development

```sh
ip_address=$(python -c 'import socket; print(socket.gethostbyname(socket.gethostname()))')
hugo server --bind="${ip_address}" --baseURL="http://${ip_address}" --port=8080
```