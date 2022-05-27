# Module_10_Repo

## Description

# This project clusters cryptos by their performance in different time periods. The results are ploted in order to visually show the reults and performance. uses the elbow method algorithm to find the best value for 'k' from a range of 1-11. Then a line chart is ploted using all the original data and picking the most optimal value for 'k'. In the next step we used PCA and reduced the components to 3 to simplify it. We then determined how much info. attributed to each principal component by retrieving the explained variance. A new datafram was created using the PCA data. Finding the best value for 'k' using PCA data meant repeating all the same steps from the original 'k' vlaue inluding the chart. We then used the KMeans to cluster cryptos using the PCA data. Using the best value for 'k' from the elbow plot we initialize the KMeans. Then we fit the KMeans model using the PCA data and predicted the clusters and viewed them. Then a copy was made of the df and a scatter plot was made. Then the graphs were compared side-by-side.

## Technologies

# This project is written with the programming language Python. It also uses the libraries Pandas, PCA, KMeans, StandardScaler, and Path. The project was written on the Windows operating system.
---

## Installation Guide

```
df_market_data = pd.read_csv(
    Path("Resources/crypto_market_data.csv"),
    index_col="coin_id")
```

```
df_market_data.hvplot.line(
    width=800,
    height=400,
    rot=90
)
```

## Usage

```
df_market_data_scaled = pd.DataFrame(
    scaled_data,
    columns=df_market_data.columns
)

for i in k:
    k_model = KMeans(n_clusters=i, random_state=1)
    k_model.fit(df_market_data_scaled)
    inertia.append(k_model.inertia_)
    
    df_elbow.hvplot.line(
    x="k", 
    y="inertia", 
    title="Elbow Chart", 
    xticks=k
)
df_market_data_scaled.hvplot.scatter(
    x="price_change_percentage_24h", 
    y="price_change_percentage_7d", 
    color= k_4,
    hover_cols="coin_id"
)

plot_df_market_data_scaled = df_elbow.hvplot.line(
    x="k", 
    y="inertia", 
    title="Elbow Chart", 
    xticks=k
)
plot_df_market_data_pca = df_elbow.hvplot.line(
    x="k", 
    y="inertia", 
    title="Elbow Chart", 
    xticks=k
)

plot_df_market_data_scaled + plot_df_market_data_pca
---

## Contributors


# Creator of this project is Thomas Burns
# Email is burns235577@gmail.com
---