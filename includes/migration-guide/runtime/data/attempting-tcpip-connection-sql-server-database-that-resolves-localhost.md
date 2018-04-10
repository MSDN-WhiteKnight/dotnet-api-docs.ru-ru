### <a name="attempting-a-tcpip-connection-to-a-sql-server-database-that-resolves-to-localhost-fails"></a>Попытка базы данных SQL Server, которая разрешает подключение по протоколу TCP/IP `localhost` завершается ошибкой

|   |   |
|---|---|
|Подробные сведения|В .NET Framework 4.6 и 4.6.1, попытка базы данных SQL Server, которая разрешает подключение по протоколу TCP/IP <code>localhost</code> завершается с ошибкой, &quot;при установлении соединения с SQL Server произошла ошибка на связанные с сетью или с определенным экземпляром. Сервер не найден или недоступен. Проверьте правильность имени экземпляра и настройку сервера SQL Server для удаленных подключений. (поставщик: сетевые интерфейсы SQL, ошибка: 26: ошибка поиске указанного сервера/экземпляра)&quot;|
|Предложение|Эта проблема будет устранена, и восстановить прежнее поведение в .NET Framework 4.6.2. Для подключения к databsae SQL Server, которая разрешает <code>localhost</code>, выполните обновление до .NET Framework 4.6.2.|
|Область|Дополнительный номер|
|Версия|4.6|
|Тип|Среда выполнения|
