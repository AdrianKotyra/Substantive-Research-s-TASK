#### **Substantive-Research-s-TASK**
------------------------------------------------------------------------------------------------------------
Substantive Research Client Payment Benchmarking App Overview This React application serves as a client payment benchmarking tool, allowing users to analyze their payment data from various market data providers. The app retrieves data from a mock API that simulates payment information and currency exchange rates, enabling users to determine whether they are over-paying or under-paying for their services.

Features Fetches payment information from a mock API. Displays key data points, including payment benchmarks for various products. Converts currency based on real-time exchange rates retrieved from another mock API. Responsive user interface built with React.

Installation To get started with the application, follow these instructions:

DEMO https://substantive-research-task-ak.netlify.app/

1.Clone the Repository: -git clone https://github.com/AdrianKotyra/Substantive-Research-s-TASK.git

2.Navigate to the Project Directory: cd Substantive-Research-s-TASK

3.Install Dependencies: Ensure you have Node.js installed. Then run: npm install

4.Start the Application: To run the application in development mode, execute: npm start

5.This will start the development server, and you can view the app in your browser at http://localhost:3000.

DETAILED WHOLE TASK INSTRUCTION:
------------------------------------------------------------------------------------------------------------------------------------

As a tech test assessor, I want to assess that the tech test deliverable is using modern web technologies and techniques. Conditions Of Satisfaction 
● All processing through JavaScript, using any modern JavaScript framework 
● Deliverable includes a README file with installation instructions 
● Web user interface that highlights key data points ● Code shared via a remote repository e.g. Github
Show over or under benchmark payment for each provider Description As a Substantive Research client user, I want to understand whether my data provider payments are over or under benchmark, so that I can make informed decisions about cost efficiency and negotiate better contracts with my providers. Conditions Of Satisfaction 
● Payment and benchmark totals over 4 years (2021-2024) presented for each provider. 
● Total benchmark difference (benchmark minus payment) presented for each provider. 
● Totals should be converted to the user’s preferred currency, which is Euros.
Show product payment year on year trends Description As a Substantive Research client user I want to understand how my product payments are changing from year to year, so I can evaluate trends, make informed budgeting decisions, and identify any significant increases or decreases in costs. Conditions Of Satisfaction 
● A chart showing the payment trend by year for each product that has more than one year of payments If you have any questions on any of the above, please feel free to contact us on technology@substantiveresearch.com and we will clarify. We look forward to seeing what you can do! APIs This is an explanation of the APIs you should use for this task. The information within these APIs is fabricated and is not affiliated with any real client. Use the base path of https://substantive.pythonanywhere.com APIs return JSON responses with 200 status codes on success. 
API key authentication Key: auth-key Value: 590e3e17b6a26a8fcda726e2a91520e476e2c894 
In: header Get product benchmarks Description Payments and benchmarks in specified currency for all providers and products 
Path GET product_benchmarks Response properties product_benchmarks: Array < product_benchmark > product_benchmark: object Properties id : integer Unique identifier for this product benchmark provider_name: string Name of the provider product_name:
string Name of the product provided by the provider end_date : string Expiry date of the product within the client agreement start_date : string Start date of the product within the client agreement currency : object < currency > 
Currency of the payment and benchmark payment : integer Client payment price for this product, in the given currency, in whole units, e.g. 1450 in USD would be $1450.00 benchmark : integer Substantive Research benchmark price for this product, in the given currency, in whole units.
E.g. 1450 in USD would be $1450.00 // Example GET product_benchmarks response { "product_benchmarks": [ { "id": 1, "product_name": "Data Stream Pro", "provider_name": "MarketData Inc.", "start_date": "2023-01-01", "end_date": "2023-12-31", "currency": { "id": 840, "name": "USD", "symbol": "$" }, "payment": 1500, "benchmark": 1450, }, ... ] } 
currency : object 
Properties id : integer Unique identifier for this currency name : string Unique 3 letter code for this currency symbol : string Currency symbol for this currency
Get exchange rates Description Return exchange rate information for all currency conversions by calendar year Path
GET exchange_rates Response properties exchange_rates: Array < exchange_rate > Exchange rates between two currencies for a calendar year. Currencies are identified by their key exchange_rate : object Properties exchange_rate : number Rate of currency exchange between from and to currency from_currency_id : integer Key of the currency to convert from to_curency_id : integer Key of the currency to convert to year : integer Period the exchange rate is valid for
