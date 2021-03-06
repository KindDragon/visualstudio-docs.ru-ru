---
title: Фрагменты кода Visual C++
ms.date: 11/04/2016
ms.topic: reference
author: corob-msft
ms.author: corob
manager: markl
dev_langs:
- CPP
ms.workload:
- cplusplus
ms.openlocfilehash: db6ea1e233d32872322926a4d75b847ee6a49ba3
ms.sourcegitcommit: 68f893f6e472df46f323db34a13a7034dccad25a
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/15/2020
ms.locfileid: "77277829"
---
# <a name="visual-c-code-snippets"></a>Фрагменты кода Visual C++

С помощью фрагментов кода в Visual Studio можно добавлять часто используемый код в файлы кода C++. В целом, фрагменты кода используются так же, как в C#, но набор фрагментов кода по умолчанию отличается.

Вы можете добавить фрагмент кода в определенное место в коде (то есть вставить его) или заключить выделенный код во фрагмент кода.

## <a name="insert-a-code-snippet"></a>Вставка фрагмента кода

Чтобы вставить фрагмент кода, откройте файл кода C++ ( *.cpp* или *.h*), щелкните в любом месте внутри файла и выполните одно из указанных ниже действий:

- Щелкните правой кнопкой мыши, чтобы открыть контекстное меню, и выберите пункт **Вставить фрагмент**.

- В меню **Правка > IntelliSense** выберите пункт **Вставить фрагмент**.

- Нажмите клавиши **CTRL**+**K**+**X**

Должен появиться список вариантов, начинающийся с **#if**. Если выбрать **#if**, в файл должен добавиться следующий код:

```cpp
#if 0

#endif // 0
```

После этого **0** можно заменить на нужное условие.

## <a name="use-a-code-snippet-to-surround-selected-code"></a>Добавление фрагмента кода вокруг выделенного кода

Чтобы заключить выделенный код во фрагмент кода, выделите одну или несколько строк и выполните одно из указанных ниже действий.

- Щелкните правой кнопкой мыши, чтобы открыть контекстное меню, и выберите пункт **Заключить в**.

- В меню **Правка** > **IntelliSense** выберите пункт **Заключить в**.

- На клавиатуре нажмите клавиши **CTRL**+**K**+**S**

Выберите **#if**. Результат должен быть примерно таким:

```cpp
#if 0
#include "pch.h"  // or whatever line you had selected
#endif // 0
```

После этого 0 можно заменить на нужное условие.

## <a name="where-can-i-find-a-complete-list-of-the-c-code-snippets"></a>Где можно найти полный список фрагментов кода C++?

Чтобы просмотреть полный список фрагментов кода C++, откройте **диспетчер фрагментов кода** (в меню **Сервис**) и выберите для параметра **Язык** значение **Visual C++** . В окне ниже разверните раздел **Visual C++** . Вы увидите список имен всех фрагментов кода C++ в алфавитном порядке.

Имена большинства фрагментов кода вполне очевидны, но некоторые могут вызвать путаницу.

## <a name="class-vs-classi"></a>Class и classi

Фрагмент кода **class** содержит определение класса `MyClass` с соответствующими конструктором и деструктором по умолчанию, определения которых находятся вне класса:

```cpp
class MyClass
{
public:
    MyClass();
    ~MyClass();

private:

};

MyClass::MyClass()
{
}

MyClass::~MyClass()
{
}
```

Фрагмент кода **classi** также содержит определение класса `MyClass`, но его конструктор и деструктор по умолчанию определены внутри определения класса:

```cpp
class MyClass
{
public:
    MyClass()
    {
    }

    ~MyClass()
    {
    }

private:

};
```

## <a name="for-vs-forr-vs-rfor"></a>Сравнение for, forr и rfor

Есть три различных фрагмента **for**, предоставляющих разные циклы `for`.

Фрагмент **rfor** предоставляет цикл for [на основе диапазона](/cpp/cpp/range-based-for-statement-cpp) (ссылку). Эта конструкция предпочтительнее, чем циклы `for` на основе индекса.

```cpp
for (auto& i : v)
{

}
```

Фрагмент **for** предоставляет цикл `for`, в качестве условия которого выступает длина объекта (в `size_t`).

```cpp
for (size_t i = 0; i < length; i++)
{

}
```

Фрагмент **forr** предоставляет обратный цикл `for`, в качестве условия которого выступает длина объекта (в виде целого числа).

```cpp
for (int i = length - 1; i >= 0; i--)
{

}
```

## <a name="the-destructor-snippet-"></a>Фрагмент деструктора (~)

Фрагмент деструктора ( **~** ) ведет себя по-разному в разных контекстах. Если вставить его в класс, он предоставит деструктор для этого класса. Допустим, имеется такой код:

```cpp
class SomeClass {

};
```

Если вставить фрагмент деструктора, добавится деструктор для класса `SomeClass`:

```cpp
class SomeClass {
    ~SomeClass()
    {

    }
};
```

При попытке вставить фрагмент деструктора вне класса будет добавлен деструктор с именем-заполнителем:

```cpp
~TypeNamePlaceholder()
{
```

## <a name="see-also"></a>См. также

- [Фрагменты кода](../ide/code-snippets.md)