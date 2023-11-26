# Declarative AlgoSpeak

Consider the following Haskell code.

```
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

```

It is not the most elegant implementation of the linear search,
because there is an attempt to avoid the usage of brackets and use mostly words, the functions in Haskell Language.

Also, we could change the indentation to make the code look almost like a natural language.

```

linearSearch' :: Int -> [Int] -> Bool
linearSearch' queryItem list = if null list then False 
  else if let theFirstItem = head list in queryItem == theFirstItem then True 
  else linearSearch' queryItem otherItemsInTheList where otherItemsInTheList = tail list

```

But it is hard to read for both programmers and non-programmers.
Bad compromise.
But Haskell uses declarative syntax and maybe implementing declarative natural language would be easier than imperative.
Who knows.

```
linear search of query_item in list EVALUATES TO
    FALSE if the list is empty,
    TRUE if the head of the list = query_item,
    OR OTHERWISE TO linear search of query_item in tail of the list.
```

Looks not bad, but there is no consideration of type signature declaration.
This is not a big problem in Haskell, where the compiler can often determine type.
But it is a good tone though to write it.
And one of the ways to imagine type signature communication in natural English would be as follows.

```
linear search of SOME Integer in SOME Integer List EVALUATES TO SOME Boolean.
linear search of query_item in list EVALUATES TO
    FALSE if the list is empty,
    TRUE if the head of the list = query_item,
    OR OTHERWISE TO linear search of query_item in tail of the list.
```

Here the SOME token is abused for indicating the following types of tokens.
May not be the most natural word to use, but the other concern is what would be the better way to describe arguments and types together.
In Haskell, the sequence of types is described associatively, in the sense that the sequence of argument types is followed by a sequence of argument names.
If we use Java approach, where the argument type is followed by the argument name, for example, we could have something like this:

```
// Java:
public int linearSearch(final Integer queryItem, final List<Integer> list) { ... }

/* AlgoSpeak?

linear search of SOME Integer query_item in SOME Integer List list EVALUATES TO SOME Boolean WHICH IS
    FALSE if the list is empty,
    TRUE if the head of the list = query_item,
    OR OTHERWISE TO linear search of query_item in tail of the list.

*/
```

The latter attempt to write argument-first syntax is awkward. Kotlin on the other hand, specifies type after name.

```

// Kotlin:
fun linearSearch(queryItem: Int, list: List<Int>): Int { ... }

/* AlgoSpeak?

linear search of SOME query_item OF TYPE Integer in SOME list OF TYPE LIST EVALUATES TO SOME Boolean WHICH IS
    FALSE if the list is empty,
    ...

*/
```

