# iPhone 18 Series: Good Buy or Just Hype?

A Power BI dashboard that asks one simple question: **is the iPhone 18 Pro and Pro Max worth buying in Nigeria, or is it just hype?**

When the iPhone 18 series came out, everyone was talking about it. As a data analyst, I wanted to see what the numbers say, so I built this project.

---

## The Business Problem

Apple's new phones come with a lot of excitement and a very high price tag. For the average Nigerian, that raises three questions:

1. **Is it worth the hype?** What do people want from the phone, and how excited are they?
2. **Can people afford it?** How many people can actually pay, and who can't?
3. **Should people upgrade?** Who should buy now, who should wait, and who should skip?

---

## Dashboard Pages

The dashboard has 3 pages. Each page answers one question.

### 1. Is It Worth the Hype?
- Pro vs Pro Max: which one people prefer
- What matters most to buyers
- Excitement level by age group
- Where the hype comes from (social media, friends, YouTube, etc.)
- KPIs: Average Price Needed, Affordability Rate, Best Occupation

<img width="1015" height="573" alt="dashboard hype" src="https://github.com/user-attachments/assets/aedde0f0-8a78-4c55-8d55-8cfcc33a81a3" />

--- 

### 2. Can People Afford It?
- How many people can afford it (gauge)
- Who can't afford it, by occupation
- How people would pay (payment plan)
- Income vs budget (scatter plot)

<img width="1013" height="567" alt="dashboard afford" src="https://github.com/user-attachments/assets/0d78a224-4420-449c-b135-7b6270e9cabb" />


---

### 3. Should You Upgrade?
- Upgrade now, wait or skip (donut)
- How old people's current phones are
- What is wrong with their current phones

<img width="1017" height="572" alt="dashboard upgrade" src="https://github.com/user-attachments/assets/9bef09ba-1d97-42a7-b07d-f9761a38404a" />


Each page has a slicer, and the buttons at the top let you move between pages.

---

## Dataset

The data is in `iPhone18_Dashboard_Dataset.xlsx`. It has two main tables:

| Table | Rows | What it holds |
|---|---|---|
| **Respondents** | 500 | Age group, city, occupation, income, savings, budget, current phone, years owned, main complaint, top priority, excitement score, hype source, preferred model, payment plan |
| **Phone_Prices** | 7 | iPhone 18 Pro and Pro Max by storage, with the Nigerian price in naira (₦) and the US price |

**Relationship:** `Respondents[Phone_Key]` → `Phone_Prices[Phone_Key]` (many to one).

> **Please note:**
> - The 500 respondents are **synthetic (made-up) survey data**. I created them to practise and show my dashboard skills. They are not real people, so the results should not be read as a real survey of Nigerians.
> - The phone prices are real Nigerian retail prices as of **October 2026**. Prices change, so this is a snapshot.
> - I covered the **Pro and Pro Max only**. 
---

## DAX Used

**Calculated columns (Respondents)**
- `Price_NGN`: pulls the price of the phone each person wants from `Phone_Prices`
- `Can Afford`: "Yes" if the person's budget is enough for that phone, otherwise "No"
- `Upgrade Verdict`: sorts each person into **Skip**, **Upgrade now** or **Wait**
  - **Skip:** owned their phone for less than 3 years and has no major complaint
  - **Upgrade now:** can afford it
  - **Wait:** everyone else

**Measures**
- `Affordability Rate`: share of respondents who can afford their chosen phone
- `Avg Excitement`: average excitement score (1 to 5)
- `Avg Price Needed`: average price of the phone people want
- `Best Occupation`: the occupation with the highest affordability rate
- `Best Model`: the model people prefer most

---

## What I Found

*(Based on the 500 synthetic respondents)*

- **About 1 in 5 people (21.8%) can afford the phone they want.**
- The average price people would need to pay is about **₦2.79 million**.
- **Tech and Finance professionals** are the group that can afford it most. Students and civil servants are at the bottom.
- The **iPhone 18 Pro** is preferred over the Pro Max (302 vs 198 people).
- Most people should **wait** (322), 92 can upgrade now, and 86 should skip.

**My conclusion:** the iPhone 18 series is a good buy for a small group, mainly people on higher incomes with older phones. For most Nigerians, it is better to wait, and anyone with a phone less than 3 years old and no problems can skip it.

---

## Tools

- **Power BI Desktop**: dashboard, bookmarks and navigation buttons
- **DAX**: calculated columns and measures
- **Excel**: dataset

---

## About Me

I'm **Deborah Bamigbade**, a data analyst and instructor based in Lagos, Nigeria. I work with Power BI, SQL and DAX. This is one of my portfolio projects.

Feel free to connect with me or leave feedback.
