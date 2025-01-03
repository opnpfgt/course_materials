# HW 3. Functions 
> *This is the repo for the third homework of the BI Python 2024/2025 course*

### Homework description

В качестве данного ДЗ вам будет необходимо написать свою собственную утилиту для работы с последовательностями нуклеиновых кислот.

#### Основное задание

Необходимо реализовать программу `dna_rna_tools.py`. Эта программа обязательно содержит функцию `run_dna_rna_tools`, а также любые другие функции которые вам понадобятся. Функция `run_dna_rna_tools` принимает на вход произвольное количество аргументов с последовательностями ДНК или РНК (*str*), а также название процедуры которую нужно выполнить (это всегда последний аргумент, *str*, см. пример использования). После этого она делает заданное действие над всеми переданными последовательностями и *возвращает* результат. 

**Список процедур:**

- `transcribe` — вернуть транскрибированную последовательность
- `reverse` — вернуть развёрнутую последовательность
- `complement` — вернуть комплементарную последовательность
- `reverse_complement` — вернуть обратную комплементарную последовательность
- любые дополнительные процедуры на ваш страх и риск (опционально)

**Пример использования**

```python
run_dna_rna_tools('ATG', 'transcribe') # 'AUG'
run_dna_rna_tools('ATG', 'reverse') # 'GTA'
run_dna_rna_tools('AtG', 'complement') # 'TaC'
run_dna_rna_tools('ATg', 'reverse_complement') # 'cAT'
run_dna_rna_tools('ATG', 'aT', 'reverse') # ['GTA', 'Ta']
```

**Требования к программе:**

- Программа должна принимать любое количество позиционых аргументов. Как это сделать - вам предлагается разобраться самостоятельно (подсказка для гуглинга: `*args **kwargs`)
- Программа должна сохранять регистр символов (напр. **complement AtGc** это **TaCg**)
- Если подана одна последовательность - возвращается строка с результатом. Если подано несколько - возвращается список из строк. 
- Программа должна работать **только** с последовательностями нуклеиновых кислот. К примеру, последовательность AUTGC не может существовать, так как содержит T и U, такие случаи нужно как-то отслеживать.
- **НЕ ИСПОЛЬЗУЙТЕ** `input()`! От вас требуются только функции (только определение, не надо их вызывать)

**Требования к выполнению ДЗ:**

- Запрещается использование сторонних модулей.
- Не пишите полотно кода в главной функции, структурируйте код, создавайте доп. функции под каждую конкретную задачу.
- **ОБЯЗАТЕЛЬНО** запустите `flake8` и `pytest` перед сдачей ДЗ (см. ниже)
    
    Запустив эти 2 программы - сделайте скриншоты успешного результата и добавьте их в репозиторий в виде файлов `flake8.png` и `pytest.png` (см. разбалловку)
- Файлы `*_test.py` редактировать запрещено! Однако посмотреть какие же автопроверки будут у преподавателя - можно:). Если случайно что то поменяли, то что делать можно посмотреть [тут](https://plausible-cannon-091.notion.site/1089bcfdc5fa80fa9626c8ce9afbe4c2?pvs=4).

### [Автопроверки](https://plausible-cannon-091.notion.site/1089bcfdc5fa80fa9626c8ce9afbe4c2?pvs=4), `flake8` и `pytest`

При оценке вашего ДЗ мы будем:

1. Проверять корректность работы
2. Проверять стиль кода
3. Делать ревью

Первые 2 пункта делаются автоматически (подобно тому как работает бот на курсе по Статистике). Вы результат этих проверок получите только уже вместе с оценкой, однако, вы можете запустить точно такие же автопроверки у себя локально перед сдачей. Как это сделать посмотреть можно тут: [Автопроверки кода](https://plausible-cannon-091.notion.site/1089bcfdc5fa80fa9626c8ce9afbe4c2?pvs=4)



### Как получить и сдать ДЗ


**1. Как получить ДЗ** 

С этого момента мы начнем работать через систему GitHub Classrom. Она удобна тем что там автоматизированы некоторые вещи для учебы.

1) Примите задание по ссылке в Google Class (выберите себя в предложенном списке)
2) Для вас будет создан ваш индивидуальный приватный репозиторий. 
3) Склонируйте его (`git clone`) и работайте локально.

> Тут **НЕ НУЖНО** создавать новых веток, бот GitHub Classrom сам со всем разберется

Просто склонируйте репозиторий и сразу пишите в нем код.

**2. Как сдать ДЗ** 

1) Сперва проверьте что вы всё сделали как хотели
2) Запустите `flake8` и `pytest`, приложите скриншоты в реп
3) Потом просто сделайте `git push` и всё:). Бот сам создает pull-request, в котором вы сможете найти фидбек преподавателя.
4) Отметьте в Google Class задание как сданное



### Pазбалловка

- За каждую из 4 процедур: **15 баллов**
- За правильную работу `run_dna_rna_tools`: **20 баллов**
- Скриншот успешного `flake8`: **10 баллов**
- Скриншот успешного `pytest`: **10 баллов**

Бонус:
- За каждую доп. процедуру:  **5 баллов** (макс. можно получить 15 доп. баллов)

Однако:
- `pytest` выдает ошибку: *-10 баллов*
- Использование `input()`: *-20 баллов*
- Если был изменен файл `*_test.py` - за ДЗ ставится *0 баллов* (можно пересдать один раз - вернув файл в исходный вид)
- Замечания по стилю кода *в этом ДЗ* не вляют на оценку

### **Предполагаемый учебный результат**

Это задание позволит лучше разобраться с системой Git на практике, потреннироваться в написании собственных биоинформатических функций, а также лучше осознать такие вещи как распаковка, args и kwargs.

Удачи! ✨✨