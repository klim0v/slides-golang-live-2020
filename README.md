# slides-golang-live-2020

[Сергей Климов на Golang Live 2020](https://golangconf.ru/2020/abstracts/6761)

Все мы сталкивались с теми трудностями, которые возникают при интеграции своего API с другими сервисами. Конечно же, документирование призвано решить эту проблему. Поэтому мы рассмотрим такие средства, как OpenAPI и Swagger.

Но как быть, если у нас достаточное количество интерфейсов, для того чтобы на их описание выделить целый день, а то и больше. И при малейшем их изменении нужно потратить время, чтобы синхронизировать их с документацией и не забыть вообще это сделать!!!

Тут нас спасает автогенерация. Она позволяет нам держать все в одном месте и не тратить уйму времени на обновления. Существует 2 подхода при написании документированных API:
1. разработка по спецификации,
2. генерация спецификации по нашему коду.

Пришло время рассмотреть, какой из подходов лучше всего выбрать именно вам и какие инструменты позволяют нам генерировать готовый веб-сервер на языке Golang из спецификации OpenAPI и генерировать спецификацию из аннотаций в нашем коде. Для этого разберем такие инструменты как:
• swagger-api/swagger-codegen,
• go-swagger/go-swagger,
• swaggo/swag,
• grpc-ecosystem/grpc-gateway.

Более детально рассмотрим grpc-gateway. Он позволит нам генерировать интерфейсы gRPC, RESTful JSON API, WebSocket и OpenAPI из одного .proto-файла.

Сначала создадим gRPC-интерфейс, поэтому рассмотрим основные моменты его описания, плюсы и минусы его использования и как их поддерживать. А после сгенерируем обратный прокси-сервер к нему, который будет переводить RESTful JSON API и WebSocket в gRPC и обратно. Поговорим о плюсах и минусах этого решения, в каких ситуациях стоит использовать, а в каких нет.
