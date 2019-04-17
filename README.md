# joi-joi
Joi validation for Joi Schema

Use this module if you'd like to validate a Joi schema object that may be external to your own system.

## Usage
```javascript
const BaseJoi = require( "joi" );
const JoiJoi = require( "joi-joi" );
const Joi = BaseJoi.extend(JoiJoi);

const validObject = Joi.object( ).keys( {
	"foo": Joi.string( )
} );

const invalidObject = { "foo": "bar" };

Joi.validate( validObject, Joi.joi( ).valid( ), ( err, result ) => {
	// err => null
	// result => Joi schema object
} );

Joi.validate( invalidObject, Joi.joi( ).valid( ), ( err, result ) => {
	// err => populated
} );
```
