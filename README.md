# PyThru API Documentation 1.0.3

## 1. Document Illustration 1.0.3 <a id="document_illustration"></a>

The documents provider is PyThru, we focus on providing our merchants a standard API integration rules. We have the right of final explanation on the document and have reserved right to update it any time.

1. After using the document, you can achieve the following functions: 'Accept credit payment online', 'Query order information', 'Refund the order' and so on.
2. The documents reader is merchants' administrator, maintainer and developer.
3. Except defined, platform mentioned in this document means PyThru.

## 2. Preparation <a id="preparation"></a>

> Example of API code to user for Integration:

```text
PyThru MERCHANT:



 type="hidden" name="api_token" value="MjZfMTEyMF8yMDE4MDcyNzEyMjgyNQ"/>
 type="hidden" name="website_id" value="1120"/>


```

1. Read all the API document carefully.
2. Obtain 2 very important parameters, they are **"api\_token" , "website\_id"**.

<table>
  <thead>
    <tr>
      <th style="text-align:left">Parameter</th>
      <th style="text-align:left">Description</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td style="text-align:left">
        <p><b>website_id</b>
        </p>
        <p>int M</p>
        <p>required</p>
      </td>
      <td style="text-align:left">Website Id is very important parameter and you can find &apos;Website
        Id&apos; as a numeric value within the <a href="https://pg.pythru.com/user/website"><b>My Website</b></a> area
        or you can find it easily by following <b>My Website &#x2192; </b><a href="https://pg.pythru.com/user/new_website"><b>Add New Website</b></a>
      </td>
    </tr>
    <tr>
      <td style="text-align:left">
        <p><b>api_token</b>
        </p>
        <p>str M</p>
        <p>required</p>
      </td>
      <td style="text-align:left">Website API Token is a string value. You can find it by following
        <br /><a href="https://pg.pythru.com/user/website"><b>My Website</b></a><b> &#x2192; Website API Token (as created inside area of New Website)</b>
      </td>
    </tr>
  </tbody>
</table>

## 3. Payment Gateway <a id="payment_gateway"></a>

> Example of Payment Gateway :

```text
 method="post" action="https://pg.pythru.com/payment" name="paymentform">



 type="hidden" name="api_token" value="MjZfMTEyMF8yMDE4MDcyNzEyMjgyNQ"/>
 type="hidden" name="website_id" value="1120"/>



 type="hidden" name="cardsend" value="CHECKOUT"/>
 type="hidden" name="action" value="product"/>



 type="hidden" name="price" value="50.00"/>
 type="hidden" name="curr" value="INR"/>
 type="hidden" name="product_name" value="Testing Product "/>



 type="hidden" name="ccholder" value="Test First Name"/>
 type="hidden" name="ccholder_lname" value="Test Last Name"/>
 type="hidden" name="email" value="test.2023@test.com"/>
 type="hidden" name="bill_street_1" value="25A Alpha"/>
 type="hidden" name="bill_street_2" value="tagore lane"/>
 type="hidden" name="bill_city" value="Jurong"/>
 type="hidden" name="bill_state" value="New Delhi"/>
 type="hidden" name="bill_country" value="India"/>
 type="hidden" name="bill_zip" value="787602"/>
 type="hidden" name="bill_phone" value="+65 62200944"/>
 type="hidden" name="id_order" value="2017013120170131"/>
 type="hidden" name="notify_url" value="https://yourdomain.com/notify.php"/>
 type="hidden" name="success_url" value="https://yourdomain.com/success.php"/>
 type="hidden" name="error_url" value="https://yourdomain.com/failed.php"/>
 type="hidden" name="source" value="Host-Redirect-Card-Payment (Core PHP)"/>

 type="submit" name="submit" value="SUBMIT"/>
	


```

To pass the parameters, we accept both POST method and GET method. You may use any of POST or GET.

Steps to generate an API code:

1. **Merchant Login -**To login the dashboard, **username & password** is mandatory.
2. **Website API Token -** Website API Token is a string value. You can find it by following [**My Website**](https://pg.pythru.com/user/website) **→ Website API Token \(as created inside area of New Website\)**.
3. **Website ID-** Website Id is very important parameter and you can find 'Website Id' as a numeric value within the [**My Website**](https://pg.pythru.com/user/website) area or you can find it easily by following **My Website →** [**Add New Website**](https://pg.pythru.com/user/new_website)
4. **Generate Website API Token -** After adding Website Details code of Website API Token will be generated automatically. This code is required when you proceed for Payment Integration.

| **Gateway URL** | https://pg.pythru.com/payment |
| :--- | :--- |
| **Method** | POST or GET |
| **Function** | Accept Check or Credit card payment online from the customers |
| **Remark** | 10 mandatory parameters, the others are all optional |

<table>
  <thead>
    <tr>
      <th style="text-align:left">Parameter</th>
      <th style="text-align:left">Description</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td style="text-align:left">
        <p><b>api_token</b>
        </p>
        <p>str M</p>
        <p>required</p>
      </td>
      <td style="text-align:left">Website API Token is a string value. You can find it by following
        <br /><a href="https://pg.pythru.com/user/website"><b>My Website</b></a><b> &#x2192; Website API Token (as created inside area of New Website)</b>
      </td>
    </tr>
    <tr>
      <td style="text-align:left">
        <p><b>website_id</b>
        </p>
        <p>int M</p>
        <p>required</p>
      </td>
      <td style="text-align:left">Website Id is very important parameter and you can find &apos;Website
        Id&apos; as a numeric value within the <a href="https://pg.pythru.com/user/website"><b>My Website</b></a> area
        or you can find it easily by following <b>My Website &#x2192; </b><a href="https://pg.pythru.com/user/new_website"><b>Add New Website</b></a>
      </td>
    </tr>
    <tr>
      <td style="text-align:left">
        <p><b>cardsend</b>
        </p>
        <p>str D</p>
        <p>required</p>
      </td>
      <td style="text-align:left">cardsend, a string for default (fixed) value <b>CHECKOUT</b>.</td>
    </tr>
    <tr>
      <td style="text-align:left">
        <p><b>action</b>
        </p>
        <p>str D</p>
        <p>required</p>
      </td>
      <td style="text-align:left">action, a string for default (fixed) value <b>product</b>.</td>
    </tr>
    <tr>
      <td style="text-align:left">
        <p><b>price</b>
        </p>
        <p>dec(10.0.0) M</p>
        <p>required</p>
      </td>
      <td style="text-align:left">Order Amount, currency format in decimal(10.0.0)</td>
    </tr>
    <tr>
      <td style="text-align:left">
        <p><b>product_name</b>
        </p>
        <p>str M</p>
        <p>required</p>
      </td>
      <td style="text-align:left">Product Name</td>
    </tr>
    <tr>
      <td style="text-align:left">
        <p><b>ccholder</b>
        </p>
        <p>str C</p>
        <p>required</p>
      </td>
      <td style="text-align:left">Customer first name</td>
    </tr>
    <tr>
      <td style="text-align:left">
        <p><b>ccholder_lname</b>
        </p>
        <p>str C</p>
        <p>required</p>
      </td>
      <td style="text-align:left">Customer last name</td>
    </tr>
    <tr>
      <td style="text-align:left">
        <p><b>email</b>
        </p>
        <p>str C</p>
        <p>required</p>
      </td>
      <td style="text-align:left">Customer billing email</td>
    </tr>
    <tr>
      <td style="text-align:left">
        <p><b>bill_street_1</b>
        </p>
        <p>str C</p>
        <p>required</p>
      </td>
      <td style="text-align:left">Customer&apos;s shipping street</td>
    </tr>
    <tr>
      <td style="text-align:left">
        <p><b>bill_street_2</b>
        </p>
        <p>str C</p>
        <p>optional</p>
      </td>
      <td style="text-align:left">Customer&apos;s shipping street 2</td>
    </tr>
    <tr>
      <td style="text-align:left">
        <p><b>bill_city</b>
        </p>
        <p>str C</p>
        <p>required</p>
      </td>
      <td style="text-align:left">Customer&apos;s shipping city</td>
    </tr>
    <tr>
      <td style="text-align:left">
        <p><b>bill_state</b>
        </p>
        <p>str C</p>
        <p>optional</p>
      </td>
      <td style="text-align:left">Customer&apos;s shipping state</td>
    </tr>
    <tr>
      <td style="text-align:left">
        <p><b>bill_country</b>
        </p>
        <p>str C</p>
        <p>required</p>
      </td>
      <td style="text-align:left">Customer&apos;s shipping country</td>
    </tr>
    <tr>
      <td style="text-align:left">
        <p><b>bill_zip</b>
        </p>
        <p>str C</p>
        <p>optional</p>
      </td>
      <td style="text-align:left">Customer&apos;s shipping zip code</td>
    </tr>
    <tr>
      <td style="text-align:left">
        <p><b>bill_phone</b>
        </p>
        <p>str C</p>
        <p>required</p>
      </td>
      <td style="text-align:left">Customer billing phone</td>
    </tr>
    <tr>
      <td style="text-align:left">
        <p><b>id_order</b>
        </p>
        <p>str M</p>
        <p>optional</p>
      </td>
      <td style="text-align:left">Merchant&#x2019;s order ID that will be returned back in a callback.</td>
    </tr>
    <tr>
      <td style="text-align:left">
        <p><b>notify_url</b>
        </p>
        <p>str M</p>
        <p>optional</p>
      </td>
      <td style="text-align:left">Synchronous notification URL, you can find it in the response data.</td>
    </tr>
    <tr>
      <td style="text-align:left">
        <p><b>success_url</b>
        </p>
        <p>str M</p>
        <p>optional</p>
      </td>
      <td style="text-align:left">Redirect url of success as per your domain</td>
    </tr>
    <tr>
      <td style="text-align:left">
        <p><b>error_url</b>
        </p>
        <p>str M</p>
        <p>optional</p>
      </td>
      <td style="text-align:left">Redirect url of error as per your domain</td>
    </tr>
  </tbody>
</table>

## 4. Notify / Callbacks <a id="notify_callbacks"></a>

> ### Example Request of curl notify\_url <a id="example-request"></a>

```text
{
    "status_nm":"1",
    "status":"Success",
    "amount":"20",
    "transaction_id":"20170928115044",
    "descriptor":"PyThru",
    "tdate": "2017-09-28 11:50:44",
    "curr": "INR",
    "reason": "Success",
    "id_order":"20170131",
}

```

You can find Notify URL in the area of Website Settings to set the value of the parameter. Notify URL parameter’s name is 'notify\_url'. However, it is optional because it has to be added dynamically during the payment processing. You will receive the Notify parameters via HTTP POST method. The value of all parameters must be treated as strings.

<table>
  <thead>
    <tr>
      <th style="text-align:left">Parameter</th>
      <th style="text-align:left">Description</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td style="text-align:left">
        <p><b>status_nm</b>
        </p>
        <p>int</p>
      </td>
      <td style="text-align:left">Numeric ID of status.</td>
    </tr>
    <tr>
      <td style="text-align:left">
        <p><b>status</b>
        </p>
        <p>string</p>
      </td>
      <td style="text-align:left">Status of a transaction. See the <a href>Transaction Status</a> section.</td>
    </tr>
    <tr>
      <td style="text-align:left">
        <p><b>amount</b>
        </p>
        <p>decimal(10,2)</p>
      </td>
      <td style="text-align:left">Amount of virtual currency to give it to a user.</td>
    </tr>
    <tr>
      <td style="text-align:left">
        <p><b>transaction_id</b>
        </p>
        <p>bigint(20)</p>
      </td>
      <td style="text-align:left">ID of transaction.</td>
    </tr>
    <tr>
      <td style="text-align:left">
        <p><b>descriptor</b>
        </p>
        <p>string</p>
      </td>
      <td style="text-align:left">Memo of Payment Receiver.</td>
    </tr>
    <tr>
      <td style="text-align:left">
        <p><b>tdate</b>
        </p>
        <p>timestamp</p>
      </td>
      <td style="text-align:left">Current Date and time when created the transaction</td>
    </tr>
    <tr>
      <td style="text-align:left">
        <p><b>curr</b>
        </p>
        <p>string(3)</p>
      </td>
      <td style="text-align:left">Currency of transaction. Price, deposit and earned parameters are in this
        curr.</td>
    </tr>
    <tr>
      <td style="text-align:left">
        <p><b>reason</b>
        </p>
        <p>string</p>
      </td>
      <td style="text-align:left">May contain a reason for transaction.</td>
    </tr>
    <tr>
      <td style="text-align:left">
        <p><b>order_id</b>
        </p>
        <p>string</p>
      </td>
      <td style="text-align:left">Your order ID, if it was provided.</td>
    </tr>
  </tbody>
</table>

## 5. Transaction Status <a id="transaction_status"></a>

> Example of Transaction Status:

```text
//
	
$url="https://pg.pythru.com/validate?transaction_id=20170928115044&api_token=MjZfMTEyMF8yMDE4MDcyNzEyMjgyNQ";

	$ch = curl_init();
	curl_setopt($ch,CURLOPT_URL, $url);
	curl_setopt($ch,CURLOPT_POST,0);
	curl_setopt($ch,CURLOPT_RETURNTRANSFER,1);
	curl_setopt($ch,CURLOPT_SSL_VERIFYPEER, false); 
	curl_setopt($ch,CURLOPT_SSL_VERIFYHOST, false);
	$response = curl_exec($ch);
	curl_close($ch);

	$json_response = json_decode($response,true);
	
echo $json_response['status_nm'];
echo $json_response['status'];
echo $json_response['amount'];
echo $json_response['transaction_id'];
echo $json_response['descriptor'];
echo $json_response['tdate'];
echo $json_response['curr'];
echo $json_response['reason'];
echo $json_response['id_order'];
Transaction Status for data you will get below response:
{
    "status_nm":"1",
    "status":"Success",
    "amount": 20,
    "transaction_id":"20170928115044",
    "descriptor": "PyThru",
    "tdate": "2017-09-28 11:50:44",
    "curr": "INR",
    "reason": "Success",
    "id_order": ""
 }



```

> ### Example of Transaction Status <a id="error-example"></a>

```text
{
    "status": Success | Failed | Pending | Test
}
```

| **Gateway URL** | https://pg.pythru.com/validate |
| :--- | :--- |
| **Method** | GET |
| **Function** | Requests data from a resource by get method |
| **Remark** | 2 mandatory parameter only \(Website API Token + \(Transaction ID or Order ID\)\) |

<table>
  <thead>
    <tr>
      <th style="text-align:left">Parameter</th>
      <th style="text-align:left">Description</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td style="text-align:left">
        <p><b>api_token</b>
        </p>
        <p>str M</p>
        <p>required</p>
      </td>
      <td style="text-align:left">Website API Token is a string value. You can find it by following <b>My Website &#x2192; Website API Token</b>
      </td>
    </tr>
    <tr>
      <td style="text-align:left">
        <p><b>transaction_id</b>
        </p>
        <p>int M</p>
        <p>required</p>
      </td>
      <td style="text-align:left">Transaction ID&#xFF0C;an integer and you will use it to login to the merchant
        dashboard. You will find it at the <b>&quot;Transactions List&quot;</b> page.
        You may find merchant login by following <b>View All Transaction &#x2192; Transaction Id.</b>
      </td>
    </tr>
    <tr>
      <td style="text-align:left">
        <p><b>id_order</b>
        </p>
        <p>int M</p>
        <p>required</p>
      </td>
      <td style="text-align:left">Your order ID, if it was provided.</td>
    </tr>
  </tbody>
</table>

## 6. Refund Order Request <a id="refund_order_request"></a>

> Example of Refund Order Request:

```text
//
	
$url="https://pg.pythru.com/refund?api_token=MjdfMTEyMl8yMDE4MDcyNTE0NDc1OA==&transaction_id=20170928115044&amount=95.50";

	$ch = curl_init();
	curl_setopt($ch,CURLOPT_URL, $url);
	curl_setopt($ch,CURLOPT_POST,0);
	curl_setopt($ch,CURLOPT_RETURNTRANSFER,1);
	curl_setopt($ch,CURLOPT_SSL_VERIFYPEER, false); 
	curl_setopt($ch,CURLOPT_SSL_VERIFYHOST, false);
	$response = curl_exec($ch);
	curl_close($ch);

	$json_response = json_decode($response,true);
	
echo $json_response['status_nm'];
echo $json_response['message'];
echo $json_response['status'];
echo $json_response['amount'];
echo $json_response['transaction_id'];
echo $json_response['descriptor'];
echo $json_response['tdate'];
echo $json_response['curr'];
echo $json_response['reason'];
echo $json_response['id_order'];
Transaction Status after refund for data you will get below response:
{
    "status_nm":"8",
    "message":"Request Processed",
    "status":"Request Processed",
    "amount": 20,
    "transaction_id":"20170928115044",
    "descriptor": "PyThru",
    "tdate": "2017-09-28 11:50:44",
    "curr": "INR",
    "reason": "Success",
    "id_order": ""
 }



```

> ### Example of Transaction Status <a id="error-example"></a>

```text
{
    "status": Success | Failed | Pending
}
```

| **Gateway URL** | https://pg.pythru.com/refund?api\_token=MjdfMTEyMl8yMDE4MDcyNTE0NDc1OA== &transaction\_id=20170928115044&amount=95.50 |
| :--- | :--- |
| **Method** | GET |
| **Function** | Requests data from a resource by get method |
| **Remark** | 3 mandatory parameters only |

<table>
  <thead>
    <tr>
      <th style="text-align:left">Parameter</th>
      <th style="text-align:left">Description</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td style="text-align:left">
        <p><b>transaction_id</b>
        </p>
        <p>int M</p>
        <p>required</p>
      </td>
      <td style="text-align:left">Transaction ID&#xFF0C;an integer and you will use it to login to the merchant
        dashboard. You will find it at the <b>&quot;Transactions List&quot;</b> page.
        You may find merchant login by following <b>View All Transaction &#x2192; Transaction Id.</b>
      </td>
    </tr>
    <tr>
      <td style="text-align:left">
        <p><b>api_token</b>
        </p>
        <p>str M</p>
        <p>required</p>
      </td>
      <td style="text-align:left">Website API Token is a string value. You can find it by following <b>My Website &#x2192; Website API Token</b>
      </td>
    </tr>
    <tr>
      <td style="text-align:left">
        <p><b>amount</b>
        </p>
        <p>dec(10,2) M</p>
        <p>required</p>
      </td>
      <td style="text-align:left">This is Order Amount and currency format is set to be in decimal (10,2)</td>
    </tr>
  </tbody>
</table>

## 7. Test Card Number <a id="test_card_number"></a>

| **Credit Card Type** | **Credit Card Number** | **Expiry Month** | **Expiry Year** | **CVV** |
| :--- | :--- | :--- | :--- | :--- |
| Visa | 4242424242424242 | 01 | 30 | 123 |
| MasterCard | 5555555555554444 | 01 | 30 | 123 |
| Rupay India | 6521111111111117 | 01 | 30 | 123 |
| Discover | 6011000990139424 | 01 | 30 | 123 |
| JCB | 3530111333300000 | 01 | 30 | 123 |
| Diners Club | 30569309025904 | 01 | 30 | 123 |
| American Express | 378282246310005 | 01 | 30 | 123 |
| American Express Corporate | 378734493671000 | 01 | 30 | 123 |
| Australian BankCard | 5610591081018250 | 01 | 30 | 123 |
| Dankort \(PBS\) | 5019717010103742 | 01 | 30 | 123 |
| Maestro | 6759649826438453 | 01 | 30 | 123 |
| Cartebleue | 5555555555554444 | 01 | 30 | 123 |

## 8. Error Code <a id="error_code"></a>

| Error Code | Description |
| :--- | :--- |
| **101** | M Wrong Website API Token |
| **102** | M Inactive Website Id |
| **104** | M Your account have not been approved yet |
| **105** | M Account Currency missing under Merchant User Profile |
| **106** | A Contact to Support Team |
| **150** | C Card Name missing from Bank Gateway |
| **151** | C Card number can not be empty |
| **152** | C Wrong card number |
| **153** | C No Payment Channel Available to process this card |
| **154** | C Card CCVV number can not be empty. |
| **155** | C Expiry date month of card can not be empty. |
| **156** | C Expiry date year of card can not be empty. |

| **Support by Gateway** |  |
| :--- | :--- |
| **Error** | BD No payment channel available to process this card |

| **Response After Transaction** |  |
| :--- | :--- |
| **Q1.** | **High Risk / Bad Card Request** |
| **Ans.** | The card has been reported as a highly risky card from the bank side. There could be several reasons. For example: there could be multiple try with this card with wrong information, or there may be bad credit history of the card. |
| **Q2.** | **Transaction in process** |
| **Ans.** | The transaction is in process and status is not confirmed yet. The delay can be due to slow internet speed or server response time. You will be notified soon through email, after the transaction status confirmation. |
| **Q3.** | **Declined, please contact your issuer or try another card Payment Failed.** |
| **Ans.** | The transaction is declined from your card issuer side. You may contact to your issuer to get more details about it. For the payment, you may try with another card. |
| **Q4.** | **User payment count daily limited Payment Failed.** |
| **Ans.** | There is a limit for any of the card to be used for every 24 hrs. If the limit exceeds, the card shall be blocked for next 24 hrs, for further use. The limit shall be refreshed by it self after every 24 hrs. To know more about daily card uses limit, you may visit the 'Scrubbed - as par customer email Id/ as per amount' area, mentioned as below. |
| **Q5.** | **VISA/ Master card type unsupported Payment Failed.** |
| **Ans.** | Acquiring bank failed to locate the issuer of this card. You may please contact to your issuer. |
| **Q6.** | **Stolen or lost card. Payment Failed.** |
| **Ans.** | The card has been reported Stolen or Lost. |
| **Q7.** | **Insufficient funds Payment Failed.** |
| **Ans.** | The card limit exceeds and remaining credit limit has insufficient funds to be used. |
| **Q8.** | **Invalid Card Verification Value \(CVV\) Payment Failed.** |
| **Ans.** | The CVV \(card verification code\) is wrong. |
| **Q9.** | **Expired card Payment Failed.** |
| **Ans.** | The card is already expired. |

| **Scrubbed - as par customer email Id/ as per amount** |  |
| :--- | :--- |
| **Q1.** | **What is minimum transaction limit?** |
| **Ans.** | The minimum transaction limit is $1 \(INR\). |
| **Q1.** | **What is maximum transaction limit?** |
| **Ans.** | The maximum transaction limit is 500 \(INR\). |
| **Q1.** | **Per day limit for successful transactions?** |
| **Ans.** | 2 \(two\) successful transactions can be done within a time frame of 24 hrs, from the same card and for the same merchant. After 24 hrs, the limit shall be refreshed and you shall be able to do next two successful transactions. This is how the limit refreshes by it self after every 24 hrs. |
| **Q1.** | **Per day limit for un-successful transactions?** |
| **Ans.** | 5 \(five\) un-successful transactions can be done within a time frame of 24 hrs, from the same card and for the same merchant. After 24 hrs, the limit shall be refreshed and you shall be able to do next five un-successful transactions. This is how the limit refreshes by it self after every 24 hrs. |
| **Note:** | Kindly contact customer service team to get more information about scrub setting on your account. |

## 9. Integration FAQ <a id="integration_faq"></a>

<table>
  <thead>
    <tr>
      <th style="text-align:left"><b>Q1.</b>
      </th>
      <th style="text-align:left">I am getting an error <b>&quot;Your account have not been approved yet. Please contact support@PyThru for assistance.&quot;</b>
      </th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td style="text-align:left"><b>Ans.</b>
      </td>
      <td style="text-align:left">
        <ol>
          <li><b>Merchant Login -</b>  <a href="https://pg.pythru.com/user/website"><b>My Website</b></a><b> &#x2192; Website API Token</b>
          </li>
          <li>You should make sure that, the mandatory parameter must be passed by the <b>approved URL</b> or
            test on localhost also.</li>
          <li>Ensure the <b>Select &quot;Website ID&quot;</b> and <b>Select Website API Token</b> has
            been selected while creating the &quot;Add A New Website&quot;.</li>
        </ol>
      </td>
    </tr>
    <tr>
      <td style="text-align:left"><b>Q2.</b>
      </td>
      <td style="text-align:left">Should I need to use the <b>Website API Token</b> for my all products?</td>
    </tr>
    <tr>
      <td style="text-align:left"><b>Ans.</b>
      </td>
      <td style="text-align:left">
        <ol>
          <li><b>No</b>
          </li>
          <li>You need to select only <b>one Website API Token</b> and <b>Website ID</b> as
            per your <b>Website ID</b>.</li>
          <li>Pass the <b>amount</b> parameters and <b>product name</b> dynamically by using
            the same Website API Token and Website ID.</li>
        </ol>
      </td>
    </tr>
    <tr>
      <td style="text-align:left"><b>Q3.</b>
      </td>
      <td style="text-align:left">My <b>woo-Commerce plugins</b> is not working?</td>
    </tr>
    <tr>
      <td style="text-align:left"><b>Ans.</b>
      </td>
      <td style="text-align:left">
        <ol>
          <li>You must create <b>one </b><a href="https://pg.pythru.com/user/new_website"><b>Add New Website</b></a> inside
            the merchant portal and pass the <b>Website API Token, Website ID and Transaction URL</b> and
            woo-Commerce parameter from the administrator area of your website.</li>
        </ol>
      </td>
    </tr>
    <tr>
      <td style="text-align:left"><b>Q4.</b>
      </td>
      <td style="text-align:left">What is <b>test card number</b>?</td>
    </tr>
    <tr>
      <td style="text-align:left"><b>Ans.</b>
      </td>
      <td style="text-align:left">
        <ol>
          <li><b>4444 4444 4444 4444</b> 01/2020 123 (4 sixteen times)</li>
          <li><b>4242 4242 4242 4242</b> 01/2020 123 (42 eight times)</li>
        </ol>
      </td>
    </tr>
    <tr>
      <td style="text-align:left"><b>Q5.</b>
      </td>
      <td style="text-align:left">Can I run this Payment Gateway On Local Host?</td>
    </tr>
    <tr>
      <td style="text-align:left"><b>Ans.</b>
      </td>
      <td style="text-align:left">
        <ol>
          <li><b>Yes</b>
          </li>
          <li>You can test on Local Host.</li>
          <li>Also, on <b>Approved Business URL</b>.</li>
        </ol>
      </td>
    </tr>
  </tbody>
</table>

<table>
  <thead>
    <tr>
      <th style="text-align:left"><b>Wordpress Plugin</b>
      </th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td style="text-align:left">
        <ol>
          <li></li>
          <li><b>Requirements</b>
          </li>
          <li>
            <br />
          </li>
          <li></li>
          <li><b>WooCommerce Version 3.3.5</b>
          </li>
          <li>
            <br />
          </li>
          <li></li>
          <li><b>Installation</b>
          </li>
          <li>Login to your admin dashboard and navigate to Admin Menu -&gt; Plugins
            -&gt; Add New -&gt; Search -&gt; PyThru.</li>
          <li>Activate the plugin</li>
          <li>Navigate to plugin settings page following by Admin Menu -&gt; WooCommerce
            -&gt; Settings -&gt; Checkout -&gt; PyThru.</li>
          <li><a href>Click here</a> to get your keys.</li>
        </ol>
      </td>
    </tr>
  </tbody>
</table>

## 11. Card <a id="cards"></a>

Continue for card details on PyThru

> ### Example Card <a id="example-object"></a>

```text
{
    "ccno": "4242424242424242",
    "ccvv": "123",
    "month": 01,
    "year": 24
}
```

<table>
  <thead>
    <tr>
      <th style="text-align:left">Parameter</th>
      <th style="text-align:left">Description</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td style="text-align:left">
        <p><b>ccno</b>
        </p>
        <p>required</p>
      </td>
      <td style="text-align:left">Card number without any separators.</td>
    </tr>
    <tr>
      <td style="text-align:left">
        <p><b>ccvv</b>
        </p>
        <p>required</p>
      </td>
      <td style="text-align:left">Card security code (CVC, CVV2).</td>
    </tr>
    <tr>
      <td style="text-align:left">
        <p><b>month</b>
        </p>
        <p>required</p>
      </td>
      <td style="text-align:left">Two digit integer (numric) value representing the card&#x2019;s expiration
        month.</td>
    </tr>
    <tr>
      <td style="text-align:left">
        <p><b>year</b>
        </p>
        <p>required</p>
      </td>
      <td style="text-align:left">Two digit integer (numric) value representing card&#x2019;s expiration
        year.</td>
    </tr>
  </tbody>
</table>

