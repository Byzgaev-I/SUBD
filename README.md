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

**1.1**  Для данного типа задач можно рассмотреть использование реляционных СУБД, потому что они поддерживают SQL-запросы, что позволяет удобно анализировать и формировать отчеты. 
 Из основных популярных реляционных СУБД можно предложить следующие: PostgeSQL, MySQL, Microsoft SQL Server.
 
 
**1.1*** Для ускорения хеширования можно использовать специализированные алгоритмы и библиотеки, такие как:
1. OpenSSL: Оно предоставляет широкий набор криптографических алгоритмов, включая хеширование. Оптимизированное для процессорной архитектуры OpenSSL может обеспечить высокую производительность.  
2. Intel Integrated Performance Primitives (IPP): Производительные библиотеки, разработанные Intel, включают оптимизированные алгоритмы хеширования и другие криптографические функции, специально адаптированные для аппаратных возможностей Intel.  
3. Intel Advanced Encryption Standard New Instructions (AES-NI): Если хеширование выполняется с использованием алгоритма AES, то можно воспользоваться аппаратной акселерацией AES-NI на поддерживаемых процессорах Intel.  
4. Графический процессор (GPU): Для некоторых алгоритмов хеширования можно использовать вычислительные возможности современных графических процессоров (например, CUDA или OpenCL), которые позволяют выполнить параллельные вычисления и ускорить процесс хеширования.    
Стоит учитывать, что выбор оптимального API зависит от используемого алгоритма хеширования, целевой платформы и других требований приложения.  
Помимо выбора алгоритма, убедитесь, что вы используете наиболее оптимизированную библиотеку для вашего языка программирования. Для Python, например, вы можете использовать библиотеку hashlib или cryptography.  
 
**Кейс 1.2**

Для лендингов и CRM систем, можно использовать  реляционную СУБД), такие как MySQL,PostgeSQL,Microsoft SQL Server и т.д. В реляционных СУБД обеспечивается структурированное хранение данных, поддерживаются транзакции, они обеспечивают целостность данных. 
Все зависит от используемой CRM , например CRM Microsoft Dynamics 365 - интегрированная платформа бизнес-приложений с CRM функциональностью имеет в составе компонент SQL Server Database. Также одна из популярных CRM систем - Salesforce уже использует СУБД NoSQL, известную как HBase (СУБД класса NoSQL с открытым исходным кодом). 

**Кейс 1.2***

Наиболее верное верное решение это применять CRM-системы, позволяющие получать отчетность и аналитику. Например среди рассмотренных - Salesforce с реализацией хранения данных в СУБД NoSQL.



**Кейс 1.3**

Для реализациии хранения данных подойдет реляционная СУБД. Например PostgeSQL, MySQL и т.д. Каждая таблица будет содержать информацию о своих объектах (нормы, правила, материалы, структура компании), а поля в таблице будут хранить данные о каждом объекте. Для упрощения работы с базой данных, можно также создать связи между таблицами. Такая структура базы данных позволит легко хранить и обновлять информацию и  организовывать структуру компании в единой системе управления. Кроме того можно реализовать на NoSQL СУБД если хранить данные не ввиде таблиц, а  в виде документов либо коллекций. 

**Кейс 1.3***

Хранение данных в виде документов реализован у MongoDB — система управления базами данных, которая работает с документоориентированной моделью данных. MongoDB не использует схемы, как это делают реляционные базы данных, что повышает производительность всей системы. В такой СУБД  поиск осуществляется по специальным запросам, тем самым обеспечивается простой доступ к данным в отличии от запросов в формате SQL.



**Кейс 1.4**

Для формированию маршрутов доставки материалов по объектам и распределению курьеров по маршрутам с доставкой документов можно использовать реляционную СУБД, например PostgeSQL. Для курьера и департамента логиситики оргнизивать связь через клиент-серверное приложение. В клиентской части получать данные об адресе назначения, текст задания "доставка документов" с описанием задяния и отметку о выполнении. На сервер будут пердаваться данные по маршрутам, геометки. Также информация о выполнении задания, и сопутствующие параметры (время доставки, общий путь курьера, и т.д.)

**Кейс 1.4***

Для оперативной работы необходима связь между СУБД отдела закупок и департамента логистики. Отдел закупок может работать в собственной СУБД.  Например в Документоориентированной СУБД. 
Для работы отдела необходимо обеспечивать поступление товаров, сырья, инвентаря для изготовления продукта. Также должен контролировать наличие запасов товара, и регулировать выбор и взаимоотношения с поставщиками, а значит в СУБД должна быть вся необходимая информация. 

**Кейс 1.5***

Стоит рассмотреть возможность использования графовых СУБД, вместо традиционной таблицы с рядами и столбцами, данные в графовой базе данных представлены в виде узлов (вершин) и ребер (связей). В таких системах   обеспечивается быстрый доступ к связям между данными, что делает их особенно полезными для приложений, требующих анализа и обработки сложных взаимосвязей. Также графовые СУБД позволяют легко добавлять новые типы узлов и ребер без изменения схемы базы данных. Графовая модель представления данных естественным образом отражает структуру и отношения между объектами. Из популярных СУБД - Amazon Neptune, JanusGraph каждая имеет свои особенности и возможности.



---
