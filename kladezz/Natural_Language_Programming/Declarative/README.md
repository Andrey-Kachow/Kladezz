# Declarative AlgoSpeak



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



'''

linearSearch' :: Int -> [Int] -> Bool
linearSearch' queryItem list = if null list then False 
  else if let theFirstItem = head list in queryItem == theFirstItem then True 
  else linearSearch' queryItem otherItemsInTheList where otherItemsInTheList = tail list
'''
