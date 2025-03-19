# MIST-4610-Project

# Team Members:
1. Andrea Lam [@anl13369](https://github.com/anl13369)
2. Sierra Cross-Thompson [@sierract](https://github.com/sierract)
3. Meghana Kottapalli [@meghanakottapalli03](https://github.com/MeghanaKottapalli03)
4. Cecilia Rizo-Patron [@cecirp](https://github.com/cecirp)

# Scenario Description
Wildflower Boutique is an e-retail store specializing in women’s clothing and accessories with locations all across the world, serving teenagers and young adults. Wildflower Boutique believes that designing a database can help efficiently track important information related to managing online sales and tracking consumer satisfaction. This database will help streamline operations, allow the owners to understand their customers’ desires, and provide prompt customer support.

# Data Model
Explanation of the Data Model:

Our model is based around the scenario of an e-commerce platform named Wildflower Boutique. At the core is one of our main entities, Customers, which has several attributes that store information on a particular user, such as name, contact details, and account information. This table branches out to connect with various other entities, such as Orders, Cart, and more. 

Each customer may be a part of Wildflower Boutique’s Loyalty Rewards program, which tracks their loyalty points, membership tier (Gold, Silver, Bronze), and enrollment date. The tier for members is point based and the members with the most points are Gold status, while those with the least have Bronze status. Because a customer can be part of only one loyalty rewards program, and a single loyalty rewards account can only belong to one customer, there is a one-to-one relationship shown between the LoyaltyRewards and Customers entities. 

Customers can add desired products to a wishlist, which stores products they are interested in but have not yet purchased. Since a wishlist is unique to each customer and each customer can only have one wishlist, there is a one-to-one relationship between Customers and Wishlist. Additionally, each customer has a cart, which temporarily stores products they intend to purchase. Similar to the Wishlist entity, there is a one-to-one relationship between Customers and Cart as each customer has only one cart, and each cart belongs only to one customer. This is important for a business to track because it shows the demand for products and what price point customers are willing to - or not willing to purchase a product.

The Products table contains all items available for purchase on the boutique’s website, including details such as price, type, and more. Since multiple products can be placed in a cart and a cart can have multiple products, there is a many-to-many relationship between Cart and Products, introducing an associative entity, Cart_has_Products. This entity stores individual cart details, such as the quantity of products in a particular cart and the date each product was added into the cart, allowing the boutique to keep track of the time a customer takes to actually purchase a product. Likewise, there is another many-to-many relationship between Products and Wishlist as many products can be placed in a wishlist and a wishlist can have many products. Another associative entity, Products_has_Wishlist, is introduced, which stores what specific products are in each wishlist. 

The Orders table contains specific details pertaining to a specific order, such as order status (i.e. Fulfilled, Canceled, etc.). Because a customer can have many orders, but a single order can only belong to one customer, there is a one-to-many relationship between Customers and Orders. When a customer completes the checkout process, the Orders table records the transaction details, such as payment method. Since a single order can include multiple products and each product can be part of multiple orders, we introduced another associative entity called Order_has_Products, which stores individual order details (i.e. which specific product was in a specific order).

Furthermore, each order must have a corresponding payment transaction. The Payments table tracks payment details, including transaction amounts, payment type (credit card, cash, etc.), and more. Since each order can have only one payment and payments can only be linked to one order, there is a one-to-one relationship between Orders and Payments. 

Additionally, as this is an online boutique, each order requires delivery, which is managed through the Shipping&Deliveries table. This table tracks shipping status, estimated delivery dates, and more. Each order is fulfilled by a single shipment but a shipment can handle multiple orders, which establishes a one-to-many relationship between Orders and Shipping&Deliveries. This is crucial for maintaining a good customer relationship by fulfilling orders in a timely manner and ensuring that the boutique remains reliable overtime.

Lastly, a feature of the Wildflower Boutique is that customers can leave feedback on their orders. The Reviews table stores customer reviews, including ratings, comments, and the date the review was made. Since each review is tied to only one order and a customer cannot leave multiple reviews for the same order, this establishes a one-to-one relationship between Orders and Reviews. Another feature of the Wildflower Boutique is that it provides online customer support. To assist customers with issues, the Customer Support entity tracks support tickets, issues, and tracks when the issues were made and resolved. Each order can have at most one customer support case and each customer support case is linked to only one order. This establishes a one-to-one relationship between Orders and Customer Support. 

All of the entities in this model were created to track the relationship the boutique has with the customer. It is important as a business that we are able to track customer interactions with the boutique to fulfill demand and anticipate changes in customer needs. Tracking the order from the boutique to the customer door and even to the customer review helps a business owner maintain a good relationship with customers and allows us to quickly solve any issues. This will help create a sustainable consumer experience.

![ACTUALFINALCOPY](https://github.com/user-attachments/assets/c809e5ca-6a3f-41d5-8f00-d2160259affe)

# Data Dictionary

<img width="667" alt="Screenshot 2025-03-18 at 9 27 47 PM" src="https://github.com/user-attachments/assets/f123adf7-948d-4970-b1e6-2f14b58d67f2" />
<img width="661" alt="Screenshot 2025-03-18 at 9 28 26 PM" src="https://github.com/user-attachments/assets/4ca022fe-ddf1-4285-a06f-4f34e712beb6" />
<img width="653" alt="Screenshot 2025-03-18 at 9 29 46 PM" src="https://github.com/user-attachments/assets/dd877c69-13a5-4682-9084-17b524429818" />
<img width="675" alt="Screenshot 2025-03-18 at 9 30 04 PM" src="https://github.com/user-attachments/assets/98ea583b-9d3b-4109-a39c-f9db369752e0" />
<img width="669" alt="Screenshot 2025-03-18 at 9 30 24 PM" src="https://github.com/user-attachments/assets/456896d6-1629-45af-8235-f613c740879e" />
<img width="658" alt="Screenshot 2025-03-18 at 9 57 47 PM" src="https://github.com/user-attachments/assets/e1ffdda6-8b33-469e-b7c6-3c442b814dca" />
<img width="662" alt="Screenshot 2025-03-18 at 9 32 29 PM" src="https://github.com/user-attachments/assets/923d197f-6f70-4411-9203-191e9cdedc12" />
<img width="657" alt="Screenshot 2025-03-18 at 9 32 46 PM" src="https://github.com/user-attachments/assets/236db1b2-92e1-4482-a1c2-425965d5ecfe" />
<img width="658" alt="Screenshot 2025-03-18 at 9 33 05 PM" src="https://github.com/user-attachments/assets/0b1fbb8c-d31d-4078-a481-1607807306c2" />
<img width="657" alt="Screenshot 2025-03-18 at 9 33 47 PM" src="https://github.com/user-attachments/assets/b4206717-a82a-4b75-ac62-daa46adbe490" />
<img width="663" alt="Screenshot 2025-03-18 at 9 34 15 PM" src="https://github.com/user-attachments/assets/d5d035a6-6a7f-42cb-b20c-212f897ec50a" />
<img width="658" alt="Screenshot 2025-03-18 at 9 34 33 PM" src="https://github.com/user-attachments/assets/5a56f285-864e-4685-b709-5b3ffe0648ae" />
<img width="662" alt="Screenshot 2025-03-18 at 9 35 04 PM" src="https://github.com/user-attachments/assets/04539f51-a8ab-434d-9eb8-9f4243826d6c" />

# Queries

Query 1: List the customerID and names of customers who have the most loyalty points. Order by descending order. 

![Screenshot 2025-03-18 232408](https://github.com/user-attachments/assets/c45195c3-bf42-48c0-9222-93171030e0a9)

Query 1 helps us to identify which customers have the highest loyalty points. Customers with the highest loyalty points are likely frequent buyers and highly engaged with the business. With this information, the boutique can identify which customers to target for special promotions, such as special perks, exclusive discounts, etc. in order to reward them and show appreciation. It also helps us to understand loyalty members’ behavior, which allows the boutique to tailor the program and personalize offers. 

Query 2:  List the products that are in a customers cart where the price of the product is greater than the average price of all products sold in the boutique.




Query 3: List the orders that have been fully shipped (Status = Completed) and were paid for in January of 2024.

<img width="490" alt="image" src="https://github.com/user-attachments/assets/1aa53f12-f131-4a43-b036-7b57f4a58d3c" />

Query 3 Helps us understand which orders were fully delivered and paid for in January of 2024. This is important to a business because as an online store, it can be easy to lose track of what payments have been fulfilled, and thereby have lots of uncollectible revenues (bad debt). By tracking January specifically, a business can reflect on the first month of operations in a new year and adjust accordingly to meet any challenges or issues faced.

Query 4: Determine the monetary value of all the current carts.




Query 5: List customers whose zip code start with 9 and who have more than 5000 loyalty points.

![Screenshot 2025-03-18 232744](https://github.com/user-attachments/assets/c53cd8a4-8544-4a8a-9ef6-27a6105e5b42)

Query 5 looks at the loyalty rewards members with more than 5000 loyalty points in an area with a ZIP code starting with ‘9’. This helps the boutique to identify the high-value rewards members in a specific geographic region, specifically West Coast Regions, such as California and Alaska. With this information, the boutique can identify whether customers in this ZIP code region have different buying habits compared to other regions and can tailor promotions, product offerings, and more to this particular area. Additionally, if many high-value members are concentrated in this area, it can help the boutique to decide whether or not to launch localized marketing campaigns to further increase sales in this specific ZIP code region. 

Query 6: Select the top 5 highest rated products.

<img width="475" alt="image" src="https://github.com/user-attachments/assets/c6577b47-c149-4a6d-9e53-14444fa51f74" />

Query 6 allows the customers and employees to view which products are the most popular. This can then lead to higher revenue for said products, but can also allow customers to view our bestsellers, which are guaranteed to be of good quality, good fit, and flattering.

Query 7: Find the percentage of orders that have had customer support tickets.

<img width="613" alt="image" src="https://github.com/user-attachments/assets/b929103f-44a1-48d8-a56d-c74b8bdd5164" />

Query 7 allows us to see what percentage of our orders require Customer Support. The higher this percentage is, the more we need to reevaluate what shipping carriers we use, which manufacturers we use, and our over customer relations system. This allows us to keep an overall outlook on our responsiveness to customer needs and allows us to create more queries when needed to solve individual customer needs. It can also help us detect any negative patterns in our business that may be attributed to different factors like management or local delivery services.


Query 8: Count the number of customers who have never left a review before.

<img width="442" alt="image" src="https://github.com/user-attachments/assets/28d244c5-4138-4e56-8551-547b7f2e6b07" />

Query 8 gauges the after purchase behavior of customers in our firm. We want to understand how engaged customers are and how motivated they are to comment after they receive their goods, whether it be a positive or negative review. Engagement translates as it is often only the most emotionally impacted customers that leave a voluntary review.The firm may use this data to establish incentives to post reviews as more commentary may incentivize other users to purchase when they see a product is reliable and widely enjoyed.

Query 9: List the names of all customers in the Silver Loyalty Level tier and live in the South/Southeast United States.




Query 10:  List how many items each customer has in their cart.

<img width="440" alt="image" src="https://github.com/user-attachments/assets/870306d3-8b1a-47d8-874f-8378663a7cf1" />
<img width="268" alt="image" src="https://github.com/user-attachments/assets/36cb17eb-d769-4330-b516-3cd3b58b0b56" />

Query 10 allows the customers to see how many items they have in their cart at one time, which can then lead to them being able to view their cart’s subtotal. This can influence a customer’s decision to then add or remove items based on their budget or need for certain items. This is also critical data on our end as we can see compare the frequency at which people add items to their carts relative to how often they actually purchase. We want this information to determine what our most profitable items are and help prioritize releasing similar items that will also perform well.


