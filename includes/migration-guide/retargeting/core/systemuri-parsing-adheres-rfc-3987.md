### <a name="systemuri-parsing-adheres-to-rfc-3987"></a>Синтаксический анализ System.Uri соответствует RFC 3987

|   |   |
|---|---|
|Подробные сведения|Синтаксический анализ URI претерпел ряд изменений в .NET 4.5. Обратите внимание, что эти изменения касаются только кода, предназначенного для .NET 4.5. Если двоичный файл предназначен для .NET 4.0, будет действовать старое поведение. В синтаксический анализ URI в .NET 4.5 внесены следующие изменения.<ul><li>Выполняет синтаксический анализ URI нормализации и проверка в соответствии с последними правилами IRI в стандарте RFC 3987 символов.</li><li>Форма нормализации Юникода C будет выполняться только на часть URI узла.</li><li>Недопустимый формат mailto: идентификаторы URI теперь будет вызывать исключение.</li><li>Теперь сохраняются конечные точки в конце сегмента пути.</li><li><code>file://</code> Идентификаторы URI не теряется <code>?</code> символов.</li><li>Управляющие символы Юникода <code>U+0080</code> через <code>U+009F</code> не поддерживаются.</li><li>Символ запятой <code>,</code> или <code>%2c</code> не автоматически отменяется.</li></ul>|
|Предложение|Если необходимы старые семантики синтаксического анализа URI .NET 4.0 (часто они не требуются), их можно использовать для нацеливания в .NET 4.0. Это можно сделать с помощью <xref:System.Runtime.Versioning.TargetFrameworkAttribute?displayProperty=name> на сборку, либо через пользовательский Интерфейс системы проектов Visual Studio на странице «свойства проекта».|
|Область|Значительно|
|Версия|4.5|
|Тип|Изменение целевой платформы|
|Затронутые API|<ul><li><xref:System.Uri.%23ctor(System.String)?displayProperty=nameWithType></li><li><xref:System.Uri.%23ctor(System.String,System.Boolean)?displayProperty=nameWithType></li><li><xref:System.Uri.%23ctor(System.String,System.UriKind)?displayProperty=nameWithType></li><li><xref:System.Uri.%23ctor(System.Uri,System.String)?displayProperty=nameWithType></li><li><xref:System.Uri.TryCreate(System.String,System.UriKind,System.Uri@)?displayProperty=nameWithType></li><li><xref:System.Uri.TryCreate(System.Uri,System.String,System.Uri@)?displayProperty=nameWithType></li><li><xref:System.Uri.TryCreate(System.Uri,System.Uri,System.Uri@)?displayProperty=nameWithType></li></ul>|
