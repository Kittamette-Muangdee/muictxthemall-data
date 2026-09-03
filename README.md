# The Mall Hackathon Data Preprocessing & Analysis

This project processes survey data from customers regarding their thoughts on Carbon Footprint Labels (CFP) and a proposed Eco-Points system for M-Card members.

## Files

- `response.csv`: The original raw data containing survey responses.
- `data-preprocessing.ipynb`: A Jupyter Notebook containing the data cleaning and preprocessing steps.
- `cleaned_response.csv`: The resulting dataset after preprocessing.
- `data-analyzing.ipynb`: A Jupyter Notebook for computing and visualizing behavioral correlations.

---

## Data Preprocessing

Here are the detailed steps performed during data preprocessing:

### 1. Renaming the columns
- The original Thai column names were lengthy and difficult to use programmatically.
- They were replaced with concise English names such as `membership_status`, `visit_frequency`, `notice_cfp_label`, `motivated_by_eco_points`, `pos_convenience`, `preferred_eco_benefits`, and `feeling_on_digital_receipt` for easier reference in code.

### 2. Dropping email and timestamp
- To ensure privacy and anonymize the responses, Personally Identifiable Information (PII) including the `email` and `timestamp` columns were completely dropped from the dataset. 

### 3. Changing the value of data into numerical for statistical work
- **Membership Status**: Mapped "เป็นสมาชิก M-Card" to 1 and "ยังไม่ได้เป็น" to 0.
- **Visit Frequency**: Converted to a 1-3 scale (3 = Weekly, 2 = 1-2 times a month, 1 = Rarely).
- **Ratings (Notice CFP, Motivation, Convenience)**: Mapped descriptive text into numerical scales (3 = Most / Convenient / Always, 2 = Medium / Sometimes, 1 = Least / Inconvenient / Never).
- **Feeling on Digital Receipt**: Mapped positive feelings to 3 and neutral/uninterested feelings to 1.
- **Preferred Eco-Benefits**: Applied one-hot encoding for the multiple-choice responses and renamed the resulting Thai column names into English (`donate_to_environment`, `shopping_discount_coupon`, `redeem_eco_product`).

---

## Data Analysis & Conclusions

Following the data preprocessing, we performed correlation analysis in `data-analyzing.ipynb` to uncover insights regarding customer behavior and interest in the Eco-Points campaign.

By segmenting the correlation analysis between M-Card Members, Non-Members, and the Overall group, we discovered the following key insights:

### 1. For M-Card Members
* **CFP Labels are the key driver:** Members show a strong positive correlation (0.47) between "noticing CFP labels" and being "motivated by Eco-Points." This means if a member already pays attention to labels, they are highly likely to participate in earning points.
* **Digital receipts contrast with Eco-Point motivation:** There is a negative correlation (-0.35) between liking digital receipts and being motivated by Eco-Points. This suggests that members who prefer digital receipts do so purely for convenience, not necessarily for environmental reasons.
**Conclusion:** The campaign targeting existing members should directly appeal to those who are already conscious of CFP labels.

### 2. For Non-Members
* **Awareness and motivation are not strongly linked:** For non-members, noticing CFP labels and wanting Eco-Points has a very weak correlation (0.16) compared to members.
* **Digital receipts have a positive impact:** Non-members show a positive correlation (0.26) between satisfaction with digital receipts and motivation from Eco-Points.
**Conclusion:** To attract non-members, the campaign should not lead with CFP labels. Instead, it should highlight modernity and convenience (like digital receipts) bundled with tangible benefits to incentivize participation and membership sign-ups.

### 3. Overall
When looking at all customers combined, "noticing CFP labels" and "motivation to collect Eco-Points" still hold the highest overall correlation (0.29).
**Overall Conclusion:** The Eco-Points campaign has real potential to drive consumer behavior. However, the mall needs a dual communication strategy: 1) Target environmentally conscious members by making Eco-Points highly rewarding for low-carbon purchases, and 2) Target general customers by emphasizing convenience (e.g., digital receipts) as a gateway to spark their interest in the environmental program.

### 4. Preferred Redemption
Survey results show that the vast majority of customers want to redeem their Eco-Points for **"Shopping Discounts / Cash Coupons" (43 votes)**, easily beating out redeeming for special eco-products (15 votes) and donating points to environmental projects (10 votes).
**Conclusion:** The campaign must focus on distributing shopping discounts or cash coupons as the primary reward. Tangible, usable benefits are the most effective way to motivate the highest number of customers to participate.

### 5. Target Demographic (Age Group Analysis)
When analyzing which age group is most interested in the campaign, the average motivation score (out of 3) was highly consistent across the board:
- **36-55 years old:** 2.33/3
- **Under 20 years old:** 2.21/3
- **20-35 years old:** 2.17/3

**Conclusion:** The campaign appeals almost equally across all generations, which is a great sign. However, because the vast majority of our survey respondents (67%) fall into the **20-35 age group**, Millennials and older Gen Z should be considered the primary target audience in terms of volume. In the meantime, knowing that older demographics are also highly receptive gives confidence for broader campaign expansion.
