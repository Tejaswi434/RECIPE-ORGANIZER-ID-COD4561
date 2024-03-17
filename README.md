**Title: CodTech IT Solutions Internship- TaskDocumentation:**RECIPE ORGANIZER**

**Introduction :**
This documentation provides detailed explanation of the task assigned during the CodTech IT Solutions internship program.The task involves in Creating  a TO -DO LIST WEB PAGE using HTML,CSS,JAVASCRIPT. This documentation will cover the implementation details,Rationale behind the code structure,and insights into the programming techniques utilised. Additionally it will include information about the intern ,Kolavanti Tejaswi, and her assigned ID COD4561.

**Intern Information**
Name:Kolavanti Tejaswi
Intern Id: COD4561 

**Task Description**
The task assigned to Kolavanti Tejaswi during the CodTech IT Solutions Internship program is to Create a TO -DO LIST WEB PAGE using HTML,CSS,JAVASCRIPT

**Implementation**
```**HTML:**
<!DOCTYPE html>
<html>

<head>
    <link rel="stylesheet" href="https://cdn.jsdelivr.net/npm/bootstrap@4.5.3/dist/css/bootstrap.min.css" integrity="sha384-TX8t27EcRE3e/ihU7zmQxVncDAy5uIKz4rEkgIXeMed4M0jlfIDPvg6uqKI2xXr2" crossorigin="anonymous">
    <script src="https://code.jquery.com/jquery-3.5.1.slim.min.js" integrity="sha384-DfXdz2htPH0lsSSs5nCTpuj/zy4C+OGpamoFVy38MVBnE+IbbVYUew+OrCXaRkfj" crossorigin="anonymous"></script>
    <script src="https://cdn.jsdelivr.net/npm/popper.js@1.16.1/dist/umd/popper.min.js" integrity="sha384-9/reFTGAW83EW2RDu2S0VKaIzap3H66lZH81PoYlFhbGU+6BZp6G7niu735Sk7lN" crossorigin="anonymous"></script>
    <script src="https://cdn.jsdelivr.net/npm/bootstrap@4.5.3/dist/js/bootstrap.min.js" integrity="sha384-w1Q4orYjBQndcko6MimVbzY0tgp4pWB4lZ7lr30WKz0vr/aWKhXdBNmNb5D92v7s" crossorigin="anonymous"></script>
    <script src="https://kit.fontawesome.com/e9264497ac.js" crossorigin="anonymous"></script>
    <link rel="stylesheet" href="assignment.css">
</head>

<body>
    <div class="main-container">
        <div class="container first_half">
            <div class="row">
                <div class="col-12">
                    <h1 class="text">Todos</h1>
                    <h1 class="create">
                        <b>Create</b> Task
                    </h1>
                    <input type="text" class="inputelement" id="first_input" />
                    <button class="btn btn-primary adding" id="main_input">Add</button>
                    <h1 class="tasks">My tasks</h1>
                    <ul class="todos-container" id="todos_container">
                    </ul>
                    <button class="btn btn-primary" id="saved">Save</button>
                </div>

            </div>
       
        </div>
      
       
       
   
   
    </div>
    <script src="assignment.js"></script>
</body>

</html>

**CSS**
@import url('https://fonts.googleapis.com/css2?family=Bree+Serif&family=Caveat:wght@400;700&family=Lobster&family=Monoton&family=Open+Sans:ital,wght@0,400;0,700;1,400;1,700&family=Playfair+Display+SC:ital,wght@0,400;0,700;1,700&family=Playfair+Display:ital,wght@0,400;0,700;1,700&family=Roboto:ital,wght@0,400;0,700;1,400;1,700&family=Source+Sans+Pro:ital,wght@0,400;0,700;1,700&family=Work+Sans:ital,wght@0,400;0,700;1,700&display=swap');
@import url('https://fonts.googleapis.com/css2?family=Bree+Serif&family=Caveat:wght@400;700&family=Lobster&family=Monoton&family=Open+Sans:ital,wght@0,400;0,700;1,400;1,700&family=Playfair+Display+SC:ital,wght@0,400;0,700;1,700&family=Playfair+Display:ital,wght@0,400;0,700;1,700&family=Roboto:ital,wght@0,400;0,700;1,400;1,700&family=Source+Sans+Pro:ital,wght@0,400;0,700;1,700&family=Work+Sans:ital,wght@0,400;0,700;1,700&display=swap');

.todos-container{
    width:1000px;
}
.text {
    text-align: center;
    font-size: 60px;
}

.create {
    font-size: 40px;
    text-align: left;
    margin-top: 30px;
    padding-left: 0px;
}

.main-container {
    height: 100vh;
    width: 100vw;
    display:flex;
    flex-direction:row;
    background-image: url("https://t3.ftcdn.net/jpg/01/28/87/04/240_F_128870437_TXj1QawSYdsDbmIy0KnIOv1ytIiiDOrX.jpg"); 
    background-size:cover;
}

.inputelement {
    width: 60%;
    padding: 10px;
    border-radius: 4px;
}

.adding {
    margin-top: 10px;
}

.tasks {
    margin-top: 50px;
}

.todo_item_list {
    padding: 10px;
    width:1000px;
    margin-right:800px;
}

.label_container {
    width: 100%;
    background-color: #e6f6ff;
    border-radius: 4px;
    padding: 20px;
    margin-left: 4px;
    border-left: 5px solid #096f92;


}

.delete_icon {
    width: 100%;
    text-align: right;
}

.checked {
    text-decoration: line-through;
}
.labelwidth{
    width:500px;
}

.first_half{
    width:800px;
}
.second_half{

margin-right:1900px; 

}
.image_sizing{
    height:500px;
    width:500px;
}

**JAVASCRIPT**
let todos_container = document.getElementById("todos_container");
let add_input = document.getElementById("main_input")
let new_input_item = document.getElementById("first_input")
let save = document.getElementById("saved")

function getting_Data() {
    let data = JSON.parse(localStorage.getItem("storedone"))
    if (data === null) {
        return [];

    } else {
        return data
    }
}
let todos_list = getting_Data();

save.onclick = function() {
    localStorage.setItem("storedone", JSON.stringify(todos_list))
}

function ontodo_change(checkbox_id, label_id, list_no) {

    let element = document.getElementById(checkbox_id);
    let striking = document.getElementById(label_id);
    striking.classList.toggle("checked");
    let element_id = todos_list.findIndex(function(every) {
        let searching_id = "list" + every.unique_no;
        if (searching_id === list_no) {
            return true;
        } else {
            return false;
        }
    });
    let final = todos_list[element_id];
    if (final.ischecked === true) {
        final.ischecked = false;
    } else {
        final.ischecked = true;

    }

}

function appending(each) {
    let checkbox_id = "checkbox" + each.unique_no
    let label_id = "label" + each.unique_no
    let list_no = "list" + each.unique_no
    let element = document.createElement("li")
    element.classList.add("d-flex", "flex-row", "todo_item_list")
    todos_container.appendChild(element)
    let input_element = document.createElement("input");
    input_element.id = checkbox_id;
    input_element.type = "checkbox";
    
    element.appendChild(input_element);
    let label_container = document.createElement("div");
    label_container.classList.add("label_container", "d-flex", "flex-row");
    element.appendChild(label_container);
    let label_element = document.createElement("label");
    label_element.id = label_id;
    label_element.htmlFor = checkbox_id;
    label_element.textContent = each.text;
    label_element.classList.add("labelwidth");
    input_element.onclick = function() {
        ontodo_change(checkbox_id, label_id, list_no);
    };
    input_element.checked = each.ischecked
    if (each.ischecked === true) {
        label_element.classList.add("checked");
    }
    label_container.appendChild(label_element);
    let delete_container = document.createElement("div");
    delete_container.classList.add("delete_icon");
    label_container.appendChild(delete_container);
    let delete_item = document.createElement("i");
    delete_container.appendChild(delete_item);
    delete_item.classList.add("fa-solid", "fa-trash");
    delete_item.onclick = function() {
        todos_container.removeChild(element);
        let item = todos_list.findIndex(function(element) {
            let new_one = "list" + element.list_no;
            if (list_no === new_one) {
                console.log(element.list_no);
                return true;
            } else {
                return false;
            }
        });
        todos_list.splice(item, 1);
    };
}

function create_new() {
    let length_item = todos_list.length;
    if (new_input_item.value === "") {
        alert("enter something");
        return;
    }
    let new_item = {
        text: new_input_item.value,
        unique_no: length_item + 1,
        ischecked: false
    };
    console.log(new_item);
    todos_list.push((new_item));



    appending(new_item);
    new_input_item.value = "";
}
add_input.onclick = function() {
    create_new();
}
for (let each of todos_list) {
    appending(each)
}
```

**CODE EXPLANATION**


1. **Variable Declarations**:
   - `checkbox_id`, `label_id`, `list_no`: These variables are used to generate unique IDs for elements in the to-do list.
   - `element`: This variable creates a new list item (`<li>`) element.
   - `input_element`: This creates a checkbox input element within the list item.
   - `label_container`: This creates a container for the label associated with the checkbox.
   - `label_element`: This creates a label element for displaying the text of the to-do item.
   - `delete_container`, `delete_item`: These create a container and an icon for deleting the to-do item.

2. **Setting Attributes and Appending Elements**:
   - Attributes like IDs, type, text content, and event listeners are set for various elements.
   - Elements are appended to each other and ultimately to the DOM (`todos_container`).

3. **Event Handling**:
   - `input_element.onclick`: This event listener triggers the `ontodo_change` function when the checkbox is clicked.
   - `delete_item.onclick`: This event listener removes the corresponding to-do item when the delete icon is clicked.

4. **Functions**:
   - `create_new`: This function creates a new to-do item based on the text entered in the input field (`new_input_item`). It adds this item to the `todos_list` array and then appends it to the DOM using the `appending` function.
   - `appending`: This function appends a new to-do item to the DOM based on the provided item object.
   
5. **Event Handling**:
   - `add_input.onclick`: This event listener calls the `create_new` function when the add button (`add_input`) is clicked.
   
6. **Loop**:
   - A loop iterates over each item in the `todos_list` array and appends them to the DOM using the `appending` function.

This code essentially creates a dynamic to-do list interface where users can add, check, and delete items. The state of each item (checked or unchecked) is stored in the `todos_list` array.

**Rationale:**
● Streamlined task management through a combination of HTML, CSS, and Bootstrap for an intuitive interface.
● Seamless CRUD operations through JavaScript event listeners and dynamic UI updates.
● Secure task persistence with local storage methods, ensuring that your tasks are always available.


**Conclusion:**

In conclusion the task assigned to kolavanti.Tejaswi during the CodTech IT Solutions internship program involved building a webpage using HTML,CSS,JAVASCRIPT. The implemented solution successfully accomplish the task using the Event handling,loops,localstorage methods and using the css for polish look.This document provides insights into the implemented details,code explanation,and rationale behind the choosen approach.
Kolavanti Tejaswi,with the intern ID COD4561 has effectively completed the task as part of the internship program.

This concludes the documentation for the task "building TO -DO LIST WEB APPLICATION " assigned during the CodTech IT Solutions Internship program.
