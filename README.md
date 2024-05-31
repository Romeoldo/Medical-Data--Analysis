# Medical-Data-Analysis
# Healthcare Cost Analysis Demo

## Overview

In this demo, we will analyze the healthcare cost data presented on the whiteboard. We will create three detailed charts to illustrate the various costs associated with hospitalization and scoliosis, including actual costs, employer costs, Medicare reimbursements, and cross-subsidization costs. The analysis will help us understand the financial dynamics hospitals face.

## Data Transcription

From the whiteboard, we have the following data:

**Hospitalization Costs:**
- Actual Cost: $100K
- Medicare Reimbursement: $50K
- Total Cost for 5 Patients: $250K

**Scoliosis Costs:**
- Actual Cost: $50K
- Employer Cost: $352.9K
- Adjusted Employer Cost (Loss Ratio 85%): $300K
- Medicare Underpayment: $250K

**Cross-Subsidization:**
- Cost per Rick: $52K
- Medicare Underpayment: $250K

**Additional Information:**
- Admin Cost: $52.9K

## Charts

We will create the following charts based on the data:

1. **Bar Chart of Hospitalization and Scoliosis Costs**
2. **Bar Chart of Adjusted Employer Costs for Scoliosis with Trend Line**
3. **Bar Chart of Cross-Subsidization Costs**

### Chart 1: Bar Chart of Hospitalization and Scoliosis Costs

This chart illustrates the different costs associated with hospitalization and scoliosis, including actual costs, employer costs, Medicare reimbursements, total costs for 5 patients, adjusted employer costs, and Medicare underpayments.

```python
import matplotlib.pyplot as plt

# Data
categories = ['Hospitalization', 'Scoliosis']
actual_costs = [100000, 50000]
employer_costs = [0, 352900]
medicare_reimbursement = [50000, 0]
total_costs_5_patients = [250000, 0]
adjusted_employer_costs = [0, 300000]
medicare_underpayment = [250000, 250000]

# Create bar chart
fig, ax = plt.subplots(figsize=(12, 6))
width = 0.12  # Width of the bars
x = range(len(categories))

# Plot each dataset
ax.bar(x, actual_costs, width, label='Actual Cost')
ax.bar([p + width for p in x], employer_costs, width, label='Employer Cost')
ax.bar([p + width * 2 for p in x], medicare_reimbursement, width, label='Medicare Reimbursement')
ax.bar([p + width * 3 for p in x], total_costs_5_patients, width, label='Total Cost for 5 Patients')
ax.bar([p + width * 4 for p in x], adjusted_employer_costs, width, label='Adjusted Employer Cost')
ax.bar([p + width * 5 for p in x], medicare_underpayment, width, label='Medicare Underpayment')

# Configure labels and title
ax.set_ylabel('Cost ($)')
ax.set_title('Healthcare Cost Analysis')
ax.set_xticks([p + 2 * width for p in x])
ax.set_xticklabels(categories)
ax.legend()

plt.show()
