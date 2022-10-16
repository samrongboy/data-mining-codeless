# data-mining-codeless
 
## README About project data mining codeless

## Overview
 The project is a text mining project which uses Ayah Al-Qur'an Surah Al-Fatihah for text mining 
by taking the text that each translator translates to find the similarity
By measuring the similarity of Surah Al-Fatihah ( The opening) using four models; text processing , 
Term Frequency-inverse Document Frequency or TF, IDF and cosine Similarity

### Method
tool of use 
- computer 
- excel
- knime analytics platform 
- github

ACCESS DATA

1.import data from Excel. By using:

- Node Excel Reader

![image](https://user-images.githubusercontent.com/78845389/196055651-f48fcbd0-0345-4ae1-8a4b-f314dafd0a2f.png)

result

![image](https://user-images.githubusercontent.com/78845389/196055666-1b6b27d0-0064-4409-a439-73892e162f3b.png)


2. Tranfrom data

![image](https://user-images.githubusercontent.com/78845389/196055696-5a26bf56-3109-4a38-b271-0fd9c8872d60.png)

1.Remove unused data by 
- Node Collumn filter

Remove 

![image](https://user-images.githubusercontent.com/78845389/196055776-a91cf30a-48d3-495a-aa09-22671dbab24d.png)

result

![image](https://user-images.githubusercontent.com/78845389/196055790-76f2e355-f55d-4001-863f-5f33b9502a47.png)

2. Convert data from column to row By  
- Node Transpose

result

 ![image](https://user-images.githubusercontent.com/78845389/196055816-b2fe564e-5e4a-4d74-94d5-2a0152865d39.png)

3. Combine each column of text into a single column. And removes unused columns. By

- Node Column Combiner
- Node Column Fillter

Result

 ![image](https://user-images.githubusercontent.com/78845389/196055843-9505eeaf-2f26-4c51-9472-f781c4cefba7.png)

4. Create a new column in the table and combine it with the original table.
- Node Table Creator 
- Node Column Appender 

![image](https://user-images.githubusercontent.com/78845389/196055903-3f175dc7-1fbe-4038-a640-3c81b2cc6564.png)

![image](https://user-images.githubusercontent.com/78845389/196055916-f54c809e-731f-46b1-a314-254c241be919.png)

5. .Remove Dashes from Text 
- Node String Manipulation
Before Remove 

![image](https://user-images.githubusercontent.com/78845389/196055936-a3452b2c-61de-40b7-945f-25414605c310.png)

After remove

![image](https://user-images.githubusercontent.com/78845389/196055957-f399b77b-f560-4b68-bcf7-70d25e1d2e9e.png)


Text Processing

![image](https://user-images.githubusercontent.com/78845389/196055978-f47fa8f2-a316-4032-b597-f1ee3a88a298.png)

![image](https://user-images.githubusercontent.com/78845389/196055988-e56467e6-0373-498c-9d09-2ac818cb29ec.png)

1	Convert String to Doccument by will be collum tran_id and text will be collum surah. And delete the collum thatare not used by 

-	Node String to Doccumet 
-	Collumm filter 

![image](https://user-images.githubusercontent.com/78845389/196056042-5f2ed8f3-6265-487c-97a8-bb3e47d131c6.png)

Result

 ![image](https://user-images.githubusercontent.com/78845389/196056061-8d2704ad-b793-46cf-b816-5c951ff929ec.png)

2.Remove special word such as (? ! , . () , : ; "") chang all letters to lowercase. Remove unnecessary word. Frequently encountered words such as the,to,and etc. by 
- Node Punctuation Erasure
- Case Converter 
- Stop Word Filter 

Result

![image](https://user-images.githubusercontent.com/78845389/196056193-7f2b7445-aa99-42a7-a7f4-5101fbee90b2.png)

3. Use POS Tagger node ,Stanford node to separate word Part of speech(nouns,verbs, adverb etc.)

-  Node POS Tagger
- Node Stanford Tagger 
- Node Standord Lemmatizer 

Result 

![image](https://user-images.githubusercontent.com/78845389/196056209-715772d0-30aa-4c64-ae61-ccbd028a8515.png)

4. Separate words into individual words. in order to be able to compare each word. By

- Node Bag Of Words Creator 

Result

![image](https://user-images.githubusercontent.com/78845389/196056238-75e442eb-b488-483b-9727-458862eac36a.png)

5. Put all the separate words together in each column of words. By 

-Node Document vecter 

![image](https://user-images.githubusercontent.com/78845389/196056268-bd5c4912-d17f-4da8-b358-bcfe1323b196.png)

Result

![image](https://user-images.githubusercontent.com/78845389/196056283-2e1e1525-f7a5-457b-a1d3-8d528e696cf5.png)

Model 

![image](https://user-images.githubusercontent.com/78845389/196056292-3c4de6e9-4439-454f-ab0f-1210a7a63499.png)

1. Model to find the frequency by using TF ,IDF and use math formula to  multiply the results of TF,IDF 
- Node TF 
- Node Colum Rename  
- Node IDF 
- Node math formula  

Resutl 

![image](https://user-images.githubusercontent.com/78845389/196056345-fb5af1f7-7d01-48bb-bad8-8ec0442b5a49.png)

Add Column And Sort Column By ID

![image](https://user-images.githubusercontent.com/78845389/196056364-022c363c-d36c-4355-ada3-3df3dd5f6628.png)

Result 

![image](https://user-images.githubusercontent.com/78845389/196056388-ad9137c1-11f5-487e-87d3-381d0907c1a6.png)

Similarity View
 Node Similarity Search
 
 ![image](https://user-images.githubusercontent.com/78845389/196056430-d1b28eec-e203-4de0-87ca-89232b8a74f5.png)

1. Assign translators to compare For analogy use columns. ID  กำหนดนักแปลเพื่อเปรียบเทียบ ความคล้ายคลึง โดยใช้ คอลัมม์ 

- Node Row Fillter

![image](https://user-images.githubusercontent.com/78845389/196056461-2ba25d3e-0e98-4f51-a08a-5e7599394a4a.png)

2. Use Similarity Search to test similarity. By 

- Node Similarity Search

![image](https://user-images.githubusercontent.com/78845389/196056527-940ea34d-797c-4fa5-9954-8b35b9e1dc9e.png)

Result 

![image](https://user-images.githubusercontent.com/78845389/196056536-24001208-a5a8-426b-94e7-5abf4b0bf538.png)
