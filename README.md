# analysis_Shopping_trends

## Overview
This project analyzes a shopping trends dataset to uncover insights into customer behavior, product preferences, and purchase patterns.

## Dataset
The dataset contains 3,900 entries and 18 columns, including customer demographics, purchase information, and product details.

### Key Columns
- `Customer ID`: Unique identifier for customers
- `Age`: Age of the customer
- `Gender`: Gender of the customer
- `Item Purchased`: Product name
- `Category`: Product category
- `Purchase Amount (USD)`: Purchase amount in USD
- `Season`: Season of the purchase
- `Review Rating`: Customer rating (1-5 scale)

## Installation and Setup
1. **Install Required Libraries**:
   ```bash
   pip install pandas matplotlib seaborn
   ```
2. **Load the Dataset**:
   Place `shopping_trends_updated.csv` in the working directory.
   ```python
   import pandas as pd
   shopping_data = pd.read_csv('shopping_trends_updated.csv')
   ```

## Analysis Questions and Steps

### 1. Age Distribution
Analyze customer age distribution:
```python
print(shopping_data['Age'].describe())
```

### 2. Avg Purchase by Category
Find average purchase by category:
```python
print(shopping_data.groupby('Category')['Purchase Amount (USD)'].mean())
```

### 3. Gender with Highest Purchases
Identify gender with most purchases:
```python
print(shopping_data['Gender'].value_counts())
```

### 4. Popular Items in Each Category
Find most popular items per category:
```python
print(shopping_data.groupby('Category')['Item Purchased'].agg(lambda x: x.mode()[0]))
```

### 5. Seasons with Higher Spending
Find seasons with high spending:
```python
print(shopping_data.groupby('Season')['Purchase Amount (USD)'].mean())
```

### 6. Avg Rating by Category
Calculate average rating for categories:
```python
print(shopping_data.groupby('Category')['Review Rating'].mean())
```

### 7. Subscribed vs Non-Subscribed
Compare spending by subscription:
```python
print(shopping_data.groupby('Subscription Status')['Purchase Amount (USD)'].mean())
```

### 8. Popular Payment Method
Identify most used payment method:
```python
print(shopping_data['Payment Method'].mode()[0])
```

### 9. Spending by Promo Code Usage
Compare spending with promo codes:
```python
print(shopping_data.groupby('Promo Code Used')['Purchase Amount (USD)'].mean())
```

### 10. Purchase Frequency by Age Group
Understand age-group purchase patterns:
```python
age_groups = pd.cut(shopping_data['Age'], bins=[0, 18, 25, 40, 60, 100], labels=['<18', '18-25', '26-40', '41-60', '>60'])
print(shopping_data.groupby(age_groups)['Frequency of Purchases'].value_counts())
```

### 11. Product Size vs Purchase Amount
Examine size correlation:
```python
print(shopping_data.groupby('Size')['Purchase Amount (USD)'].mean())
```

### 12. Shipping Preference
Find preferred shipping methods:
```python
print(shopping_data.groupby('Category')['Shipping Type'].agg(lambda x: x.mode()[0]))
```

### 13. Discounts Impact Spending
Analyze discount impact:
```python
print(shopping_data.groupby('Discount Applied')['Purchase Amount (USD)'].mean())
```

### 14. Popular Colors
Identify top colors:
```python
print(shopping_data['Color'].value_counts().head())
```

### 15. Avg Previous Purchases
Calculate average past purchases:
```python
print(shopping_data['Previous Purchases'].mean())
```

### 16. Purchase by Ratings
Analyze purchase amounts by ratings:
```python
print(shopping_data.groupby('Review Rating')['Purchase Amount (USD)'].mean())
```

### 17. Spending by Location
Understand location patterns:
```python
print(shopping_data.groupby('Location')['Purchase Amount (USD)'].mean().head())
```

### 18. Age and Product Category
Find category preferences by age group:
```python
print(shopping_data.groupby(age_groups)['Category'].value_counts())
```

### 19. Spending by Gender
Compare spending by gender:
```python
print(shopping_data.groupby('Gender')['Purchase Amount (USD)'].mean())
```
