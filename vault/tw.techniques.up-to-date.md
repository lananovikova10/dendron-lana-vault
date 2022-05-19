---
id: ate1fwu1g2bxf6s8pui0jd6
title: Up to Date
desc: ''
updated: 1652953949796
created: 1652953944367
---

The holy grail of always-up-to-date documentation

---
Outline
Should the documentation be actual to the programming code
How to select the depth of describing 
Low-hanging fruits 
How not ot block the dev processes and over complicate the documentation process
---

When you ask someone what’s wrong with your documentation, the top-3 answers will be: no one reads it, it is misleading and it is outdated. In this post we will discuss how to keep the documentation actual and how far can you go with it. 

Documentation is not a source code. For code we can write tests and check if it works before the release, but for content-related things it is harder to implement. How can we make sure documentation is up-to-date and works? 
 
But before that let’s take one step back and understand why it becomes outdated? 

First of all, because it is too detailed. There is no need in document each line in the code. 

Second, it describes an interface instead of scenarios and logic behind it. It is also called descriptional writing. In this approach an author describes each window, button , and switcher, even the obvious ones. As a result, the doc becomes outdated quickly and is overloaded with details. Unlike with the action-based approach, when you start from the user scenarios and problems. In this case you explain an overall logic of the solution and teach, guide(?) the user. 

So the trickies part of the process is to choose the perfect balance .... 

One more point to discuss is how to organize the process of documentation updates without making it sa blocker or a ... (повинность?). 

The idea of always actual documentation does not match with the Agile manifesto which states "working software over comprehensive documentation" that is why in fast and furious companies it is often a reactive, post-processing thing.  So the question is not document or not, but when and how. 
 
The documentation and the code serve different business goals. Code provides customer with the solution they need, the documentation is a way to communicate that this solution exist and how to use it effectively. To keep documentation up-to-date you need to insert it in your processes. 

Below I share a few ways to keep up. 

Keep docs closer to the code

Good practice is to keep the documentation within the code repository in a separate /doc folder, because it makes it easier to update and check during the releases. For example, you can add a check in CI/CD that code is updated while the documentation is not and raise a warning. 

Automate where possible

Docs usually consist of some prose part that explains concepts, approaches, etc, and the reference. You can autogenerate the reference part which is a list of settings, options or parameters, as well as some code examples and even screenshots. 

Get notified about the changes

Another way is to create ticket in yor task-tracker automatically along with the development tickets. For example, it can be triggered by some status change or tag. 

The bonus of this approach is that writer became more integrated into the development process. The developers knew that you exist. The more you are intehgreted (attent their planning and standups, place you tasks on the board, etc). 

At the same time, the backflip is that sometimes the implementation changes during the development process, so there might be some double work. 

Also, you can set up the notifications about code changes or pull requests in Slack. 

Schedule the updates

You can store the timestamp for each doc and create a schedule for regular maintenance. For example, guys from gov.uk have a “review by” date for each page and set up a bot https://technology.blog.gov.uk/2020/09/25/keeping-tech-docs-up-to-date-with-daniel-the-manual-spaniel/ which sends an automatic reminder to review documentation. They called it Daniel the Manual Spaniel. They even made it open-source so you can adapt it for yourself. 

The main idea that an effort put into the doc updates should not overcomplicate the documenting process and .... the development process. 

Use special tools

Recently, the idea of the documentation that is coupled with the code became popular. Such startups as Swimm and HastyDocs are both based on the idea that you can match the code and the documentation with some tags or comments and the the tool, inserted in your delivery pipeline follows changes in the code and flag docs as outdated. 

---
So let's sum up what are the options to keep the docs up-to-date and update in time? 
 



---
https://gds-way.cloudapps.digital/#about-the-gds-way 

https://www.nuclino.com/articles/agile-documentation 

Documentation coupled with the code

Swimm is able to follow changes in the code base itself and flag docs that are outdated because something has changed,” Toledano said.

“The docs sit where the code sits in the user’s repository, and it behaves as code, meaning when you’re pushing your code, you’re also pushing Swimm documentation, and it goes through the same process, the same CI [pipeline], the same apps that deploy code, and then we’re able to use this environment to make sure that the documentation stays up-to-date,” he said.


---
Лан, а напиши может какой-нить аутлайн/драфтец/брэйндамп поста про техники синхронизации доки и кода, когда будет время? Можно же такой будет сделать прямо с овервью техник-тулов, наверное? Не листикл, конечно, но с упоминанием разного интересного. И invitation to discussion, конечно, в конце.
В любой форме braindump - в гуглодок? Мне кажется, очень хороший был бы контент для нашего блога.

Svetlana Novikova  2 days ago
Сделаю
21

alexandra.maximova  2 days ago
А у Ярека и Марека (Лелека и Болека) спросить про их вижн - чем они отличаются от Свимма и т.п. Вставить в блог, чо 
В общем, жирная почва, по-моему
11


