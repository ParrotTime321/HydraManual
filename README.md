# HydraManual

Синтаксис: hydra [[[-l LOGIN|-L FILE] [-p PASS|-P FILE]] | [-C FILE]] [-e nsr] [-o FILE] [-t TASKS] [-M FILE [-T TASKS]] [-w TIME] [-W TIME] [-f] [-s PORT] [-x MIN:MAX:CHARSET] [-c TIME] [-ISOuvVd46] [-m MODULE_OPT] [service://server[:PORT][/OPT]]
Опцыъ:
  -R        Відновлення попереднього перерваного сеансу
  -I        Ігнорувати існуючий файл відновлення (не чекати 10 секунд)
  -S        Виконати SSL-підключення
  -s PORT   Якщо служба працює на іншому порту за замовчуванням, вкажіть його тут
  -l LOGIN або -L FILE  Авторизуватися під ім'ям LOGIN, або завантажити кілька логінів з FILE
  -p PASSWORD  або -P FILE  Спробувати пароль PASS, або завантажити кілька паролів з FILE
  -x MIN:MAX:CHARSET  Генерація паролів методом перебору, введіть "-x -h" для довідки
  -y        Вимкнути використання символів при переборі паролів, див. вище
  -r        Використовувати не випадковий метод перемішування для опції -x
  -e nsr    Спробувати "n" нульовий пароль, "s" пароль як логін і/або "r" обернений логін
  -u        Цикл навколо користувачів, а не паролів (ефективно! мається на увазі з -x)
  -C FILE   Формат "login:pass", розділений двокрапкою, замість опцій -L/-P
  -M FILE   Список серверів для атаки, один запис на рядок, ':' для вказівки порту
  -o FILE   Записати знайдені пари login/password в FILE, а не на стандартний вивід
  -b FORMAT Вказати формат для -o FILE: текст (за замовчуванням), json, jsonv1
  -f / -F   Вийти, коли знайдена пара login/pass (-M: -f для кожного хоста, -F глобально)
  -t TASKS  Виконати завдання кількість з'єднань паралельно на кожну ціль (за замовчуванням: 16)
  -T TASKS  Виконати завдання з'єднань паралельно в цілому (для -M, за замовчуванням: 64)
  -w / -W TIME  Час очікування відповіді (32) / між з'єднаннями на кожен потік (0)
  -c TIME   Час очікування на спробу входу для всіх потоків (застосовується -t 1)
  -4 / -6   Використовувати IPv4 (за замовчуванням) / IPv6 адреси (завжди вкладайте в [] також у -M)
  -v / -V / -d  Режим розширеного виводу / показати login+pass для кожної спроби / режим налагодження
  -O        Використовувати старий SSL v2 і v3
  -K        Не повторювати невдачі (добре для масового сканування -M)
  -q        Не виводити повідомлення про помилки з'єднання
  -U        Деталі використання модуля сервісу
  -m OPT    Опції, що специфічні для модуля, див. вивід -U для інформації
  -h        Більше параметрів командного рядка (complete help)
  SERVER    Ціль: DNS, IP або 192.168.0.0/24 (або -M параметр)
  SERVICE   Сервіс для взлому (список підтримуваних протоколів дивіться нижче)
  OPT       Деякі сервісні модулі підтримують додаткове введення (-U для довідки модуля)
