
# Исправление ошибок в модах

С течением времени и обновлением игр случаются ситуации, когда моды ломаются из-за обновлений и всевозможных технических недоработок. Обычно моддеры объединяются, чтобы создать простые в использовании исправления, которые обновляют мод до текущей версии игры. По крайней мере, для наиболее популярных элементов игры.

::: внимание!
Пожалуйста, не спешите загружать первый попавшийся в сети .exe файл - злоумышленники обычно пользуются ситуацией и загружают поддельные исправления, которые могут навредить вашему компьютеру. Всегда скачивайте файлы из проверенных источников или авторов.
:::

Вот список проверенных разработчиков, которые предоставляют исправления для модов:

- [SilentNightSound](https://gamebanana.com/members/2176153)
- [Petrascyll](https://gamebanana.com/members/2644630)
- [Gustav0](https://gamebanana.com/members/2890460)
- [SpectrumQT](https://gamebanana.com/members/2837527) - Specializes in WW fixes
- [sora_](https://gamebanana.com/members/1367828) - Специализируется на ремонтах HSR
- [Thoronium](https://gamebanana.com/members/3210319) - Специализируется на «обратных» исправлениях для частных серверов

## Метод половинок или что делать если у вас не запускается игра

Если у вас возникла проблема, и вы не знаете, какой мод ее вызывает, вы можете использовать «метод половинок», чтобы найти проблемный мод. Вот как это работает:

    1. Переместите половину модов в другую папку
    2. Запустите игру
    3. Если все работает, переместите половину модов назад.
    4. Если это не сработает, переместите вторую половину модов назад.
    5. Повторяйте, пока не найдете проблемный мод.

С математической точки зрения, этот метод - самый эффективный способ найти проблемный мод (если не более 7 итераций/попыток).
Иногда бывает так, что никаких модов, ломающих игру, нет, а конфликт вызван каким-то файлом в `/ShaderFixes`. Если удаление всех модов из папки `/Mods` не устраняет проблему, тогда используйте этот метод в `/ShaderFixes`.

## Mod doesn't load at all

Ensure 3dmigoto is actually running, and that you have placed the mod in the correct Mod folder. Also make sure to press F10 in-game to reload any changed mods. Finally, if all else fails try emptying your ShaderCache and ShaderFixes folders, since sometimes those can cause issues when loading mods.

## Большое количество предупреждений (оранжевый текст) о конфликтах с модами

Это происходит из-за того, что игра пытается загрузить более одного файла в один и тот же хэш. Обычно это происходит при одновременном использовании двух модов для одного и того же персонажа.

Чтобы исправить ситуацию, удалите все дублирующиеся папки с модами. Если вы уверены, что удалили их все, но предупреждения все равно появляются, зайдите в .ini файл, о котором говорится в предупреждении, и удалите или закомментируйте строки.

## Игра крашится, когда я пытаюсь ее запустить

Убедитесь, что у вас установлена последняя версия лаунчера, игры и самих модов. Если все остальное не помогает, вы можете попробовать «метод половинок» о котором говорилось выше, чтобы найти проблемный мод. После обнаружения вы можете диагностировать его проблему или попросить помощи [в канале #mod-help сервера Discord](https://discord.com/channels/971945032552697897/995556765179596890), более опытные пользователи будут рады оказать помощь. В качестве альтернативы вы можете просто избавиться от мода и дождаться выхода обновления или исправления.

## Мод отображается частично или разрушается сам по себе

Из-за технических ограничений при первой загрузке мода лучше избегать появления персонажа на экране. Это известная проблема, и мы работаем над более сложным исправлением. 
Чтобы исправить это, вам просто нужно перезагрузить персонажа/объект в память, самый безопасный способ добиться этого - перезапустить игру. 
В качестве альтернативы вы можете попробовать скрыть персонажа/объект от камеры и телепортироваться или загрузить новую сцену. Это должно очистить достаточно памяти, чтобы заставить персонажа/объект перезагрузиться.

## Мод загружается, но не отображается в игре / Ошибки при загрузке мода (желтый текст)

В отличие от предупреждений, ошибки обычно указывают на то, что 3DMigoto не смогла загрузить мод. Причина может быть разной, но некоторые распространенные из них:

- Неправильные наименование (имя в .ini файле не совпадает с именем файла в папке, например, разное расширение)
- Текстуры имеют неправильный формат (посмотрите на оригинал, чтобы узнать, какой формат, обычно это dds, и они должны иметь высоту/ширину, равные степени 2 и целочисленные соотношения, например 1024x1024, 2048x2048, 1024x2048 и т. д.)
- Не рисовали/переносили группы вершин на новую модель, если в старой модели были группы вершин

## Объекты загружаются в неправильном положении

Это происходит потому, что объект в blender, импортированный 3dmigoto, и объект, которым вы его заменяете, используют разные координатные пространства. Даже если кажется, что они совпадают в blender, на самом деле вам может потребоваться повернуть и перевести модель 3dmigoto, чтобы получить правильную ориентацию. Чаще всего модели персонажей поворачивают на 90 градусов, чтобы они были обращены вверх, затем выбирают все и применяют все преобразования.

Пример правильной ориентации между оригиналом (Кадзуха) и новым (Ноэль)

## Модель полностью НЕИСПРАВНА (Плавающее тело)
  
Очень вероятно, что это связано с проблемами с группами вершин(Vertex Groups). Количество, порядок и позиции вершинных групп должны совпадать в новой и старой модели. Убедитесь, что в новой модели есть все вершинные группы, что они расположены в правильном порядке (например, 4 6 7 8 5 должно быть 4 5 6 7 8) и что нет пробелов (например, 4 7 8 9 -> 4 5 6 7 8 9), если есть пробелы, заполните их новыми пустыми вершинными группами.

## Модель ну-немножечко, не работает

Всё также, проблемы с группами вершин. Перепроверьте все вышеперечисленное, а также убедитесь, что вес новой модели в этой секции совпадает с весом оригинальной модели

## Неправильные текстуры

Это может быть вызвано разными причинами. Частые из них:

- Отсутствие именования UV развёртки как TEXCOORD.xy
- Перевернутые нормали
- Поврежденный или неправильный файл ObjectTexcoord.buf
- Забыли заменить текстуры на новые, поэтому все еще загружаются старые текстуры из оригинальной модели
- Очень яркие/светящиеся текстуры

Скорее всего, это связано с тем, что используемая вами карта текстур не имеет альфа-канала. За подробностями обратитесь к руководствам на этом репозитории, но в основном убедитесь, что у вас есть прозрачный слой поверх всех текстурных файлов (верхний слой альфы используется для контроля излучения и делает элементы яркими, а вот нижний слой используется для непосредственно отображения цветов).

## Приватные серверы и игровые версии

Если вы используете приватный сервер, есть вероятность, что мод, который вы скачали, был сделан не для старой версии, как та, которую вы используете. Поэтому вам нужно будет «починить»/даунгрейднуть версию мода до той, на которой вы находитесь. Существуют «обратные исправления», которые позволяют добиться этого, но они не так распространены, как обычные исправления. Вы можете обратиться за помощью в [канал #mod-help сервера Discord](https://discord.com/channels/971945032552697897/995556765179596890), чтобы узнать подробности.

## [GI] Мод отображается как беспорядочная каша из геометрии

В версии 4.1 была введена функция DCR (Dynamic Character Resolution или же Динамическое разрешение персонажей), которая при включении нарушает рендеринг модов. Чтобы решить эту проблему, просто отключите его в настройках графики вашей игры. Некоторые обновления драйверов видеокарты или программы вроде Nvidia Geforce Experience могут принудительно включить его, так что проверяйте это каждый раз, когда видите, что проблема возникает.
![DCR](./img/dcr.png)

## [GI] Сетка должна быть прозрачной, но она по-прежнему непрозрачна

Современный метод сделать сетку модели прозрачной заключается в использовании библиотеки под названием `TexFX`, которая по умолчанию устанавливается в XXMI launcher. Если вы используете традиционную установку 3DMigoto, вам может потребоваться вручную установить `TexFX`. Обновленное руководство по этому вопросу [читайте здесь](https://gamebanana.com/mods/485763)

## [GI] Отражение/контур персонажа имеет неправильную окраску

Это связано с конвейером рендеринга игры. К счастью, существует универсальное решение. Если вы используете XXMI Launcher для модинга игры, это решение установлено по умолчанию. Если вы используете 3dmigoto, вы можете [скачать исправление отсюда](https://github.com/leotorrez/LeoTools/blob/main/releases/ORFix.ini) и [прочитать о нем подробнее здесь](https://github.com/leotorrez/LeoTools/blob/main/guides/ORFixGuide.md).
После установки нажмите F10, чтобы перезагрузить мод.

## [GI] Персонаж или его очертания утоплены в пол

Как и предыдущая проблема, она решается установкой некоторых необходимых файлов в папку 3dmigoto. Вы можете [скачать исправление отсюда](https://github.com/leotorrez/LeoTools/releases/tag/offset-scaleChangerV3). Для установки распакуйте файлы в папке 3dmigoto и нажмите F10, чтобы перезагрузить мод.

## [HSR] Когда мой персонаж перестает бегать, его модель ломается. 0_0

<!-- TODO: Find good resources about this xD -->

## [ZZZ] Активированная функция V-Sync задерживает ввод пользователя на секунду или более

Эта проблема является новой для меня и наименее изученной из всех. Я буду исследовать и пытаться воспроизвести эту проблему, а пока вы можете попробовать установить fps на 60 или отключить vsync.

## [ZZZ] Модели исчезают, когда я отхожу от них на некоторое расстояние

Это срабатывания LOD'а, и инструменты моддинга не могут предотвратить это. Что он делает, так это загружает версию модели и ее текстур более низкого качества по мере удаления от вас. Чтобы бороться с этим, вы можете получить хэши LOD-модели и создать новый ini для вашего мода, чтобы применить его к этой модели, однако этот процесс очень утомителен для ручного управления и сложен для автоматизации.

## [ZZZ] Текстуры/модели мода не загружаются

 Устройства с памятью VRAM менее 6 ГБ вынуждены использовать 1K-текстуры, а моды рассчитаны на работу с 2k-текстурами, поэтому некоторые текстуры модов выглядят сломанными. Текущие скрипты исправлений патчируют моды, чтобы решить эту проблему, а также обновляют их до текущей версии.

## [ZZZ] Моделька лица Джэйн Доу сломано

Эта проблема вызвана конфликтом с модами Люси. Чтобы исправить это, автору мода придется обновить его, чтобы избежать конфликта. Однако если вам удобно редактировать ini-файлы, вы можете обновить его самостоятельно.

Найдите переопределение текстуры `LucyHairPosition` в ini-файле мода. Он должен выглядеть примерно так:
```ini
...

[TextureOverrideLucyHairPosition]
hash = ...
handling = skip
vb0 = ResourceLucyHairPosition
vb2 = ResourceLucyHairBlend
draw = 3079,0

...
```
Вы должны заменить его на переопределение текстуры `LucyHairBlend`, имейте в виду, что его хэш будет обновлен до `5315f036`.

```ini
...

[TextureOverrideLucyHairPosition]
hash = 5315f036
handling = skip
if DRAW_TYPE == 1
    vb0 = ResourceLucyHairPosition
    vb2 = ResourceLucyHairBlend
    draw = 3079,0
endif

...
```