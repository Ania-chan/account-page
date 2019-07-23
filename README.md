# account-page

This is a simple account page component including profile picture, full name, email and password. Profile picture is fetched from gravatar. Each field can be edited and saved.

## Input validation:

- Full name (required): shouldn't be longer than 30 characters and can only contain letters.
- Email (required): is a valid email address.
- Password (required): is longer than 8 characters and strength estimation is higher that 2.

## Getting Started

### Install

```
yarn install
```

### Start

```
yarn start
```

## Built with

- [Vue](https://vuejs.org/) - A progressive framework for building user interfaces using JavaScript
- [Buefy](https://buefy.org/) - A lightweight UI components library for Vue.js based on Bulma
- [VeeValidate](https://baianat.github.io/vee-validate/) - Template Based Validation Framework for Vue.js
- [zxcvbn](https://github.com/dropbox/zxcvbn) - Open-source Password Strength Estimation

## License

See [Configuration Reference](https://cli.vuejs.org/config/).
