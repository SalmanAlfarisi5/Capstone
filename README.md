I guess this is okay since we're using dummy data anyways

Notes for methodology:

The formula for Attribute Score: 0.5 * (same category) + 0.15 * (same brand) + 0.15 * (same models) + 0.2 * (price after MinMaxScaler)
We will have two Trasaction Score for this task, one is based on Apriori Association and the other one is Yule’s Q
For computing Apriori Association, we will use this source: https://medium.com/@yamanbsr/developing-a-marketing-strategy-by-using-apriori-algorithm-and-association-rules-on-datasets-675630eed4f5
For computing Yule's Q, we will use this source: https://www.wallstreetmojo.com/yules-q/

I will highly recommend to read the above sources
Notes for dataset:

product_relations.csv is from Matthew (for reference only)
ProductAttributeScores.csv is the generated data form Attribute.ipyb
ProductTransactionScores.csv is the generated data from Transaction.ipyb