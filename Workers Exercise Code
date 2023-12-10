const BASE_URL = "https://exam-17814-default-rtdb.europe-west1.firebasedatabase.app/.json";

function getAllEmployees(){
    const table = document.getElementById("results").getElementsByTagName('tbody')[0];
    const addBtn = document.getElementById("add-button");
    addBtn.addEventListener("click", addEmployee);
    table.innerHTML = "";
    fetch(BASE_URL)
    .then((response) => response.json())
    .then((result) => 
    {
        Object.entries(result).forEach((emp
            
            ) => {
                console.log(emp);
                Object.entries(emp[1].workers).forEach((emp1) => {
                    console.log(emp1);
                    table.innerHTML += `<tr>
                <td>${emp1[1].id}</td>
                <td>${emp1[1].firstName}</td>
                <td>${emp1[1].lastName}</td>
                <td>${emp1[1].ssn}</td>
            </tr> `;
            });})
                
                
});
}
getAllEmployees();
function addEmployee(ev){
    ev.preventDefault();
    let form = ev.target.parentElement;
    let[id,firstName,lastName,ssn] = form.querySelectorAll("input");
    if(id.value != "" && firstName.value != "" && lastName != "" && ssn != ""){
        const options = {
            method: 'Patch',
            headers:{
                "content-type":"application/json",
            },
            body: JSON.stringify({
                
                "workers/id":id.value,
                "workers/firstName":firstName.value,
                "workers/lastName":lastName.value,
                "workers/ssn":ssn.value,
            }
                
        ),
        };
        fetch(BASE_URL, options)
        .then(response => response.json())
        .then(result => getAllEmployees());
    }
    else{
        alert('bffh');
    }
}
