Исходные файлы взяты из проекта **loginom-install** папка **wix/l10n**.

### Интеграция с LingoHub

Наиболее схожий формат, поддерживаемый LingoHub - [Android Localization](https://lingohub.com/developers/resource-files/android-localization/).

Чтобы подготовить файл **ru-RU.wxl** для LingoHub нужно:

* Изменить расширение файла `wxl` на `xml`,
* Выполнить замену:
    * тег `WixLocalization` на `resources`,
    * тег `String` на `string`,
    * атрибута `Id`  на `name`.

Чтобы получить `en-US.wxl` из файла полученного из LingoHub:

* Переименовать его в **en-US.wxl**
* Восстановить перевод строк с `\n` на `\r\n`
* Выполнить замену: 
    * тег `resources` на `WixLocalization`,
    * тег `string` на `String`
    * атрибута `name` на `Id`.
* Изменить атрибут `Culture` на `"en-US"`
* Некоторые символы могут быть экранированы, их нужно сделать как были. Например `&#0037` нужно заменить на `%`

> **NOTE:** Особенности экспорта LingoHub
>
> По умолчанию LingoHub не добавляется локаль к исходному файлу, даже если при импорте она была. Поэтому, **необходимо включить эту опцию самостоятельно**:
>
> `Dashboard` > `Preferences` > `Files` > (`Export - General`) `Add language information to file name`, выбрать `to all resource files`