#goals: import the data
#strip text of extra charcters and split text with ' '
#turn columns into sets
#see intersection of words in search_term and product_title columns

import re
import pandas as pd 
def count_matches(x):
    set1 = set(x['split_search'])
    set2 = set(x['split_title'])
    #print(set1.intersection(set2))
    #turn words {'faucet', 'only', 'shower'} into numbers
    num_matches = (len(set1.intersection(set2)))
    return num_matches
    
df = pd.read_csv('train.csv', encoding="ISO-8859-1")
#strip the text
df['split_search'] = df['search_term'].str.lower().replace('\*', '').str.split()
df['split_title'] = df['product_title'].str.lower().replace('\*', '').str.split()

df['match'] = df.apply(count_matches, axis=1)
df
