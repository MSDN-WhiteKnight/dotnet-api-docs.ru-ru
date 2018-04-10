### <a name="sslstream-supports-tls-alerts"></a>SslStream поддерживает TLS оповещения

|   |   |
|---|---|
|Подробные сведения|После сбоя подтверждения TLS <xref:System.IO.IOException?displayProperty=name> внутренний <xref:System.ComponentModel.Win32Exception?displayProperty=name> первой операцией ввода -вывода чтения и записи будет создано исключение. <xref:System.ComponentModel.Win32Exception.NativeErrorCode?displayProperty=name> Кода для <xref:System.ComponentModel.Win32Exception?displayProperty=name> может быть сопоставлен TLS предупреждения от удаленной стороны с помощью этого [документации Schannel](https://msdn.microsoft.com/library/windows/desktop/dd721886%28v=vs.85%29.aspx). Дополнительные сведения см. в разделе [RFC 2246: сообщения об ошибках раздел 7.2.2](https://tools.ietf.org/html/rfc2246#section-7.2.2)поведение .NET 4.6.2 и ниже не, канал транспорта (обычно TCP-соединение) будет время ожидания во время записи или чтения, если другая сторона не удалось Подтверждение и сразу же после этого отклонил соединение.|
|Предложение|Приложения, вызывающие сетевых API-интерфейсов ввода-вывода, таких как <xref:System.IO.Stream.Read(System.Byte[],System.Int32,System.Int32)> / <xref:System.IO.Stream.Write(System.Byte[],System.Int32,System.Int32)> должен обрабатывать <xref:System.IO.IOException> или <xref:System.TimeoutException?displayProperty=name>. По умолчанию, начиная с .NET 4.7 включена функция оповещений TLS. Приложения, предназначенные для .NET 4.0 - .NET 4.6.2 под управлением .NET 4.7 или более поздней версии системы будет отключен для сохранения совместимости. Чтобы включить или отключить функцию .NET 4.6 и выше приложений, выполняющихся на .NET 4.7 или более поздней версии framework доступна следующая конфигурация API.<ul><li>Программная работа</li></ul>Должны быть очень первое, что делает приложение, поскольку ServicePointManager будет инициализировать только один раз:<pre><code class="language-C#">AppContext.SetSwitch(&quot;TestSwitch.LocalAppContext.DisableCaching&quot;, true);&#13;&#10;AppContext.SetSwitch(&quot;Switch.System.Net.DontEnableTlsAlerts&quot;, true); // Set to &#39;false&#39; to enable the feature in .NET 4.6 - 4.6.2.&#13;&#10;</code></pre><ul><li>AppConfig:</li></ul><pre><code class="language-XML">&lt;runtime&gt;&#13;&#10;&lt;AppContextSwitchOverrides value=&quot;Switch.System.Net.DontEnableTlsAlerts=true&quot;/&gt;&#13;&#10;&lt;!-- Set to &#39;false&#39; to enable the feature in .NET 4.6 - 4.6.2. --&gt;&#13;&#10;&lt;/runtime&gt;&#13;&#10;</code></pre><ul><li>Раздел реестра (глобальный по умолчанию):</li></ul>Значение 'false' Включение компонента в .NET 4.6 - 4.6.2.<pre><code>Key = HKLM\SOFTWARE\[Wow6432Node\]Microsoft\.NETFramework\AppContext\Switch.System.Net.DontEnableTlsAlerts&#13;&#10;Type = String&#13;&#10;Value = &quot;true&quot;&#13;&#10;</code></pre>|
|Область|Пограничный случай|
|Версия|4.7|
|Тип|Изменение целевой платформы|
|Затронутые API|<ul><li><xref:System.Net.Security.SslStream?displayProperty=nameWithType></li><li><xref:System.Net.WebRequest?displayProperty=nameWithType></li><li><xref:System.Net.HttpWebRequest?displayProperty=nameWithType></li><li><xref:System.Net.FtpWebRequest?displayProperty=nameWithType></li><li><xref:System.Net.Mail.SmtpClient?displayProperty=nameWithType></li><li><xref:System.Net.Http?displayProperty=nameWithType></li></ul>|
