# Tooling task. Part 2

## 1) Network
1.1) записать и сохранить в HAR архив профиль загрузки ресурсов при открытии страницы - [HAR](duplication/gd.ru_har.har)
1.2) найти неоптимальные места:
- 1.2.1) дублирование ресурсов
<img width="1194" alt="image" src="https://github.com/lexarudak/tooling_2/assets/106698008/e08c94db-1e31-422a-b9ba-297488af18d8">
запросы на один url
<img width="1209" alt="image" src="https://github.com/lexarudak/tooling_2/assets/106698008/fe7c726e-764f-4cdc-8e24-2241696cb37c">
два похожих запроса плюс два их preflight-а. соответственно 4 объединяются в 2
<img width="1208" alt="image" src="https://github.com/lexarudak/tooling_2/assets/106698008/1a3f0959-f03b-4cf3-b577-602338a7d448">
одинаковые запросы с разными айдишниками. если можно в один запрос передать несколько айдишников то их можно объединить или проверить их целесообразность 
<img width="1206" alt="image" src="https://github.com/lexarudak/tooling_2/assets/106698008/f465d7bb-f0d3-4c07-a717-75c2555ef3b6">
<img width="1205" alt="image" src="https://github.com/lexarudak/tooling_2/assets/106698008/28de3e73-ae74-4fb2-bd97-bacec3fdf487">
одинаковые запросы с разными путями и только у четвертого отличается респонс можно объединить или убрать лишние
<img width="1179" alt="image" src="https://github.com/lexarudak/tooling_2/assets/106698008/e76febb1-f397-415c-b225-26d84f6cd643">
одинаковый шрифт запрашивается
<img width="1209" alt="image" src="https://github.com/lexarudak/tooling_2/assets/106698008/05ce1ba5-6243-43a2-9d21-6bdeb0c5f091">
один и тот же скрипт
<img width="1199" alt="image" src="https://github.com/lexarudak/tooling_2/assets/106698008/cd358587-1b89-4945-b889-bef71c49ed14">
бустрап грузится дважды
<img width="1200" alt="image" src="https://github.com/lexarudak/tooling_2/assets/106698008/8601d126-6aa2-405e-8541-c0e6306ecd73">
<img width="1194" alt="image" src="https://github.com/lexarudak/tooling_2/assets/106698008/ebe3ad52-25cb-4813-9451-d64f02e18584">
практически одинаковые запросы
<img width="642" alt="image" src="https://github.com/lexarudak/tooling_2/assets/106698008/c63918c9-77e7-44aa-9ce5-87e8ac849227">
одинаковые картинки

- 1.2.2) лишний размер ресурса
<img width="1188" alt="image" src="https://github.com/lexarudak/tooling_2/assets/106698008/6706f96f-8e1d-48d5-8594-6f84cb5f05a1">
шрифт не должен столько весить
<img width="733" alt="image" src="https://github.com/lexarudak/tooling_2/assets/106698008/66ea1eab-d9fd-460b-a80a-7f20ebc9bd7a">
стоит уточнить, нужны ли такие тяжелые плагины контакта
<img width="840" alt="image" src="https://github.com/lexarudak/tooling_2/assets/106698008/8d699760-a4b0-41ca-a74a-b2c46191d8a3">
<img width="729" alt="image" src="https://github.com/lexarudak/tooling_2/assets/106698008/7b3481b1-78b4-4a31-b789-4c47f850d19f">
файлы с большим процентом неиспользованного кода

- 1.2.3) медленно загружающиеся ресурсы
<img width="709" alt="image" src="https://github.com/lexarudak/tooling_2/assets/106698008/91a21a1b-4133-42a5-b912-98a150dd6f96">
долго грузятся перемещенные svg
<img width="770" alt="image" src="https://github.com/lexarudak/tooling_2/assets/106698008/f34d6e5d-b635-4a1a-a713-83d3c90985dd">
не столько медленно грузится, сколько поздно начинает грузиться. это критично, т.к. она находится вверху страницы
<img width="747" alt="image" src="https://github.com/lexarudak/tooling_2/assets/106698008/8dd2ec2c-55ef-4317-81f4-b407d3756f64">
все, что касается вк грузится медленно, но учитывая, что вся страница грузится медленно - это не особо выбивается
<img width="728" alt="image" src="https://github.com/lexarudak/tooling_2/assets/106698008/b25d72fa-e48a-438a-a3fa-11f6d8c617be">
очень долго грузится
<img width="678" alt="image" src="https://github.com/lexarudak/tooling_2/assets/106698008/7c781753-edec-4602-82c3-4f1572eae395">
почти секунду грузится

- 1.2.4) ресурсы, блокирующие загрузку
<img width="766" alt="image" src="https://github.com/lexarudak/tooling_2/assets/106698008/902282ce-0294-4423-a281-bbf7e418b80f">
на всякий случай уточню, что он блокирующий
<img width="954" alt="image" src="https://github.com/lexarudak/tooling_2/assets/106698008/76ae63f5-098c-4d1a-8689-a51bd88dde22">
цсс и шрифты -  блокирующие ресурсы. Но выделю этот из-за его аномального размера. Соответственно, он торбзит дальнейшую загрузку зависимых ресурсов
<img width="1160" alt="image" src="https://github.com/lexarudak/tooling_2/assets/106698008/29ac59e1-8d31-41df-b6c5-6c518c02e641">
этот виджет блокирует загрузку нескольких картинок. на скрие только одна из них и ее время в очереди 

- 1.2.5) что-то ещё
<img width="908" alt="image" src="https://github.com/lexarudak/tooling_2/assets/106698008/c2edcee5-c45b-44a4-bf88-6e1e96b9aaeb">
<img width="943" alt="image" src="https://github.com/lexarudak/tooling_2/assets/106698008/d7d7e1cf-61a8-43ff-bc73-4942ca62468b">
ошибки cors

<img width="917" alt="image" src="https://github.com/lexarudak/tooling_2/assets/106698008/cf8f4297-981d-4ccf-b682-da800f585e50">
пустые файл

<img width="971" alt="image" src="https://github.com/lexarudak/tooling_2/assets/106698008/419614cd-6ba7-47ab-8e9a-249966a7cf62">
переехавшие

## 2) на вкладке Performance

- 2.1) записать и сохранить в файл профиль загрузки страницы - [Файл]()

