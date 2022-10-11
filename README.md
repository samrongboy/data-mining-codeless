# data-mining-codeless
 
## README About project data mining codeless

## Overview
 This project is about the Quran. To compare translators with similar percentages using surah Al-fatihah to compare. with a total of 14 translators, using Dr. Mustafa Kattab as the main translator for comparison. And this is the first project to do text mining using knime. 
### Method
1. We need to put the data in our excel into knime by using
* Node excel reader
![image](https://user-images.githubusercontent.com/78845389/195181715-23139baa-9a19-4e8e-ac50-2635d1fedf65.png)
* result
![image](https://user-images.githubusercontent.com/78845389/195181925-404ec717-5fd6-4e29-8799-bd402b97b23f.png)
2. Take the column that we want to run.
* Node Cullum filter
![image](https://user-images.githubusercontent.com/78845389/195182709-b08adda8-4878-435d-8137-118f6cd2709b.png)

* result
![image](https://user-images.githubusercontent.com/78845389/195182624-e2295653-4fc9-42a0-8790-d76b6e6c4fbb.png)

3. Change data from Number to String
 ![image](https://user-images.githubusercontent.com/78845389/195182864-e0b03943-8733-457b-830f-1e76bf3f7943.png)

4. Change data from String to Document.
 ![image](https://user-images.githubusercontent.com/78845389/195182884-66c56b03-53ae-41c8-9965-b3b80a0c9684.png)

5. Do text processing, select the columns first and then will remove the letters of magic words and removes unnecessary words such as a , the , and then converts all uppercase to lowercase words. and then abbreviate From words that have the same meaning but are written differently, change them to the same word. After that, the numerical words will be removed. Then later we will choose the ROW to compare. After that, it will spread the word in ROW, what will be the word?
* Node Cullum filter
* Node Punctuation Erasure
* Node Stop Word filter
* Node Case converter
* Node N chars filter
* Node Row filter
* Node Bag of word Creator
  ![image](https://user-images.githubusercontent.com/78845389/195183185-66ab40d7-79d5-4ef4-9526-64f0dfa80fca.png)
* result
 ![image](https://user-images.githubusercontent.com/78845389/195183579-6e17b22c-e5eb-4e34-a0a0-31f3410117e6.png)

6. model to find the frequency using TF and IDF and use math formula to multiply the results of TF,IDF.
* Node TF
* Node Cullum Rename changed column name from TF rel to Tf.
* Node IDF
* Node math formula
![image](https://user-images.githubusercontent.com/78845389/195185329-8c30a167-7f08-4e16-bc59-cb65ff5c1e16.png)

Result TF
 ![image](https://user-images.githubusercontent.com/78845389/195183763-bd10fc1d-3b72-4f99-8ef4-7fad91c5372d.png)

*Result IDF
 ![image](https://user-images.githubusercontent.com/78845389/195183794-cfe6236e-8dfe-4253-b866-01a3d7b40c79.png)

*Result Math formula
 ![image](https://user-images.githubusercontent.com/78845389/195183845-785f61d5-2408-480c-a788-35be73ab570b.png)

7. Put all the values together.
* Node Document Vector
  ![image](https://user-images.githubusercontent.com/78845389/195184032-9579674f-9e56-44d9-b260-6f02e410e66a.png)

*Result
![image](https://user-images.githubusercontent.com/78845389/195184087-16647b92-b7f5-479e-a3ee-2496957edaf5.png)

8. Select the column that you want to use. and select the translators we want to compare using
 * Node Column Filler
 * Node Row Filter
  ![image](https://user-images.githubusercontent.com/78845389/195184162-ac7e9570-5780-4e69-887a-736e6df40dfc.png)

9. Use the selected comparator to test for similarity using
* Node Similarity Search
 ![image](https://user-images.githubusercontent.com/78845389/195184271-10cebf23-558a-4e89-b38c-6d70f8c4ff10.png)

*Result

![image](https://user-images.githubusercontent.com/78845389/195184325-1c9374ac-aa02-4088-913b-4fddeee1964f.png)

