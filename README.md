# Process modeling hands-on exercise

Login to Business Central as : 
  - A developer using `username-developer` (change `username` with your id, eg. `m999svs-developer`), or
  - An analyst using `username-analyst` (change `username` with your id, eg. `m999svs-analyst`)

1- Open the **onboarding** project after the login screen

![](img/1.gif)

2- Navigate to the **onboarding** project form the **Spaces** screen

![](img/2.gif)

3- Add a new business process to the project, name it `username-onboarding-process` (change `username` with your id, eg. `m999svs-onboarding-process`)

![](img/3.gif)

4- let's start modeling our process. First, create a **Start Event** and name it `new employee`

![](img/4.gif)


5- Create a **User Task** and name it `Validate employee`

![](img/5.gif)

6- Create an **Exclusive Gateway** and name it `valid ?`

![](img/6.gif)

7- Create a **Business Rule Task** and name it `Assign email`

![](img/7.gif)

8- Create an **End Event**, arrange and name the information flows

![](img/8.gif)

9- Create a **Parallel Gateway**

![](img/9.gif)

10- Select the whole process and move it

![](img/10.gif)

11- Add 1x **User Task**, and 2x **Rest Task**

![](img/11.gif)

12- Link the tasks, by adding the information flows. Add the closing **Parallel Gateway**

![](img/12.gif)

13- Arrange the information flows

![](img/13.gif)

14- Name the tasks: `Procure Laptop`, `Create email account`, and `Add to HR system`

![](img/14.gif)

15- Arrange the tasks

![](img/15.gif)

16- Add an **End Event**, and name it `onboarding succeeded`

![](img/16.gif)

17- Name the other **End Event** `onboarding failed`

![](img/17.gif)

18- Don't forget to save often !! 

![](img/18.gif)

19- Open the process properties on side panel, and add these input **process variables** : 

>  - `firstName` of type `String`
>  - `lastName` of type `String`
>  - `address` of type `String`

  
![](img/19.gif)

20- Continue adding these internal **process variables**

>  - `email` of type `String`
>  - `valid` of type `Boolean` 
>  - `laptopProcured` of type `Boolean`

![](img/20.gif)

21- Fix `Valid ?` **Exclusive Gateway** routing logic

![](img/21.gif)

22- Configure the `Validate employee` **User Task**, click on the task then open the properties on the side panel

![](img/22.gif)

23- Add the **input data assignments** to the `Validate employee` **User Task**, using the properties on the side panel

![](img/23.gif)

24- On the same task, add the **output data assignments** 

![](img/24.gif)

25- lets now configure the  `Assign email` **Business Rule Task** to embed DMN decision logic, click on the task then open the properties on the side panel

![](img/25.gif)

26- Add these information from the DMN model to the `Assign email` **Business Rule Task** 

>  - `Namespace` : `https://kiegroup.org/dmn/_D3887DD7-0DE8-4926-9425-13E4D3024A4F`
>  - `Decision Name` : `Email` 
>  - `DMN Model Name` : `email-assignment-rules`

![](img/26.gif)

27- Add the **input data assignments** to the `Assign email` **Business Rule Task**, using the properties on the side panel

![](img/27.gif)

28- On the same task, add the **output data assignments** 

![](img/28.gif)

29- Copy, then paste the `Validate employee` **User Task** 

![](img/29.gif)

30- Delete the `Procure Laptop` **User Task**, and replace it with the one you copied, then rename it back to `Procure Laptop`

![](img/30.gif)

31- Configure the `Procure Laptop` **User Task**, click on the task then open the properties on the side panel

![](img/31.gif)

32- Now let configure the Rest service calls in the `Create email account` **Rest Task**, by adding these parameters

>  - `Method` : `POST`
>  - `Url` : `https://dummy.restapiexample.com/api/v1/create` 

![](img/32.gif)

33- Configure the Rest service calls in the `Add to HR system` **Rest Task** , by adding these parameters

>  - `Method` : `POST`
>  - `Url` : `https://dummy.restapiexample.com/api/v1/create` 

![](img/33.gif)

34- Generate the **process form** to use for filling input data when starting a new **process instance** in Business Central

![](img/34.gif)

35- Open the **process form** and arrange and keep the required input process variables only

![](img/35.gif)


Finally, explore the other roles, logout and login as:
  - a manager using `username-manager` (change `username` with your id, eg. `m999svs-manager`), or
  - a user using `username-user` (change `username` with your id, eg. `m999svs-user`)