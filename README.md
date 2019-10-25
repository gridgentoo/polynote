## код интерактивной среды вычислений Polynote 

Компания Netflix представила новую интерактивную среду вычислений Polynote, предназначенную для сопровождения процесса научных исследований, обработки и визуализации данных (позволяет сочетать код с научными выкладками и материалами для публикации). Код Polynote написан на языке Scala и распространяется под лицензией Apache 2.0.

Документы в Polynote представляют собой упорядоченный набор ячеек, которые могут содержать код или текст. Каждая ячейка редактируется и исполняется по отдельности. Допускается перегруппировка, удаление и добавление ячеек, но при этом состояние данных для каждой ячейки зависит от вычислений в прошлых ячейках (выполнение сверху-вниз). Подобный подход гарантирует повторяемость определённых в документе вычислений (повторное выполнение документа на любых системах приведёт к тому же результату). Информация о зависимостях и конфигурация сохраняются непосредственно в документе, а не в отдельных файлах. 

В отличие от похожих проектов Jupyter и Zeppelin, новая среда позволяет смешивать в одном документе код на нескольких языках программирования, обеспечивая совместный доступ к данным из кода на нескольких языках (определяется общая схема данных). Например, в одном документе можно совмещать код на языке Scala с применением популярных библиотеки машинного обучения и визуализации для языка Python. На текущем этапе развития реализована поддержка языков Scala, Python, SQL и Vega.    

Из других особенностей Polynote выделяются расширенные средства для редактирования кода и текста, близкие к возможностям интегрированных сред разработки и текстовых процессоров. При редактировании кода поддерживается автодополнение, подсветка мест возникновения ошибок, вывод подсказок для параметров функций и методов. В планах возможность перехода на определения переменных/функций из мест их вызова (jump-to-definition).  

Что касается подготовки документации и отчётов, процесс редактирования теста осуществляется в режиме WYSIWYG, позволяющем сразу наблюдать конечный отформатированный результат. При этом для определения формул предусмотрена возможность вставки выражений в формате LaTeX.

Среда позволяет полностью контролировать процесс выполнения - в области задач показывается какой код сейчас выполняется, и на какой стадии находятся вычисления. Через таблицу символов можно просмотреть все определённые функции и переменные, а также проинспектировать их значение или выполнить визуализацию изменений. Все сбои при выполнении и исключительные ситуации сразу подсвечиваются в редакторе кода. В редакторе в режиме реального времени выделяется выполняемая в текущий момент строка кода.

Обрабатываемые данные отображаются в наглядном виде с разбивкой по типам или в табличном представлении. Поддерживается интеграция с Apache Spark для просмотра, анализа и визуализации больших объёмов данных. Для упрощения визуализации предлагается встроенных редактор графиков и диаграмм. В качестве опции предусмотрена возможность применения для визуализации Vega и Matplotlib. 


# polynote
[![Gitter chat](https://badges.gitter.im/polynote/polynote.png)](https://gitter.im/polynote/polynote)
[![Build status](https://github.com/polynote/polynote/workflows/Build/badge.svg)](https://github.com/polynote/polynote/workflows/Build)

Polynote is an experimental polyglot notebook environment. Currently, it supports Scala and Python (with or without Spark),
SQL, and Vega.

For more information, see [Polynote's website](https://polynote.org)

## Why?

Current notebook solutions, like Jupyter and Zeppelin, are lacking in some fundamental features:

- *Code editing* – the code editing capabilities in most notebook tools leave plenty to be desired. Why can't a notebook
  tool have modern editing capabilities like those you'd find in an IDE? Polynote provides useful autocomplete,
  parameter hints, and more – we're planning to add even more features, like jump-to-definition.
- *Text editing* – you can use the WYSIWYG editor for composing text cells, so you'll know what the text will look like as
  you're writing. TeX equations are also supported.
- *Multi-language support* – Polynote allows you to mix multiple languages in one notebook, while sharing definitions
  seamlessly between them.
- *Runtime insight* – Polynote tries to keep you informed of what's going on at runtime:
    - The tasks area shows you what the kernel is doing at any given time.
    - The symbol table shows you what variables and functions you've defined, so you don't have to scroll around to remind yourself.
    - Compile failures and runtime exceptions are highlighted in the editor (for supported languages), so you can see exactly what's going wrong.

