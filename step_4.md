# Шаг 4

1. Когда пользователь жмет на кнопку ✅, это значит что он знает это слово на флэш карте, и ее нужно убрать из списка изучаемых слов.
Например, если список french_words.csv имеет только 3 слова:
```
chaque,each
parlé,speak
arrivé,come
```
Если пользователь говорит, что он знает слово `parlé,speak`, это слово нужно удалить из списка, и в итоге у нас будет список таким:
```
chaque,each
arrivé,come
```
2. Поэтому будет целесообразно хранить список изучаемых слов отдельным файлом, а весь список слов неизменным. Например у вас будет один файл `french_words.csv` где содержится весь список слов, и другой файл `words_to_learn.csv` где содержатся только те слова, которые все еще не известны пользователю. И если пользователь говорит, что он знает это слово, мы обновляем файл `words_to_learn.csv`.

3. Как только запускается программа нужно проверить существует ли файл `words_to_learn.csv`. Если данный файл существует, то программа должна загрузить список слов для показа из этого файла. А если файл `words_to_learn.csv` не существует (то есть, это самый первый запуск программы), то нужно загрузить слова из файла `french_words.csv`.

Мы хотим чтобы программа выдавала нам только те слова которые мы изучаем и еще не знаем, поэтому нажав на кнопку ✅, программа не должна более показывать это слово пользователю.

## Подсказки
1. Можно использовать метод `remove()`, чтобы удалить элемент из списка, например. [https://www.w3schools.com/python/ref_list_remove.asp](https://www.w3schools.com/python/ref_list_remove.asp)
2. Вы можете создать новый csv файл из словаря используя `DataFrame.to_csv()` Вот тут пример как это сделать можно: [https://pandas.pydata.org/pandas-docs/stable/reference/api/pandas.DataFrame.to_csv.html](https://pandas.pydata.org/pandas-docs/stable/reference/api/pandas.DataFrame.to_csv.html)
3. Если вы не хотите чтобы pandas также создавал и записывал индекс/порядковый номер в ваш новый csv, вы можете задать параметр `index` на `False`. Пример:
```python
data.to_csv("filename.csv", index=False) 
```
