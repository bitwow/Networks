# Сети и протоколы, лекция 2


## В чем суть лекции.


Разберем стандарты в сетях
Рассмотрим эталонную модель OSI и разберем все уровни
Рассмотрим модель TCP/IP, эталонную модель TCP/IP
Обсудим работу протоколов стека TCP/IP
Рассмотрим принцип передачи данных в TCP/IP
Разберемся в кватировании и заглянем в заголовки протоколов

### Введение


Каким образом же достигается консенсус в сетевых технологиях, протоколах и оборудовании? 
Данная лекция посвящена рассмотрению стандартизирующих органов, регламентирующих работу сетевых протоколов, устройств, сервисов и так далее.
Вторая часть лекции посвящена рассмотрению эталонной модели OSI, TCP/IP, эталонной модели TCP/IP.
Третья часть лекции – обзор на протоколы, inside в TCP/IP, введение в объективную передачу данных.

### Сетевые стандарты и институты


Институты и организации, стандартизирующие Интернет и оборудование

Существует множество организаций, участвующих в стандартизации Интернета и оборудования. Вот некоторые из наиболее важных:


Международная организация по стандартизации (ISO):
ISO - это международный некоммерческий союз национальных стандартизирующих организаций. Она разрабатывает и публикует международные стандарты в различных областях, включая информационные технологии и сетевые коммуникации. Некоторые из наиболее известных стандартов ISO, относящихся к Интернету, включают модель OSI и протокол TCP/IP.

Международная электротехническая комиссия (IEC): IEC - это международная организация, занимающаяся разработкой и публикацией международных стандартов для электротехнических, электронных и смежных технологий. Она работает в тесном сотрудничестве с ISO по разработке стандартов для информационных технологий. Некоторые из наиболее известных стандартов IEC, относящихся к Интернету, включают стандарты на кабели и разъемы Ethernet.
Институт инженеров по электротехнике и электронике (IEEE): IEEE - это профессиональная организация, посвященная продвижению развития и применению электротехники и электроники. Она издает ряд журналов и конференций, посвященных сетевым технологиям, и разрабатывает стандарты для различных сетевых технологий, таких как Wi-Fi и Bluetooth.
Альянс по открытым стандартам (OSA): OSA - это консорциум отрасли, занимающийся разработкой и продвижением открытых стандартов для оптических и сетевых технологий. Она разрабатывает стандарты для различных технологий, таких как Fibre Channel и Infiniband.
Консорциум Всемирной паутины (W3C): W3C - это международный консорциум, занимающийся разработкой стандартов для Всемирной паутины. Она разработала ряд стандартов, лежащих в основе Интернета, таких как HTML, CSS и JavaScript.
Это основные организации, участвующие в стандартизации Интернета и оборудования. Эти организации играют жизненно важную роль в обеспечении совместимости и взаимодействия различных сетевых устройств и технологий.

OSI	– Open Systems Interconnection Model (Модель взаимодействия открытых систем)					
ISO	– International Organization for Standardization (Международная организация по стандартизации)			
IEC	– International Electrotechnical Commission (Международная электротехническая комиссия)			
IEEE – Institute of Electrical and Electronics Engineers (Институт инженеров по электротехнике и электронике)	
OSA – Open Standards Alliance (Альянс по открытым стандартам)					
W3C – World Wide Web Consortium (Консорциум Всемирной паутины)

### Приложения и данные


Приложения позволяют человеку выполнять некоторый перечень задач, таких как: доступ к веб-страницам, генерация документов и так далее. Приложения позволяют пользователю создавать некоторый объем данных.

Внедрение приложений – Данные 
Генерирование данных – В области вычислительной техники данные являются формой представления всех видов
информации. 
Передача данных – Данные, сгенерированные большинством приложений, передаются между устройствами.

Компьютер может идентифицировать только цифровые данные, представленные в виде 0 и 1. Он не может читать другие типы информации, поэтому информацию необходимо преобразовывать по определенным правилам.
Однако люди не имеют возможности читать электронные данные. Поэтому данные должны быть преобразованы в информацию, понятную людям.
Сетевой инженер должен уделять много внимания процессу сквозной передачи данных.

### Эталонная модель данных



Уровни модели OSI:

1. Физический уровень
2. Уровень кадра
3. Сетевой уровень
4. Транспортный уровень
5. Сеансовый уровень
6. Представленческий уровень
7. Прикладной уровень


Модель взаимодействия открытых систем (OSI) была включена в стандарт ISO 7489 и опубликована в 1984 году. ISO – это Международная организация по стандартизации.
Эталонную модель OSI также называют семиуровневой моделью. Она включает семь уровней (перечислены снизу вверх):
Физический уровень: передает битовые потоки между устройствами и определяет физические спецификации каналов связи, такие как уровень электрических сигналов, скорость, коннекторы кабелей и разъемы портов.
Уровень канала данных (канальный уровень): инкапсулирует биты в октеты и октеты в кадры, использует MAC-адреса для доступа к среде передачи и осуществляет проверку на ошибки.
Сетевой уровень: определяет логические адреса, чтобы маршрутизаторы могли определить пути и передавать данные из исходных сетей в сети назначения.
Транспортный уровень: реализует передачу данных с установлением соединения и без него, а также проверку на ошибки перед повторной передачей.
Уровень сеанса: устанавливает, управляет и завершает сеансы между сущностями на уровне представления. Связь на этом уровне осуществляется через запросы услуг и ответы, передаваемые между приложениями на различных устройствах.
Уровень представления: обеспечивает кодирование и преобразование данных, чтобы данные, отправленные уровнем приложений одной системы, могли быть идентифицированы уровнем приложений другой системы.
Уровень приложений: этот уровень ближайший к конечному пользователю, предоставляет сетевые сервисы для приложений.

### Эталонная модель TCP/IP



Уровни модели TCP/IP:
Уровень сетевого доступа
Межсетевой уровень
Уровень взаимодействия хостов
Уровень приложений

Модель TCP/IP по структуре аналогична модели OSI и использует иерархическую архитектуру. Прилегающие уровни TCP/IP тесно связаны.
В стандартной модели TCP/IP Канальный уровень (уровень канала данных) и Физический уровень модели OSI объединены в уровень сетевого доступа. Поэтому предлагается эквивалентная модель TCP/IP, которая связывает стандартную модель TCP/IP и модель OSI. Информация на следующих слайдах приведена для эквивалентной модели TCP/IP.

Эквивалентная модель TCP/IP, предложенная Эндрю Таненбаумом состоит из 5 уровней.


Уровни эквивалентной модели TCP/IP:
Физический уровень
Уровень канала данных
Сетевой уровень
Транспортный уровень
Уровень приложений

### Стандартные протоколы TCP/IP


Уровень приложений
Протокол передачи гипертекста (HTTP): используется для доступа к различным страницам веб-серверов.
Протокол передачи файлов (FTP): предоставляет способ передачи файлов. Он позволяет передавать данные от одного хоста к другому.
Служба доменных имен (DNS): преобразует доменные имена хостов в IP-адреса. Транспортный уровень
Протокол управления передачей (TCP): предоставляет приложениям надежные услуги связи, ориентированные на соединение. В настоящее время протокол TCP используется многими популярными приложениями.
Протокол пользовательских датаграмм (UDP): обеспечивает связь без соединения и не гарантирует надежность передачи пакетов. Надежность может быть обеспечена уровнем приложений.
Сетевой уровень
Internetwork Protocol (IP): инкапсулирует данные транспортного уровня в пакеты данных и пересылает пакеты от источника к получателю. IP предоставляет услуги без установления соединения, и без обеспечения надежности.
Internet Group Management Protocol (IGMP): протокол управления многоадресной рассылкой данных в сетях, основанных на протоколе IP. В частности, IGMP устанавливает и поддерживает членство между IP-хостами и их многоадресными маршрутизаторами, подключенными напрямую.
Internet Control Message Protocol (ICMP): отправляет контрольные сообщения на основе IP-протокола и предоставляет информацию о различных проблемах, которые могут существовать в среде связи. Такая информация помогает администраторам диагностировать проблемы и принимать надлежащие меры для
решения этих проблем. Канальный уровень
Point-to-Point Protocol (PPP): является протоколом уровня канала данных, который работает в режиме точка-точка. PPP используется в основном в сетях WAN.
Ethernet: широковещательный протокол с множественным доступом на уровне передачи данных, который является наиболее широко используемой технологией локальной сети (LAN).
Протокол PPPoE: подключает несколько хостов в сети к концентратору удаленного доступа через простое устройство связи (устройство доступа). Стандартные области применения включают домашний широкополосный доступ.

Пробежимся по каждому из уровней эквивалентной модели, начиная с самого верхнего. 

### Уровень приложений


Стек TCP/IP позволяет передавать данные по сети. Уровни используют блоки данных (PDU) для обмена данными, реализуя связь между сетевыми устройствами.
Блоки данных, передаваемые на различных уровнях, содержат различную информацию. Поэтому у блоков разные имена на разных уровнях.

TCP и UDP – форматы заголовков 
Заголовок TCP:
Порт источника: идентифицирует приложение, отправившее сегмент. Это поле длиной 16 бит.
Порт назначения: идентифицирует приложение, которое принимает сегмент. Это поле длиной 16 бит.
Порядковый номер: каждый байт данных, отправленный через TCP-соединение, имеет порядковый номер. Поле порядкового номера указывает на порядковый номер первого байта в отправленном сегменте. Это поле длиной 32 бит.
Номер подтверждения: порядковый номер первого байта следующего сегмента, который ожидается для получения. Значение этого поля равно порядковому номеру последнего байта, полученного в предыдущем сегменте, увеличенному на единицу. Это поле действительно только при установлении флага ACK. Это поле длиной 32 бит.
Длина заголовка: указывает на длину заголовка TCP, измеряется в блоках по 32 бита (4 байта). Если нет содержимого в поле опции, то длина заголовка составляет 5. Это означает, что заголовок содержит 20 байт.
Резерв: это поле зарезервировано и имеет значение 0. Это поле длиной 6 бит.
Биты управления: биты управления включают в себя флаги FIN, ACK и SYN, и указывают на различные состоянии TCP соединения.
Окно: используется для управления потоком TCP. Значение представляет собой максимальное количество байтов, разрешенных получателем. Максимальный размер окна составляет 65535 байт. Это поле длиной 16 бит.
Контрольная сумма: обязательное поле. Она вычисляется и помещается в сегмент отправителем и проверяется получателем. При вычислении контрольной суммы используются заголовок TCP и данные TCP, а перед сегментом TCP добавляется 12-байтный псевдозаголовок. Это поле длиной 16 бит.
передачи данных
уровень


TCP
Порт источника (16) Порт назначения (16)
Порядковый номер (32)
Номер подтверждения (32)
Длина заголовка (4)
Резерв (6)
Биты управления (6)
Окно (16)
Контрольная сумма (16)
Указатель срочности (16)
Опции
Данные (варьируются)


UPD
Порт источника (16)
Порт назначения (16)
Длина (16)
Контрольная сумма (16)
Данные (при наличии)
  
Указатель срочности: поле указателя срочности. Указатель срочности действует только при установке флага URG. Поле указывает на то, что отправитель передает данные в аварийном режиме. Указатель срочности указывает количество байт срочных данных в сегменте (срочные данные размещаются в начале сегмента). Это поле длиной 16 бит.
Параметры: это поле необязательно. Длина составляет от 0 до 40 байт.
Заголовок UDP:
Порт отправителя: идентифицирует приложение, которое отправляет сегмент. Это поле длиной 16 бит.
Порт получателя: идентифицирует приложение, которое принимает сегмент. Это поле длиной 16 бит.
Длина: определяет общую длину заголовка UDP и данных. Возможная минимальная длина 8 байт, так как заголовок UDP уже занимает 8 байтов. Из-за существования этого поля общая длина сегмента UDP не превышает 65535 байт (включая 8 байт заголовка и 65527 байт данных).
Контрольная сумма: контрольная сумма вычисляется по заголовку UDP и данным UDP. Это поле длиной 16 бит.


### Установление TCP-соединения – 
трехстороннее квитирование


Процесс установления TCP-соединения:
Инициатор TCP-соединения (ПК1 на рисунке) отправляет первый TCP-сегмент с установленным флагом SYN. Начальный порядковый номер (а) является случайно сгенерированным числом. Номер подтверждения равен 0, потому что ранее от ПК 2 не поступали сегменты.
После получения корректного TCP-сегмента с установленным флагом SYN, получатель (ПК2) отвечает TCP-сегментом с установленными флагами SYN и ACK. Начальный порядковый номер (b) является случайно сгенерированным числом. Поскольку сегмент является ответом для ПК1, номер подтверждения равен a+1.
После получения TCP-сегмента, в котором установлены флаги SYN и ACK, ПК1 отвечает сегментом, в котором установлен флаг ACK, порядковый номер равен a+1, а номер подтверждения – b+1. После того, как ПК2 получает сегмент, устанавливается TCP-соединение.

Еще нужно уточнить один момент: практически все протоколы и интерфейсы используют специализированные флаги, в телеграм отправляю перечень флагов при TCP-подключении
В TCP-подключении используются флаги, которые служат для управления ходом соединения и передачи данных. 
Каждый флаг представляет собой 1-битовую информацию, и его значение может быть либо 0 (выключено), либо 1 (включено).

### Флаги TCP:


SYN (Synchronize) – используется для инициализации TCP-соединения.
ACK (Acknowledge) –  подтверждает успешное получение пакета данных.
FIN (Finish) – сообщает о том, что сторона, отправляющая флаг, завершила передачу данных.
RST (Reset) – используется для сброса TCP-соединения в случае ошибки или сбоя.
PSH (Push) – говорит получателю не буферизовать данные, а сразу же отправить их прикладному программному обеспечению.
URG (Urgent) –указывает на наличие срочных данных в пакете.
ECE (ECN Echo) –используется для поддержки механизма контроля перегрузки ECN (Explicit Congestion Notification).
CWR (Congestion Window Reduced) – сообщает о том, что сторона, отправляющая флаг, уменьшила размер окна перегрузки.
SACK (Selective Acknowledgment) – используется для подтверждения успешного получения отдельных частей пакета данных.
KP (Keep-Alive) – используется для проверки работоспособности TCP-соединения.
NS (Nonce Sense) – используется для защиты TCP-соединения от атак повторного воспроизведения.

Пример использования флагов:

Когда клиент хочет установить TCP-соединение с сервером, он отправляет TCP-пакет с флагом SYN.
Сервер отвечает TCP-пакетом с флагами SYN и ACK.
После этого клиент и сервер могут обмениваться данными, используя флаги ACK, PSH и FIN.
Если происходит ошибка или сбой, одна из сторон может отправить TCP-пакет с флагом RST, чтобы сбросить соединение.

Понимание флагов TCP-подключения может помочь вам:

Диагностировать проблемы с TCP-соединениями.
Написать сетевые приложения, которые правильно используют TCP-протокол.
Улучшить производительность и надежность TCP-передач.


### Порядковый номер TCP и номер подтверждения 

Предположим, что ПК1 необходимо отправить сегменты данных на ПК2. Процесс передачи будет следующим:
1. ПК1 нумерует каждый байт, отправляемый через TCP-соединение. Предположим, что номер первого байта равен a+1. Номер второго байта будет равен a +2, третьего байта – a+3 и так далее.
2. ПК1 использует номер первого байта каждого сегмента данных в качестве порядкового номера и отправляет TCP-сегмент.
3. После получения от ПК1 TCP-сегмента ПК2 необходимо подтвердить сегмент и запросить следующий. Как определяется следующий сегмент данных? Порядковый номер (a+1) + длина полезной нагрузки = порядковый номер первого байта следующего сегмента (a+1+12)
4. После получения TCP-сегмента, отправленного ПК2, ПК1 обнаруживает, что номер подтверждения равен a+1+12, что указывает на получение сегментов от a+1 до a+12. Порядковый номер будущего сегмента должен быть a+1+12.
Чтобы повысить эффективность отправки, отправитель может отправлять несколько сегментов данных одновременно, которые затем по очереди будет подтверждать получатель.

Механизм движущихся окон TCP 
1. При трехстороннем квитировании в TCP-соединении обе стороны уведомляют друг друга о максимальном количестве байтов (размере буфера), которые могут быть получены локальной стороной с помощью поля Окно.
2. После установления TCP-соединения отправитель отправляет данные указанного количества байтов на основе размера окна, заявленного получателем.
3. После получения данных получатель хранит данные в буфере и ожидает получения буферизированных данных приложением верхнего уровня. После получения данных приложением верхнего уровня освобождается соответствующее пространство в буфере.
4. Получатель сообщает текущий приемлемый размер данных (окна) в соответствии с его размером буфера.
5. Отправитель отправляет определенный объем данных в зависимости от текущего размера окна получателя.

### Выключение TCP - четырехстороннее квитирование 


TCP поддерживает передачу данных в дуплексном режиме. Это означает, что данные можно передавать в обоих направлениях одновременно. Перед передачей данных TCP устанавливает соединение в обоих направлениях посредством трехстороннего квитирования. Поэтому после завершения передачи данных соединение должно быть разъединено в обоих направлениях. Это показано на рисунке.
1. ПК1 отправляет TCP-сегмент с установленным флагом FIN. Сегмент не содержит данных.
2. После получения ПК1 сегмента TCP ПК2 отвечает сегментом TCP с установленным флагом ACK.
3. ПК2 проверяет необходимость отправки данных. Если необходимо, ПК2 отправляет данные, а затем TCP-сегмент с флагом FIN для закрытия соединения. Если нет, ПК2 напрямую отправляет TCP-сегмент с установленным флагом FIN.
4. После получения TCP-сегмента с установленным флагом FIN ПК1 отвечает сегментом с флагом ACK. Затем TCP-соединение разрывается в обоих направлениях.

### Сетевой уровень 

Интернет-протокол версии 4 (IPv4) является наиболее распространенным протоколом сетевого уровня.

Процесс протокола сетевого уровня

Когда в качестве протокола сетевого уровня используется IP, участникам коммуникации присваивается уникальный IP-адрес для идентификации. IP-адрес может быть записан в формате 32-разрядного двоичного числа. Чтобы облегчить чтение и анализ, IP-адрес представляется в формате четырех десятичных чисел, разделенных точкой, каждое в пределах от 0 до 255, например, 192.168.1.1.
Инкапсуляция и переадресация IP-пакетов данных:
При получении данных от верхнего уровня (например, транспортного уровня), сетевой уровень инкапсулирует заголовок IP-пакета и добавляет IP-адреса источника и назначения в заголовок.
Каждое промежуточное сетевое устройство (например, маршрутизатор) поддерживает таблицу маршрутизации, выступающую в роли маршрутной карты, согласно которой выполняется переадресация IP-пакетов. При получении пакета промежуточное сетевое устройство считывает адрес назначения пакета, ищет в локальной таблице маршрутизации соответствующую запись и пересылает IP- пакет в соответствии с инструкцией в этой записи.
Когда IP-пакет достигает хоста назначения, хост назначения определяет, следует ли принимать пакет на основе IP-адреса назначения, а затем обрабатывает пакет.
В работе IP-протокола требуются протоколы маршрутизации, такие как OSPF, IS-IS и BGP, чтобы помочь маршрутизаторам создавать таблицы маршрутизации, а протокол ICMP требуется для контроля сетей и диагностики состояния сетей.

### MAC-адреса Ethernet и источников 


MAC-адрес представляет собой шесть групп по два шестнадцатеричных значения, разделенные дефисами, двоеточиями или без разделителя. Пример: 48-A4-72-1C-8F-4F 

### ARP 

Протокол ARP является протоколом TCP/IP, который обнаруживает адрес канального уровня, связанный с указанным IP-адресом.
ARP является незаменимым протоколом в IPv4. Он выполняет следующие функции: Обнаруживает MAC-адрес, связанный с указанным IP-адресом.
Сохраняет и кэширует сопоставление между IP-адресами и MAC-адресами через записи ARP.
Обнаруживает дублирующие IP-адреса в сегменте сети.

### Принципы реализации ARP


Как правило, у сетевого устройства есть кэш ARP. В кэше ARP хранится сопоставление между IP-адресами и MAC-адресами.
Перед отправкой датаграммы устройство выполняет поиск в своей таблице ARP. Если устройство находит соответствующую запись ARP, оно инкапсулирует соответствующий MAC-адрес в кадре и отправляет кадр. Если устройство не находит соответствующую запись ARP, оно отправляет запрос ARP для обнаружения MAC-адреса.
Полученное сопоставление между IP-адресом и MAC-адресом хранится в таблице ARP в течение некоторого периода. В течение периода действия (180 с по умолчанию) устройство может напрямую искать в этой таблице MAC-адрес назначения для инкапсуляции данных без выполнения запроса ARP. После истечения срока действия запись ARP автоматически удаляется.
Если устройство назначения расположено в другой сети, устройство-источник ищет в таблице ARP в поиске MAC-адрес шлюза адреса назначения и отправляет датаграмму шлюзу. Затем шлюз переадресует датаграмму устройству назначения.

### Принципы реализации ARP_2  


В этом примере таблица ARP хоста 1 не содержит MAC-адрес хоста 2. Поэтому хост 1 отправляет ARP-запрос для обнаружения MAC-адреса назначения.
Запрос ARP инкапсулируется в кадре Ethernet. MAC-адрес источника в заголовке кадра – это MAC-адрес хоста 1 на стороне передачи. Поскольку хост 1 не знает MAC-адрес хоста 2, MAC-адрес назначения является широковещательным адресом FF-FF-FF-FF- FF-FF-FF-FF.
Запрос ARP содержит MAC-адрес источника, IP-адрес источника, MAC-адрес назначения и IP-адрес назначения. MAC-адрес назначения - все 0. Запрос ARP передается всем хостам сети, включая шлюзы.

### все еще арп 3


После получения запроса ARP каждый хост проверяет, является ли он адресатом сообщения, на основе переданного IP-адреса назначения. Если нет, хост не отвечает на запрос ARP. Если да, хост добавляет MAC- и IP-адреса отправителя, содержащиеся в запросе ARP, в таблицу ARP, а затем отвечает сообщением с ответом ARP.

### АРП 4


Хост 2 отправляет ответ ARP на хост 1.
В ответном сообщении ARP IP-адрес отправителя является IP-адресом хоста 2, а IP- адрес получателя - IP-адресом хоста 1. MAC-адрес получателя является MAC-адресом хоста 1, а MAC-адрес отправителя - MAC-адресом хоста 2. Тип операции – ответ.
Ответные сообщения ARP передаются в одноадресном режиме.

### АРП 5


После получения ответного сообщения ARP хост 1 проверяет, является ли он адресатом сообщения, на основе переданного IP-адреса назначения. Если да, хост 1 записывает MAC- и IP-адреса отправителя в свою таблицу ARP.

### Физический уровень 


Стандартные среды передачи данных 
Витая пар: самая распространенная среда передачи данных, используемая в сетях Ethernet. Витые пары могут быть классифицированы на следующие типы в зависимости от степени сопротивления электромагнитным помехам:
STP: экранированные витые пары
UTP: неэкранированные витые пары
Волоконно-оптическую среду передачи можно классифицировать на следующие типы в зависимости от функциональных компонентов:
Оптические волокна: оптическая среда передачи, которая представляют собой стеклянные волокна.
Оптические модули: преобразовывают электрические сигналы в оптические.
Последовательные (serial) кабели широко используются в глобальных сетях (WAN). Типы интерфейсов, подключенных к последовательным кабелям, различаются в зависимости от типов линий WAN. Интерфейсы включают синхронные / асинхронные последовательные интерфейсы, интерфейсы ATM-терминалов, интерфейсы POS- терминалов и интерфейсы CE1/PRI.
Беспроводные сигналы могут передаваться с помощью электромагнитных волн. Например, беспроводной маршрутизатор модулирует и отправляет данные с помощью электромагнитных волн, а беспроводной сетевой интерфейс мобильного устройства демодулирует электромагнитные волны для получения данных. Таким образом выполняется передача данных от беспроводного маршрутизатора на мобильное устройство.

### Инкапсуляция данных отправителем

Предположим, что вы используете веб-браузер для доступа к официальному сайту Huawei. После ввода адреса веб-сайта и нажатия Enter на вашем компьютере происходят следующие события: 
1.	Браузер (программа) вызывает HTTP (протокол уровня приложений) для инкапсуляции данных уровня приложений. (ДАННЫЕ на рисунке включают заголовок HTTP, который здесь не показан.) 
2.	HTTP использует модуль TCP для обеспечения надежной передачи данных и передает инкапсулированные данные протоколу TCP. 
3.	Протокол TCP добавляет соответствующую информацию заголовка TCP (например, номера портов источника и назначения) к данным, передаваемым с уровня приложений. На транспортном уровне блок данных называется сегментом. 
4.	TCP отправляет инкапсулированный сегмент протоколу IPv4, расположенному на сетевом уровне. (В сети IPv6 сегмент отправляется протоколу IPv6 для обработки.) 
5.	После получения сегмента TCP модуль IPv4 инкапсулирует полученные данные, добавляя заголовок IPv4. На этом уровне блок данных называется пакетом. 
Ethernet используется в качестве протокола канального уровня. Поэтому после завершения инкапсуляции IPv4 отправляет пакет для обработки модулю Ethernet (например, Ethernet NIC) на канальном уровне. 
После получения пакета от IPv4 модуль Ethernet добавляет соответствующий заголовок Ethernet и концевик кадра (FCS) к пакету. На этом уровне блок данных называется кадром. 
После завершения инкапсуляции модуль Ethernet отправляет данные на физический уровень. 
В соответствии с физической средой передачи физический уровень преобразует цифровые сигналы в электрические, оптические или электромагнитные е(беспроводные) сигналы
Преобразованные сигналы передаются в сети. 

### Передача данных в промежуточной сети 

В большинстве случаев:
Устройство 2-го уровня (например, коммутатор Ethernet) декапсулирует только заголовок 2-го уровня данных и выполняет соответствующую операцию коммутации в соответствии с информацией в заголовке 2-го уровня.
Устройство 3-го уровня (например, маршрутизатор) декапсулирует заголовок 3-го уровня и выполняет операции маршрутизации на основе информации о заголовке 3-го уровня.
Примечание: подробные описания и принципы коммутации и маршрутизации будут рассмотрены в курсе позже.

### Декапсуляция данных получателем 


После передачи по промежуточной сети данные достигают сервера назначения. На основе информации в различных заголовках протоколов данные декапсулируются уровень за уровнем, обрабатываются, передаются выше и, наконец, отправляются в приложение на веб-сервере для обработки.
