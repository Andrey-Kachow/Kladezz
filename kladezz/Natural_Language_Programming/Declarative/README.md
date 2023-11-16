# Declarative AlgoSpeak

Consider the following Haskell code.

'''
linearSearch :: Int -> [Int] -> Bool
linearSearch queryItem list =
  if 
    null list 
  then 
    False 
  else
    if
      let
        theFirstItem = head list
      in
        queryItem == theFirstItem  
    then 
      True 
    else
      linearSearch queryItem otherItemsInTheList 
  where 
    otherItemsInTheList = tail list

'''

It is not the most elegant implementation of the linear search,
because there is an attempt to avoid the usage of brackets and use mostly words, the functions in Haskell Language.

Also we could change the indentation to make the code look almost like a natural language.

'''

linearSearch' :: Int -> [Int] -> Bool
linearSearch' queryItem list = if null list then False 
  else if let theFirstItem = head list in queryItem == theFirstItem then True 
  else linearSearch' queryItem otherItemsInTheList where otherItemsInTheList = tail list

'''

But it is hard to read for both programmers and non-programmers.
Bad compromise.
But Haskell uses declarative syntax and maybe implement declarative natural language would be easier than imperative.
Who knows.


