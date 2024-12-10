Домашнее задание к занятию «Базы данных, их типы» Пономарев Игорь Олегович
# Домашнее задание к занятию "`Название занятия`" - `Фамилия и имя студента`


### Инструкция по выполнению домашнего задания

   1. Сделайте `fork` данного репозитория к себе в Github и переименуйте его по названию или номеру занятия, например, https://github.com/имя-вашего-репозитория/git-hw или  https://github.com/имя-вашего-репозитория/7-1-ansible-hw).
   2. Выполните клонирование данного репозитория к себе на ПК с помощью команды `git clone`.
   3. Выполните домашнее задание и заполните у себя локально этот файл README.md:
      - впишите вверху название занятия и вашу фамилию и имя
      - в каждом задании добавьте решение в требуемом виде (текст/код/скриншоты/ссылка)
      - для корректного добавления скриншотов воспользуйтесь [инструкцией "Как вставить скриншот в шаблон с решением](https://github.com/netology-code/sys-pattern-homework/blob/main/screen-instruction.md)
      - при оформлении используйте возможности языка разметки md (коротко об этом можно посмотреть в [инструкции  по MarkDown](https://github.com/netology-code/sys-pattern-homework/blob/main/md-instruction.md))
   4. После завершения работы над домашним заданием сделайте коммит (`git commit -m "comment"`) и отправьте его на Github (`git push origin`);
   5. Для проверки домашнего задания преподавателем в личном кабинете прикрепите и отправьте ссылку на решение в виде md-файла в вашем Github.
   6. Любые вопросы по выполнению заданий спрашивайте в чате учебной группы и/или в разделе “Вопросы по заданию” в личном кабинете.
   
Желаем успехов в выполнении домашнего задания!
   
### Дополнительные материалы, которые могут быть полезны для выполнения задания

1. [Руководство по оформлению Markdown файлов](https://gist.github.com/Jekins/2bf2d0638163f1294637#Code)

---

### Задание 1
**Задание 1. СУБД**
Кейс
Крупная строительная компания, которая также занимается проектированием и девелопментом, решила создать правильную архитектуру для работы с данными. Ниже представлены задачи, которые необходимо решить для каждой предметной области.
Какие типы СУБД, на ваш взгляд, лучше всего подойдут для решения этих задач и почему?
1.1. Бюджетирование проектов с дальнейшим формированием финансовых аналитических отчётов и прогнозирования рисков. СУБД должна гарантировать целостность и чёткую структуру данных.
1.1.* Хеширование стало занимать длительно время, какое API можно использовать для ускорения работы?
1.2. Под каждый девелоперский проект создаётся отдельный лендинг, и все данные по лидам стекаются в CRM к маркетологам и менеджерам по продажам. Какой тип СУБД лучше использовать для лендингов и для CRM? СУБД должны быть гибкими и быстрыми.
1.2.* Можно ли эту задачу закрыть одной СУБД? И если да, то какой именно СУБД и какой реализацией?
1.3. Отдел контроля качества решил создать базу по корпоративным нормам и правилам, обучающему материалу и так далее, сформированную согласно структуре компании. СУБД должна иметь простую и понятную структуру.
1.3.* Можно ли под эту задачу использовать уже существующую СУБД из задач выше и если да, то как лучше это реализовать?
1.4. Департамент логистики нуждается в решении задач по быстрому формированию маршрутов доставки материалов по объектам и распределению курьеров по маршрутам с доставкой документов. СУБД должна уметь быстро работать со связями.
1.4.* Можно ли к этой СУБД подключить отдел закупок или для них лучше сформировать свою СУБД в связке с СУБД логистов?
1.5.* Можно ли все перечисленные выше задачи решить, используя одну СУБД? Если да, то какую именно?

Приведите ответ в свободной форме

1.1 Бюджетирование проектов с дальнейшим формированием финансовых аналитических отчётов и прогнозирования рисков 
Для таких задач требуется высокая степень целостности данных и строгая структура. Реляционные базы данных хорошо подходят для хранения финансовой информации, где важна консистентность данных и поддержка транзакций. Они позволяют легко формировать сложные запросы и аналитические отчёты благодаря мощному языку SQL. Примеры: PostgreSQL, MySQL, Oracle Database, Microsoft SQL Server.
1.1.* Если хеширование выполняется слишком долго, возможно, стоит рассмотреть следующие подходы:
- использование специализированных библиотек для ускорения вычислений, например, OpenSSL или Bcrypt.
- применение аппаратного ускорения, такого как GPU или специализированные чипы для криптографических операций.
- оптимизация алгоритмов хеширования и использование более эффективных методов, таких как Argon2id вместо SHA256.
1.2. Лендинговые страницы и CRM-система
Документоориентированная NoSQL СУБД подходит для лендинга так как часто требуют быстрой обработки динамических данных, высокой скорости чтения/записи и возможности масштабироваться горизонтально. Документоориентированные базы данных (например, MongoDB) отлично справляются с такими задачами, позволяя хранить JSON-документы и выполнять гибкие запросы.
Гибридная реляционно-документоориентированная СУБД подходит для CRM-систем и важно сочетать структурированность данных (контакты, сделки, события) с возможностью хранения менее структурированных данных (комментарии, заметки). Гибридные СУБД, такие как PostgreSQL с поддержкой JSONB или ArangoDB, могут обеспечить баланс между структурой и гибкостью.
1.2.* Да, возможно использовать гибридную реляционно-документоориентированную СУБД, такую как PostgreSQL с поддержкой JSONB или ArangoDB. Эти СУБД позволят хранить как структурированные данные (для CRM), так и неструктурированные документы (для лендинга).
1.3. Графовые базы данных идеально подходят для моделирования сложных взаимосвязей между различными элементами структуры компании, нормами, правилами и обучающими материалами. Они обеспечивают высокую скорость выполнения запросов, связанных с навигацией по графовым структурам, например: Neo4j, OrientDB.
1.3.* Да, можно попробовать документоориентированную СУБД, которую мы выбрали для лендинга и CRM (например, MongoDB). Эта база данных способна поддерживать как структурированные данные (лендинг и CRM), так и менее структурированные данные (корпоративные нормы и правила).
Как реализовать:
Создание коллекций: Создайте отдельные коллекции для хранения корпоративных норм, правил и обучающих материалов. Каждая коллекция может содержать документы с различной структурой, что позволяет гибко управлять данными.
Индексация: Настройте индексы для полей, по которым чаще всего будут выполняться поисковые запросы. Это ускорит доступ к данным и повысит производительность системы.
Безопасность: Обеспечьте разграничение прав доступа к различным документам, чтобы только авторизованные пользователи могли просматривать и редактировать определенные записи.
Таким образом, документоориентированная СУБД, такая как MongoDB, может использоваться для всех трёх задач: бюджетирования, лендинга/CRM и базы корпоративных норм.
1.4. Для задач департамента логистики, связанных с формированием маршрутов доставки материалов и распределением курьеров, лучше всего подойдет графовая СУБД. Графовые СУБД, такие как Neo4j, ArangoDB или Amazon Neptune, специально разработаны для работы с данными, которые имеют сложные взаимосвязи, что делает их идеальными для задач, связанных с логистикой.
Почему графовая СУБД?
- эффективная работа со связями: Графовые СУБД оптимизированы для хранения и обработки данных, связанных между собой. Это позволяет быстро находить кратчайшие пути, оптимизировать маршруты и анализировать связи между различными объектами (например, курьерами, складами и клиентами).
- гибкость в моделировании данных: Графовые СУБД позволяют легко добавлять новые узлы и связи, что делает их удобными для динамически меняющихся данных, таких как маршруты и курьеры.
- поддержка сложных запросов: Графовые СУБД поддерживают сложные запросы, которые могут включать несколько уровней связей, что полезно для анализа маршрутов и оптимизации логистических процессов.
Что касается подключения отдела закупок, это зависит от специфики их задач:
- интеграция в графовую СУБД: Если задачи отдела закупок связаны с логистикой (например, управление поставками, взаимодействие с поставщиками), то их можно интегрировать в ту же графовую СУБД. Это позволит создать единую модель данных, где закупки, логистика и маршруты будут связаны между собой, что упростит анализ и оптимизацию процессов.
- отдельная СУБД: Если задачи отдела закупок имеют свои уникальные требования и не пересекаются с логистическими процессами, можно рассмотреть возможность создания отдельной СУБД. В этом случае важно обеспечить интеграцию между системами, чтобы данные могли обмениваться и синхронизироваться.
Для задач департамента логистики рекомендуется использовать графовую СУБД, которая обеспечит быструю и эффективную работу со связями. Интеграция отдела закупок в эту же СУБД возможна, если их задачи пересекаются с логистическими процессами. В противном случае, можно рассмотреть создание отдельной СУБД с интеграцией для обмена данными.
1.4.* Подключение отдела закупок к СУБД, используемой департаментом логистики, зависит от специфики данных, которые обрабатываются в обоих отделах, а также от требований к интеграции и взаимодействию между ними. 
Возможность подключения отдела закупок к СУБД логистов:
- Схожесть данных:
Если данные, которые обрабатываются в отделе закупок, имеют значительное пересечение с данными логистов (например, информация о поставках, поставщиках, материалах и т.д.), то целесообразно использовать одну СУБД. Это упростит доступ к данным и обеспечит целостность информации.
- Интеграция процессов:
Если процессы закупок и логистики тесно связаны (например, закупка материалов напрямую влияет на маршруты доставки), то объединение данных в одной СУБД может улучшить координацию между отделами и упростить анализ данных.
- Гибкость и масштабируемость:
Графовая СУБД, такая как Neo4j, позволяет легко добавлять новые узлы и связи, что может быть полезно для интеграции данных из отдела закупок. Это позволит создать единую модель данных, которая будет учитывать как логистические, так и закупочные процессы.
Альтернативный подход: отдельная СУБД для отдела закупок
- Специфика данных:
Если данные отдела закупок имеют уникальные требования или структуру, которые значительно отличаются от данных логистов, может быть целесообразно создать отдельную СУБД. Это позволит более гибко управлять данными и адаптировать систему под специфические нужды отдела.
- Нагрузка на систему:
Если ожидается высокая нагрузка на систему из-за большого объема данных или частоты запросов, разделение на две СУБД может помочь избежать узких мест и повысить производительность.
- Безопасность и доступ:
Если данные отдела закупок требуют более строгих мер безопасности или контроля доступа, создание отдельной СУБД может быть более подходящим решением.
В целом, если отдел закупок и департамент логистики работают с взаимосвязанными данными и процессами, подключение отдела закупок к СУБД логистов может быть целесообразным и эффективным решением. Это упростит интеграцию и анализ данных. Однако, если данные и процессы существенно различаются, или если есть специфические требования к безопасности и производительности, создание отдельной СУБД для отдела закупок может быть более подходящим вариантом.
В любом случае, важно провести анализ требований и возможностей, чтобы выбрать оптимальное решение для обеих сторон.
1.5* После рассмотрения всех аспектов задач строительной компании, можно сделать вывод, что использование одной универсальной СУБД для решения всех перечисленных задач не является оптимальным решением.
Причины этому следующие:
Различие требований к данным: У каждой предметной области свои уникальные требования к типу данных, их структуре и способам обработки. Например, для бюджетирования нужны реляционные базы данных с четкой структурой и целостностью, тогда как для лендинга и CRM необходима гибкость и быстрота работы с документами.
Производительность и специализация: Специфичные задачи, такие как работа с маршрутами и связями в департаменте логистики, требуют специализированной СУБД, такой как графовая база данных, которая обеспечивает быстрый анализ связей и эффективное построение маршрутов.
Масштабируемость и гибкость: Использование разных типов СУБД позволяет легче адаптироваться к изменениям в бизнес-процессах и масштабированию систем. Например, документоориентированные базы данных проще расширять и изменять, чем реляционные, когда речь идет о неструктурированных данных.
Исходя из этого, наиболее эффективным решением будет применение комбинации следующих типов СУБД:
Реляционная СУБД (PostgreSQL, MySQL) для бюджетирования и финансового учета.
Документоориентированная СУБД (MongoDB, Couchbase) для лендинга и CRM.
Графовая СУБД (Neo4j, JanusGraph) для департамента логистики.
Документоориентированная СУБД (MongoDB) для базы корпоративных норм и правил.
Такой подход позволит каждому отделу компании работать с данными максимально эффективно, учитывая специфику их задач, и обеспечит необходимую гибкость и производительность системы в целом.

**Задание 2. Транзакции**
2.1. Пользователь пополняет баланс счёта телефона, распишите пошагово, какие действия должны произойти для того, чтобы транзакция завершилась успешно. Ориентируйтесь на шесть действий.
2.1.* Какие действия должны произойти, если пополнение счёта телефона происходило бы через автоплатёж?

2.1. Пополнение баланса счёта телефона
Пошаговое описание процесса пополнения баланса счёта телефона может выглядеть следующим образом:
Инициализация запроса: Пользователь вводит сумму пополнения и подтверждает операцию через интерфейс мобильного приложения или веб-сайта оператора.
Проверка средств: Система проверяет наличие достаточного количества средств на банковском счёте пользователя или другом источнике оплаты (электронный кошелёк, карта и т.д.).
Резервирование средств: На счету пользователя временно блокируется сумма, необходимая для пополнения баланса телефона. Это предотвращает возможность использования этих денег до завершения операции.
Передача данных оператору: Информация о платеже передается оператору мобильной связи. Оператор получает запрос на зачисление средств на счёт абонента.
Зачисление средств: Оператор обрабатывает запрос и зачисляет средства на баланс телефона пользователя. После этого резервирование средств снимается.
Уведомление об успешном завершении: Пользователю отправляется уведомление о том, что операция завершена успешно, а баланс телефона пополнился на указанную сумму.
2.1.* Пополнение счёта телефона через автоплатёж
В случае автоплатежа процесс будет несколько отличаться:
Настройка автоплатежа: Пользователь настраивает параметры автоплатежа, указывая сумму пополнения, периодичность (ежедневно, еженедельно, ежемесячно и т.п.) и источник списания средств (банковская карта, электронный кошелек и др.).
Мониторинг баланса: Система автоматически отслеживает баланс счёта телефона пользователя. Когда баланс достигает установленного минимального порога, инициируется процесс пополнения.
Запрос на пополнение: Система отправляет запрос на пополнение счета телефона на основании настроек автоплатежа.
Списание средств: Средства списываются с указанного источника (карты, кошелька и т.д.). Как и при обычном пополнении, система предварительно проверяет доступность средств.
Зачисление средств: Оператор мобильной связи получает информацию о пополнении и зачисляет средства на счет телефона.
Уведомление об успешной операции: Пользователю отправляется уведомление о том, что баланс телефона был успешно пополнен через автоплатёж.
Таким образом, основные различия заключаются в инициации процесса (автоматически при достижении определённого уровня баланса) и отсутствии необходимости ручного подтверждения пользователем каждой отдельной операции.


### Задание 3
**Задание 3. SQL vs NoSQL**
3.1. Напишите пять преимуществ SQL-систем по отношению к NoSQL.
3.1.* Какие, на ваш взгляд, преимущества у NewSQL систем перед SQL и NoSQL.

3.1. Преимущества SQL-систем по отношению к NoSQL
1.Строгая схема данных: SQL-системы имеют четко определенную схему, что обеспечивает целостность и структурированность данных, что особенно важно для сложных транзакционных приложений.
2.Поддержка ACID-транзакций: SQL-системы гарантируют, что все транзакции являются атомарными, согласованными, изолированными и долговечными, что критично для финансовых и бизнес-приложений.
3.Мощные инструменты для управления данными: SQL предоставляет богатый набор операторов и функций для сложных запросов, что позволяет выполнять сложные аналитические задачи.
4.Стандартизированный язык запросов (SQL): Упрощает обучение и переносимость между различными СУБД, так как большинство из них поддерживают стандартный SQL.
5.Поддержка сложных связей: SQL-системы хорошо работают с реляционными данными и позволяют легко устанавливать связи между таблицами, что упрощает работу с взаимосвязанными данными.
3.1.* Преимущества NewSQL систем перед SQL и NoSQL
- скорость и производительность: NewSQL-системы предлагают высокую производительность, сопоставимую с NoSQL, благодаря использованию современных технологий и архитектур, таких как распределенные системы.
- поддержка ACID-транзакций: NewSQL наследует преимущества SQL, обеспечивая надежные транзакции и согласованность данных, что критично для бизнес-приложений.
- гибкость и масштабируемость: NewSQL-системы способны масштабироваться горизонтально, подобно NoSQL, что позволяет обрабатывать большие объемы данных и пользователей.
- удобство использования стандартного SQL: NewSQL-системы обычно используют SQL или его расширения, что упрощает миграцию с традиционных SQL-систем.
- интеграция с аналитическими функциями: Многие NewSQL-системы предлагают встроенные аналитические функции, что позволяет выполнять анализ данных в реальном времени без необходимости интеграции с отдельными аналитическими инструментами.
Таким образом, NewSQL объединяет лучшие черты SQL и NoSQL, обеспечивая надежность и производительность.

### Задание 4
**Задание 4. Кластеры**
Необходимо производить большое количество вычислений при работе с огромным количеством данных, под эту задачу выделено 1000 машин.
На основе какого критерия будете выбирать тип СУБД и какая модель распределённых вычислений здесь справится лучше всего и почему?
Приведите ответ в свободной форме.

При выборе типа СУБД для обработки большого объема данных на 1000 машинах необходимо учитывать несколько ключевых критериев:
Критерии выбора СУБД:
Масштабируемость: Система должна поддерживать горизонтальное масштабирование, чтобы эффективно использовать все 1000 машин. Это позволит добавлять узлы без значительных изменений в архитектуре.
Производительность: СУБД должна обеспечивать высокую производительность при чтении и записи данных, особенно при выполнении сложных вычислений. Важно, чтобы система могла обрабатывать запросы параллельно.
Поддержка распределённых вычислений: Система должна быть способна выполнять вычисления в распределенной среде и обеспечивать эффективное распределение задач между машинами.
Тип данных: Нужно учитывать характер данных — структурированные, неструктурированные или полуструктурированные. Это поможет выбрать между реляционными и NoSQL решениями.
Требования к согласованности: В зависимости от задач, может понадобиться сильная или eventual consistency. Это также может повлиять на выбор СУБД.
Рекомендуемые типы СУБД:
NoSQL СУБД: Например, Cassandra или MongoDB, которые обеспечивают горизонтальное масштабирование и высокую производительность при обработке больших объемов данных. NoSQL решения хорошо подходят для неструктурированных данных и могут эффективно управлять распределенными вычислениями.
NewSQL СУБД: Например, CockroachDB или Google Spanner, которые сочетают в себе преимущества реляционных и NoSQL систем, обеспечивая надежность и масштабируемость.

Модель распределённых вычислений:
Для выполнения большого количества вычислений на 1000 машинах лучше всего подойдет модель MapReduce. Она эффективно распределяет задачи по вычислительным узлам, что позволяет:
- разделять задачи на подзадачи (Map) и затем объединять результаты (Reduce), что идеально подходит для обработки больших объемов данных.
- параллелизм: Каждая машина может обрабатывать свою часть данных одновременно, что существенно ускоряет процесс вычислений.
- отказоустойчивость: В случае сбоя одной из машин, задачи могут быть перераспределены на другие узлы, что обеспечивает надежность обработки.
Таким образом, выбор NoSQL или NewSQL СУБД в сочетании с моделью MapReduce позволит эффективно обрабатывать большие объемы данных на 1000 машинах, обеспечивая высокую производительность и масштабируемость.
