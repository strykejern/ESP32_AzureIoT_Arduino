project(esp32-azure)

add_library(${PROJECT_NAME} STATIC)

target_sources(${PROJECT_NAME} PRIVATE
        src/az_iot/azureiotcerts.c
        src/az_iot/c-utility/pal/agenttime.c
        src/az_iot/c-utility/pal/dns_async.c
        src/az_iot/c-utility/pal/freertos/lock.c
        src/az_iot/c-utility/pal/freertos/threadapi.c
        src/az_iot/c-utility/pal/freertos/tickcounter.c
        src/az_iot/c-utility/pal/lwip/sntp_lwip.c
        src/az_iot/c-utility/pal/socket_async.c
        src/az_iot/c-utility/pal/src/platform_openssl_compact.c
        src/az_iot/c-utility/pal/src/tlsio_openssl_compact.c
        src/az_iot/c-utility/pal/tlsio_options.c
        src/az_iot/c-utility/src/base64.c
        src/az_iot/c-utility/src/buffer.c
        src/az_iot/c-utility/src/connection_string_parser.c
        src/az_iot/c-utility/src/consolelogger.c
        src/az_iot/c-utility/src/constbuffer.c
        src/az_iot/c-utility/src/constmap.c
        src/az_iot/c-utility/src/crt_abstractions.c
        src/az_iot/c-utility/src/doublylinkedlist.c
        src/az_iot/c-utility/src/gballoc.c
        src/az_iot/c-utility/src/gb_stdio.c
        src/az_iot/c-utility/src/gb_time.c
        src/az_iot/c-utility/src/hmac.c
        src/az_iot/c-utility/src/hmacsha256.c
        src/az_iot/c-utility/src/httpapiex.c
        src/az_iot/c-utility/src/httpapiexsas.c
        src/az_iot/c-utility/src/httpheaders.c
        src/az_iot/c-utility/src/http_proxy_io.c
        src/az_iot/c-utility/src/map.c
        src/az_iot/c-utility/src/optionhandler.c
        src/az_iot/c-utility/src/sastoken.c
        src/az_iot/c-utility/src/sha1.c
        src/az_iot/c-utility/src/sha224.c
        src/az_iot/c-utility/src/sha384-512.c
        src/az_iot/c-utility/src/singlylinkedlist.c
        src/az_iot/c-utility/src/strings.c
        src/az_iot/c-utility/src/string_tokenizer.c
        src/az_iot/c-utility/src/urlencode.c
        src/az_iot/c-utility/src/usha.c
        src/az_iot/c-utility/src/vector.c
        src/az_iot/c-utility/src/xio.c
        src/az_iot/c-utility/src/xlogging.c
        src/az_iot/iothub_client/src/blob.c
        src/az_iot/iothub_client/src/iothub_client_authorization.c
        src/az_iot/iothub_client/src/iothub_client.c
        src/az_iot/iothub_client/src/iothub_client_ll.c
        src/az_iot/iothub_client/src/iothub_client_retry_control.c
        src/az_iot/iothub_client/src/iothub_message.c
        src/az_iot/iothub_client/src/iothubtransport.c
        src/az_iot/iothub_client/src/iothubtransportmqtt.c
        src/az_iot/iothub_client/src/iothubtransport_mqtt_common.c
        src/az_iot/iothub_client/src/version.c
        src/az_iot/umqtt/src/mqtt_client.c
        src/az_iot/umqtt/src/mqtt_codec.c
        src/az_iot/umqtt/src/mqtt_message.c
        src/AzureIotHub.cpp
        src/Esp32MQTTClient.cpp
        )

target_include_directories(${PROJECT_NAME} PUBLIC
        src
        )

target_link_libraries(${PROJECT_NAME} PRIVATE
        arduino-variant
        esp32-sdk
        )