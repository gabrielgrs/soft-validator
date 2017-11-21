# Tutorial para usar o soft-validator

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
}