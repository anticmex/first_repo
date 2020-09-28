# first_repo.github.io

## бывшее название Репозитария
**Текущее** название - *First_repo*

Забавный список:
	* еще забавнее
	* и еще забавнее

[ссылки на яндекс](yandex.ru)

```html
<head> Hellow WorK! </head>



```
(^[А-Яа-я]+([^,]|[^ ]))([А-Яа-я]+([^,]|[^ ]))([А-Яа-я]+([^,]|[^ ]))
(^[А-Яа-я]+)(,*| *)([А-Яа-я]+)(.)([А-Яа-я]+)
(^[А-Яа-я]+)(,*| *)([А-Яа-я]+)((.)([А-Яа-я]+)|())(,*)(([А-Яа-я]+)|())(,*)(([а-яa-zА-Я ]+( . )[а-яa-zА-Я ]+)|([а-яa-zА-Я ]+)|())(,*)((\D)|())((\d((\D+)|()))[0-9]{3}((\D+)|())((\d+)|())((\D)|())|())

(^[А-Яа-я]+)(,*| *)([А-Яа-я]+)((.)([А-Яа-я]+)|())(,*)(([А-Яа-я]+)|())(,*)(([а-яa-zА-Я ]+( . )[а-яa-zА-Я ]+)|([а-яa-zА-Я ]+)|())(,*)((\W)|())((\d\D{1,3}\d{3}\D{1,3}\d+\D\d+((\d+)|(\D\d+)))|(\d+)|())((\D+доб\D+[0-9]+)|())((\W{1,2})|())(([0-9A-Za-z((.)|())]+@\w+.\w+)|())

from pprint import pprint
import re
# читаем адресную книгу в формате CSV в список contacts_list
import csv

pattern = r"(^[А-Яа-я]+)(,*| *)([А-Яа-я]+)(.)(([А-Яа-я]+)|())(,*)(([А-Яа-я]+)|())(,*)(([а-яa-zА-Я ]+( . )[а-яa-zА-Я " \
          r"]+)|([а-яa-zА-Я ]+)|())(,*)((\W)|())((\d\D{1,3}\d{3}\D{1,3}\d+\D\d+((\d+)|(\D\d+)))|(\d+)|())((\D+доб\D+[" \
          r"0-9]+)|())((\W{1,2})|())(([0-9A-Za-z((.)|())]+@\w+.\w+)|())"

#pattern = re.compile(pattern)

with open("phonebook_raw.csv", encoding='utf-8') as f:
    rows = csv.reader(f, delimiter=",")
    contacts_list = list(rows)



# TODO 1: выполните пункты 1-3 ДЗ
# ваш код

# pattern = r"(\w+( |,)\w+( |,)\w+(вич|вна))"
# pattern = r"(.*вич|.*вна)(,*)([А-Я]\w+)(,*)"

new_dict = {}
for element in contacts_list:
    #print(element)
    str_element = ",".join(element)
    result = re.search(pattern, str_element)
    if result is not None:
        print(result[5])
    #print(result)
    '''if result is None:
        str_element = ",".join(element)
        result = pattern.search(str_element)

    if result is not None:
        new_result = str_element[result.start():result.end()]
        new_result = re.sub('[,]', ' ', new_result)
        print(f'вот что получилось = {new_result}')
        #print(re.sub('[,]', ' ', new_result))
        new_list = new_result.split(" ")
        new_dict = {'first_name': new_list[0], 'second_name': new_list[1], 'third_name': new_list[2]}

print(new_dict)'''





# TODO 2: сохраните получившиеся данные в другой файл
# код для записи файла в формате CSV
'''with open("phonebook.csv", "w") as f:
  datawriter = csv.writer(f, delimiter=',')
  # Вместо contacts_list подставьте свой список
  datawriter.writerows(contacts_list)'''

