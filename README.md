# Compiler-Design-Project-CFG-Left-Recursion-Elimination
The main aim of this project is to implement the context-free grammar (CFG) left-recursion elimination
algorithm.  
A CFG is a quadruple (V, Σ, R, S):  
* where V and Σ are disjoint alphabets (respectively, containing variables and terminals)  
* R ⊆ V × (V ∪ Σ)∗ is a set of rules  
* S ∈ V is the start variable.  
• This project is implemeted using Java:
• Assumptions:  
a) The set V of variables consists of upper-case English symbols.  
b) The start variable is the symbol S.  
c) The set Σ of terminals consists of lower-case English symbols.  
d) We only consider CFGs with no cycles and no ε-rules.  
• The code takes an input string encoding a CFG and returns a string encoding an equivalent CFG which is not left-recursive.  
• A string encoding a CFG is a semi-colon separated sequence of items. Each item represents a largest set of rules with the same left-hand side and is a comma-separated sequence of strings. The first string of each item is a member of V , representing the common left hand side. The first string of the first item is S.  
• For example, consider the CFG ({S, T, L}, {i, a, b, c, d}, R, S), where R is given by the
following productions.  
S −→ S c T | T  
T −→ a S b | i a L b | i  
L −→ S d L | S  
This CFG will have the following string encoding.  
**S,ScT,T;T,aSb,iaLb,i;L,SdL,S**  
• The function LRE will assume the ordering of variables as they appear in the string
encoding of the CFG. Thus, in the above example, the variables are ordered thus: S, T, L.  
• LRE returns a string encoding the resulting CFG where a newly-introduced variable, for
the elimination of immediate left-recursion for variable A, is the string A0. Thus, for the above example, the output should be as follows.  
**S,TS';T,aSb,iaLb,i;L,aSbS'dL,aSbS',iaLbS'dL,iaLbS',iS'dL,iS';S',cTS', ;**
