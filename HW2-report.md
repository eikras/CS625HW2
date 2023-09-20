# HW 2 - CS 625, Fall 2023

Eikra Shithil 
Due: September 20, 2023

## Part 1 process

Type of animal column starts with 83 choices
- In the type of animal column trimming white space. 
- Using cluster tool "fingerprint", "n-Gram fingerprint", "Metaphone3" and "Beider-Morse" merged a few type of animal. Haha it wants to place Cat with God! Even though that is hilarious I think God has to go with Dog! This bought me to 54 choices. 
- Use GREL (value.replace("Other ","").replace("Other:", "").replace("Other-", "")) then did trimming and clustering again on type of animal column. 
- Did some manual editing of things that were clearly supposed to be something but was a typo like "dlg" or "Car". 
- Replaced bunny with rabbit. 
- Down to 40 choices

Breed 
- Using almost the same process as the types of animals column for filtering and clustering
- using more of the clustering types to try and match better
- leaving the individually written out mixes as is instead of combining all under "mix"
- leaving individually discribed cat shorthair breeds as is

Age column
- I replaced all week or months with 0 years and all dead animals with 100 as we will not count dead animals for the answer and we will consider animals only a few months or weeks to be 0 years. 
if(value.contains(/months|weeks|mos/), "less than a year old", "") and 
if(value.contains(/Deceased|dead|passed|no|No|died|Dead/), "dead", "")
- I did this by creating new columns then edit the original based on the results to be either 0 for less than a year old or nothing if dead.
- I left only the digits in the age column. 
value.find(/\d+(\.\d+)?/).join(" ")

After this I continued to use clustering to refine and merge the breed names. And lastly I looked at the breed column by cound and the ones with the lease count I tried to merge them into a bigger breed category. 

## Part 2 questions and answers

1. How many types (kinds) of pets are there?
    * There are 40 types of pets in this dataset. 
2. How many cats?
    * There are 498 cats total. 
3. How many breeds of cats?
    * There are 35 breeds of cats. 
4. What's the most popular cat breed? How many cats are in that breed?
    * Domestic Shorthair is the most popular breed of Cats and there are 105 Domestic Shorthair on in the dataset. 
5. What's the age range of the cats?
    * Cats are from a few weeks old (0 years) to 24 years
6. What's the age range of the rabbits? (Don't forget to look for bunny, too.)
    * Rabbits are 2 years to 13 years old. 
7. What is the oldest pet? Give the pet's name, kind, and age.
    * The oldest pet is a 24 year old cat Bruce Springsteen who is a mix. 
8. What are the top 5 most popular dog breeds? List the breed and number.
    * The top 5 breeds of dogs are:
        * Golden Retriever: 174
        * Mutt(mix): 35
        * Beagle: 27
        * Boarder Collie, German Shepherd, Labrador Retriever: (tied for) 26
        * and Pit Bull: 23
9. What's the most popular everyday name for a dog?
    * The most popular everyday dog name is Daisy.
10. What's the most popular full name any pet?
    * The most popular full name of any pet is Sophie.

## References


* Reference 1, <https://vickysteeves.gitlab.io/2018-uutah-repro/cleaning-data.html>
* Reference 2, <https://stackoverflow.com/questions/54679433/checking-for-different-words-in-a-value>
* Reference 3, <https://stackoverflow.com/questions/73780617/how-to-keep-only-digits-in-a-cell-in-openrefine-using-grel>
* Reference 4, <https://openrefine.org/docs/manual/grel>
* Reference 5, <https://openrefine.org/docs/manual/grelfunctions>
