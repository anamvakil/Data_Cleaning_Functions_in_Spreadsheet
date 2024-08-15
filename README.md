# Data cleaning Functions in Spreadsheet

Listing down some of the functions that I used on a dataset named as ***International Logistics Association Membership*** in google spreadsheets.

### CountIF():

We use these functions when the values are much less or much more than expected. To see how this function works, the dataset that we will consider is ***International Logistics Association Membership***
 
To consider a valid example for the CountIf function, we will consider the lowest cost of membership in the column which is $100 and explore all the values below this value.

__Syntax:__ 

```
= COUNTIF(range,"value") 
```

![image](https://github.com/user-attachments/assets/192c61e9-02c2-4590-ad7b-145a48d36f04)

__Result:__

![image](https://github.com/user-attachments/assets/d400b99a-e244-43d4-a30d-0ede768def4f)

As we can see the result that comes up is 1 and this means that we have one value that is below $100. Now, let us scroll the spreadsheet and look for that value.

![7](https://github.com/user-attachments/assets/a77f4cd3-42e2-4ca9-8545-a712015cf04f)

This shows that the data was mistakenly filled as a negative number and hence we need to correct it by removing the negative sign. Similarly, we can find the values that exceed the limit in our dataset by using the greater sign (<) in the formula.

### Len()
This function is used when we need to keep the length of the string in a particular column the same. In our spreadsheet, we have a column named Member ID that uses 6 6-digit member identification code. To check if all the numbers are of the correct length we use the function Len as shown in the example screenshots below.

__Syntax:__

```
=LEN(range)
```

![image](https://github.com/user-attachments/assets/8c45eb17-6b5b-4eae-8a75-6d3276a1dce5)

__Result:__

![image](https://github.com/user-attachments/assets/f82fee73-1aad-4bea-affb-e3fd8511bad9)

Instead of going through the column and checking the individual values, we can expedite the process by using conditional formatting as shown below.

![image](https://github.com/user-attachments/assets/fe01482d-776b-4dab-bc9d-0424f023d0a0)

![image](https://github.com/user-attachments/assets/459615a4-4e11-4b08-8ca7-45b8f753ea32)

Finally, we can correct the Member ID number that shows an extra 4 to achieve clean data.

### LEFT()

We will use the following cosmetics spreadsheet to explore the Left function: https://docs.google.com/spreadsheets/d/1h1koeGo5jmBHah0QvCsjKvaF0VE-p3gOypjHLK6hgPc/edit?gid=0#gid=0. In the first column, we can see the text string and numeric string seems to be together. To test the Left function in a separate column, we will consider that we only need the 5-digit code and use the syntax as shown below. As we can see performing the Left function, provides the result given below. Finally, we can use double-click to automatically populate the rest of this column.

__Syntax:__

```
=LEFT(range,number of characters)
```
![image](https://github.com/user-attachments/assets/fbaae79c-e430-4894-8039-17fb747afc71)

__Result:__

![image](https://github.com/user-attachments/assets/f847d992-332b-4f8e-90b4-e62612f63190)

### Right()

This function is very similar to the Left function and is used to return the segment from the right side of the string. Similar to the Left function, we can use this function as shown below. Also, we can use double-click to automatically populate the rest of this column.

__Syntax:__
```
RIGHT(range,number of characters)
```
![image](https://github.com/user-attachments/assets/ea19d304-7952-49b7-a8ba-6b1f0b461972)

__Result:__

![image](https://github.com/user-attachments/assets/a8249200-8d73-44d5-bb7b-0af73ecbd362)

### MID() :
_needs to be changed_

This function is used to return the segment from the middle of the string. We see this in our spreadsheet where the client's data is composed of the first three letters of the city where the client is located, its state abbreviation, and then a three-digit identifier. now suppose we just need the country code from that string.

__SYNTAX:__
```
=MID(range,reference starting point,number of middle characters)
```
![image](https://github.com/user-attachments/assets/40385f17-551a-4e13-a8c6-3996b30731b3)

__Result:__

![image](https://github.com/user-attachments/assets/a94b49cd-f1e0-4281-af7e-70c59aa8e5c5)

### TRIM()

This function is used to remove the extra spaces in the data that can get in the way of our analysis.

__Syntax:__

```
=TRIM(range)
```
![image](https://github.com/user-attachments/assets/3f57396c-b021-4cb2-a5a4-3732f85ac237)

__Result:__

![image](https://github.com/user-attachments/assets/e9d2e03f-1720-4d35-9b9a-cb49d7261282)


### Concatenate():

This function is used to connect two or more text strings. As shown in the below example, we will re-join our Left and Right columns in our spreadsheet back into the complete product code.

__Syntax:__

```
=Concatenate(iten 1, item 2)
```
![image](https://github.com/user-attachments/assets/c925abec-ef16-493d-9a8e-16363eb1fa2e)

__Result:__

![image](https://github.com/user-attachments/assets/a109c13b-8b26-4e4b-8dae-c91171a82bf0)

The Concatenate function can do much more than joining two columns in a spreadsheet. We will explore Data Mapping by going back to the merger between our two logistics associations and using the following spreadsheet:
https://docs.google.com/spreadsheets/d/1se7dEsL7WOcpwA6eVrdegyq6W__CtxgBzWmLsiEDzWk/edit?gid=1764281342#gid=1764281342

First, let us consider that we want to concatenate the columns D and E to get the whole address in a single column and as a single string. Transforming the data into a consistent format is one of the core strengths of the Concatenate function.

![image](https://github.com/user-attachments/assets/b565768c-465c-471b-9caf-d9381a368ecd)

![image](https://github.com/user-attachments/assets/d12bb6f7-1c05-49bc-89cc-2d8780c3750d)

![image](https://github.com/user-attachments/assets/e22f4a35-3944-4784-a1e8-06b149afabf3)

As we can see the strings in both columns have merged, however, there is no space between Rd and Ste which represents the street address and the unit or suite number. To fix this efficiently and without doing manual work, we can use Concatenate function and add a space in the formula as shown here: =CONCATENATE(D2, " ", E2)

![image](https://github.com/user-attachments/assets/e24d0bd6-eb9f-4794-a9df-6f86ccf2771e)

![image](https://github.com/user-attachments/assets/a4d95039-36ba-499b-81a5-b94379c8bddb)

![image](https://github.com/user-attachments/assets/09e29967-be79-45f4-afe1-5c1043e8d21e)

