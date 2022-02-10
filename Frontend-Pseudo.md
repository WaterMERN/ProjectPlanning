// -- NavBar -- // 
Home 
About 


//--Landing Page -- // 
image and tagline describing the app? 


//---Create Trip Component --// 
Has an input field for Total Budget, Trip Length and Daily budget 
The trip length field is what is used to calculate the daily budget 
Once an input is put into the trip length , the total budget is divided by that and populates the daily budget field 
This component has an input field with a drop down menu for adding expenses
The dropdown menu includes the categories: Food , Transportation , Lodging and Other 
Once an expense is added using the input field and drop down menu it renders with the type and cost underneath with a button next to it you can click to delete that expense
Adding an expense populates the total trip cost area . Each time an expense is added, this number is changed  
You can delete exenses that are added to the list and the amount of that expense will be decremented from the total budget  

There is  save trip button that saves the info input  and renders it on a current trip card 
The create trip component sends data to the database that is then mapped over to create the current trip card 

Current Trip Card/My Trip component: 
This component displays the information that was input in the create trip component 
git p

PseudoCode Map 
#### Header 
combine with Navbar into one component
- NavBar
    - home page which has the create trip /my trips 
    - about page app
links no state here  
#### BodyNav
- tabs 
    - create Trip
    - my trips
links no state here 

### Body (create trip, my trips, and totals component)
- routes 
    - routes to create trip
    - route to my trips
Main provider state is in body 
- state 
    - expenselist setexpenselist (change from budget list)
    - tripname settripname
    - total budget settotalbudget
    - triplength settriplength
    ###### changing pieces of state all used in Totals component
    - totalcost 
    - food cost 
    - lodging cost
    - transportation cost
    - other cost
    - expenselistitem

#### Create Trip Body 
Create trip, add expense, expense list and totals component
- state needed
    - set tripname 
    - set totalbudget
    - set triplength
- addExpenseList component (changed from budget list)
    - set expenseList 
- expenseList
    - expenseListItem
Use save button to POST to db 

#### My trips component maps through trips database

##### MY Trips Card component 
Has Totals, expenselist , and add expense components 
- from db
    - tripname 
    - total budget
    - trip length
    - expenseList array
- totals component
    - state needed 
        - totalcost 
        - food cost 
        - lodging cost
        - transportation cost
        - other cost
- other state needed 
    - addExpenseList component (changed from budget list)
        - set expenseList 
    - expenseList
        - expenseListItem