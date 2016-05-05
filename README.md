LogicalEquivalency
===================

We check for equivalency of two given logical formulas.

The basic outline of the program is below:
1. Use the Identity, Annihilation, and Inverse laws to simplify expressions involving ⊥ and ⊤.
Note that this will either eliminate all ⊥ and ⊤’s, or one ends up with ⊥ or ⊤ as the final
statement. If the resulting statement is ⊥, then the statement is in CDNF, and we can stop.
We’ll also stop if the statement is ⊤, and A(ϕ, ψ) is empty. If the statement is ⊤, and A(ϕ, ψ) is
not empty, then use Complement to replace with A ∨ ¬A where A ∈ A(ϕ, ψ), and proceed.
2. Put the statement into NNF by repeated applications of DeMorgan and Double Negation.
3. Put the statement into DNF by repeated applications of Distribution of ∧ over ∨.
4. ** Use Adjacency to ensure that every conjunction contains a literal A or ¬A for every A ∈ A(ϕ,
ψ). That is: use Adjacency to ‘add’ literals that are ‘missing’ in any conjunction. E.g. if A(ϕ, ψ)
={P,Q, R}, then a conjunct such as P ∧ Q becomes (P ∧ Q ∧ R) ∨ (P ∧ Q ∧ ¬R)
5. ** Use Commutation to order the conjuncts in any conjunction according to O. E.g. A ∧ B ∧ A ∧
¬A becomes A ∧ A ∧ ¬A ∧ B
6. Use Idempotence to eliminate duplicate conjuncts. E.g. A ∧ A ∧ ¬A ∧ B becomes A ∧ ¬A ∧ B
7. Use Complement and Annihilation to replace any conjunction containing a literal and its
negation with a contradiction symbol. E.g. A ∧ ¬A ∧ B becomes ⊥ ∧ B becomes ⊥.
8. Use Identity to get rid of all disjuncts that are ⊥. If there is only one disjunct ⊥ left, then the
statement is in CDNF and the process can stop.
9. ** Use Idempotence to eliminate any duplicate disjuncts.
10. ** Finally, use Commutation to get all disjuncts in the ‘right’ order