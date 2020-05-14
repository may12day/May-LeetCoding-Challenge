# Solution
```
class TrieNode:
    def __init__(self):
        self.next = {}
        
class Trie:

    def __init__(self):
        """
        Initialize your data structure here.
        """
        self.root = TrieNode()

    def insert(self, word: str) -> None:
        """
        Inserts a word into the trie.
        """
        curr = self.root
        for i in word:
            if i not in curr.next:
                curr.next[i] = TrieNode()
            curr = curr.next[i]
        curr.next['/'] = None
        

    def search(self, word: str) -> bool:
        """
        Returns if the word is in the trie.
        """
        curr = self.root
        for i in word:
            if i not in curr.next:
                return False
            curr = curr.next[i]
        if '/' not in curr.next:
            return False
        return True
        

    def startsWith(self, prefix: str) -> bool:
        """
        Returns if there is any word in the trie that starts with the given prefix.
        """
        curr = self.root
        for i in prefix:
            if i not in curr.next:
                return False
            curr = curr.next[i]
        return True
        


# Your Trie object will be instantiated and called as such:
# obj = Trie()
# obj.insert(word)
# param_2 = obj.search(word)
# param_3 = obj.startsWith(prefix)
```
