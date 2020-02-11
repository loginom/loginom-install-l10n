Исходные файлы взяты из [loginom-install/wix/l10n](../../../../loginom-install/tree/master/wix/l10n)

### Интеграция с LingoHub

Наиболее схожий формат, поддерживаемый LingoHub - [Android Localization](https://lingohub.com/developers/resource-files/android-localization/).

Чтобы подготовить файл **ru-RU.wxl** для LingoHub нужно:

* Изменить расширение файла `wxl` на `xml`,
* Выполнить замену:
    * тег `String` на `string`,
    * атрибута `Id`  на `name`.

Чтобы получить `en-US.wxl` из файла полученного из LingoHub:

* Переименовать его в **en-US.wxl**
* Выполнить замену: 
    * тег `resources` на `WixLocalization`,
    * тег `string` на `String`
    * атрибута `name` на `Id`.
* Изменить атрибут `Culture` на `"en-US"`
