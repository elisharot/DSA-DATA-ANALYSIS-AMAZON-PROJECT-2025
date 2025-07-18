# Amazon Product Data Analysis 

##  Dataset Overview
The dataset contains product listing and review data scraped from Amazon, including pricing, ratings, discounts, and review details.

###  Key Columns:
- `product_id`, `product_name`, `category`
- `actual_price`, `discounted_price`, `discount_percentage`
- `rating`, `rating_count`
- `review_content`, `user_name`, `user_id`
  
 ##  Objective:
     The main goal of the Amazon Product Review Analysis project is to help sellers and decision-makers on the Amazon platform gain data-driven insights into:

  -   Product performance: Understand how products are rated and reviewed.
        
  -  Customer engagement: Measure how users interact through reviews.

  -  Pricing strategies: Identify trends in discounts and actual vs. discounted prices.

  - Revenue opportunities: Estimate potential earnings based on pricing and review volume.

  - These insights enable better marketing strategies, inventory planning, and product improvements.


##  Key Business Questions Answered

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
- Pivot Tables, Charts and slicers

 ## Data Visualization
 <img width="1752" height="869" alt="image" src="https://github.com/user-attachments/assets/cdeb037b-a636-47e7-8d73-1733bbb87309" />


## 🔚 Conclusion
This repository demonstrates how product pricing, discounting, and customer sentiment (via reviews and ratings) interact across categories. Insights can help inform pricing strategies and identify top-performing product types.
## Key Recommendations:
        1. Optimize Discounts Strategically
Categories with high average discounts may drive traffic but could reduce profitability. Use A/B testing to find the sweet spot between discounts and conversion.

Offer targeted discounts to underperforming but well-rated products to boost visibility without hurting margins.


     2. Invest in Top-Rated Products
Products with high ratings and review counts (e.g., 4.5★ and above) are more likely to convert new customers.

Feature these in promoted listings, sponsored ads, and seasonal campaigns.


        3. Revise Low-Engagement Categories
Categories with many products but low total reviews suggest low customer interaction.

Recommendation: Improve product descriptions, images, and incentivize early reviews (within Amazon’s TOS) to boost credibility.


        4. Target High-Potential Products for Upscaling
Products with moderate reviews but high ratings are emerging stars.



           5. Track Rating vs. Discount Trends
Some products with heavy discounts still receive poor ratings.

 Evaluate such products for quality concerns—discounting alone won’t improve brand image.

6. Price Bucket Strategy
Products priced under ₹500 dominate in volume but may yield lower profit per unitExplore upselling tactics or bundle deals to improve average order value.

7. Focus on High-Revenue Categories
Categories with the highest potential revenue (actual price × rating count) should get priority in ad spend, inventory restocking, and regional targeting.













