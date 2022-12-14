# Демо-приложение Мессенджера (инструкция для внешних потребителей)

В рамках данного демо-приложения показано, как можно подключить Мессенджер в свое приложение.

## Структура приложения

### messenger_demo_ext - модуль приложения

В нем фактически подключается мессенджер.

### repo - локальный maven-репозиторий с SDK Мессенджера

Можно переложить содержимое в свой внутренний maven, либо положить и подключить папку прямо в свой проект.
Пример локального подключения реализован в демо-приложении, см. build.gradle в корне.
Рекомендуется подключать артефакты именно через maven-репозиторий, т.к. это позволяет транзитивно подтянуть необходимые внешние зависимости. Если вы будете подключать AAR-файлы напрямую, то вам придется явно прописать с десяток внешних зависимостей, которые могут еще и меняться от версии к версии.

### Сборка демо-приложения

1. В коде messenger_demo_ext/build.gradle прописана версия артефактов 1.0.0.9999 - это сделано для внутренних нужд команды, и ее нужно заменить на ту, что предоставляется в архиве.
2. Для сборки проекта нужны репозитории mavenCentral и google.
3. Демо-приложение использует Kotlin DSL для сборочных скриптов, но в своем приложении вы можете использовать и Groovy DSL аналогичным образом.
4. Про все остальные опции в комментариях явно указано - обязательно ли это, или остается на усмотрение потребителя.
