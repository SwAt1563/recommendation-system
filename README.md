# Recommendation System and Analytics Engine

## Overview

This repository contains the solution for the skill set assessment task. The task involves creating an analytics engine to produce various reports, insights, and analyses using the provided datasets. The primary goal was to develop a recommendation system based on system scores for multiple users across different categories such as content, contacts, and events.

## Datasets

The datasets provided include:
1. Users
2. Organizations
3. Contents
4. Contacts
5. Events
6. Recommendations

## Task Breakdown

### 1. Data Preprocessing

#### Tools and Libraries
- **Kaggle Platform**
- **Python**
  - NumPy
  - Pandas

#### Steps and Cleaning

1. **Users Dataset**
   - Removed empty columns: `city`, `country`, `state`, `phone_number`, `linkedin_url`, `description`.

2. **Organizations Dataset**
   - Removed empty columns: `email`, `year_founded`, `phone_number`, `linkedin_url`.

3. **Contents Dataset**
   - Removed empty columns: `organisation_id`, `creator_id`.
   - Removed unhelpful column: `content_type` (all records had the same value).
   - Cast `id` column from float to integer.
   - Removed leading spaces from column names.
   - Dropped records without `id` values.

4. **Events Dataset**
   - Removed empty column: `organisation_id`.
   - Corrected `location` value for `id` 854 from ',' to 'online'.
   - Processed the row with `id` 438, which had 68 concatenated records in the `title` field, by identifying the erroneous row, extracting and parsing the concatenated string into individual records, splitting them into 68 distinct rows, reinserting these rows back into the dataset, and verifying the consistency and accuracy of all other fields. As seen in the figure below, all 68 records were originally placed in one row in the `title` field.
![row 438](https://github.com/SwAt1563/recommendation-system/assets/79475839/c0fbe17c-9c84-43a8-9bb4-83c24debb998)

   - Reformatted `Price` column: converted 'Free' to 0 and string values to float.
   - Reformatted `location` into three columns: `meeting`, `state`, `city`.

6. **Contacts Dataset**
   - Removed empty columns: `organisation_id`, `picture_name`, `position`, `gender`, `phone_number`.
   - Removed unhelpful column: `role_id` (all records had the same value).

7. **Recommendations Dataset**
   - Removed empty column: `user_score`.

### 2. Categorizing Recommendations

The recommendations table was divided into three categories based on `asset_type`:
1. **Content Recommendations**
   - Renamed `asset_id` to `content_id`.
2. **Event Recommendations**
   - Renamed `asset_id` to `event_id`.
3. **Contact Recommendations**
   - Renamed `asset_id` to `contact_id`.

### 3. Data Export Post-Cleanup

The cleaned datasets were exported for further use in building the recommendation system and analytics engine.

### 4. Recommendation System

#### Tools and Libraries
- **Kaggle Platform**
- **Python**
  - NumPy
  - Pandas
  - Scikit-learn
  - SciPy

#### Methodology

A collaborative filtering recommendation system was developed for content recommendations based on `user_id`, `content_id`, and `system_score`. The `system_score` is assumed to reflect user interactions like clicks or time spent on content. The same algorithm can be applied to events and contacts.

##### Services Provided
1. **User-based Recommendations**
   - Input: `user_id`
   - Output: Top 5 recommended contents for the user.
2. **Content-based Recommendations**
   - Input: `content_id`
   - Output: Top 5 contents similar to the provided content.

### 5. Analytics Engine and Visualization

#### Tool
- **Power BI Desktop**

Certainly! Here’s the enhanced format for the reports section:

---

#### Reports

Various reports covering all datasets were created and visualized in Power BI:

1. **Users**
   ![Users Report](https://github.com/SwAt1563/recommendation-system/assets/79475839/9aeab5f1-a810-4b08-908a-6c1995bbd55f)

2. **Organizations**
   ![Organizations Report](https://github.com/SwAt1563/recommendation-system/assets/79475839/e21b6950-0aa6-4211-b18b-ebdcd1ac6e8e)

3. **Contents**
   ![Contents Report](https://github.com/SwAt1563/recommendation-system/assets/79475839/3d395d95-a2c0-4b6a-9a6b-9d38568871db)

4. **Contacts**
   ![Contacts Report](https://github.com/SwAt1563/recommendation-system/assets/79475839/71707ccc-8f0e-47c3-b91d-b5a1e8c6accd)

5. **Events**
   ![Events Report](https://github.com/SwAt1563/recommendation-system/assets/79475839/90ce93a0-0f35-4eab-9ce7-c78944d101b2)

6. **Content Recommendations System**
   ![Content Recommendations Report](https://github.com/SwAt1563/recommendation-system/assets/79475839/8052e426-ceca-4206-95a0-500a0cb4a760)

7. **Contact Recommendations System**
   ![Contact Recommendations Report](https://github.com/SwAt1563/recommendation-system/assets/79475839/c1468aea-3f96-4da9-b299-69f4faf907e6)

8. **Event Recommendations System**
   ![Event Recommendations Report](https://github.com/SwAt1563/recommendation-system/assets/79475839/f994ae38-028b-444e-901f-606ed85c4544)


## Repository Structure

- **Data Wrangling Code:** [Kaggle Notebook](https://www.kaggle.com/code/swat1563/data-wrangling)
- **Content Recommendations System Code:** [Kaggle Notebook](https://www.kaggle.com/code/swat1563/content-recommendations-system)
- **Power BI Reports PDF:** Available in the `reports` directory.
- **Analytics Engine Files:** Power BI files (.pbit, .pbix) for interaction and visualization, available in the repository.

## Links

- **GitHub Repository:** [Recommendation System](https://github.com/SwAt1563/recommendation-system)


