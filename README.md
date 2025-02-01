

# Chomsky Hierarchy Grammar Classifier

**Introduction:**

This project is related to the topic **Theory of Computation**. It is a Python-based grammar classifier that categorizes a given grammar into one of the four types in the Chomsky Hierarchy:

- **Type 3 - Regular Grammar**
- **Type 2 - Context-Free Grammar**
- **Type 1 - Context-Sensitive Grammar**
- **Type 0 - Recursively Enumerable Grammar**

It takes a set of production rules as input and determines the category to which the grammar belongs.

**Chomsky Hierarchy:**

The Chomsky Hierarchy is a classification of formal grammars used in theoretical computer science and linguistics. It consists of four types:

1. **Regular Grammar (Type 3)**  
   Rules must be of the form:  
   - A → aB (A single terminal followed by a non-terminal)  
   - A → a (A single terminal)  
   - A → ε (Empty string, optional)  
   Recognized by finite automata.

2. **Context-Free Grammar (Type 2)**  
   Rules must be of the form:  
   - A → γ, where A is a single non-terminal and γ is a string of terminals and/or non-terminals.  
   Recognized by pushdown automata.

3. **Context-Sensitive Grammar (Type 1)**  
   Rules must be of the form:  
   - αAβ → αγβ, where |LHS| ≤ |RHS|.  
   Recognized by linear bounded automata.

4. **Recursively Enumerable Grammar (Type 0)**  
   No restrictions on the form of rules.  
   Recognized by Turing machines.

**How the Code Works:**

The project includes several functions to check the type of grammar:

1. **is_regular(grammar)**  
   Checks if the given grammar follows the rules of Regular Grammar (Type 3).  
   Uses the `re` module for regular expressions to validate production rules.

2. **is_context_free(grammar)**  
   Checks if the grammar is Context-Free (Type 2).  
   Ensures that all rules have a single non-terminal on the left-hand side.

3. **is_context_sensitive(grammar)**  
   Checks if the grammar is Context-Sensitive (Type 1).  
   Ensures that the length of the left-hand side is less than or equal to the right-hand side.

4. **is_recursively_enumerable(grammar)**  
   Returns `True` since all grammars are Type 0 by default.

5. **classify_grammar(grammar)**  
   Determines the type of the given grammar by calling the above functions in order of strictest to loosest constraints.

**About the `re` Module:**

The `re` module in Python is used for working with regular expressions. It provides functions to search for patterns in strings, such as:

- **re.match()**: Checks if the pattern matches at the start of the string.
- **re.search()**: Searches the string for a pattern and returns the first match.
- **re.findall()**: Returns all non-overlapping matches of a pattern in a string.
- **re.sub()**: Replaces parts of the string that match the pattern with a new string.

In this project, `re` is used to validate production rules against the pattern of Regular Grammar (Type 3), ensuring that the left-hand side of each rule is either a single non-terminal followed by another non-terminal or a terminal, and that the rule fits the required format.

**How to Use:**

1. Run the Python script.
2. Enter production rules one by one.
3. Type 'done' when finished.
4. The program will classify the grammar and display the result.

**Example Input:**

```
S -> aA | bB
A -> a
B -> b
```

**Example Output:**

```
The grammar belongs to: Regular Language (Type 3)
```

**Requirements:**

- Python 3.x
- `re` module (built-in)

**License:**

This project is open-source and available for modifications and improvements.

---


