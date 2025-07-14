<img width="638" height="211" alt="hotel_operations" src="https://github.com/user-attachments/assets/2739774d-664e-4a20-a86d-f31c89246403" />


# LuxurStay Data Cleaning & Analysis
# Author: Praveen Dommalapati

This repository contains SQL solutions for the **LuxurStay Hotels** data-quality and performance analysis project. All queries run in a read-only SQL environment, exposing results as named CTEs for easy consumption.

## Repository Structure

* **`task1_clean_branch.sql`** — Cleans and validates the `Branch` table, producing **`clean_branch_data`**
* **`task2_average_time_service.sql`** — Calculates average and maximum response times per service and branch, producing **`average_time_service`**
* **`task3_target_hotels.sql`** — Extracts Meal and Laundry service requests in EMEA and LATAM branches, producing **`target_hotels`**
* **`task4_average_rating.sql`** — Identifies branch-service combinations with average rating below 4.5, producing **`average_rating`**

## Prerequisites

* A SQL client with **read-only** access to:

  * **`Branch`** (hotel metadata)
  * **`Request`** (service requests with `service_id`, `branch_id`, `rating`, and optionally `time_taken`)
  * **`Service`** (service metadata with `description`)
* A **PostgreSQL-compatible** dialect (uses CTEs, `ROUND()`, regex for validation)

## How to Run

1. **Clone** the repository:

   ```bash
   git clone https://github.com/your-username/luxurstay-analysis.git
   cd luxurstay-analysis
   ```

2. **Open** each SQL file in your SQL client.

3. **Execute** in order:

   1. `task1_clean_branch.sql`
   2. `task2_average_time_service.sql`
   3. `task3_target_hotels.sql`
   4. `task4_average_rating.sql`

4. **Verify** outputs:

   ```sql
   -- Task 1
   WITH clean_branch_data AS (...) 
   SELECT * FROM clean_branch_data;

   -- Task 2
   WITH average_time_service AS (...) 
   SELECT * FROM average_time_service;

   -- Task 3
   WITH target_hotels AS (...) 
   SELECT * FROM target_hotels;

   -- Task 4
   WITH average_rating AS (...) 
   SELECT * FROM average_rating;
   ```

## Output CTEs / Views

| **Name**               | **Description**                                                    |
| ---------------------- | ------------------------------------------------------------------ |
| `clean_branch_data`    | Validated & cleaned `Branch` table (locations, rooms, dates, etc.) |
| `average_time_service` | Avg & max response times per service and branch                    |
| `target_hotels`        | Meal/Laundry requests in EMEA & LATAM branches                     |
| `average_rating`       | Branch-service combos with avg rating below 4.5                    |

## Contributing

Contributions are welcome via pull requests. Please follow existing query style and naming conventions.
