### <a name="accessibility-improvements-in-wpf"></a>Более удобным в WPF

|   |   |
|---|---|
|Подробные сведения|<strong>Усовершенствования Высокая контрастность</strong><ul><li>Фокус <xref:System.Windows.Controls.Expander> теперь отображается элемент управления. В предыдущих версиях платформы .NET Framework было.</li><li>Текст в <xref:System.Windows.Controls.CheckBox> и <xref:System.Windows.Controls.RadioButton> элементов управления при их выборе теперь стало проще восприятия, чем в предыдущих версиях .NET Framework.</li><li>Границы отключенного <xref:System.Windows.Controls.ComboBox> теперь является цвет отключенного текста. В предыдущих версиях платформы .NET Framework было.</li><li>Отключенные и имеющего фокус кнопки теперь использовать цвет правильный темы. В предыдущих версиях платформы .NET Framework они не поддерживались.</li><li>Кнопка раскрывающегося меню отображается при <xref:System.Windows.Controls.ComboBox> стиля элемента управления имеет значение <xref:System.Windows.Controls.ToolBar.ComboBoxStyleKey?displayProperty=nameWithType>, в предыдущих версиях платформы .NET Framework не.</li><li>Индикатор стрелку сортировки в <xref:System.Windows.Controls.DataGrid> элемент управления использует цвета темы. В предыдущих версиях платформы .NET Framework это не так.</li><li>Стиль по умолчанию гиперссылки теперь изменяется правильный темы мыши. В предыдущих версиях платформы .NET Framework это не так.</li><li>Теперь отображается на переключателей фокус клавиатуры. В предыдущих версиях платформы .NET Framework было.</li><li><xref:System.Windows.Controls.DataGrid> Столбцов элемента управления checkbox теперь использует ожидаемый цвета для отзывов фокус клавиатуры. В предыдущих версиях платформы .NET Framework это не так.</li><li>визуальные элементы фокус клавиатуры будут отображены на <xref:System.Windows.Controls.ComboBox> и <xref:System.Windows.Controls.ListBox>. В предыдущих версиях платформы .NET Framework было.</li></ul><strong>Улучшения взаимодействия чтения экрана</strong><ul><li><xref:System.Windows.Controls.Expander> элементы управления, теперь правильно объявляются как группы (развернуть или свернуть) с экрана.</li><li><xref:System.Windows.Controls.DataGridCell> элементы управления, теперь правильно объявляются как ячейки сетки данных (локализованный) с экрана.</li><li>Средства чтения с экрана теперь будут сообщать имя редактируемого <xref:System.Windows.Controls.ComboBox>.</li><li><xref:System.Windows.Controls.PasswordBox> элементы управления больше не было объявлено как &quot;элемент отсутствует в представлении&quot; программами чтения с экрана.</li></ul><strong>Поддержка LiveRegion</strong>экрана, например Экранный диктор проще определять содержимое пользовательского интерфейса приложения, обычно с описания что-нибудь о пользовательском Интерфейсе, который находится в данный момент в фокусе, так как это, скорее всего, элемент наибольший интерес для пользователя. Тем не менее если где-либо изменяет элемент пользовательского интерфейса на экране и не имеет фокуса, пользователь может не представлять и упустите важные сведения. LiveRegions предназначены для решения этой проблемы. Разработчик может использовать их для информирования чтения с экрана или любые другие [модели автоматизации пользовательского интерфейса][Обзор модели автоматизации пользовательского интерфейса](~/docs/framework/ui-automation/ui-automation-overview.md) клиента, важных изменений в элемент пользовательского интерфейса. После этого средство чтения с экрана может решить, уведомлять ли пользователя об этом изменении. Свойство LiveSetting также позволяет узнать, насколько важно информировать пользователей об изменения, сделанные в пользовательский интерфейс средства чтения с экрана.|
|Предложение|<strong>Как принять или отклонить изменения</strong>чтобы приложения для использования преимуществ эти изменения, оно должно выполняться на платформе .NET Framework 4.7.1 или более поздней версии. Приложения могут использовать преимущества этих изменений в одном из следующих способов:<ul><li>Повторная компиляция для использования в .NET Framework 4.7.1. Эти специальные возможности изменения включено по умолчанию в приложениях WPF, ориентированных на .NET Framework 4.7.1 или более поздней версии.</li><li>Он означает отказ от участия поведения предыдущих версий специальных возможностей, добавив следующий код [коммутатора параметров AppContext](~/docs/framework/configure-apps/file-schema/runtime/appcontextswitchoverrides-element.md) в <code>&lt;runtime&gt;</code> раздел файла конфигурации приложения и задать его значение false, как показано в следующем примере.</li></ul><pre><code>&lt;?xml version=&quot;1.0&quot; encoding=&quot;utf-8&quot;?&gt;&#13;&#10;&lt;configuration&gt;&#13;&#10;&lt;startup&gt;&#13;&#10;&lt;supportedRuntime version=&quot;v4.0&quot; sku=&quot;.NETFramework,Version=v4.7&quot;/&gt;&#13;&#10;&lt;/startup&gt;&#13;&#10;&lt;runtime&gt;&#13;&#10;&lt;!-- AppContextSwitchOverrides value attribute is in the form of &#39;key1=true/false;key2=true/false  --&gt;&#13;&#10;&lt;AppContextSwitchOverrides value=&quot;Switch.UseLegacyAccessibilityFeatures=false&quot; /&gt;&#13;&#10;&lt;/runtime&gt;&#13;&#10;&lt;/configuration&gt;&#13;&#10;</code></pre>Приложения, предназначенные для .NET Framework 4.7.1 или более поздней версии и хотите сохранить прежних поведение специальных возможностей можно выбрать с использованием предыдущих версий специальные возможности, явно установите значение этого параметра параметров AppContext <code>true</code>. Обзор модели автоматизации пользовательского интерфейса см. в разделе [Обзор модели автоматизации пользовательского интерфейса](~/docs/framework/ui-automation/ui-automation-overview.md).|
|Область|Значительно|
|Версия|4.7.1|
|Тип|Изменение целевой платформы|
|Затронутые API|<ul><li><xref:System.Windows.Automation.AutomationElementIdentifiers.LiveSettingProperty?displayProperty=nameWithType></li><li><xref:System.Windows.Automation.AutomationElementIdentifiers.LiveRegionChangedEvent?displayProperty=nameWithType></li><li><xref:System.Windows.Automation.AutomationLiveSetting?displayProperty=nameWithType></li><li><xref:System.Windows.Automation.AutomationProperties.LiveSettingProperty?displayProperty=nameWithType></li><li><xref:System.Windows.Automation.AutomationProperties.SetLiveSetting(System.Windows.DependencyObject,System.Windows.Automation.AutomationLiveSetting)?displayProperty=nameWithType></li><li><xref:System.Windows.Automation.AutomationProperties.GetLiveSetting(System.Windows.DependencyObject)?displayProperty=nameWithType></li><li><xref:System.Windows.Automation.Peers.AutomationPeer.GetLiveSettingCore?displayProperty=nameWithType></li></ul>|
