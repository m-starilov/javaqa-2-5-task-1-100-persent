Краткое описание счетчиков покрытия JaCoCo:
1. `INSTRUCTION` - считает покрытие инструкций одиночного байт-кода (наименьшая единица счёта)
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

![image](https://user-images.githubusercontent.com/68705045/102531875-47158c80-40cd-11eb-81b6-1cdb79150cc1.png)

2. `BRANCH` - считает покрытие ветвей для операторов условия `if` и `switch`
![image](https://user-images.githubusercontent.com/68705045/102532043-8e038200-40cd-11eb-8fc2-bc33485bea4a.png)

2. `LINE` - рассчитывает информацию о покрытии для отдельных строк исходного кода
![image](https://user-images.githubusercontent.com/68705045/102532157-c014e400-40cd-11eb-89fd-755c6e0fff52.png)

2. `COMPLEXITY` - вычисляет цикломатическую сложность
![image](https://user-images.githubusercontent.com/68705045/102532332-05391600-40ce-11eb-8cd3-8a727a66ed1d.png)
