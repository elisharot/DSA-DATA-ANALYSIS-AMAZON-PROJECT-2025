# Amazon Product Data Analysis 📊

## 📁 Dataset Overview
The dataset contains product listing and review data scraped from Amazon, including pricing, ratings, discounts, and review details.

### 🔧 Key Columns:
- `product_id`, `product_name`, `category`
- `actual_price`, `discounted_price`, `discount_percentage`
- `rating`, `rating_count`
- `review_content`, `user_name`, `user_id`

---

## 🧠 Key Business Questions Answered

1. **Average discount percentage by product category**
   - Pivot Table:
     - Rows: Category
     - Values: Average of `discount_percentage`

2. **Number of products per category**
   - Pivot Table:
     - Rows: Category
     - Values: Count of `product_id`

3. **Total number of reviews per category**
   - Pivot Table:
     - Rows: Category
     - Values: Sum of `rating_count`

4. **Products with the highest average ratings**
   - Pivot Table:
     - Rows: Product Name
     - Values: Average of `rating`
     - Sort descending

5. **Average actual vs discounted price by category**
   - Pivot Table:
     - Rows: Category
     - Values: Average of `actual_price`, Average of `discounted_price`

6. **Products with the highest number of reviews**
   - Pivot Table:
     - Rows: Product Name
     - Values: Sum of `rating_count`
     - Sort descending

7. **Number of products with 50%+ discount**
   - Apply filter on `discount_percentage >= 0.50`
   - Use `=COUNTA()` in Excel

8. **Distribution by product rating**
   - Pivot Table:
     - Rows: Rating
     - Values: Count of `product_id`

9. **Total potential revenue by category**
   - Add new column: `=actual_price * rating_count`
   - Pivot Table:
     - Rows: Category
     - Values: Sum of new column

10. **Unique products per price range**
    - Add column with:
      ```excel
      =IF(actual_price<200,"<$200",IF(actual_price<=500,"$200-$500","> $500"))
      ```
    - Pivot Table:
      - Rows: Bucket
      - Values: Count of unique `product_id`

11. **How rating relates to discount**
    - Insert a **scatter plot** with:
      - X: `discount_percentage`
      - Y: `rating`

12. **Number of products with < 1,000 reviews**
    - Filter `rating_count < 1000`
    - Use `=COUNTA()` on filtered `product_id`

13. **Categories with highest discounts**
    - Pivot Table:
      - Rows: Category
      - Values: Max of `discount_percentage`

14. **Top 5 products by combined rating & reviews**
    - Add column: `=rating * rating_count`
    - Sort descending
    - Pick top 5 rows

---

## 🧩 Tools Used
- Excel / 
- Power Query (for data cleaning)
- Pivot Tables & Charts

---

## 🔚 Conclusion
This repository demonstrates how product pricing, discounting, and customer sentiment (via reviews and ratings) interact across categories. Insights can help inform pricing strategies and identify top-performing product types.

---

