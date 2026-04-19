


## Элементы промпта

**Инструкция** - конкретная задача или инструкция, которую вы хотите, чтобы модель выполнила

**Контекст** - внешняя информация или дополнительный контекст, который может направить модель на более точные ответы

**Входные данные** - вход или вопрос, на который мы хотим найти ответ

**Индикатор вывода** - тип или формат вывода.

Разработка промтов это итеративный процесс!

> Итеративный (от лат. _iterare_ — повторять) — это подход, основанный на циклическом повторении процесса для улучшения, уточнения или развития продукта.
 
 > Умение разбивать крупную задачу на более мелкие поможет получить более лучшие результаты, а также "краткость сестра таланта" 
 
 Еще одна рекомендация состоит в использовании некоторого ясного разделителя, например "###", для отделения инструкции и контекста.

Например:

_Промпт:_

```
### Instruction ###Translate the text below to Spanish:Text: "hello!"
```

_Результат:_

```
¡Hola!
```



Вот пример неудачного чат-бота по рекомендации фильмов, когда я указываю, что не нужно делать, из-за того, как я сформулировал инструкцию - фокусируясь на том, что не нужно делать.

_Промпт:_

```
The following is an agent that recommends movies to a customer. DO NOT ASK FOR INTERESTS. DO NOT ASK FOR PERSONAL INFORMATION.Customer: Please recommend a movie based on my interests.Agent: 
```

_Результат:_

```
Sure, I can recommend a movie based on your interests. What kind of movie would you like to watch? Do you prefer action, comedy, romance, or something else?
```

Вот лучший промпт:

_Промпт:_

```
The following is an agent that recommends movies to a customer. The agent is responsible to recommend a movie from the top global trending movies. It should refrain from asking users for their preferences and avoid asking for personal information. If the agent doesn't have a movie to recommend, it should respond "Sorry, couldn't find a movie to recommend today.".Customer: Please recommend a movie based on my interests.Agent:
```

_Результат:_

```
Sorry, I don't have any information about your interests. However, here's a list of the top global trending movies right now: [list of movies]. I hope you find something you like!
```