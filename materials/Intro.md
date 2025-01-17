## Введение ##

Компьютерная лингвистика — зачем?

По сути, компьютерная лингвистика — для тех ситуаций, когда компьютер взаимодействует с естественным языком.

Что такое естественный язык?

в чем отличие от формальных языков (языков программирования / запросов)?

- (не)однозначность. Формальный — это такой язык, в котором одинаковые сочетания знаков всегда имеют одинаковый смысл.

Языки программирования созданы для того, чтобы специально отдавать команды компьютеру.

Как человек общается с компьютером?

- изначально компьютер — это вообще просто вычислительная машина, которая умеет только в нули и единицы
- потом — языки программирования. и вообще другие формальные языки. тоже не очень удобно — нам нужно изучать синтаксис языков программирования, как мы это делаем с иностранными языками. а языки программирования, как и другие формальные языки, устроены сильно легче, чем естественный язык. естественный язык настолько же сложнее, чем формальный язык, насколько мозг сложнее современного компьютера. а можно как-нибудь общаться с компьютером на естественном языке?
- ура! учим компьютер понимать язык!

(и думаем, на самом ли деле компьютер понимает язык?) ((конечно нет, он только делает вид! :))

(Давайте условимся: когда мы говорим “компьютер”, мы имеем в виду не ваш ноут или телефон, а некоторую вычислительную штуку, у которой нет человеческого мозга, но есть память и способность выполнять операции. то есть то, что под оболочкой у любого компьютера в бытовом смысле этого слова.)

Окей. Что мы хотим? Давайте от простого, того, что мы замечаем каждый день, к сложному (чем мы тоже пользуемся каждый день, только не замечаем). Быстро посмотрим, как вообще это устроено.

Две главных задачи — это сделать так, чтобы компьютер умел **понимать** и **порождать** тексты на естественном языке.

Но сначала проясним еще немного терминологии.

Еще где-то рядышком болтается NLP. NLP — это не [нейролингвистическое программирование](https://ru.wikipedia.org/wiki/%D0%9D%D0%B5%D0%B9%D1%80%D0%BE%D0%BB%D0%B8%D0%BD%D0%B3%D0%B2%D0%B8%D1%81%D1%82%D0%B8%D1%87%D0%B5%D1%81%D0%BA%D0%BE%D0%B5_%D0%BF%D1%80%D0%BE%D0%B3%D1%80%D0%B0%D0%BC%D0%BC%D0%B8%D1%80%D0%BE%D0%B2%D0%B0%D0%BD%D0%B8%D0%B5), как вы могли подумать, а natural language processing — обработка естественного языка. чем это отличается от компьютерной лингвистики? НЛП — это скорее попытка что-то делать с языком в компьютерных науках. а компьютерная лингвистика — это скорее попытка в лингвистике делать что-то в лингвистике компьютерными методами.

С другой стороны, компьютерная лингвистика может употребляться не только в значении НЛП — то есть исключительно прикладной области для решения прикладных технических задач, но и как фундаментальная научная область. эдакая “теоретическая компьютерная лингвистика” — мы пытаемся компьютерными методами понять что-то о языке.

но по факту граница между этими двумя полями очень размытая, и разница, как кажется на первый взгляд, только в том, что ответвлением чего мы считаем.

(а еще NLP смешно называется по-русски — **автобрея**)

### Перевод

с этого все началось.

нам кажется, что это настолько простая вещь — мы ведь пользуемся ей каждый день, но я лично как только начинаю задумываться о том, как это происходит, мне становится немного не по себе.

окей, переводить отдельные слова мы умеем — по сути, у нас есть огромный русско-(например) английский словарь, и мы просто ищем соответствия. окей, формы слов — тоже ок (как вообще компьютер понимает, что разные формы слов, иногда совсем непохожие (типа, _я_ и _меня_) — это еще одна очень интересная история, и о ней мы поговорим подробнее позже). но как переводить грамматику?

сначала переводчики работали на правилах — но понятно, что этого недостаточно. и очень сложно: вообще-то, не про все языки мы понимаем все их правила. а есть малые языки — что с ними делать? да и вообще, это же сколько надо времени, сил и денег? и все равно остаются проблемы — ну, точнее, это такие фундаментальные проблемы, ой, то есть особенности языков. например, неоднозначность

отсюда вот эти вот смешные ложные друзья переводчика

конечно, кроме правил используются и вероятностные модели. понятно, что если у слова _бить_ есть значение “истекать”, типа “нефть бьет ключом”, то маловероятно, что у нас в предложении это именно оно, а не _бить_, которое привычное _бить_.

а что делать, например, с порядком слов?

а со словами без перевода? и я сейчас не о тоске, а например, об артиклях. и если мы переводим с английского, то всё ок — мы просто, скажем, их опускаем. а если с русского на английский?

сейчас переводчики работают на нейросетях

а как вообще работают нейросети? если очень кратко, то мы загружаем в программу размеченные данные, программа на них обучается (думая, какие признаки более, а какие менее важные), и потом научается предсказывать или создавать что-то самостоятельно.

А вот пример плохой работы машинных переводчиков: это шуточный перевод, сделанный на правиловом переводчике с использованием юридического и медицинского словаря.

_“специалисты Microsoft компании после большого числа опытов выявили, что наиболее эффективной командой из-под Окон 95 является «Послать на…», которая доступна в любом времени и месте при ударе по правой почке мыши.”_

[Гуртовщики Мыши (lib.ru)](http://lib.ru/ANEKDOTY/mouse_driver.txt)

### Поисковые системы

конечно, в строку яндекса или гугла мы вбиваем запрос на естественном языке. сравните, например, запросы, которые посылаются в базу данных на языке SQL (или даже в корпус — на языке CQL — corpus query language)

вот так вы бы задали вопрос в SQL:

_SELECT \* FROM Linguists_

_WHERE FieldTripLanguage IN ('Kildin Saami', 'Tundra Nenets', 'Shugni') AND Course = 2_

а вот так в простом советском поисковом запросе в Яндекс:

_найди всех лингвистов-второкурсников, которые ездят в экспедицию в кильдинский саамский, тундровый ненецкий или шугнанский язык_

или вот например такое:

_дорогой Яндекс! очень прошу тебя прояснить мне, кто в 1957 году написал знаменитую работу “Введение в синтаксические структуры”? заранее благодарю за ответ, с благодарностью, Екатерина Шерстнева, лингвистка из Москвы._

(у вас сто процентов было такое, что вас что-то спросили, а что спросили — непонятно. вот и как поисковик понимает, что из этого — часть вопроса, а что — просто ерунда какая-то?)

и как яндекс понимает, что нам надо? и как он понимает, что где поесть в санкт-петербурге, где похавать в питере, где пожрать в культурной столице — это все одно и то же (и выдает рестораны)? там же не сидит тысяча маленьких умных гномиков, которые знают всё в этой вселенной?

### **Испр**авление оши**бок —** спеллчекеры

например, можно просто проверять, есть ли слово в словаре. но что мы будем делать в таком случае:

_вижу в окрошке белую кошку_

вроде ок, но, наверное, имелось в виду окошко? (если, конечно, это не песня вени д’ркина)))

или вот так:

_с луками оторвут_

луками и окрошку — самые обычные формы русского языка, и они существуют. и в словаре они есть. тут в дело вступают вероятностные модели. давайте посмотрим на контекст вокруг, и посмотрим, а что вообще более вероятно встретить в таком контекста. наверное в контексте _с \___оторвут_ мы все-таки ожидаем встретить _руками_, а не _луками_

а еще вероятностные модели позволяют предсказывать продолжение. например, если вы начинаете писать _Дорогие_, то, с большой вероятностью, вы продолжите словами _друзья_ или _коллеги_.

### Извлечение информации из текста

Набор ключевых слов должен быть:

**исчерпывающим** — покрывать все явления и события, о которых говорится в тексте;

**минимально достаточным** — каждый документ должен выражаться минимально необходимым количеством слов, среди ключевых слов не должно быть полных синонимов;

**специфичным** — найденные ключевые слова должны отличать текст от всех других.

в основном это нужно для информационного поиска или расстановки тэгов — например, по тематикам. короче, ура, классификация текстов!

### **Диалоговые агенты**

Здесь задействуется и понимание, и порождение текста. И здесь вообще смешная история успеха.

Люди много мечтали о говорящих головах: они появляются в мифах разных народах, такой говорящий механизм есть и в Иллиаде Гомера. короче, научить механизм говорить хотелось всем. и когда с помощью алхимии это сделать не вышло — все головы почему-то отказывались давать пророчества и взрывались, это решили сделать с помощью техники.

_Двинулся к двери. Навстречу ему золотые служанки_

_Вмиг подбежали, подобные девам живым, у которых_

_Разум в груди заключен, и голос, и сила, - которых_

_Самым различным трудам обучили бессмертные боги._

Чарльз Бэббидж в 19 веке придумал первый почти-компьютер — и даже задумывался о том, как можно его применить для машинного перевода, но не смог продать эту идею британскому правительству. компьютера не вышло :( но когда в 20 веке машину Бэббиджа воссоздали по чертежам, оказалось, что она вполне себе рабочая :)

и все отложилось еще лет на 100.

а после второй мировой — она вообще, как вы знаете, стала таким мощным спусковым крючком для развития многих технологий. стало понятно, что войну выигрывает не тот, у кого больше солдат, а у кого умнее и технологичнее армия. и вычислительные технологии — тоже один из важных флагманов.

Криптография! компьютерная лингвистика, можно сказать, вышла из криптографии — ведь она имеет дело с сигналом на естественном языке.

важный человек здесь — Тьюринг. вы, наверное слышал о нем. например, в контексте теста Тьюринга или машины Тьюринга. а тем временем Алан Тьюринг “взламывал” немецкую шифровальную машину Энигма

- Тест Тьюринга — может ли человек отличить машину от человека, когда с ней разговаривает? конечно, это не очень формальная вещь: непонятно, какой человек это оценивает? может тестировщик просто задает такие вопросы, которые разработчики хорошо прописали?
- 1964 — SHRDLU — умела переставлять фигуры в геометрическом пространстве
- 1969 — [Eliza](https://web.njit.edu/~ronkowit/eliza.html). даже проходила тест тьюринга!

[When PARRY Met ELIZA: A Ridiculous Chatbot Conversation From 1972 - The Atlantic](https://www.theatlantic.com/technology/archive/2014/06/when-parry-met-eliza-a-ridiculous-chatbot-conversation-from-1972/372428/) — 1972 год. притворяется пациентом с параноидальной шизофренией.

(на самом деле элиза просто не умеет отвечать на вопрос “как дела?”. жиза?)

а еще один пионер компьютерной лингвистики – американский криптограф Уивер. В отличие от Бэббиджа он на полном серьезе высказывал идею машинного перевода. и даже не как фантазию, а как то, что надо и можно осуществить в ближайшие годы (и даже на том уровне развития компьютеров)

_Когда я смотрю на текст на русском языке, я вижу не текст на русском языке, а некоторый код, который кодирует текст на английском языке_

1954 год. Джорджтаунский эксперимент IBM

VYELYICHINA UGLA OPRYEDYELYAETSYA OTNOSHYENIYEM DLYINI DUGI RADIUSU

\>>>

MAGNITUDE OF ANGLE IS DETERMINED BY THE RELATION OF LENGTH OF ARC TO RADIUS.

(вообще развитие комплинга зависело от того, насколько острая фаза холодной войны была))

После Элизы наступила AI WINTER, потому что ничего не работало. а потом случился новый виток холодной войны, и в сферу снова полились деньги

и в восьмидесятых возникает новая идея: переход **от правил к статистическим моделям** (это связано в том числе и с увеличением вычислительных мощностей)

ура! нейросети! (мы не моделируем это вручную)

(и вообще так-то не очень погружаемся в то, как устроен язык)

### Анализ тональности

по-английски это sentiment analysis

нет, это не анализ системы нот.

вот это довольно неочевидная вещь, о которой обычно мы не вспоминаем действительно, с пользовательской стороны она скорее не нужна. но что же это такое?

тут начинается совсем какая-то метафизика. если в задачах выше мы хотели, чтобы компьютер понимал хотя бы язык на базовом уровне, здесь мы хотим, чтобы он понимал мнения авторов текстов. их эмоций. их отношения. для чего это может быть нужно? в первую очередь, для классификации отзывов. вот вам вопрос. есть два отзыва:

**Ужасно** понравился фильм! **Жутко** классный! Огонь! А **отстой** — это не фильм, а те, кто так о нём говорит. Кому **не понравилось** — **идиоты**!

**Ну и ну**! Вы что, **смеетесь**, когда пишете, что это **афигенно**? **Супер**, я **благодаря** этому фильму перестал ходить в кинотеарты вообще, **настолько сильно** он мне **понравился**

какой из них положительный? но ведь в нем столько слов с отрицательной оценкой!

а как понять, что коза — это не только животное, но и ругательство? привет курсу по семантике! надеюсь, вы уже сломали там мозг. а теперь представьте, как с этим справляется компьютер.

короче, как и во многих задачах, на самом деле, это задача классификации текстов.

ну а как быть все-таки?

- rule-based approach — у нас есть размеченные по тональности словари, и мы смотрим на ключевые слова, и на их помету в таком словаре (как обычно, супер-долго и дорого, и не оч удобно. см. пример выше)
- машобуч. мы кормим модели кучу размеченных текстов, она их кушает, что-то понимает про жизнь, и научается предсказывать значения (но тоже нужны большие размеченные вручную массивы данных)

[Sentiment Analysis - Free Online Demo (text2data.com)](https://text2data.com/Demo) — можно попробовать сломать классификатор :)

## Что с фундаментальными вещами?

в основном изучение малых языков

### **Морфологический анализ**

(скорее под оболочкой, но мб и глоссирование (морфологическая разметка) текстов на малых языках — тогда это самозадача)

### Корпусная лингвистика

Удобное хранение — тоже задача! Во-первых, корпуса нужны для того, чтобы удобно хранить и искать тексты на любом языке. Ну, например, вы ездите в лесной ненецкий, и у вас собралось какое-то количество отглоссированных текстов — то есть с переводом и поморфемно размеченных — но они в виде гуглдоков. а вам хочется, например, искать все формы множественного числа. или что-нибудь еще эдакое. тогда создается корпус с морфологической разметкой и переводом, и в нем всякими хитрыми образами можно искать разные запросы. например, задавать начальную форму слова, или то, с чего она начинается / какую подстроку она содержит, или какие морфологические признаки оно имеет, или как переводится.

но корпуса бывают не только для внутриэкспедиционного использования. это даже такой довольно маргинальный пример. бывают огромные монолингвальные корпуса — например, НКРЯ. вот представьте, что вы в 18 веке, вы богатый аристократ, который на досуге решил заняться языкознанием и изучить использование какого-нибудь слова. а как известно, самое главное в любом исследовании — это языковые примеры. что вы делаете? достаете всю свою многотомную домашнюю библиотеку, открываете каждую книжечку и ищете использование вашего слова. и выписываете себе в блокнотик. представили? адское занятие.

с появлением компьютеров жить сразу стало сильно легче. например, сейчас в нкря больше 2 миллиардов слов. и он размечен морфологически и синтаксически. а иногда еще и ударения размечены.

а есть такие, fancy корпуса. например, мультимедийный корпус нкря — там еще есть видео, и можно смотреть жесты. есть параллельные корпуса,

(а какой самый большой параллельный корпус?)))

корпуса [сновидений](https://spokencorpora.ru/showcorpus.py?dir=00dreams), детской речи, ошибок и вообще кажется примерно всего, что можно собрать

можно делать свои корпуса, например, если вы любите анекдоты про штирлица, вы можете собрать корпус анекдотов про штирлица.

Как еще можно что-то изучать о языке? Семантические сдвиги. Параллельные корпуса — для изучения лингвоспецичиной лексики — для переводоведения.

По-русски — компьютерная лингвистика. И вроде бы понятно, почему компьютерная?

Но как по-английски?

\> Computational

То есть перевод на самом деле не совсем верный: это скорее **вычислительная** (compute — вычислять), а не компьютерная лингвистика

что под оболочкой?

- предобработка (токенизация)
- морфологический анализ + лемматизация
- синтаксический анализ
- семантический анализ
- анализ дискурса

Начнем с того, что поговорим о том, как мы анализируем слова

