## Три алгоритми сортування

У цьому документі описані три алгоритми сортування: сортування вибором, сортування злиттям і швидке сортування.

**Сортування вибором**

Сортування вибором - це простий алгоритм сортування, який працює шляхом послідовного пошуку мінімального елемента в масиві та його заміни з першим елементом.

```python
def selection_sort(array):
  for i in range(len(array) - 1):
    min_index = i
    for j in range(i + 1, len(array)):
      if array[j] < array[min_index]:
        min_index = j
    array[i], array[min_index] = array[min_index], array[i]


array = [5, 3, 2, 1, 4]
selection_sort(array)
print(array)
[1, 2, 3, 4, 5]


**Сортування злиттям**

Сортування злиттям - це алгоритм сортування, який працює шляхом рекурсивного поділу масиву на два менші підмасиви, сортування кожного з них окремо, а потім об'єднання двох відсортованих підмасивів в один відсортований масив.

python
def merge_sort(array):
  if len(array) <= 1:
    return array

  middle = len(array) // 2
  left_array = merge_sort(array[:middle])
  right_array = merge_sort(array[middle:])

  return merge(left_array, right_array)


def merge(left_array, right_array):
  merged_array = []
  i = 0
  j = 0
  while i < len(left_array) and j < len(right_array):
    if left_array[i] <= right_array[j]:
      merged_array.append(left_array[i])
      i += 1
    else:
      merged_array.append(right_array[j])
      j += 1

  merged_array.extend(left_array[i:])
  merged_array.extend(right_array[j:])
  return merged_array


array = [5, 3, 2, 1, 4]
sorted_array = merge_sort(array)
print(sorted_array)[1, 2, 3, 4, 5]


**Швидке сортування**

Швидке сортування - це алгоритм сортування, який працює шляхом вибору опорного елемента в масиві та розподілу елементів масиву на дві частини: елементи, які менше опорного елемента, та елементи, які більше або дорівнюють опорному елементу. Потім кожна з цих частин сортується рекурсивно, і процес повторюється до тих пір, поки весь масив не буде відсортований.

python
def quick_sort(array):
  if len(array) <= 1:
    return array

  pivot = array[len(array) // 2]
  smaller = []
  larger = []

  for i in range(len(array)):
    if array[i] < pivot:
      smaller.append(array[i])
    elif array[i] > pivot:
      larger.append(array[i])

  return quick_sort(smaller) + [pivot] + quick_sort(larger)


array = [5, 3, 2, 1, 4]
sorted_array = quick_sort(array)
print(sorted_array)[1, 2, 3, 4, 5]


**Висновок**

Всі три алгоритми сортування є ефективними способами сортування масивів. Однак швидке сортування, як правило, є найефективнішим, особливо для великих масивів.



 **Практична робота номер 3**



