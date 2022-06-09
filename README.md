# Item_card_testing
Тестирование функционала карточки товара в сервисе для оптимизации размещения товаров на складе и в магазине на соответствие ожидаемому поведению.
---
Чек-лист со сценариями для тестового покрытия карточки товара (включая сведения об ошибках и их критичности) доступен по [ссылке](https://docs.google.com/spreadsheets/d/1Ee2ld3osE4s_8K32OO7M-nkHGAa7e5xER5YiHPjjBX8/edit?usp=sharing).
Несколько отчетов об ошибках доступны по [ссылке](https://docs.google.com/spreadsheets/d/1Nv0NXJs5nPUDJBtQRFN7RB9SIUEDhULDXQM_KX3_gQg/edit?usp=sharing).

#### Рекомендации для улучшения функциональности карточки товара
При функциональном тестировании карточки товара возникли следующие предложения для улучшений:
- при указании группы товара следует сделать выпадающее окно с заданными вариантами, так как при самостоятельном вводе групп товара существует возможность создания нескольких однотипных групп с различными названиями, что приведет к утере некоторых товаров при фильтрации, хотя эти товары потенциально соответствуют группе товара. Например, при ручном вводе можно указать как “брюки”, так и “штаны”, что очень схоже по своему содержанию, но при фильтрации только по “брюкам” возможно исключение товаров в группе “штаны”. Аналогичные размышления можно отнести и к пункту “категория” в основных свойствах товара.
- чек-лист проверки карточки товара содержит несколько рекомендованных сценариев касательно кода товара и кода EAN-13. Данные сведения рекомендуется сделать обязательными для заполнения, так как при возникновении ошибок при поиске по коду товара останется возможность поиска по коду EAN-13 и наоборот. Также следует ввести ограничение на ввод такого значения, которое уже существует в базе, это поможет избежать конфликта наименований при поиске по этим значениям. 
- следует ограничить ввод нескольких идентичных значений атрибутов во вкладке дополнительных свойств товара, так как это потенциально может привести к конфликтам при фильтрации по атрибутам.
- на определенные группы товаров следует сделать поле с указанием массы обязательным к заполнению, либо выводить предупреждение о возможной высокой массе товара.

#### Рекомендации для улучшения UI
Что касается тестирования интерфейса пользователя, то предварительно хотелось бы уточнить, что тестирование UI следует проводить на основании технической документации к продукту, либо при непосредственном взаимодействии с командой разработки (при отсутствии исчерпывающих требований). В данном случае, при составлении сценариев для покрытия тестами карточки товара недостаточно лишь сервисного справочника с указанием настроек свойств товара. К тому же, в данных указаниях некоторые действия либо отсутствуют, либо противоречат фактическим примерам, указанным в карточке товара. Например, в [свойствах товара](https://spaceplanner.ru/svoystva-tovara) элемент “ценники” графически обозначен в одном виде, но фактически выглядит по другому:
![Форма ценники не соответствуует форме из требований](https://github.com/Ordbe/Item_card_testing/blob/main/%D0%A4%D0%BE%D1%80%D0%BC%D0%B0%20%D1%86%D0%B5%D0%BD%D0%BD%D0%B8%D0%BA%D0%B8.png)
