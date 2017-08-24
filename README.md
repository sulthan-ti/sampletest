<h><b>Description<b></h>

This is a node package for actum payment processing. Developer can use this package for credit issuing, status, cancellation, refund, revoke, etc

You can install this module using npm:

npm install actum-titech
This will install the given package into your project. Then require this package to your project.

var actum=require("actum-titech");
1) Credit issuing

Usage:

    actum.creditIssuing(paymentdata, (res) =>{
        // res contains response data
    });

Required fields are :

     parent_id      :   Your ParentID (Alphanumeric 8)
     sub_id         :   Your SubID  (Alphanumeric 8)
     custname       :   Consumer's full name (Alphanumeric 64)
     custaddress1   :   Consumer's street address (Alphanumeric 64)
     custcity       :   Consumer's city (Alphanumeric 32)
     custstate      :   Consumer's state (Alphanumeric 32)
     custzip        :   Consumer's zip code (Alphanumeric 16)
     custphone      :   Consumer's phone number (Alphanumeric 16)
     chk_acct       :   Consumer's checking account number (Alphanumeric 32)
     initial_amount :   Initial amount of the bill (xx.xx)
     billing_cycle  :   -1 = One-Time (Number)
     pmt_type       :   [chk|crd]: 'chk'=check; 'crd'= credit card
     chk_aba        :   Consumers ABA/Routing number (Alphanumeric 9)
2) Billing Status

Usage:

    actum.billingStatus(paymentdata, (res) => {
         // res contains response data
    });

Required Fileds are:

        username        : username for actom(ALPHANUMERIC)
        password        : password for actom(ALPHANUMERIC)
        action_code     :   'A'
        prev_history_id     : previous transaction Id
3) Payment cancellation

Usage:

    actum.paymentCancellation(paymentdata, (res) => {
        // res contains response data
    });

Required Fields are:

        username        : username for actom(ALPHANUMERIC)
        password        : password for actom(ALPHANUMERIC)
        action_code     : 'C'
        prev_history_id         :  previous transaction Id
