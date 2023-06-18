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

- 1.2.2) лишний размер ресурса
- <img width="1188" alt="image" src="https://github.com/lexarudak/tooling_2/assets/106698008/6706f96f-8e1d-48d5-8594-6f84cb5f05a1">




    

