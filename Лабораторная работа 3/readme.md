# **Лабораторная работа №3**  
*Цель работы:*  
- Улучшить функцию сортировки слиянием
- Улучшить функцию быстрой сортировки 
---  
## **Сортировка слиянием до:**  
```py
def merge(a, b):
    if a == [] or b == []: return a + b
    if a[0] < b[0]: 
        return [a[0]] + merge(a[1:], b) 
    else:
        return [b[0]] + merge(a, b[1:])
```
## **Сортировка слиянием после:**
```py
def merge(a, b):
    result = []
    difficalty = 0
    while True:
        difficalty += 1
        if len(a) == 0 or len(b) == 0:
            result += a + b
            break;
        else:
            if a[0] < b[0]: 
                result.append(a[0])
                a = a[1:]
            else:
                result.append(b[0])
                b = b[1:]
    return result
```
### **Быстрая сортировка до:**  
```py
def sort_quick(lst):
    if len(lst) < 2: return lst
    pivot = lst[0]
    left = list(filter(lambda x: x < pivot, lst))
    middle = list(filter(lambda x: x == pivot, lst))
    right = list(filter(lambda x: x > pivot, lst))
    return sort_quick(left) + middle + sort_quick(right)
```  
### **Быстрая сортировка после:** 
def sort_quick(lst):
    if len(lst) > 2: 
        pivot = lst[0]
        
        left = []
        middle = []
        right = []
        for i in range(len(lst)):
            if(lst[i] < pivot):
                left.append(lst[i])
            elif(lst[i] == pivot):
                middle.append(lst[i])
            else:
                right.append(lst[i])
        return sort_quick(left) + middle + sort_quick(right)
    else:
        return lst
```
### **Проведение опыта**  
После разработки и проверки алгоритма были получены следующие результаты:  
---  
*** 
---   
