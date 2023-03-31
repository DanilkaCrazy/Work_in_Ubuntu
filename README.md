# Инструкция по работе в Ubuntu

## <b> Цель работы: </b> научиться работать с виртуальной машиной (в моем случае c Ubuntu), выполнение ряда заданий, установленного в инструкции, и описание к нему, для закрепления практических навыков.

## Ход работы:

### Сначала необходимо разобраться с терминологией, прежде чем приступать к установке.

Что такое Ubuntu? Виртуальная машина? Гипервизор?

Ubuntu — это разрабатываемая сообществом, основанная на ядре Linux операционная система, которая идеально подходит для использования на персональных компьютерах, ноутбуках и серверах. Она содержит все необходимые программы, которые вам нужны: программу просмотра Интернет, офисный пакет для работы с текстами, электронными таблицами и презентациями, программы для общения в Интернет и много других.

Виртуальная машина – это некая компьютерная система (программная и аппаратная), которая позволяет визуализировать и служит для эмуляции некоторой платформы, позволяет разграничивать (изолировать), создавать и определять доступ сред и программ.

Гипервизор -  программа или аппаратная схема, обеспечивающая или позволяющая одновременное, параллельное выполнение нескольких операционных систем на одном и том же хост-компьютере. Гипервизор также обеспечивает изоляцию операционных систем друг от друга, защиту и безопасность, разделение ресурсов между различными запущенными ОС и управление ресурсами. Существует 3 типа гипервизоров.



## 1. Необходимо скачать, установить и настроить Ubuntu в виде виртуальной машины: 

1) скачать с официального сайта Ubuntu дистрибутив в редакции серверной OS Ubuntu Server. https://ubuntu.com/download/server
2) установить данную операционную систему в гипервизор, запустить и настроить её в соответствии с информации из лекции
3) cделать скриншот, в окне гипервизора (в моем случае VirtualBox), виртуальной машины, а также внутри виртуальной машины сделать скриншот с данными о системе и аппаратном обеспечении: 
Окно гипервизора

![Screenshot_6](https://user-images.githubusercontent.com/95550202/229161971-37833f65-70c8-466c-91e7-26f7d9abc611.png)

 
Виртуальная машина с данными

![Screenshot_100](https://user-images.githubusercontent.com/95550202/229162807-e11ff8f6-c1be-4f87-aecc-359ac46135ae.png)

## 2. Далее установим окружение рабочего стола:

Менеджер пакетов – это программа, которая помогает устанавливать и удалять приложения. А еще менеджер пакетов отслеживает зависимости между программами и сохраняет систему в целостности.

dpkg – это программное обеспечение, являющееся основой системы управления пакетами в Debian и ряде других операционных систем, основанных на Debian, например Ubuntu. dpkg  используется для установки, удаления и получения информации о .deb пакетах.

Advanced package tool, или APT - это пользовательский интерфейс свободного программного обеспечения, который работает с основными библиотеками для установки и удаления программного обеспечения в Debian и дистрибутивах Linux на базе Debian.

Synaptic - графический интерфейс для системы управления пакетами apt или проекта Debian а также варианта apt-rpm, используемого в дистрибутивах Conectiva и других.
 
Установка рабочего стола(окружения)

![Screenshot_8](https://user-images.githubusercontent.com/95550202/229163598-49d7bbcc-e8ac-43d4-aff8-49b7519b79fc.png)


Командой sudo apt install kubuntu-desktop скачиваем рабочий стол KDE Plasma (KDE Plasma — пожалуй, самая продвинутая оболочка рабочего стола из всех. При этом она ещё и очень красива. Для KDE разработано множество тем, сторонних расширений и виджетов.)
Если получаем подобную ошибку, значит есть системные незавершенные процессы, которые необходимо завершить следующей командой: 
sudo fuser -vki /…/…/…
Теперь нужно выполнить следующую команду, которая переконфигурирует пакетный менеджер: sudo dpkg --configure -a
И необходимо повторить команду для скачивания рабочего стола: sudo apt install kubuntu-desktop 

До выбора Plasma

![Screenshot_9](https://user-images.githubusercontent.com/95550202/229163822-6f8bd915-ddf4-4ab4-aae8-da4d6b576501.png)


Ждем, и после установки перезагружаем, выбирая в настройках KDE Plasma.

После перезагрузки

![Screenshot_10](https://user-images.githubusercontent.com/95550202/229164123-161d8e6e-b903-47a2-95f4-d96233c09b2d.png)
 
##3. Файловая система и диски

Добавим еще один диск, используя выход из виртуальной машины командой sudo shutdown now в терминале. Далее в программе VirtualBox в Настройках своей виртуальной машины, необходимо перейти в Носители, выбрать SATA-контроллер и добавить новый Диск.
 
Посмотреть дисковое пространство

![Screenshot_11](https://user-images.githubusercontent.com/95550202/229165094-3f2c0d43-9533-4838-b966-27d2bbe05fe6.png)


Чтобы было понятнее, как и для чего работает каждая команда, приведу следующий скриншот со списком необходимых команд:

 ![Screenshot_22](https://user-images.githubusercontent.com/95550202/229165183-97cfba0f-b87e-40d0-9985-6c35d7a55bff.png)

Добавления нового диска

![Screenshot_12](https://user-images.githubusercontent.com/95550202/229165378-df09d681-c8e3-4b31-8a06-fadc0293df04.png)


Далее используем команду для отображения всех дисков, и как видно, наш диск успешно воспринимается виртуальным окружением.

![Screenshot_13](https://user-images.githubusercontent.com/95550202/229165488-f7c0ae95-cdaf-437b-bbf1-3f2b9b6c3bb0.png)

Разделим диск на несколько частей по 4 Гигабайта, его общий размер – 8 Гигабайт (предыдущий слайд).

Добавление наименований и разбиение

![Screenshot_1011](https://user-images.githubusercontent.com/95550202/229165892-88f6d121-49ed-4e61-a910-445fb056f18b.png)

 
Добавление наименований и разбиение 1

![Screenshot_1](https://user-images.githubusercontent.com/95550202/229166412-f16008ba-2e17-4278-a9ac-46c81a7a6cf3.png)

 
Добавление наименований и разбиение 2

![Screenshot_2](https://user-images.githubusercontent.com/95550202/229166448-8d449ee3-1498-4e54-8e02-ec0f86543d41.png)


Теперь перейдем к форматированию диска:

Команда для форматирования

![Screenshot_3](https://user-images.githubusercontent.com/95550202/229166482-fd9ef70e-d9d2-4963-af65-af120c4ecff8.png)
 
Форматирование диска

![Screenshot_4](https://user-images.githubusercontent.com/95550202/229166733-36741f96-f579-4d6b-83bd-a68ceef8dd99.png)


Для монтирования необходимо указывать соответствующую директорию:

![Screenshot_5](https://user-images.githubusercontent.com/95550202/229166911-9df753f9-d859-4118-9f6e-b1a40ef52798.png)

Монтирование диска 

![Screenshot_5](https://user-images.githubusercontent.com/95550202/229167631-dbccf645-52c4-460b-afe7-14db9f80edaa.png)
 
Сохранение смонтированного диска

![Screenshot_6](https://user-images.githubusercontent.com/95550202/229167664-e74b6dfd-d60a-4e7d-83e6-cecfc3d1fc05.png)

 
Визуальное отобрание на раб экране 

![Screenshot_7](https://user-images.githubusercontent.com/95550202/229167714-dbedd6a3-2fb9-424b-b62b-7cc7940357c7.png)

 
Создание рандомного файла 

![Screenshot_8](https://user-images.githubusercontent.com/95550202/229167760-146104a3-61d7-4346-add7-1aad85a81ecd.png)

Установка пакета quote и квотирование 

![Screenshot_9](https://user-images.githubusercontent.com/95550202/229167812-a6c6c133-28a2-43a1-aa63-575c472adf37.png)

Используемые команды для квотирования 

![Screenshot_10](https://user-images.githubusercontent.com/95550202/229167872-ef0aa77e-f479-44d3-9301-b80685e08869.png)
 
Создание tar архива 

![Screenshot_11](https://user-images.githubusercontent.com/95550202/229167973-657c8b4e-1dfb-4804-8dfa-721169e88fd1.png)


Переконвертирование в gzip 

![Screenshot_12](https://user-images.githubusercontent.com/95550202/229168001-ac3671ed-676f-4708-87f0-726787a3657e.png)


## 4. Процессы, аналоги диспетчера задач в Linux и приоритеты в системе

Запущенные процессы при помощи утилит htop, atop, ps можно посмотреть следующим образом при помощи команд:

 
Проcмотр при помощи ps

В Linux есть очень большое количество утилит для решения различных задач по управлению процессами. Это и такие многофункциональные решения, как htop, top, а также простые утилиты, например, ps, kill, killall, who и т д. Я не буду рассматривать в этой статье графические утилиты, и top тоже рассматривать не буду. Первое потому что слишком просто, второе - потому что htop лучше. Мы остановимся на работе с программой htop и ее аналогами в форме утилит в стиле GNU, одна утилита - одна функция.
Давайте установим htop, если она у вас еще не установлена. В Ubuntu это делается так:
sudo apt install htop
В других дистрибутивах вам нужно просто использовать свой менеджер пакетов. Имя пакета такое же.

 
Установка утилиты htop

Посмотреть запущенные процессы можно аналогично. Открыв htop, мы сразу видим список запущенных процессов. Конечно, здесь отображены не все процессы linux, их-то в системе очень много, вы уже знаете, все они на один экран не поместятся. К отображению можно добавить и дополнительные параметры, но эти главные. Добавить параметры можно с помощью меню Setup. Там все очень просто, читайте подсказки и следуйте указаниям. Очень важной особенностью программы есть то, что вы можете сортировать процессы в Linux по нужному параметру. Просто кликните по названию параметра, оно выделится зеленым и будет выполнена сортировка.

Теперь попробуем изменить приоритет процессов. Список процессов, это хорошо. Но иногда, когда какой-нибудь процесс завис и нужно убить процесс Linux или нам нужно провести с ним какие-либо действия, нужно выделить этот процесс из списка, узнать его PID и информацию о нем.
Чтобы найти процесс linux в htop можно использовать кнопку F3. Нажмите F3 и наберите нужное слово. Для поиска процессов в htop можно использовать также фильтр htop. Нажмите F4, введите слово и будут выведены только процессы linux, имя которых включает это слово.
В утилите ps фильтрации нет, но зато мы можем использовать утилиту grep, перенаправив вывод ps на нее чтобы найти процесс linux:
ps aux | grep chromium
Это очень часто употребляемая команда.
Приоритет процесса linux означает, насколько больше процессорного времени будет отдано этому процессу по сравнению с другими. Так мы можем очень тонко настроить какая программа будет работать быстрее, а какая медленнее. Значение приоритета может колебаться от 19 (минимальный приоритет) до -20 - максимальный приоритет процесса linux. Причем, уменьшать приоритет можно с правами обычного пользователя, но чтобы его увеличить нужны права суперпользователя.
В htop для управления приоритетом используется параметр Nice. Напомню, что Priv, это всего лишь поправка, она в большинстве случаев больше за Nice на 20. Чтобы изменить приоритет процесса просто установите на него курсор и нажимайте F7 для уменьшения числа (увеличения приоритета) или F8 - для увеличения числа.
Но и для решения этой задачи управления процессами Linux необязательно использовать htop. Вы можете сделать все и другими командами. Например, команда nice. С помощью нее вы можете указать приоритет для запускаемого процесса:
nice -n 10 apt-get upgrade
Или изменить приоритет для уже существующего по его pid:
renice -n 10 -p 1343

 
Изменение приоритета процесса через nicе
Чтобы наглядней показать завершение процессов в linux, создадим пару простых процессов командой sleep … & (засыпание компьютера на х секунд). Заранее можно выйти из него, используя сочетание клавиш Ctrl + C или Ctrl + Z.
Вначале завершим один какой-либо процесс при помощи kill, для этого используем ID этого процесса. Либо завершим их все при помощи команды killall + имя самого процесса (то есть sleep).
 
Завершение процессов
Ограничение процессов c помощью команды ulimit и конфигурационного файла /etc/security/limits.conf

Управление процессами в Linux позволяет контролировать практически все. Вы уже видели что можно сделать, но можно еще больше. С помощью команды ulimit и конфигурационного файла /etc/security/limits.conf вы можете ограничить процессам доступ к системным ресурсам, таким как память, файлы и процессор. Например, вы можете ограничить память процесса Linux, количество файлов и т д.
Запись в файле имеет следующий вид:
<домен> <тип> <элемент> <значение>
•	домен - имя пользователя, группы или UID
•	тип - вид ограничений - soft или hard
•	элемент - ресурс который будет ограничен
•	значение - необходимый предел
Жесткие ограничения устанавливаются суперпользователем и не могут быть изменены обычными пользователями. Мягкие, soft ограничения могут меняться пользователями с помощью команды ulimit.
Рассмотрим основные ограничения, которые можно применить к процессам:
•	nofile - максимальное количество открытых файлов
•	as - максимальное количество оперативной памяти
•	stack - максимальный размер стека
•	cpu - максимальное процессорное время
•	nproc - максимальное количество ядер процессора
•	locks - количество заблокированных файлов
•	nice - максимальный приоритет процесса
Например, ограничим процессорное время для процессов пользователя felkan:
felkan hard nproc 20
Посмотреть ограничения для определенного процесса вы можете в папке proc:
cat /proc/PID/limits
 
## 5. Управление пользователями и группами

Список пользователей системы можно получить при помощи команды 
ls – l /home

 
Список пользователей системы
Добавить нового пользователя можно при помощи команды 
sudo useradd -m user1

 
Add new user


Запретить пользователю user1 интерактивный вход в систему можно при использовании следующей команды:

 

Сменить владельца директории или файла через clown можно следующим образом:
 

Используйте ls -l команду, чтобы узнать, кому принадлежит файл или к какой группе принадлежит файл:

ls -l filename.txt

Чтобы изменить владельца файла, используйте chown команду, за которой следует имя пользователя нового владельца и целевой файл в качестве аргумента:

chown USER FILE

Сменить пароль нового пользователя можно при помощи утилиты passwd. Это очень мощная утилита, она позволяет не только менять пароль, но и управлять сроком его жизни.

 


Для создания групп в Linux используется команда groupadd

 

Для добавления пользователя используется следующая команда:

 


Locale (локаль) – это региональные настройки операционной системы.

Каждая GNU/Linux система поставляется с конкретными региональными настройками. Эти настройки влияют на язык:

•	интерфейса,
•	сообщений об ошибках;
•	справочной информации;
•	вывода консольных утилит.
Но locale влияет не только на язык. Дополнительно это влияет на формат чисел, даты и времени, денежной валюты и другого.

Чтобы сменить локаль или кодировку, или сгенерировать новые, можно использовать следующие команды:

Просмотр локалей:

  

Генерация локалей:

 

Наиболее популярный и поддерживаемый в большинстве дистрибутивов способ установки часового пояса для всех пользователей - с помощью символической ссылки /etc/localtime на файл нужного часового пояса.
Список доступных часовых поясов можно посмотреть командой:

 ls /usr/share/zoneinfo/

 

Сначала создайте резервную копию текущего часового пояса:

 cp /etc/localtime /etc/localtime.bak

Для создания символической ссылки используйте команду ln -sf. Файл зоны нужно выбрать из доступных в системе. Например, мой часовой пояс – Бишкек, для установки будет использоваться следующая команда:

 

Вернул назад екбшное время:

 

## 6. BASH Скрипты

Nano – это довольно простой консольный текстовый редактор Linux и предустановлен на большинстве дистрибутивов. Он будет полезен, если большую часть работы вы выполняете в консоли или же подключаетесь удалённо по SSH. Он имеет функцию подсветки синтаксиса, а также полезную панель с подсказками горячих клавиш.

Редактор текстовых файлов Linux под названием Vim гораздо менее дружелюбен к пользователю. Перед его использованием необходимо ознакомиться с основными горячими клавишами и командами, а также настроить приложение под себя. С помощью плагинов можно расширить функционал редактора практически до уровня IDE. Однако, его сильной стороной остаётся именно большой набор команд, который позволяет выполнять многие действия быстрее, чем с графическим интерфейсом.
 


 

 

 

Командная оболочка (shell) обеспечивает взаимодействие между пользователем и средой операционной системы Linux. Она является специализированным программным продуктом, который обеспечивает выполнение команд и получения результатов их выполнения, или, если совсем уж упрощенно, оболочка - это программа, которая предназначена для обеспечения выполнения других программ по желанию пользователя.

Для просмотра истории команд в терминале можно набрать history, и мы получим последние 500 (по умолчанию) использованных команд. Команда clear очистит консоль.

 

Стереть историю команд можно также с помощью history -c

Утилита more предназначена для постраничного просмотра файлов в терминале Linux. Своим названием она обязана надписи more (в русскоязычном варианте — дальше), появляющейся внизу каждой страницы.

  


Команда more linux — одна из самых примитивных команд для работы с текстом. Её ближайшая родственница — команда less — обладает куда большим набором опций и дополнительных возможностей.
less — позволяет перематывать текст не только вперёд, но и назад, осуществлять поиск в обоих направлениях, переходить сразу в конец или в начало файла.

Перенаправление ввода / вывода позволяет заменить один из этих файлов на свой. Например, вы можете заставить программу читать данные из файла в файловой системе, а не клавиатуры, также можете выводить ошибки в файл, а не на экран и т д. Все это делается с помощью символов "<" и ">".

 

Опция -b заставляет программу работать в не интерактивном пакетном режиме, а n - повторяет операцию пять раз, чтобы получить информацию обо всех процессах.

Для перенаправления можно использовать символы >> в предыдущей команде в консоли вместо >.

Для написания скрипта Hello world, используем текстовый редактор nano и создадим в нем скрипт, затем сохраняем его

 

Программу можно расширить и аналогично запустить скрипт:

 

Alias Linux - это, по сути, ярлыки команд Linux. Команда alias позволяет пользователю запускать любую команду или даже группу команд, в том числе с опциями, параметрами и файлами, вводом одного слова или даже символа. Это очень удобно во многих ситуациях, например чтобы не вводить полностью команду при обновлении или же очень быстро перемещаться по каталогам.

 

