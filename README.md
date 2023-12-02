# ТЗ Аксессориз

## Задача:

- Откомментировать что по вашему мнению могут значить поля в ответе сервера ( Можно предположить что это может быть )
- Реализовать интерфейс ( табличку для возможности просмотра стран с фильтрацией ) 
- Использовать поля из ответа для удобного пролистывания списка стран ( Подумать как использовать в отображении массив rpag. )
- Интерфейс должен предпологать адаптивность.

### API
```json
{
  "form_errors": null,
  "success_message": "Success",
  "page_data": {
    "data": [
      {
        "iso_3166_1_a2": "RU",
        "iso_3166_1_a3": "RUS",
        "iso_3166_1_numeric": "643",
        "printable_name": "Russian Federation",
        "name": "",
        "display_order": 0,
        "is_shipping_country": false
      }
    ],
    "rpag": {
      "has_next": false,
      "has_previous": false,
      "has_other_pages": false,
      "next_page_number": null,
      "previous_page_number": null,
      "start_index": 1,
      "end_index": 1,
      "total_count": 249,
      "selected_count": 1,
      "pages": 1
    }
  },
  "redirect": "",
  "exc_stack": "",
  "debug": [],
  "user_groups": "",
  "user_perms": ""
}
```

## Решение задачи

**Поля в ответе сервера могут иметь следующие значения:**
1. "form_errors": null - это поле указывает на отсутствие ошибок в форме, если были отправлены какие-либо данные.
2. "success_message": "Success" - это поле содержит сообщение об успешном выполнении запроса.
3. "page_data": это поле содержит данные о странах, соответствующих заданным фильтрам и параметрам пагинации.
   - "data": это массив объектов, каждый из которых представляет информацию о конкретной стране. Поля объекта могут включать:
     - "iso_3166_1_a2": двухсимвольный код страны по стандарту ISO 3166-1.
     - "iso_3166_1_a3": трехсимвольный код страны по стандарту ISO 3166-1.
     - "iso_3166_1_numeric": числовой код страны по стандарту ISO 3166-1.
     - "printable_name": полное название страны.
     - "name": дополнительное название страны (в данном случае пустое поле).
     - "display_order": порядок отображения страны.
     - "is_shipping_country": флаг, указывающий, является ли страна страной доставки.
   - **"rpag": это объект, содержащий информацию о пагинации.**
     - "has_next": флаг, указывающий, есть ли следующая страница.
     - "has_previous": флаг, указывающий, есть ли предыдущая страница.
     - "has_other_pages": флаг, указывающий, есть ли другие страницы.
     - "next_page_number": номер следующей страницы (если есть).
     - "previous_page_number": номер предыдущей страницы (если есть).
     - "start_index": индекс первого элемента на текущей странице.
     - "end_index": индекс последнего элемента на текущей странице.
     - "total_count": общее количество стран, удовлетворяющих фильтрам.
     - "selected_count": количество стран на текущей странице.
     - "pages": общее количество страниц.
4. "redirect": пустая строка - это поле указывает на отсутствие перенаправления.
5. "exc_stack": пустая строка - это поле содержит стек исключений (в данном случае отсутствует).
6. "debug": пустой массив - это поле содержит отладо**чную информацию (в данном случае отсутствует).
7. "user_groups": пустая строка - это поле содержит информацию о группах пользователя (в данном случае отсутствует).
8. "user_perms": пустая строка - это поле содержит информацию о правах пользователя (в данном случае отсутствует).

**Код компонента ctable реализован в файле `index.html`** на 32 строчке.