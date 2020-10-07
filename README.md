# checkbox
You can console.log what you query selected in order to check if you selected the correct elements

let checkbox = document.querySelectorAll('input[type="checkbox"]');
console.log(checkbox);

checkbox is an array of input elements so you can add an event listener for each element by looping through them

checkbox.forEach(input => input.addEventListener('click', handleCheck));

You can console.log the event to check the event listener

function handleCheck(e){
 console.log(e);
}

Create a variable that stores which element was checked

let lastChecked;
function handleCheck(e){
lastChecked = this;
}

Check if shift key was pressed down and checkbox has been checked

function handleCheck(e){
 if(e.shiftKey && this.checked){
 }
lastChecked = this;
}

Create a checking variable with default value false and loop through each checkbox element.

If the checkbox element is equal to lastChecked value or the element that was shift clicked, the variable value is set to the opposite value
If the variable value is true, the checkbox is checked

let lastChecked;
function handleCheck(e) {
 let inBetween = false;
 if (e.shiftKey && this.checked) {
  // loop over every single checkbox
  checkboxes.forEach(checkbox => {
   if (checkbox === this || checkbox === lastChecked) {
   inBetween = !inBetween;
   }
   if (inBetween) {
   checkbox.checked = true;
   }
  });
 }
lastChecked = this;
}
