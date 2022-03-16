# E-Commerce-Recommendation
E-Commerce recommendation system using product data and user events
# Summary
Frequently bought together items(products bought together in the same shopping session frequently) indicates products that complement each other. The recommendation system in this repository predicts a list of products that could complement a given item under consideration. 
The approach used in this model is to first create embeddings that represent each product along with its features and later use these embeddings to train and predict recommendations.

# Dataset
The approach here uses the kaggle dataset https://www.kaggle.com/mkechinov/ecommerce-behavior-data-from-multi-category-store
The dataset contains information on user behaviour with events such as view, cart and purchase with user id and user session, product information such as id, category and price.

# Approach
Depending on user events, products can be categorized as products that are viewed together and purchased together(co-purchased products) and products that are viewed together with only one product being purchased(similar/substitutable products). 
### Creating Embeddings
Create a product embedding model using Graph Neural Network so as to create embeddings for all products including cold start items. The embedding model will be trained only on similar links, so that similar products will have similar embeddings.

### Data Analysis and recommendation
Perform statistical analysis to understand the most frequently bought item categories for a query category. That is, for each product category, get the top 3 most frequently co_purchased complementary product categories. Type transition module trained on product embeddings to ouput complementary categories.

Next, for each product, get the most frequently purchased complementary product in each category. Train a neural network model to take a query embedding and query type as input and predict an output an embedding that resembles the complementary product embedding.

# Model Architechture
![alt text](https://github.com/bhavya-rema/E-Commerce-Recommendation/blob/main/Recommendation.png)
