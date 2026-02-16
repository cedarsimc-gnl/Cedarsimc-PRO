# Cedarsimc-PRO
Media and Livestreaming 
cedarsimc-level3
│
├── client/
│   ├── index.html
│   ├── dashboard.html
│   ├── style.css
│   ├── script.js
│
├── server/
│   ├── server.js
│   ├── invoice.js
│   ├── payment.js
│   └── package.json
│
├── assets/
├── uploads/
└── README.txt

const express = require("express");
const app = express();
const fs = require("fs");

app.use(express.json());
app.use(express.static("../client"));

let clients = [];

app.post("/login", (req,res)=>{
const {email} = req.body;
clients.push(email);
res.json({status:"logged"});
});

app.post("/invoice",(req,res)=>{
const {name,amount} = req.body;

const invoice = `
Client: ${name}
Amount: ₦${amount}
Cedarsimc GNL Invoice
`;

fs.writeFileSync(`invoice-${name}.txt`,invoice);

res.json({status:"invoice created"});
});

app.listen(3000,()=>console.log("Studio server running"));

const express = require("express");
const app = express();
const fs = require("fs");

app.use(express.json());
app.use(express.static("../client"));

let clients = [];

app.post("/login", (req,res)=>{
const {email} = req.body;
clients.push(email);
res.json({status:"logged"});
});

app.post("/invoice",(req,res)=>{
const {name,amount} = req.body;

const invoice = `
Client: ${name}
Amount: ₦${amount}
Cedarsimc GNL Invoice
`;

fs.writeFileSync(`invoice-${name}.txt`,invoice);

res.json({status:"invoice created"});
});

app.listen(3000,()=>console.log("Studio server running"));

npm install
node server.js

<h2>Client Dashboard</h2>

<input id="email" placeholder="Enter email">
<button onclick="login()">Login</button>

<script>
function login(){
fetch("/login",{
method:"POST",
headers:{"Content-Type":"application/json"},
body:JSON.stringify({email:email.value})
})
.then(()=>alert("Welcome to your portal"));
}
</script>

<button onclick="invoice()">Generate Invoice</button>

<script>
function invoice(){
fetch("/invoice",{
method:"POST",
headers:{"Content-Type":"application/json"},
body:JSON.stringify({name:"Client",amount:150000})
})
.then(()=>alert("Invoice created"));
}
</script>

<script src="https://js.paystack.co/v1/inline.js"></script>

<button onclick="pay()">Pay Now</button>

<script>
function pay(){
PaystackPop.setup({
key:"YOUR_PUBLIC_KEY",
email:"client@email.com",
amount:15000000,
callback:function(){
alert("Payment successful");
}
}).openIframe();
}
</script>


document.addEventListener("contextmenu",e=>e.preventDefault());



img {
pointer-events:none;
user-select:none;
}



Mobile App (React Native)
Web Platform (Next.js)

↓ API Gateway

Microservices:
- Booking service
- Payment service
- AI editing engine
- Streaming server
- Licensing blockchain node
- Creator wallet system

↓ Database Cluster
MongoDB + Redis

↓ Cloud
AWS / Google Cloud
