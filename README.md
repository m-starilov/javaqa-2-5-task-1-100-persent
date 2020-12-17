Счетчики покрытия JaCoCo:
1. `INSTRUCTION` - считает инструкции одиночного байт-кода (наименьшая единица счёта).
<details>
  <summary>Пример</summary> 
Исходный код:

```java
outer:
for (int i = 2; i < 1000; i++) {
    for (int j = 2; j < i; j++) {
        if (i % j == 0)
            continue outer;
    }
    System.out.println(i);
}
```

Байт-код:

```0:   iconst_2
1:   istore_1
2:   iload_1
3:   sipush  1000
6:   if_icmpge       44
9:   iconst_2
10:  istore_2
11:  iload_2
12:  iload_1
13:  if_icmpge       31
16:  iload_1
17:  iload_2
18:  irem
19:  ifne    25
22:  goto    38
25:  iinc    2, 1
28:  goto    11
31:  getstatic       #84; //Field java/lang/System.out:Ljava/io/PrintStream;
34:  iload_1
35:  invokevirtual   #85; //Method java/io/PrintStream.println:(I)V
38:  iinc    1, 1
41:  goto    2
44:  return
```
</details>

2. `BRANCH` - считает покрытие ветвей для операторов условия `if` и `switch`.
2. `LINES` - рассчитывает информацию о покрытии для отдельных строк исходного кода.
2. `COMPLEXITY` - вычисляет цикломатическую сложность.