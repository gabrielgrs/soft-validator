# Soft-Validator

### Getting Start

1. Install
 ```bash
 npm i -S soft-validator
 ```
2. Use to easy

```js
const SoftValidator = require('soft-validator');

exports.post = async(req, res, next) => {
    var firstText = 'Hello World!';
    var secondText = 'Hey';

    let validator = new SoftValidator();
    validator.hasMaxLen(req.body.firstText, 5, 'Field with a maximum of 5 characters');
    validator.hasMinLen(req.body.secondText, 5, 'Field with a minimum of 5 characters');

    // Invalid data
    if (!validator.isValid()) {
        res.status(400).send(validator.errors()).end();
        return;
    }
};
```

#### Contributors
 [@renanbastos93](https://github.com/renanbastos93)

#### LICENSE
 [MIT](https://opensource.org/licenses/MIT)