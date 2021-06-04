## Intro to MVC
### Learning Goals

- Identify the elements of the MVC design pattern
- Describe the single responsibility of each of the Model, View, and Controller
- Describe how data is passed through the MVC pattern

### Vocabulary

- MVC
- Model
- View
- Controller
- DSL (Domain Specific Language)

#### Diagram
![image](https://user-images.githubusercontent.com/46441816/120845070-845fc080-c52d-11eb-8935-9da837ba6f12.png)

### Logic “Responsibilities”

The MVC Design Pattern describes the primary responsibility of each portion of code that we’ll describe a little bit deeper here.

#### Models – Data Logic

We saw earlier that the Model is responsible for interaction with the database. In MVC, we say that the Model is responsible for “data logic”. Calculations, filtering of data, or other manipulation of data should happen at the Model level. When fetching data from a Model, the Model should only return raw data in an appropriate data structure – usually an array, but can also be a hash.

A Model generally does not alter data. For example, it would be appropriate for the Model to calculate the average age of all students, but it should NOT ‘round’ that data to, say, two decimal places. It can force the result to be a floating point number with .to_f, but it should return raw data as much as possible.

#### Views – Presentation Logic

Views have very little logic in them, generally just if/else statements and perhaps doing some basic iteration over a dataset. The primary goal of a View is to manipulate raw data given to it by a Controller to present that data in a way that is useful to our users.

If a View has access to an instance variable, or a collection of instances in an array that it is iterating over, it’s appropriate for the View to call “instance methods” from the Model class if needed. A View should not call class methods except in extremely rare cases where a data builder requires it, such as a drop-down select in a form for example.

#### Controllers – Business Logic, or Application Logic

Our Controllers are the “traffic cop” between our Models and our Views. Based on the incoming request, each controller method knows precisely which Model(s) it needs to utilize to fetch or write data, and will generally hand that data off to a View for presentation.

Controllers should limit their database actions to very simple lookups, or creation of a resource. A controller should not do very much data manipulation, that “data logic” is the role of the Model. Likewise, the controller should pre-fetch as much data as possible so the View does not call Class methods from the Models.