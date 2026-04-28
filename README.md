## Seniority Checker: Resume Tenure Calculator

### Story
You are building an automated recruitment system. The HR department is tired of manually calculating how many months of experience each candidate has. Your task is to build a robust parser that processes a list of employment intervals and returns the total duration of a candidate's career in **months**.

### Task
Implement the function `calculate_seniority` which takes a list of strings representing employment intervals and returns the total number of **inclusive months**.

### Rules
1. **Inclusive Counting:** Every month mentioned is counted.
   - `"January 2020 - January 2020"` = **1 month**.
   - `"January 2020 - February 2020"` = **2 months**.
2. **Format:** Intervals follow the strict pattern `"Month Year - Month Year"`.
3. **Summation:** If multiple intervals are provided, return the total sum. 
   - **Note:** If intervals overlap, sum their durations independently (treat them as separate projects/entries).

---

### Error Handling
The system must be robust. Instead of specific class names, your function should return an error (or raise an exception) in the following cases:

* **Invalid Format:** The string doesn't match the required pattern or the year is not a valid number.
* **Unknown Month:** A month name is unrecognized (e.g., `"Maaaay"`).
* **Chronology Error:** The end date is strictly before the start date.

#### [Rust]
The function signature is `Result<u32, String>`. If any error occurs, return the error message as a `String`.

#### [Python]
The function should raise an **exception** (any type, though `ValueError` or a custom one is recommended) if the input is invalid.

---

### Examples

**Rust:**
```rust
calculate_seniority(vec!["May 2019 - July 2020"]) // Ok(15)
calculate_seniority(vec!["January 2020 - January 2020"]) // Ok(1)
calculate_seniority(vec!["March 2021 - January 2021"]) // Err(...)
```

**Python:**
```python
calculate_seniority(["May 2019 - July 2020"]) # 15
calculate_seniority(["January 2020 - January 2020"]) # 1
calculate_seniority(["March 2021 - January 2021"]) # Raises Exception
```

