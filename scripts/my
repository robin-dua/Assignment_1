// Form validation

const form = document.querySelector('#myForm');
const usernameInput = document.querySelector('#username');
const emailInput = document.querySelector('#email');
const messageInput = document.querySelector('#message');

form.addEventListener('submit', (event) => {
    validateForm();
    console.log(isFormValid());
    if (isFormValid() == true) {
        form.submit();
        alert('You are being redirected');
        window.open("https://lng-consultancy.com/", "_blank");
    } else {
        event.preventDefault();
    }

});

//Email validation function
function isEmailValid(email) {
    const reg = /^(([^<>()[\]\.,;:\s@\"]+(\.[^<>()[\]\.,;:\s@\"]+)*)|(\".+\"))@(([^<>()[\]\.,;:\s@\"]+\.)+[^<>()[\]\.,;:\s@\"]{2,})$/i;

    return reg.test(email);
}

// Validating the form
function isFormValid() {
    const inputContainers = form.querySelectorAll('.form-group');
    let result = true;
    inputContainers.forEach((container) => {
        if (container.classList.contains('error')) {
            result = false;
        }
    });
    return result;
}

//Form validations
function validateForm() {
    let correct_way = /^[A-Z a-z]+$/;

    //Username validation
    if (usernameInput.value == '') {
        setError(usernameInput, 'Name cannot be blank ');
    } else if (!usernameInput.value.match(correct_way)) {
        setError(usernameInput, 'Name cannot contain special characters or numbers and should only be alphabets');
    } else {
        setSuccess(usernameInput);
    }

    //Email validation
    if (emailInput.value == '') {
        setError(emailInput, 'Email address should not be blank');
    } else if (isEmailValid(emailInput.value)) {
        setSuccess(emailInput);
    } else {
        setError(emailInput, 'Provide valid email address');
    }

    //Message validation
    if (messageInput.value == '') {
        setError(messageInput, 'Message cannot be blank');
    } else if (messageInput.value.length <= 40) {
        setError(messageInput, 'Message should be a minimum of 40 characters long');
    } else {
        setSuccess(messageInput);
    }

}

// Setting the error function
function setError(element, errorMessage) {
    const parent = element.parentElement;
    if (parent.classList.contains('success')) {
        parent.classList.remove('success');
    }
    parent.classList.add('error');
    const paragraph = parent.querySelector('span');
    paragraph.textContent = errorMessage;
}

// Setting the success function
function setSuccess(element) {
    const parent = element.parentElement;
    if (parent.classList.contains('error')) {
        parent.classList.remove('error');
    }
    parent.classList.add('success');
}
