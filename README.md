![ga](https://cloud.githubusercontent.com/assets/20629455/23824362/2c9817c2-066d-11e7-8988-7b1eefc6d628.jpg)![wdi](https://cloud.githubusercontent.com/assets/20629455/23824363/2ddeaa7e-066d-11e7-8630-f7c890c9f1c1.png)___<br>#Project 3 | CodeFund##OverviewFor our third project at GA, and our first group project, we were tasked with creating a MEAN stack app. We decided to improve upon Stack Overflow, by incorporating a charity aspect to the operation.See the app in action [here](https://codefund.herokuapp.com/). ##The IdeaWe decided to create a coding resource app, inspired by Stack Overflow, with an additional charity-giving element. Implementing the JustGiving API, users select the charity they'd like donations to be made to on their behalf. Users with questions can then post their coding queries to the app, and users with answers can suggest solutions. Once the person posting the question is satisfied with a response, he can select it as the 'chosen' one and then donate money to the question respondent's charity.

<img width="1275" alt="cf-homepage" src="https://cloud.githubusercontent.com/assets/22897108/23889990/9881fe28-0887-11e7-8bc0-868be9eda47c.png">##The Build* Back-end: Express/Node* Database: MongoDB* Front-end: AngularJS* CSS framework: Bootstrap* External API: JustGiving* Angular modules:	* Simple HTTP requests: ngResource	* Authentication: angular-jwt	* Text editor: textAngular##The ProcessThis was the first time we were required to work in a team, so our first task was to get everyone on the same page. After everyone was happy with the idea for the app, we took over a day and a half to hash out how the app would work, how the models would function together, the overall look of the app using wire-frames and who would take on which task, which we then noted in Trello. Once we had planned out as much as possible, we then broke up into our programming pairs and began the work.Unsurprisingly, the models proved to be the most difficult portion of this project. Because we knew we wanted to filter the questions by coding language, we decided we would require four models - user, language, question, and answer - the language model created to filter. The user model would store the basic authentication information, along with the charity selected by the user, and the questions he asked. The language model stored the languages, which were seeded in, and the questions associated with each language. The question models stored the obvious information, plus the monetary value the question asker would donate in return for a solution. Finally, the answer model stored the response, the owner, the question and whether it was the chosen solution by the question asker, as a Boolean value set to default false.Concurrently to half the team working on the models, the other half of the team worked on building out the AngularJS authentication.

Tasks were organised and delegated using a Trello board. We had three stand-ups and Git merges a day to ascertain what had to be achieved and what still needed to be done.

###Planning
<img width="772" alt="cf-wireframe" src="https://cloud.githubusercontent.com/assets/22897108/23889992/9891fe72-0887-11e7-8a77-80303690fb0f.png">

<img width="562" alt="cf-trello" src="https://cloud.githubusercontent.com/assets/22897108/23889991/988b6dbe-0887-11e7-897f-1eb4760f83bb.png">

##The App###Registration viewHere the user supplies his profile information, email and password. This is also where the user selects the charity he wishes to support using the JustGiving API. To make it easy, we created a function where the user could type in a charitable interest and then our app would send the search to the API, which would return up to five charities to select from. This information would then be stored in the user model.

<img width="1280" alt="cf-register" src="https://cloud.githubusercontent.com/assets/22897108/23889988/987e42ce-0887-11e7-9728-99b668864222.png">###User index viewOnce a user registers or logs into the app, he is taken to the user index page, which displays all the registered users.

<img width="1275" alt="cf-userindex" src="https://cloud.githubusercontent.com/assets/22897108/23889989/9880a17c-0887-11e7-96f1-cab4b1a39db9.png">###User show viewHere, the user can find out more about any individual user, including which charity he supports and any questions he has posted.

<img width="1275" alt="cd-userpage" src="https://cloud.githubusercontent.com/assets/22897108/23889983/98513d42-0887-11e7-9694-6a039778691f.png">###Language index view and language show viewIf a user wants to see the various questions asked per language, he must go to the language index page to select the language. 
<img width="1275" alt="cf-language" src="https://cloud.githubusercontent.com/assets/22897108/23889985/9874e85a-0887-11e7-9caa-5b60b737f70c.png">

####This then takes him to a list of all the questions for that language.
<img width="1275" alt="cf-questionlist" src="https://cloud.githubusercontent.com/assets/22897108/23889984/98695a1c-0887-11e7-9e1f-e819e7bd8de1.png">
###Question new viewHere, the user can post his question, including the incentive he wishes to offer. Using textAngular on this page allows the user to directly type in his question and also to preserve the format of any code he wishes to include. 

<img width="1275" alt="cf-question" src="https://cloud.githubusercontent.com/assets/22897108/23889987/987ab352-0887-11e7-8ee1-a8400bd21aa2.png">###Question show pageThe question show page lists the question and a blank box, created using textAngular, where other users can submit their answers, again preserving the format of any code supplied. This is also the page where the user posting the question can select the answer he found most helpful. Once he has done this, a model pops up on the page to inform him how much and to which charity he should donate money to.

<img width="1275" alt="cf-questionpage" src="https://cloud.githubusercontent.com/assets/22897108/23889986/98789c7a-0887-11e7-9743-bee25eeaf8f6.png">##My ContributionFor this project, my main responsibilities included:* keeping the team on track using our Trello boards* building the models* building the AngularJS routes* implementing the JustGiving API into the register process* creating and collaborating on various views* styling and branding##Key Challenges / Learnings- The biggest challenge on this project was working with four other people who had different strengths, weaknesses and ideas regarding the final product. Overall, I am very happy to have worked as a team on this project, as it taught me a lot about collaborating with other people on code and making decisions, and more often, compromises. The result, however, was well worth any struggles. Plus, the wins were way more fun when shared!- As the backbone of the project, we knew we had to have good models to make this a success. Figuring out how many models we'd need, how to have them interact and what information to store was a good challenge made harder (and easier) by working in a group.- This was also the first project to use AngularJS. This was great for the overall result but it was difficult to wrap my head around the framework under the time pressure of this assignment.- Because of the way our models were structured, seeding the data was a big challenge, as one model's input often depended on another model's input that depended on the first model's input (and so on, and so on). We were lucky in that our instructors were keen to help us to understand how to seed such data, and to use bluebird and asyc Angular dependencies.- Creating the functionality for the user to select one answer as the best was quite difficult. To do this, we had the API populate the answers to a called question. The user then selected the answer he found most helpful, which was then pushed into the model when submitted. This then returned the user's charity information, which was displayed on a model for the user.- Including the JustGiving API in the app was a welcome challenge, as it gave the app purpose. As we had worked with external APIs previously, it wasn't too hard to implement.- Because of the amount of manpower provided, we knew this app had to look killer. As someone who is not strong in design, it was a pleasure to work with other people to collaborate on the final product.##Future WorkA few features I'd love to implement in the future:- a payment gateway to allow charity donations to be made through the site- a way for users to show how much they've had donated on their behalf - an instant messaging chat feature to foster more one-on-one contact- a chat room to foster more community