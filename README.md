Генерация Go-кода из Proto

В проекте используется Protocol Buffers и gRPC. Для генерации Go-кода есть задача Taskfile generate (alias gen).

Как использовать
task generate
# или сокращённо
task gen

Требуется:

Установленные плагины Go для protoc:

go install google.golang.org/protobuf/cmd/protoc-gen-go@latest
go install google.golang.org/grpc/cmd/protoc-gen-go-grpc@latest
Что делает задача
tasks:
  generate:
    aliases:
      - gen
    desc: "Generate code from proto files"
    cmds:
      - protoc -I proto proto/sso/sso.proto \
        --go_out=./gen/go --go_opt=paths=source_relative \
        --go-grpc_out=./gen/go/ --go-grpc_opt=paths=source_relative
Берёт proto/sso/sso.proto
Генерирует Go-код в gen/go/
Создаёт обычные структуры и gRPC-клиент/сервер
Совет

После изменения .proto файлов всегда запускайте task gen.
