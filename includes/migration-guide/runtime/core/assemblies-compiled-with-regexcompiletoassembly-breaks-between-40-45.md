### <a name="assemblies-compiled-with-regexcompiletoassembly-breaks-between-40-and-45"></a>Сборок, скомпилированных с разрывами Regex.CompileToAssembly между 4.0 и 4.5

|   |   |
|---|---|
|Подробные сведения|Если сборка компилированных регулярных выражений создается с .NET Framework 4.5, но нацелен на .NET Framework 4, попытка использовать одно из регулярных выражений в том, что сборка в системе с .NET Framework 4 установлена возникло исключение.|
|Предложение|Чтобы обойти эту проблему, можно воспользоваться одним из следующих способов:<ul><li>Создать сборку, содержащую регулярные выражения .NET Framework 4.</li><li>использовать интерпретированное регулярное выражение.</li></ul>|
|Область|Дополнительный номер|
|Версия|4.5|
|Тип|Среда выполнения|
|Затронутые API|<ul><li><xref:System.Text.RegularExpressions.Regex.CompileToAssembly(System.Text.RegularExpressions.RegexCompilationInfo[],System.Reflection.AssemblyName)?displayProperty=nameWithType></li><li><xref:System.Text.RegularExpressions.Regex.CompileToAssembly(System.Text.RegularExpressions.RegexCompilationInfo[],System.Reflection.AssemblyName,System.Reflection.Emit.CustomAttributeBuilder[])?displayProperty=nameWithType></li><li><xref:System.Text.RegularExpressions.Regex.CompileToAssembly(System.Text.RegularExpressions.RegexCompilationInfo[],System.Reflection.AssemblyName,System.Reflection.Emit.CustomAttributeBuilder[],System.String)?displayProperty=nameWithType></li></ul>|
