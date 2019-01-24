# NativeSleep_1C
Внешняя Native компонента для 1C 8.3, которая реализует метод sleep(), делающий паузу выполнения кода. Пауза для большой устойчивости сделана платформозависимой и требует WinAPI. Ид компоненты - AddIn.AddInNativeSleep.NativeSleep. Компонента работает с 32 и 64 битной платформой 1С

Компонента имеет следующие методы:

<b>Sleep (Милисекунд)</b> - переводит в ожидающее (sustain) состояние текущий тред без нагрузки на ядро CPU.

Пример использования на сервере
``` bsl
    УстановитьВнешнююКомпоненту("ОбщийМакет.AddInNativeSleep"); // из макета с zip архивом
    ПодключитьВнешнююКомпоненту("ОбщийМакет.AddInNativeSleep", "AddInNativeSleep", ТипВнешнейКомпоненты.Native);
    Компонента = Новый("AddIn.AddInNativeSleep.NativeSleep");
    Компонента.Sleep(1000) - сон на 1 секунду, блокирующий метод
```

## Установка в конфигурацию

1. Скачать архив в каталоге dlll_compiled/NativeSleep.zip
2. Загрузить в конфигурацию в качестве общего макета с двоичными данными

## Разворачивание окружения разработки

1. Установить Visual Studio 2015 (2017 не поддерживается). При установке выбрать среди обязательных компонентов также WIndows SDK 10 
2. Запустть файл проекта в каталоге example/AddIn.sln
