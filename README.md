# Генерация Go-кода из Proto

Как использовать:

```task generate```
или сокращённо
```task gen```

Требуемые плагины Go для protoc:
go install google.golang.org/protobuf/cmd/protoc-gen-go@latest
go install google.golang.org/grpc/cmd/protoc-gen-go-grpc@latest

Принцип работы:
Берёт proto/sso/sso.proto
Генерирует Go-код в gen/go/
Создаёт обычные структуры и gRPC-клиент/сервер

Совет:
После изменения .proto файлов всегда запускайте task gen.
