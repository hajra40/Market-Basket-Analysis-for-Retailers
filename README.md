# Market Basket Analysis for Retailers

## Task Overview
In this task, you will implement a Market Basket Analysis using association rule mining, specifically using the Apriori algorithm. The goal is to extract meaningful patterns from retail transaction data and use these insights to make actionable business decisions. You will work with a dataset of retail transactions and apply MBA to identify products frequently bought together.

## Problem Statement & Use Cases
Retailers are constantly looking for ways to improve their product placement and increase sales. Market Basket Analysis helps retailers to discover associations between products frequently bought together. These insights can be used for better product bundling, improved store layout, and creating cross-selling opportunities. By identifying hidden patterns in transaction data, businesses can gain a competitive edge.

Consider a supermarket that wants to optimize its product placement strategy. By using Market Basket Analysis, the store can identify pairs or groups of products that customers often purchase together, such as bread and butter, or chips and soda. With this knowledge, the store can reorganize the product layout or create bundle offers to increase convenience and boost sales.

## Data Used
Link: https://github.com/rsharankumar/Learn_Data_Science_in_100Days/blob/master/Data/MBA/groceries%20-%20groceries.csv

## How Market Basket Analysis help retailers?
Apriori algorithm is the core of MBA process which helps the retailers to discover the patterns lying in the dataset, frequently bought items, what should be the placement of the products to maximise sales, create bundles and promotions which customers actually want, and avoid stockouts of frequently bought items. In short, MBA can help in the following ways:
- **Placement:** Place the products in such a way which is easier for the customers to grab them. For eg, let milk and break is oftenly purchased together, then they can be placed near to each other.
- **Cross-Selling:** It is a marketing strategy that aims to increase the average order value by offering customers additional or related products that complement their original purchase. It is based on the principle that customers are more likely to buy from you if you provide them with relevant and valuable suggestions that enhance their shopping experience.
- **Promotions:** Provide promotions to sell more products if there exists any association between the products. For instance, “Buy Milk and Bread, Get 10% Off Butter.”
- **Strategic Bundling** 

## Steps
1. Import the required libraries. In this task the following libraries were used: pandas, matplotlib, seaborn, apriori & association_rules from mlxtend.frequest_patterns.
2. Perform EDA & Understand the data: In the dataset each row represents a transaction or a purchase done by a customer. Though there are null values present we can avoid them as we will perform one hot encoding.
3. Perform Hot encoding on the data either by using get_dummies or TransactionEncoder from mlxtend.preprocessing. get_dummies() has been used in this task with axis=1 refers to operations along columns or the horizontal axis. It means that the operation will be applied column-wise across the DataFrame. 
4. Apply Apriori Algorthim and generate the rules.
5. Visualise the rules.

## Insights:
- Whole milk & other vegetables are highly associated with each other. If a customer buys either one of these then the other product is also bought.
<div>
<style scoped>
    .dataframe tbody tr th:only-of-type {
        vertical-align: middle;
    }

    .dataframe tbody tr th {
        vertical-align: top;
    }

    .dataframe thead th {
        text-align: right;
    }
</style>
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>antecedents</th>
      <th>consequents</th>
      <th>antecedent support</th>
      <th>consequent support</th>
      <th>support</th>
      <th>confidence</th>
      <th>lift</th>
      <th>representativity</th>
      <th>leverage</th>
      <th>conviction</th>
      <th>zhangs_metric</th>
      <th>jaccard</th>
      <th>certainty</th>
      <th>kulczynski</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>1</th>
      <td>(i_whole milk)</td>
      <td>(i_other vegetables)</td>
      <td>0.015150</td>
      <td>0.025826</td>
      <td>0.017285</td>
      <td>1.140940</td>
      <td>44.17772</td>
      <td>1.0</td>
      <td>0.016894</td>
      <td>inf</td>
      <td>0.992399</td>
      <td>0.729614</td>
      <td>1.144676</td>
      <td>0.905115</td>
    </tr>
    <tr>
      <th>0</th>
      <td>(i_other vegetables)</td>
      <td>(i_whole milk)</td>
      <td>0.025826</td>
      <td>0.015150</td>
      <td>0.017285</td>
      <td>0.669291</td>
      <td>44.17772</td>
      <td>1.0</td>
      <td>0.016894</td>
      <td>2.977999</td>
      <td>1.003275</td>
      <td>0.729614</td>
      <td>0.664204</td>
      <td>0.905115</td>
    </tr>
  </tbody>
</table>
</div>



