# Account Page for Vue.js

This is a simple account page card showing gravatar profile picture, full name, email and password. Each field can be edited and saved.

## Input validation:

- Full name (required): shouldn't be longer than 30 characters and can only contain letters.
- Email (required): is a valid email address.
- Password (required): is longer than 8 characters and strength estimation is higher that 2 (in the scale of 4).

## Getting Started

### Use [yarn](https://yarnpkg.com/en/) to install dependencies.

```
$ yarn install
```

### Serve with hot reload at localhost:8080

```
$ yarn serve
```

### Build for production

```
$ yarn build
```

### Start in production mode at localhost:5000

```
$ yarn start
```

## Built with

- [Vue](https://vuejs.org/) - A progressive framework for building user interfaces using JavaScript.
- [Buefy](https://buefy.org/) - A lightweight UI components library for Vue.js based on Bulma.
- [VeeValidate](https://baianat.github.io/vee-validate/) - Template Based Validation Framework for Vue.js.
- [zxcvbn](https://github.com/dropbox/zxcvbn) - Open-source Password Strength Estimation

## License

[MIT](https://choosealicense.com/licenses/mit/)
