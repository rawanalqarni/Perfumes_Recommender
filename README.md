# Perfumes_Recommender

<img src="https://github.com/rawanalqarni/Perfumes_Recommender/blob/main/images/3.jpg" width="1000" height="300" />

Perfumes recommender is a recommendation system for perfumes. As we all know recommendation systems are popular these days and used by a lot of companies in order to understand their customer and provide them with a better service. This project aim to find similar perfumes based on perfumes features. 

This project have 4 main phases: 
Phase1: collecting the data, data was collected from GoldenScent website https://www.goldenscent.com/en/, using scraping packages in python.
Phase2: cleaning the dataset and in the phase I faced many issues because data obtained from goldenscent website have a lot of incosistencies and null values that lead to a lot of problems and have to be resolved before starting the building recommender phase. 

### Datasets obtained from GoldenScent:
- Perfumes Dataset: 
This dataset contain Perfumes data: Perfumes_Name, Brand, Describtion, Price, Gender, Product_type, Fragrance_Family, Character, Average Rate, Ingredients, Top, Middle and Base Notes, image_URL.

- Reviews Dataset: 
This dataset contain User nickname, Perfume_name, Brand, Fragrance_Family, Overall_rating, User_rating, Revirews, Date. 

### Data Dictionary:
<table>
<tr>
<th> Column </th>
<th> Description </th>
</tr>

<tr>
    <td> Name </td>
    <td> Full name of the perfume </td>
</tr>


<tr>
    <td> Price </td>
    <td> The price is in SAR and it is an object type not a float </td>
</tr>  


<tr>
    <td> Description </td>
    <td> The description consist of a perfume description as well as a small description about the brand </td>
</tr>


<tr>
    <td> Rate </td>
    <td> This represent the average rating for the perfume by the users on a scale 0-5</td>
</tr>


<tr>
    <td> Rating_count </td>
    <td> This represent how many users have rated the perfume </td>
</tr>


<tr>
    <td> image </td>
    <td> This contain the image url of the perfume </td>
</tr>

<tr>
    <td> Brand </td>
    <td> The dataset contains 484 brands </td>
</tr>

<tr>
    <td> Gender </td>
    <td> The gender as Wonem, Men, Home, Unisex </td>
</tr>

<tr>
    <td> Product_Type </td>
    <td> This specify the product type such as perfume, perfume set, perfume oil, candle </td>
</tr>

<tr>
    <td> Character </td>
    <td> this specify a character for each perfume such as Romantic,Charismatic. </td>
</tr>

<tr>
    <td> Fragrance_Family </td>
    <td> This reperesent the class of the perfume such as floral, woody </td>
</tr>

<tr>
    <td> Size </td>
    <td> Most Perfume measured in ml, however the dataset contains other sizes: g </td>
</tr>

<tr>
    <td> Year </td>
    <td> This represent the year the perfume have lunched </td>
</tr>

<tr>
    <td> Ingredients </td>
    <td> This contain all the perfume Ingredients </td>
</tr>

<tr>
    <td> Concentration</td>
    <td> This represent how strong the perfume is such as Parfum which is the strongest </td>
</tr>

<tr>
    <td> Top_note </td>
    <td> The Top Note is the note Ingredients, this note is the light note </td>
</tr>

<tr>
    <td> Middle_note </td>
    <td> The Middle note is the core and very essence of the of the perfume</td>
</tr>

<tr>
    <td> Base_note </td>
    <td> The base notes of the perfume give it depth, richness (the foundation of the perfume)</td>
</tr>

</table>

Phase3: Exploring the dataset by doing a proper Exploratory Data Analysis.
Phase4: Building the recommender, using content-based similarity recommender based on cosine similarity. This approach was chosen due to the nature of the dataset in hand where there are no enough rating data avaliable in the dataset. 

This Repository contains:
1. Scraping_scripts folder that contains scripts used to scrape data from GoldenScent
2. Dataset folder which consist of 4 csv files:
      - Perfume_Dataset that is the uncleaned dataset from scraping 
      - Reviews_Dataset that contains reviews from scraping
      - Dataset that is the Perfume_dataset after cleaning 
      - final_df is the final dataset used in the recommender building phase 
3. EDA.ipynb: this notebook for EDA phase for Perfumes_Dataset 
4. EDA_Reviews: this notebook for EDA phase for Reviews_Dataset 
5. Model_1.ipynb: this notebook contains the recommender 
6. Model.ipynb: this notebook contains recommender based on description which perform poorly and replced by Model_1 


In Conclusion, two recommender was built in order to see which perform better. First recommender was based on perfume description, unfortanatily it did not perform well. the reason is that not all perfume descriptions have a useful information about the perfume not only this some brand have the same description for all their perfumes. Second recommender was based on selected features: Gender, Fragrance_Family, Ingredients, Top_note, Middle_note, Base_note. therfore the second recommender perfome better and produce 5 most similar perfumes with high cosine similarity scores.  

![Alt text](https://github.com/rawanalqarni/Perfumes_Recommender/blob/main/images/image_2.png?raw=true "Title")
