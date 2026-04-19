📸 Instagram Affiliate Marketing — SQL Analytics Project

A complete SQL portfolio project simulating a real-world Instagram affiliate marketing analytics system — covering post performance, engagement metrics, link click tracking, conversion funnels, and revenue reporting.


🗂️ Project Structure
instagram-affiliate-sql/
│
├── README.md                  ← You are here
├── schema.sql                 ← CREATE TABLE statements + FK constraints
├── sample_data.sql            ← 500 rows per table × 5 tables = 2,500 rows of data
├── questions/
│   ├── level1_basic.sql       ← Q01–Q08  | SELECT, WHERE, ORDER BY
│   ├── level2_intermediate.sql← Q09–Q18  | JOINs, GROUP BY, HAVING
│   ├── level3_advanced.sql    ← Q19–Q25  | CTEs, Subqueries, CASE WHEN
│   └── level4_expert.sql      ← Q26–Q30  | Window Functions, Running Totals
└── .gitignore

🏗️ Database Schema (5 Tables)
affiliate_products ──┐
                     │  1:N
                   posts ──────────── post_insights
                     │  1:N
                  link_clicks
                     │  1:N
                  conversions

📊 Entity Relationship Diagram
┌─────────────────────┐
│  affiliate_products │
│  ─────────────────  │
│  product_id  (PK)   │
│  product_name       │
│  brand              │
│  category           │
│  price              │
│  commission_rate    │
└──────────┬──────────┘
           │ 1
           │ has many
           │ N
┌──────────▼──────────┐        ┌─────────────────────┐
│       posts         │        │    post_insights     │
│  ─────────────────  │  1:1   │  ─────────────────  │
│  post_id     (PK)   │───────►│  insight_id  (PK)   │
│  post_date          │        │  post_id     (FK)   │
│  caption            │        │  views              │
│  media_type         │        │  comments           │
│  affiliate_prod_id  │        │  likes              │
│  hashtags           │        │  saves              │
└──────────┬──────────┘        │  reach              │
           │ 1                 │  recorded_at        │
           │ generates         └─────────────────────┘
           │ N
┌──────────▼──────────┐
│    link_clicks      │
│  ─────────────────  │
│  click_id    (PK)   │
│  post_id     (FK)   │
│  click_source       │
│  device_type        │
│  clicked_at         │
│  session_id         │
└──────────┬──────────┘
           │ 1
           │ leads to
           │ N
┌──────────▼──────────┐
│    conversions      │
│  ─────────────────  │
│  conversion_id (PK) │
│  click_id      (FK) │
│  post_id       (FK) │
│  sale_amount        │
│  commission         │
│  converted_at       │
│  status             │
└─────────────────────┘

🧠 SQL Concepts Covered
🟢 BasicSELECT, WHERE, DISTINCT, ORDER BY, LIMIT, COUNT, SUM, AVG
🔵 IntermediateINNER JOIN, LEFT JOIN, multi-table JOINs, GROUP BY, HAVING, DATE_FORMAT
🟣 AdvancedWITH (CTEs), Subqueries, CASE WHEN, NOT EXISTS, NULLIF, COALESCE
🔴 ExpertRANK(), DENSE_RANK(), LAG(), SUM() OVER, PARTITION BY, Running Totals

🚀 Quick Start
 MySQL Workbench 
 # 1. Create a new database
CREATE DATABASE instagram_affiliate;
USE instagram_affiliate;

# 2. Run schema first
SOURCE schema.sql;

# 3. Run Queries

## 💡 Key Business Questions Answered
- Which posts generate the most affiliate revenue?
- Which click source (bio/story/reel) converts best?
- Which product category earns the most commission?
- What media type (Reel/Photo/Carousel) performs best?

## 🛠️ Tools Used
- MySQL 8.0 / MySQL Workbench

## 📬 Connect
**Anupam_Dubey** — [LinkedIn](https://www.linkedin.com/in/anupam-dubey-23862830b/) · [GitHub](https://github.com/Anupam3601/instagram-affiliate-sql)

---
⭐ If this helped you, please star the repo!
















