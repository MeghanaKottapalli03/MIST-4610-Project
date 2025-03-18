# MIST-4610-Project

# Team Members:
1. Andrea Lam @anl13369
2. Sierra Cross-Thompson @sierract
3. Meghana Kottapalli @meghanakottapalli03
4. Cecilia Rizo-Patron @cecirp

# Scenario Description
Wildflower Boutique is an e-retail store specializing in women’s clothing and accessories with locations all across the world, serving teenagers and young adults. Wildflower Boutique believes that designing a database can help efficiently track important information related to managing online sales and tracking consumer satisfaction. This database will help streamline operations, allow the owners to understand their customers’ desires, and provide prompt customer support.

# Data Model
Explanation of the Data Model:

Our model is based around the scenario of an e-commerce platform named Wildflower Boutique. At the core is one of our main entities, Customers, which has several attributes that store information on a particular user, such as name, contact details, and account information. This table branches out to connect with various other entities, such as Products, Cart, and more. 

Each customer may be a part of Wildflower Boutique’s Loyalty Rewards program, which tracks their loyalty points, membership tier (i.e. Silver, Gold, Platinum), and enrollment date. Because a customer can be part of only one loyalty rewards program, but a loyalty rewards program can serve many customers, there is a one-to-many relationship shown between the LoyaltyRewards and Customers entities. 

Customers can add desired products to a wishlist, which stores products they are interested in but have not yet purchased. Since a wishlist is unique to each customer and each customer can only have one wishlist, there is a one-to-one relationship between Customers and Wishlist. Additionally, each customer has a cart, which temporarily stores products they intend to purchase. Similar to the Wishlist entity, there is a one-to-one relationship between Customers and Cart as each customer has only one cart, and each cart belongs only to one customer. This is important for a business to track because it shows the demand for products and what price point customers are willing to - or not willing to purchase a product.

The Products table contains all items available for purchase on the boutique’s website, including details such as price, type, and more. Since multiple customers can purchase multiple products, there is a many-to-many relationship between Customers and Products. To connect these two entities, we introduced an associative entity called Products_has_Customers to track individual product interactions (i.e. which specific customer purchased which specific product). 
When a Customer completes the checkout process, the Orders table records the transaction details, including total amount, payment method, etc. Since a single order can include multiple products and each product can be part of multiple orders, we introduced another associative entity called Order_has_Products, which stores individual order details (i.e. which specific product was in a specific order).

Furthermore, each order must have a corresponding payment transaction. The Payments table tracks payment details, including transaction amounts, payment type (credit card, cash, etc.), and more. Since each order can have only one payment and payments can only be linked to one order, there is a one-to-one relationship between Orders and Payments. 

Additionally, as this is an online boutique, each order requires delivery, which is managed through the Shipping&Deliveries table. This table tracks shipping status, estimated delivery dates, and more. Each order is fulfilled by a single shipment but a shipment can handle multiple orders, which establishes a one-to-many relationship between Orders and Shipping&Deliveries. This is crucial for maintaining a good customer relationship by fulfilling orders in a timely manner and ensuring that the boutique remains reliable overtime.

Lastly, a feature of the Wildflower Boutique is that customers can leave feedback on their orders. The Reviews table stores customer reviews, including ratings, comments, and the date the review was made. Since each review is tied to only one order and a customer cannot leave multiple reviews for the same order, this establishes a one-to-one relationship between Orders and Reviews. Another feature of the Wildflower Boutique is that it provides online customer support. To assist customers with issues, the Customer Support entity tracks support tickets, issues, and tracks when the issues were made and resolved. Each order can have at most one customer support case and each customer support case is linked to only one order. This establishes a one-to-one relationship between Orders and Customer Support. 

All of the entities in this model were created to track the relationship the boutique has with the customer. It is important as a business that we are able to track customer interactions with the boutique to fulfill demand and anticipate changes in customer needs. Tracking the order from the boutique to the customer door and even to the customer review helps a business owner maintain a good relationship with customers and allows us to quickly solve any issues. This will help create a sustainable consumer experience.

