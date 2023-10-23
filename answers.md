# Quiz questions

This is only a "quiz" in the loosest sense that it's asking questions whose
answers will be part of your grade. Please use *any resources you want*, as
long as you list those resources (e.g. peers, websites, etc.)

## Navigating logs

1. What is the SHA for the last commit made by Prof. Xanda on the branch
xanda_0000_movie_processing?
(For this and future questions, the first 5 characters is plenty - neither
Git nor I need the whole SHA.)

c4921

2. What is the SHA for the last commit associated with line 9 of this file?

b2ed3

3. What did line 12 of this file say in commit d1d83?

"2. I should really finish writing this."

4. What changed between commit e474c and 82045?

"gross_sort = lambda x : x["Gross"]" became "gross_sort = lambda x : int(x["Gross"])" and "top_five = rows[:-5:-1]" became "top_five = rows[:-6:-1]".

## Predicting merges

Assume at the start of each of these three questions that your
branch for switching to a top-10 list was called `top_ten`
and your branch generalizing to any number of movies was called `top_N`.
Predict the behavior of these three possible operations - you don't
have to provide a full `diff` but you should describe at a high level
what changes would happen.

These questions are supposed to be separate paths, not cumulative;
for example, you should *not* assume that the operations of 5 were run
before 6. When testing outcomes later in the lab, you should make sure to
revert back to the state of the branch before you started these questions.

5. What do you think would happen if you ran the following commands?
What branches would change, and how?
```
git checkout test
git merge top_N
```

If I ran the following commands, test and top_N would merge. The process_movie_data.py file in the test branch will change to have the find_top_N function instead of the find_top_5 function.

6. What do you think would happen if you ran the following commands?
What branches would change, and how?
```
git checkout top_ten
git merge test
```

If I ran the following commands, test and top_ten would merge. The process_movie_data.py file in the top_ten branch will change to have the find_top_5 function instead of the find_top_10 function.

7. What do you think would happen if you ran the following commands?
What branches would change, and how?
```
git checkout test
git rebase top_ten
git rebase top_N
```

If I ran the following commands, there would be a merge conflict. Git wouldn't know whether it should keep the changes from top_ten or top_N, so I have to manually pick which lines of code to pick.