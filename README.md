# node-duphlux
A small NodeJS  wrapper library for the telephone verification service Duphlux. 

## Installation

  npm install node-duphlux --save

## Usage

var Duphlux = require('node-duphlux');
var duphlux = new Duphlux({token:'your_token'});

## To Verify Number
duphlux.verifyNumber(UserNumber, Unique Reference Number, Site Redirect URL).then(
        function(payLoad){
            console.log(payLoad);
        }, 
        function(e){
            console.log(e)
        }
    );
Method verfyNumber Returns a promise with resolve and reject implemented. For a succesful interaction with Duphlux server, the Payload returns something similar to : 
        {   
            status: true,
            data: 
            { number: '+15097745654',
                expires_at: 1498012830,
                transaction_reference: 'iUuqvqyT2e1C4ogl',
                verification_reference: 'b30e29d3a8a201a62180a8bd2d06d23b0533e467',
                verification_url: 'https://duphlux.com/verify/b30e29d3a8a201a62180a8bd2d06d23b0533e467' 
                } 
        } 

You can also generate a unique reference number by making use of the duphlux.generateRef();

##To Check Previous Authentication Request Status
    duphlux.checkStatus(Unique Reference Number)

    This also returns a Promise

    For further Documentation kindly goto Duphlux


## Tests
In progress...



## Release History

* 0.1.0 Initial releas

