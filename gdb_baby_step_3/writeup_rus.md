
# Сайт: PicoCTF
# Автор: LT 'syreal' Jones
# Название: GDB Baby Step 3
# Сложность: Medium

Переходим к третьему заданию из серии `GDB Baby step`. Задание достаточно легкое и практически повторяет 
все шаги из предыдущих райтапов. Однако, здесь мы будем просматривать не содрежимое регистров, а значение находящиеся по адресу.
Дизассмеблируем функцию main
```gdb
  disas main
```
![image](https://github.com/user-attachments/assets/a87a36ad-71a9-41fd-8a48-b1648b061fff)

Число `0x2262c96b` хранится по смещению `rbp-0x4`. Поэтому прописываем следующие команды: 

```gdb
b main
b *0x000000000040111f
r
c
x/4xb $rbp-0x4
```
![image](https://github.com/user-attachments/assets/53c060b6-32ba-43f9-add8-612d78424a49)
