## Шаг 3
1. После **4 секунды** (4000ms), карта должна перевернуться и показать **перевод текущего слова** на экран. 
2. Изображение карты должно смениться на  **card_back.png** и цвет текста должен поменяться на белый (**white**). И загаловок флэш карты должен показать язык перевода например "*English*".

### Пример
![card_flip](https://img-c.udemycdn.com/redactor/raw/2020-07-09_09-42-09-48ceef3e82b50344d8e85e3ad15c07cf.gif)

## Подсказки
1. Для смены изображения на виджете canvas, вам понадобится **reference**(ссылка или айди) к картинке, наподобие того, что вы используете для созданного текста на canvas. Используя эту ссылку вы сможете использовать метод canvas-а `itemconfig()`.

```python
new_image = PhotoImage(file="new_image.png")
old_image = PhotoImage(file="old_image.png")
canvas_image = canvas.create_image(300, 300, image=old_image)
#To change the image:
canvas.itemconfig(canvas_image, image=new_image)
```

### ВАЖНО: Объекты PhotoImage для фона флэшкарты не должны создвавться внутри функции иначе они не будут доступны за пределами ее.

2. Чтобы поменять цвет текста в canvas используйте параметр `fill`, например:

```python
text_ref = canvas.create_text(300, 460, text=itemThree, font=('Impact', 30), fill="yellow")
```

3. Помните используя `mainloop()` вам не нужно создавать дополнительную логику с циколм для задержки времени например time.sleep(), вместо этого используйте удобный метод `window.after()`.
Вот ссылка на документацию этого метода [https://tcl.tk/man/tcl8.6/TclCmd/after.htm](https://tcl.tk/man/tcl8.6/TclCmd/after.htm)

4. Вы можете отменить `window.after()` используя метод `window.cancel()`.


