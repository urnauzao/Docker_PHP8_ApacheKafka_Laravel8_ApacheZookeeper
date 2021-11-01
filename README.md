# Dependências do Sistema Operacional/PHP
- @CentOS
> RUN apt install librdkafka-dev -y && pecl install rdkafka 

- Habilitar/adicionar extensão no php.ini: <br>
extension=rdkafka.so
    
# Dependências em Prod do Composer
"ext-rdkafka": "^5.0|^4.0",
"flix-tech/avro-serde-php": "^1.7",
"flix-tech/confluent-schema-registry-api": "^7.5"

# Pacote Laravel-kafka do Composer
"mateusjunges/laravel-kafka": "^1.1"

# Publicando config do pacote
php artisan vendor:publish --tag=laravel-kafka-config

# Variaveis de ambiente 
KAFKA_BROKERS=localhost:9092
KAFKA_CONSUMER_GROUP_ID=group
KAFKA_OFFSET_RESET=latest
KAFKA_AUTO_COMMIT=true
KAFKA_ERROR_SLEEP=5
KAFKA_PARTITION=0
KAFKA_COMPRESSION_TYPE=snappy
KAFKA_DEBUG=false

# Material de Apoio
* [Laravel Kafka Package](https://laravel-news.com/laravel-kafka-package)
* [Git Laravel Kafka Package](https://github.dev/mateusjunges/laravel-kafka)
* [Git Orinal Lib Kafka](https://github.com/edenhill/librdkafka)
* [Docker Image Kafka](https://hub.docker.com/r/bitnami/kafka/)
* [Docker Image Zookeeper](https://hub.docker.com/r/bitnami/zookeeper)
* [Comparação Kafka vs RabbitMQ](https://gago.io/blog/kafka-vs-rabbitmq/)
* [Vídeo Tudo Sobre Kafka](https://www.youtube.com/watch?v=M4mHkuQ0mqQ)
* [Exemplo Docker + Kafka](https://github.com/confluentinc/cp-docker-images/tree/5.3.3-post/examples)
* [Git Avro Serialization](https://github.com/flix-tech/avro-serde-php)
* [Doc Rdkafka Extension PHP](https://arnaud.le-blanc.net/php-rdkafka-doc/phpdoc/)
* [Dependência PHP/PECL Kafka](https://pecl.php.net/package/rdkafka)

