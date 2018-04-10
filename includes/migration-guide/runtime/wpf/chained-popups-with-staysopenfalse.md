### <a name="chained-popups-with-staysopenfalse"></a>Связанные всплывающие окна которого staysopen = = False

|   |   |
|---|---|
|Подробные сведения|Всплывающее окно с staysopen = = False должен закрыть при первом щелчке вне всплывающее окно. Когда соединяются две или более таких всплывающие окна (т. е. один содержит другой), отсутствуют многие проблемы, включая:<ul><li>Откройте два уровня, щелкните за пределами P2, но внутри P1.  Ничего не происходит.</li><li>Откройте два уровня, щелкните вне P1.  Закройте оба всплывающие окна.</li><li>Откройте и закройте два уровня.  Затем попытайтесь снова открыть P2.  Ничего не происходит.</li><li>Попробуйте открыть тремя уровнями.  Вы не можете.  (Ничего не происходит или закрыть первые два уровня, в зависимости от щелчка.) Эти варианты (и другие варианты) теперь работать должным образом.</li></ul>|
|Область|Пограничный случай|
|Версия|4.7.1|
|Тип|Среда выполнения|
|Затронутые API|<ul><li><xref:System.Windows.Controls.Primitives.Popup.StaysOpen?displayProperty=nameWithType></li></ul>|
