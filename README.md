#Form.js

JavaScript form validation framework inspired by Django.form

## define a form

```
var SignUpForm = Form({
    username: StringField({ required: true, maxLength: 20, minLength: 6 }),
    password: PasswordField({ required: true, maxLength: 30, minLength: 6 }),
    repassword: PasswordField({ required: true, maxLength: 30, minLength: 6 }),
    // cleaner
    clean_password_repassword: function (password, repassword) {
        if (password !== repassword) {
            throw new Error('Sorry! You need to input a same password twice.')
        }
    }
});
```

## bind to DOM

```
var form = SignUpForm({
	$el: $('form')
})
```

that's all