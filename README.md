# longest-compounded-word

## Approach
- I used trie data structure as it is time and space efficient for string storage and search.
- we scan the input list from the beginning and insert each word into the trie.
- while inserting a word, we check whether it has any prefixes.
- If yes, then it’s a candidate for the longest compound word.
- We append a pair of current word and its suffix (word-prefix) into a list(or queue).
- The reason is that the current word is a valid construct only if the suffix is also a valid word or a compound word.
- So we build the trie and list(or queue) while scanning the array.
- After building the trie and the queue, then we start processing the queue by popping a pair from the beginning.
- As explained above, the pair contains the original word and the suffix we want to validate.
- We check whether the suffix is a valid or compound word. If it’s a valid word and the original word is the longest up to now, we store the result.
- Otherwise we discard the pair. The suffix may be a compound word itself, so we check if the it has any prefixes.
- If it does, then we apply the above procedure by adding the original word and the new suffix to the queue.
- If the suffix of the original popped pair is neither a valid word nor has a prefix, we simply discard that pair.
- while processing when we find a new longestCompoundWord we will store current longestCompoundWord in secondLongestCompoundWord and new one to longestCompoundWord.
- we will also check if any word longest than secondLongestCompoundWord but smaller than longestCompoundWord then we will update secondLongestCompoundWord.
