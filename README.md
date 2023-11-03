---

### Задание 1. СУБД

### Кейс
Крупная строительная компания, которая также занимается проектированием и девелопментом, решила создать 
правильную архитектуру для работы с данными. Ниже представлены задачи, которые необходимо решить для
каждой предметной области. 

Какие типы СУБД, на ваш взгляд, лучше всего подойдут для решения этих задач и почему? 
 
1.1. Бюджетирование проектов с дальнейшим формированием финансовых аналитических отчётов и прогнозирования рисков.
СУБД должна гарантировать целостность и чёткую структуру данных.

1.1.* Хеширование стало занимать длительно время, какое API можно использовать для ускорения работы? 

1.2. Под каждый девелоперский проект создаётся отдельный лендинг, и все данные по лидам стекаются в CRM к 
маркетологам и менеджерам по продажам. Какой тип СУБД лучше использовать для лендингов и для CRM? 
СУБД должны быть гибкими и быстрыми.

1.2.* Можно ли эту задачу закрыть одной СУБД? И если да, то какой именно СУБД и какой реализацией?

1.3. Отдел контроля качества решил создать базу по корпоративным нормам и правилам, обучающему материалу 
и так далее, сформированную согласно структуре компании. СУБД должна иметь простую и понятную структуру.

1.3.* Можно ли под эту задачу использовать уже существующую СУБД из задач выше и если да, то как лучше это 
реализовать?

1.4. Департамент логистики нуждается в решении задач по быстрому формированию маршрутов доставки материалов 
по объектам и распределению курьеров по маршрутам с доставкой документов. СУБД должна уметь быстро работать
со связями.

1.4.* Можно ли к этой СУБД подключить отдел закупок или для них лучше сформировать свою СУБД в связке с СУБД 
логистов?

1.5.* Можно ли все перечисленные выше задачи решить, используя одну СУБД? Если да, то какую именно?

*Приведите ответ в свободной форме.*

---

**Выполнение задания 1.**

**Задача 1.1**  Для данного типа задач можно рассмотреть использование реляционных СУБД, потому что они поддерживают SQL-запросы, что позволяет удобно анализировать и формировать отчеты. 
 Из основных популярных реляционных СУБД можно предложить следующие: PostgeSQL, MySQL, Microsoft SQL Server.
 
 
**Задача 1.1*** Для ускорения хеширования можно использовать специализированные алгоритмы и библиотеки, такие как:
1. OpenSSL: Оно предоставляет широкий набор криптографических алгоритмов, включая хеширование. Оптимизированное для процессорной архитектуры OpenSSL может обеспечить высокую производительность.  
2. Intel Integrated Performance Primitives (IPP): Производительные библиотеки, разработанные Intel, включают оптимизированные алгоритмы хеширования и другие криптографические функции, специально адаптированные для аппаратных возможностей Intel.  
3. Intel Advanced Encryption Standard New Instructions (AES-NI): Если хеширование выполняется с использованием алгоритма AES, то можно воспользоваться аппаратной акселерацией AES-NI на поддерживаемых процессорах Intel.  
4. Графический процессор (GPU): Для некоторых алгоритмов хеширования можно использовать вычислительные возможности современных графических процессоров (например, CUDA или OpenCL), которые позволяют выполнить параллельные вычисления и ускорить процесс хеширования.    
Стоит учитывать, что выбор оптимального API зависит от используемого алгоритма хеширования, целевой платформы и других требований приложения.  
Помимо выбора алгоритма, убедитесь, что вы используете наиболее оптимизированную библиотеку для вашего языка программирования. Для Python, например, вы можете использовать библиотеку hashlib или cryptography.  
 
**Задача 1.2** Для лендингов и CRM лучше всего использовать реляционные СУБД, такие как MySQL или PostgreSQL. Они обеспечивают гибкость и скорость работы с данными, а также имеют широкий спектр функций для управления и анализа информации.

**Задача 1.2*** Да, можно использовать одну СУБД для лендингов и CRM. Например, MySQL или PostgreSQL будут достаточно гибкими и быстрыми для этих задач. Однако, если есть другие системы, которые требуют использования другой СУБД, то может потребоваться использовать несколько СУБД.

**Задача 1.3** Для создания базы данных, которая будет соответствовать всем предъявленным выше требованиям, можно выбрать реляционные системы управления базами данных, такие как MySQL или PostgreSQL. Оба эти решения имеют простой и понятный интерфейс, позволяющий легко создавать базы данных с нужной структурой. Кроме того, они обладают высокой производительностью и надежностью, что важно для хранения корпоративных данных. Также можно реализовать на NoSQL СУБД, если хранить данные не ввиде таблиц, а в виде документов либо коллекций.

**Задача 1.3*** Можно использовать уже существующую СУБД такую как MySQL и PostgreSQL, которые подходят для реализации такой задачи. 
Обе СУБД обладают простой и понятной структурой и могут быть использованы для создания базы данных, которая будет содержать информацию о корпоративных нормах и правилах, обучающем материале и т. д.
Чтобы реализовать это, можно создать таблицы, которые соответствуют различным аспектам компании. Например, можно создать таблицу "Norms" для хранения информации о нормах и правилах, таблицу "TrainingMaterials" для хранения обучающих материалов и т. д. 
Каждая таблица должна иметь уникальный идентификатор для каждой записи, а также столбцы, соответствующие различным атрибутам каждой записи. Например, таблица "Norms" может иметь столбцы "ID", "Title", "Description" и т. д.
Также можно создать связи между таблицами, если данные требуют такого отношения. Например, если есть таблица "Employees", которая содержит информацию о сотрудниках, и таблица "Norms", которая содержит ссылку на конкретные нормы, связанные с каждым сотрудником.
При создании базы данных потребуется использовать SQL, чтобы создать таблицы, определить связи и выполнить другие операции по настройке базы данных. В обоих MySQL и PostgreSQL есть средства создания таблиц и внесения данных.
В итоге, выбор между MySQL и PostgreSQL зависит от предпочтений и требований. Они подходят для создания простой и понятной структуры базы данных.

**Задача 1.4** Для решения этих задач можно использовать СУБД, такую как PostgreSQL или Oracle. Эти СУБД позволяют быстро работать со сложными связями между объектами и эффективно распределять ресурсы. Можно подключить отдел закупок к СУБД PostgreSQL или Oracle. Обе эти СУБД предоставляют широкие возможности для создания и управления базами данных, которые могут быть использованы в разных отделах компании, включая отдел закупок. 


**Задача 1.4*** Для отдела закупок можно создать отдельную базу данных, связанную с базой данных отдела логистики. Это позволит избежать дублирования данных и упростить процесс обмена информацией между отделами. Однако решение о том, нужно ли формировать отдельную СУБД для отдела закупок или использовать СУБД логистов, зависит от множества факторов, включая объем данных, специфические требования и процессы работы отделов, а также потребности в интеграции данных между отделами. Важно учитывать, что в случае разделения СУБД между отделами, возникает необходимость взаимодействия и интеграции данных между ними. Это может потребовать дополнительных усилий для синхронизации, обмена или экспорта-импорта данных между СУБД.


**Задача 1.5*** Да, все перечисленные задачи можно решить, используя одну СУБД. Одной из самых популярных и подходящих для данных задач является СУБД PostgreSQL. PostgreSQL обладает мощными возможностями работы со связанными данными, включая поддержку графовых баз данных с помощью расширения Graph. Это позволяет эффективно моделировать связи между объектами, что полезно при формировании маршрутов доставки и распределении курьеров.

---
