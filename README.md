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
