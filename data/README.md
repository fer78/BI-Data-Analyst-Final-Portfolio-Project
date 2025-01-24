# Brazilian E-Commerce Public Dataset by Olist

Welcome! This is a Brazilian ecommerce public dataset of orders made at Olist Store. The dataset has information of 100k orders from 2016 to 2018 made at multiple marketplaces in Brazil. Its features allows viewing an order from multiple dimensions: from order status, price, payment and freight performance to customer location, product attributes and finally reviews written by customers. We also released a geolocation dataset that relates Brazilian zip codes to lat/lng coordinates.

This is real commercial data, it has been anonymised, and references to the companies and partners in the review text have been replaced with the names of Game of Thrones great houses.

## olist_customers_dataset

This dataset has information about the customer and its location. Use it to identify unique customers in the orders dataset and to find the orders delivery location.

At our system each order is assigned to a unique customer_id. This means that the same customer will get different ids for different orders. The purpose of having a customer_unique_id on the dataset is to allow you to identify customers that made repurchases at the store. Otherwise you would find that each order had a different customer associated with.

**customer_id**: key to the orders dataset. Each order has a unique customer_id.
**customer_unique_id**: unique identifier of a customer.
**customer_zip_code_prefix:** first five digits of customer zip code
**customer_city**: customer city name
**customer_state**: customer state

## olist_geolocation_dataset

Geolocation Dataset
This dataset has information Brazilian zip codes and its lat/lng coordinates. Use it to plot maps and find distances between sellers and customers.

**geolocation_zip_code_prefix**: first 5 digits of zip code
**geolocation_lat**: latitude
**geolocation_lng**: Longitude
**geolocation_city**: city name
**geolocation_state**: state

## olist_order_items_dataset

Order Items Dataset
This dataset includes data about the items purchased within each order.

Example:
The order_id = 00143d0f86d6fbd9f9b38ab440ac16f5 has 3 items (same product). Each item has the freight calculated accordingly to its measures and weight. To get the total freight value for each order you just have to sum.

*The total order_item value is: 21.33 * 3 = 63.99*
*The total freight value is: 15.10 * 3 = 45.30*
*The total order value (product + freight) is: 45.30 + 63.99 = 109.29*

**order_id**: order unique identifier
**order_item_id**: sequential number identifying number of items included in the same order.
**product_id**: product unique identifier
**seller_id**: seller unique identifier
**shipping_limit_date**: Shows the seller shipping limit date for handling the order over to the logistic partner.
**price**: item price
**freight_value**: item freight value item (if an order has more than one item the freight value is splitted between items)

## olist_order_payments_dataset

Payments Dataset
This dataset includes data about the orders payment options.

**order_id**: unique identifier of an order.
**payment_sequential**: a customer may pay an order with more than one payment method. If he does so, a sequence will be created to accommodate all payments.
**payment_type**: method of payment chosen by the customer.
**payment_installments**: number of installments chosen by the customer.
**payment_value**: transaction value.

## olist_order_reviews_dataset

Order Reviews Dataset
This dataset includes data about the reviews made by the customers.

After a customer purchases the product from Olist Store a seller gets notified to fulfill that order. Once the customer receives the product, or the estimated delivery date is due, the customer gets a satisfaction survey by email where he can give a note for the purchase experience and write down some comments.

**review_id:** unique review identifier
**order_id**: unique order identifier
**review_score**: Note ranging from 1 to 5 given by the customer on a satisfaction survey.
**review_comment_title**: Comment title from the review left by the customer, in Portuguese.
**review_comment_message**: Comment message from the review left by the customer, in Portuguese.
**review_creation_date**: Shows the date in which the satisfaction survey was sent to the customer.
**review_answer_timestamp**: Shows satisfaction survey answer timestamp.

## olist_orders_dataset

**Order Dataset**: This is the core dataset. From each order you might find all other information.
**order_id:** unique identifier of the order.
**customer_id**: key to the customer dataset. Each order has a unique customer_id.
**order_status**: Reference to the order status (delivered, shipped, etc).
**order_purchase_timestamp**: Shows the purchase timestamp.
**order_approved_at** Shows the payment approval timestamp.
**order_delivered_carrier_date**: Shows the order posting timestamp. When it was handled to the logistic partner.
**order_delivered_customer_date**:Shows the actual order delivery date to the customer.
**order_estimated_delivery_date**: Shows the estimated delivery date that was informed to customer at the purchase moment.

## olist_products_dataset

Products Dataset
This dataset includes data about the products sold by Olist.

**product_id:** unique product identifier
**product_category_name**: root category of product, in Portuguese.
**product_name_lenght**: number of characters extracted from the product name.
**product_description_lenght**: number of characters extracted from the product description.
**product_photos_qty**: number of product published photos
**product_weight_g**: product weight measured in grams.
**product_length_cm**: product length measured in centimeters.
**product_height_cm**: product height measured in centimeters.
**product_width_cm**: product width measured in centimeters.

## olist_sellers_dataset

Sellers Dataset
This dataset includes data about the sellers that fulfilled orders made at Olist. Use it to find the seller location and to identify which seller fulfilled each product.

**seller_id**: seller unique identifier
**seller_zip_code_prefix**: first 5 digits of seller zip code
**seller_city**: seller city name
**seller_state**:seller state

## product_category_name_translation

Category Name Translation
Translates the product_category_name to english.

**product_category_name_english**: category name in English
**product_category_name**: category name in Portuguese

## olist_closed_deals_dataset

Closed Deals Dataset
After a qualified lead fills in a form at a landing page he is contacted by a Sales Development Representative. At this step some information is checked and more information about the lead is gathered.

**mql_id:** Marketing Qualified Lead id
**seller_id**: Seller id
**sdr_id**: Sales Development Representative id
**sr_id**: Sales Representative
**won_date**: Date the deal was closed.
**business_segment**:Lead business segment. Informed on contact.
**lead_type**: Lead type. Informed on contact.
**lead_behaviour_profile**: Lead behaviour profile. SDR identify it on contact.
**has_company**: Does the lead have a company (formal documentation)?
**has_gtin**: Does the lead have Global Trade Item Number (barcode) for his products?

## olist_marketing_qualified_leads_dataset

Marketing Qualified Leads
After a lead fills in a form at a landing page, a filter is made to select the ones that are qualified to sell their products at Olist. They are the Marketing Qualified Leads (MQLs).

**mql_id**: Marketing Qualified Lead id
**first_contact_date**: Date of the first contact solicitation.
**landing_page_id:**Landing page id where the lead was acquired
**origin**: Type of media where the lead was acquired
