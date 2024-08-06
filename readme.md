### Интерфейс командной строки для торрент-клиента

Настало время для того, чтобы дать нашему торрент-клиенту пользовательский интерфейс.
Одним из распространенных типов интерфейсов является CLI -- Command Line Interface.
Программы, взаимодействующие с пользователем через CLI, запускаются из shell'а (командной строки).
Удобство CLI заключается в возможности вызова программы из скриптов, из других программ или из терминала при подключении к удаленному серверу.

В данном задании требуется, воспользовавшись тем кодом, который был написан в предыдущих заданиях, написать cmake-проект `torrent-client-prototype` и положить его в соответствующей директории.
Вы можете редактировать и размещать любые файлы в директории `torrent-client-prototype`.
Использовать можно только свой код.
Запрещается использовать готовые реализации торрент-клиентов, либо библиотек для работы с торрент-файлами.
Важно, чтобы ваш проект собирался с помощью команды, размещенной в файле `Makefile` в корневой директории текущего задания.

Собранная по вашему проекту программа должна запускаться так:
`./torrent-client-prototype -d <путь к директории для сохранения скачанного файла> -p <сколько процентов от файла надо скачать> <путь к torrent-файлу>`

Параметр `-p` нужен для того, чтобы не скачивать большой файл в тестовой системе, а загрузить лишь первые несколько процентов от всего количества частей файла, начиная с первой части.
Например, если программа была вызвана так:
`./torrent-client-prototype -p /tmp/downloads/super_papka -p 5 resources/cool_file.torrent`,
и, допустим, что скаичваемый файл разбит на 1432 части, то программе нужно будет скачать всего 71 часть, с нулевой по 70 включительно.