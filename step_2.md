# Шаг 2
1. Откройте файл в режиме чтения, где у вас хранятся слова в формате CSV. Например, **french_words.csv** в каталоге **data**.
2. Выберите случайное слово, используя **random** и его перевод и вставьте слово в флэш карту. Каждый раз, когда вы **нажимаете** кнопку ❌ или ✅, вы должны сгенерировать **новое слово** для показа на экран.

Пример:
![example gif](https://img-c.udemycdn.com/redactor/raw/2020-07-09_09-14-54-d7775dfde5cc88a7a20ba612d3b489bd.gif)

## Подсказка
1. Для работы с CSV вам понадобится библиотека **pandas**. Для работы со словами вы можете извлечь данные в формате словаря и создать структуру списка слов как на этом примере: 
`[ {"french_word": "english_word"}, {"french_word2": "english_word2"}, {"french_word3": "english_word3"}]`

### Документация pandas
- [https://pandas.pydata.org/pandas-docs/stable/reference/api/pandas.DataFrame.to_dict.html](https://pandas.pydata.org/pandas-docs/stable/reference/api/pandas.DataFrame.to_dict.html)
