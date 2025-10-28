# Teaching Guide: Using Visual Illustrations for EDA Concepts

This guide helps instructors effectively use the visual illustrations when teaching the EDA Basic Lesson.

## Overview

The main notebook (`eda_basic_lesson.ipynb`) focuses on pandas fundamentals without introducing visualization libraries. These separate illustrations allow you to demonstrate visual concepts without mixing topics.

## Quick Reference by Topic

### 1. Descriptive Statistics

**Notebook Section**: "Summarizing and Computing Descriptive Statistics"
**Illustration**: `01_descriptive_statistics.png`

**Teaching Points**:
- Show students how `describe()` output maps to visual distributions
- Point out mean vs. median in skewed distributions
- Explain quartiles using box plots
- Demonstrate standard deviation as spread around mean

**Key Questions to Ask**:
- "Looking at the histogram, why might mean and median be different?"
- "What does the box plot tell us that the histogram doesn't?"
- "How does standard deviation relate to the spread we see?"

---

### 2. Value Counts

**Notebook Section**: After `obj.value_counts()` examples
**Illustration**: `02_value_counts.png`

**Teaching Points**:
- Compare different visualization styles for same data
- Show when to use vertical vs. horizontal bar charts
- Explain when pie charts are appropriate (percentages matter)
- Demonstrate sorting by frequency vs. alphabetically

**Key Questions to Ask**:
- "Which visualization makes it easier to compare frequencies?"
- "When would you prefer a table over a chart?"
- "Why might sorting by index be useful?"

---

### 3. Missing Data

**Notebook Section**: "Handling Missing Data"
**Illustration**: `03_missing_data.png`

**Teaching Points**:
- Use heatmap to identify missing data patterns
- Show impact of `dropna()` with different parameters
- Compare fillna strategies visually
- Discuss missing data correlation (do some columns tend to be missing together?)

**Key Questions to Ask**:
- "Do you see any patterns in the missing data?"
- "What's the trade-off between `dropna(how='any')` and `dropna(how='all')`?"
- "When would forward fill be appropriate vs. filling with mean?"

**Common Mistakes to Address**:
- Students might not check for missing data patterns
- May not realize impact of dropna on sample size
- Might apply inappropriate fill strategies

---

### 4. Outlier Detection

**Notebook Section**: "Handling Outliers"
**Illustration**: `04_outliers.png`

**Teaching Points**:
- Compare IQR method vs. Z-score method
- Show how outliers appear in different plot types
- Demonstrate impact of outlier removal vs. capping
- Discuss when to remove vs. transform outliers

**Key Questions to Ask**:
- "Why do IQR and Z-score methods identify different outliers?"
- "What happens to our statistics when we remove outliers?"
- "When might capping be better than removal?"

**Real-World Context**:
- Income data (right-skewed, legitimate high earners)
- Sensor data (equipment failures vs. measurement errors)
- Age data (typos vs. actual centenarians)

---

### 5. Categorical Data & Binning

**Notebook Section**: "Categorical Data" and "Computations with Categoricals"
**Illustration**: `05_categorical_binning.png`

**Teaching Points**:
- Contrast `pd.cut()` (equal width) vs. `pd.qcut()` (equal frequency)
- Show how binning converts continuous to categorical
- Explain when to use each binning method
- Demonstrate categorical type benefits and dummy variables

**Key Questions to Ask**:
- "Why are the bin widths different in qcut vs. cut?"
- "When would you want equal-frequency bins?"
- "Why do we need dummy variables for machine learning?"

**Common Use Cases**:
- Age groups for demographics (cut)
- Income quintiles for economic analysis (qcut)
- Grade brackets (cut with custom bins)

---

### 6. Handling Duplicates

**Notebook Section**: "Handling Duplicates"
**Illustration**: `06_duplicates.png`

**Teaching Points**:
- Show impact of duplicates on dataset size and statistics
- Explain `keep` parameter options ('first', 'last', False)
- Demonstrate checking duplicates on subset of columns
- Discuss when duplicates are legitimate vs. errors

**Key Questions to Ask**:
- "How do duplicates affect mean and median differently?"
- "When would you use `keep='last'` instead of `keep='first'`?"
- "Why check for duplicates on subset of columns?"

**Real-World Scenarios**:
- Time-series data with accidental double-logging
- Survey responses with duplicate submissions
- Product catalogs with legitimate variant duplicates

---

### 7. Cumulative Operations

**Notebook Section**: After `df.cumsum()` example
**Illustration**: `07_cumulative_operations.png`

**Teaching Points**:
- Show difference between daily values and cumulative totals
- Demonstrate cumsum for running totals
- Explain cumprod for compound growth
- Show cummax/cummin for tracking extremes

**Key Questions to Ask**:
- "How does the cumulative sum relate to the daily changes?"
- "Why does cumprod grow exponentially?"
- "What does a flat line in cummax tell us?"

**Real-World Applications**:
- Financial: Portfolio returns (cumprod), account balance (cumsum)
- Sports: Season points total (cumsum), personal bests (cummax)
- Operations: Inventory levels, quality metrics

---

## Teaching Strategies

### For Synchronous Classes

1. **Show, Then Code**: Display the visualization first, then work through the pandas code
2. **Interactive Questions**: Ask students to interpret visualizations before revealing answers
3. **Compare and Contrast**: Show multiple approaches side-by-side
4. **Real Data**: Connect to domains students care about (sports, social media, finance)

### For Asynchronous Learning

1. **Self-Check Questions**: Include in slide notes or video descriptions
2. **Before/After**: Show what happens without proper EDA
3. **Common Mistakes**: Highlight typical errors and their visual consequences
4. **Checkpoints**: Have students reproduce similar visualizations

### For Hands-On Labs

1. **Starter Code**: Provide the data generation code from illustration scripts
2. **Progressive Difficulty**: Start with guided exercises, then open-ended
3. **Peer Review**: Have students compare their interpretations
4. **Portfolio Projects**: Encourage students to apply to their own datasets

---

## Lesson Flow Suggestion

### Day 1: Understanding Your Data
- Descriptive Statistics (01)
- Value Counts (02)
- Missing Data (03)

### Day 2: Cleaning Your Data
- Duplicates (06)
- Outliers (04)

### Day 3: Transforming Your Data
- Categorical & Binning (05)
- Cumulative Operations (07)

---

## Assessment Ideas

### Quick Checks
- "Which plot type would best show _____?"
- "Interpret this box plot..."
- "What does this missing data pattern suggest?"

### Project-Based
- Provide a messy dataset, ask students to:
  1. Generate descriptive statistics and interpret
  2. Identify and handle missing data
  3. Detect and handle outliers
  4. Document decisions with visualizations

### Critical Thinking
- "When might removing outliers be unethical?"
- "How can missing data patterns reveal data collection issues?"
- "Why might equal-frequency bins be misleading?"

---

## Common Student Questions

**Q: "When should I use each type of plot?"**
A: Refer to 02_value_counts.png - show how different plots emphasize different aspects

**Q: "How do I know if something is really an outlier?"**
A: Refer to 04_outliers.png - discuss domain knowledge vs. statistical methods

**Q: "Why do we need cumulative operations?"**
A: Refer to 07_cumulative_operations.png - show real-world examples

**Q: "Should I always remove duplicates?"**
A: Refer to 06_duplicates.png - discuss legitimate vs. erroneous duplicates

---

## Additional Resources

### For Students
- Encourage recreating illustrations with own data
- Suggest exploring different plot types
- Recommend pandas documentation visualization section

### For Instructors
- All scripts are editable for custom examples
- Generate domain-specific examples (biology, finance, etc.)
- Create quizzes using the visualizations

---

## Troubleshooting

### If students struggle with interpretation:
- Start with simpler examples
- Use familiar domains (sports stats, movie ratings)
- Draw connections to everyday experiences

### If visualizations seem overwhelming:
- Show one plot type at a time
- Build complexity gradually
- Focus on "what does this tell us?" not "how to code this?"

### If students want to create visualizations now:
- Acknowledge interest but maintain focus
- Assure them visualization skills are coming
- Show how understanding data first makes better visualizations later

---

## Notes

- These visualizations use matplotlib and seaborn (not covered in main notebook)
- Visualization skills will be taught in subsequent lessons
- Focus on **interpreting** visualizations, not creating them (for now)
- Emphasize that EDA is about understanding data, not just making pretty pictures
