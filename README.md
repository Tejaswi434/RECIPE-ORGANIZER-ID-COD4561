**Title: CodTech IT Solutions Internship- TaskDocumentation:**RECIPE ORGANIZER**

**Introduction :**
This documentation provides detailed explanation of the task assigned during the CodTech IT Solutions internship program.The task involves in Creating  a RECIPE ORGANIZER page using HTML,CSS,JAVASCRIPT. This documentation will cover the implementation details,Rationale behind the code structure,and insights into the programming techniques utilised. Additionally it will include information about the intern ,Kolavanti Tejaswi, and her assigned ID COD4561.

**Intern Information**
Name:Kolavanti Tejaswi
Intern Id: COD4561 

**Task Description**
The task assigned to Kolavanti Tejaswi during the CodTech IT Solutions Internship program is to Create a  PAGE using HTML,CSS,JAVASCRIPT

**Implementation**
```**HTML:**
<!DOCTYPE html>
<html>
<head>
    <link rel="stylesheet" href="recipe.css">
</head>
<body>
    <h1>Recipe Organizer</h1>
    <input class="searching" type="search" placeholder="enter your favourite food" id="searching"/>
<ul class="main-container" id="main_container">
   
</ul>
<script src="recipe.js"></script>
</body>
</html>

**CSS**
.smallMainContainerflexing{
    display:flex;
    flex-direction:row;
    justify-content:center; 
    background-color: antiquewhite;
    border-radius: 3px;
    border-width:1px;
    margin-bottom:20px;
    
}


.imageSizing{
    height:200px;
    width:200px;
    margin-right:30px;
} 

.main-container{
    display:flex;
    flex-direction:column;
    justify-content:center;
}

.searching{
    text-align:center;
    width:600px;
    margin-bottom:30px;
}

**JAVASCRIPT**
let mainContainer=document.getElementById("main_container");

let searchingData=document.getElementById("searching")

let inputdata=""

function createAndAppend(each) {
   
    let small_main_container=document.createElement("div") 
    small_main_container.classList.add("smallMainContainerflexing")
    mainContainer.appendChild(small_main_container) 

    let imageElement=document.createElement("img")
    imageElement.classList.add("imageSizing")
    imageElement.src=each.image 

    small_main_container.appendChild(imageElement)

    let detailsBox=document.createElement("div")
    small_main_container.appendChild(detailsBox)  
    let paragraph=document.createElement("h1")
    paragraph.textContent=each.title 
    detailsBox.appendChild(paragraph)

    let paragraph_2=document.createElement("p")
    paragraph_2.textContent=each. instructions
    detailsBox.appendChild(paragraph_2) 

 

}

function AppendingRecipies(){
    mainContainer.textContent=""
   for (let each of newData){
    let search=each.title 
    if(search.includes(inputdata)){
    createAndAppend(each)
    }
   } 
}

let apiUrl="https://api.spoonacular.com/recipes/random?number=10&apiKey=275d58779ccf4e22af03e792e8819fff" 
let options={
    method:"GET"
}

fetch(apiUrl,options) 
.then(function(response){
    return response.json() 
})
.then(function(jsonData){
    RecipeList=jsonData 
    newData=RecipeList.recipes
    AppendingRecipies()
})

function gettingDetails(event){
    console.log("trrr") 
   inputdata=event.target.value  
  AppendingRecipies()

}

searchingData.addEventListener("keydown",gettingDetails)
```

**CODE EXPLANATION**


**Initialization and Retrieval of Data from Local Storage**:

It initializes variables and retrieves data from the local storage (if available) using localStorage.getItem("storedone"). If no data is found, an empty array is returned.
**Event Listener for Saving Data**:

It adds an event listener to the "Save" button (save), which triggers the function save.onclick. This function stores the todos_list array in the local storage whenever the "Save" button is clicked.

**Function for Handling Changes in To-Do Items**:

The ontodo_change function toggles the strike-through effect on the to-do item text when its corresponding checkbox is clicked. It also updates the ischecked property of the corresponding to-do item in the todos_list array.

**Function for Appending To-Do Items**:

The appending function dynamically appends a new to-do item to the list. It creates HTML elements for the checkbox, label, and delete icon. It also adds event listeners for checking/unchecking the checkbox and deleting the item.

**Function for Creating New To-Do Item**s:

The create_new function creates a new to-do item when the "Add" button (add_input) is clicked. It retrieves the text input from the user, creates a new object representing the to-do item, adds it to the todos_list array, and appends it to the list.

**Event Listener for Adding To-Do Items**:

It adds an event listener to the "Add" button (add_input), triggering the create_new function when clicked.

**Loop for Appending Existing To-Do Items**:

It iterates through each item in the todos_list array and appends them to the list using the appending function.

**Conclusion:**

In conclusion the task assigned to kolavanti.Tejaswi during the CodTech IT Solutions internship program involved building a webpage using HTML,CSS,JAVASCRIPT. The implemented solution successfully accomplish the task using the Event handling,loops,localstorage methods and using the css for polish look.This document provides insights into the implemented details,code explanation,and rationale behind the choosen approach.
Kolavanti Tejaswi,with the intern ID COD4561 has effectively completed the task as part of the internship program.

This concludes the documentation for the task "RECIPE ORGANIZER APPLICATION " assigned during the CodTech IT Solutions Internship program.
