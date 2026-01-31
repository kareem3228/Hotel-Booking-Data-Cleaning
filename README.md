# Hotel Booking Data Cleaning Pipeline

## The Problem
I took a raw dataset of **119,000 hotel bookings** that was full of errors—missing values, duplicate rows, and inconsistent country names. 

My goal was to build a "cleaning pipeline" to make this data ready for analysis. I focused on fixing the messy parts that standard functions like `dropna()` usually destroy.

## What I Fixed
* **Messy Strings:** Used **Fuzzy Logic (`thefuzz`)** to find country names that were spelled slightly differently (e.g., "PRT" vs "Portugal") and standardized them.
* **Logical Errors:** Found 30,000+ rows where the *Arrival Date* was before the *Reservation Date* (impossible). I fixed these by recalculating dates based on the 'Lead Time'.
* **Missing Data:** Instead of deleting rows with missing 'Agent' IDs, I used booking patterns to fill them logically, saving 15% of the data.
* **Complex Duplicates:** Used custom Lambda functions to merge duplicate rows while keeping the most important information (like the maximum days waited).

## How to Run It
1.  Install dependencies: `pip install -r requirements.txt`
2.  Open `cleaning_pipeline.ipynb` to see the step-by-step logic.
