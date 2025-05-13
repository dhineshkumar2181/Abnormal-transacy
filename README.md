import pandas as pd
import numpy as np

# Sample transaction data
data = {
    'transaction_id': range(1, 11),
    'user_id': [101, 102, 101, 103, 104, 105, 101, 102, 106, 107],
    'amount': [50, 200, 75, 4000, 60, 100, 80, 250, 5000, 30]
}

df = pd.DataFrame(data)

# Compute statistical threshold
mean = df['amount'].mean()
std = df['amount'].std()
threshold = mean + 2 * std  # or use 3 * std for more tolerance

# Mark abnormal transactions
df['is_abnormal'] = df['amount'] > threshold

# Output results
print("Mean:", mean)
print("Std Dev:", std)
print("Threshold:", threshold)
print(df)
