# Часто задаваемые вопросы

## 1. Как установить расширение?

Решение:

* Перейти в раздел Администрирование: Печатные формы, отчеты и обработки -> Расширения.
* Нажать на кнопку ``Добавить из файла...``
* Выбрать файл с расширением.

* Внимание: Для установки расширения, база должна быть запущена в монопольном режиме. Иначе говоря, в базе должен быть один активный пользователь - тот, под которым вы запустили свой сеанс. 

## 2. При открытии обработки возникает ошибка: ``Установлен безопасный режим. Выполнение операции запрещено``.

Решение:

* Перейти в раздел Администрирование: ``Печатные формы, отчеты и обработки -> Расширения``.
* Снять галку ``Безопасный режим`` с расширения ``Импорт из АЦК и Кристы``.

## 3. Когда нажимаю на Предварительный просмотр, таблица с результатами пустая.

Решение:

Убедитесь, что на форме обработки, на вкладке ``Файлы`` поле ``Период`` очищено или заполнено теми датами, в которые точно попадут документы из файла.

## 4. При импорте из АЦК возникает ошибка: "Не поддержимаемый формат файла".

Решение:

На текущий момент поддерживаются следующие версии форматов файлов АЦК: ``2.5``, ``2.6``, ``2.8``.

Версия ``2.8`` поддерживается в расширении, начиная с версии ``1.1.4.8``.

Чтобы проверить версию формата АЦК загружаемого файла, нужно открыть его, например, через `Блокнот` и найти строку ``<WTFORMAT VERSION="ВЕРСИЯ_ФОРМАТА">``, где ВЕРСИЯ_ФОРМАТА - номер версии.

## 5. При импорте из АЦК возникает ошибка: `Преобразование значения к типу Дата не может быть выполнено`.

Решение: 

В АЦК при выгрузке, надо ставить статус документа: ``Обработка завершена``.

## 6. При импорте не заполняется организация, лицевой счет, КПС и.т.п.

Решение:

Убедитесь, что в базе созданы все нужные элементы, которые указаны в файле.
Обработка не создает данные справочников из файла. Подразумевается, что в базе настроены все справочники.

Исключениями являются ``Контрагенты`` и ``Договоры``. 
Контрагентов программа сама предложит создать, а для договоров можно включить настройку в обработке: ``Настройки -> Создавать новые договоры``.

## 7. При импорте не заполняется ``Счет Дт``.

Решение:

Если должен быть заполнен налоговый счет, то убедитесь, что КПС, указанный в файле, создан и привязан к виду налога в базе. Поиск видов налогов происходит по КПС. 

## 8. При импорте из Кристы не заполняются ``КФО`` и ``Счет Кт``.

Решение:

* Убедитесь, что ``Настройки КФО`` заполнены корректно. Как настроить см. [здесь](https://sorokinltd.github.io/import-from-treasury-systems-doc.github.io/docs/settings-kfo/index)

## 9. При импорте КПС заполняются нулями.

Решение:

Убедитесь, что в справочнике КПС созданы все КПС, которые указаны в файле.

## 10. При импорте не заполняется организация, хотя она есть в базе.

Решение:

См. вопрос 8.

Также должна быть корректно настроена Структура РПС у организации.

## 11. При импорте из АЦК, есть заявка на одну и ту же сумму в двух организациях, загружаю по первой, кассовое выбытие создается, загружаю вторую организацию, кассовое выбытие меняется на вторую организацию.

Решение:

Уникальность документов определяется по дате и первичному номеру документа.
Для корректного импорта номера первичных документов не должны совпадать.
