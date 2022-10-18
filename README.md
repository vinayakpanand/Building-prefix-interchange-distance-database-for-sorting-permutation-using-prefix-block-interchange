# BUILDING-PREFIX-INTERCHANGE-DISTANCE-DATABASE-FOR-SORTING-PERMUTATIONS-USING-PREFIX-BLOCK-INTERCHANGE-OPERATION
Sorting by prefix block interchange is a combinatorial optimization problem in which a given permutation is to be sorted with minimum number of prefix block interchanges. The minimum number of prefix block interchanges required to sort a permutation is called the prefix block interchange distance of the permutation . The complexity class of this problem is unknown. As part of this project we build a database of prefix block interchange distances for permutations with length at most 7. Building such a database is useful in multiple ways. This could help understand the distribution of prefix block interchange distances, or it could help partition the symmetric group into various classes with same distance, or it could be used as a benchmark data for studying the optimality of various algorithms.
# BACKGROUND

The problem of transforming a given sequence into another using a specified set
of operations is a fundamental algorithmic problem that has received a lot of attention in the last decades dues to its multiple applications various fields such as
computational biology interconnection network design, and quantum computing.
The problem is formulated as follows. A permutation of n objects is a bijection
form the set to itself. The objects we consider are {1, 2, . . . , n}. The set of all permutations of these objects, along with function composition operation defines the
symmetric group Sn. A generating set of Sn, denoted by G is a subset of Sn such
that any permutation can be expressed as a finite composition of permutations in
G. A generating set is also called an operation.
Given two permutation, say α, β ∈ Sn and an operation G, the problem of
transforming α to β using the generators in G is a combinatorial optimization
problem that reduces to a sorting problem. A sequence of generators g1, g2. . . . gt
that transforms a given permutation to I is called a sorting sequence, where I
is the identity permutation in Sn. The problem that we study in this work is to
compute a shortest sequence of generators in G that sorts a given permutation π.
The length of shortest sequence is called the distance.
The problem is known to be NP-hard in general , but for some of operations,
it can be solved in polynomial time (e.g. block-interchanges and signed reversals ), while other families yield hard problems that admit good approximations
(e.g. 11/8 for reversals and for block-transpositions ).Several restrictions of these
families have also been studied, one of which stands out in the field of interconnection network design: the so-called prefix constraint, which forces operations
to act on a prefix of the permutation rather than on an arbitrary interval. Those restrictions were introduced as a way of reducing the size of the generated network
while maintaining a low value for its diameter, thereby guaranteeing a low maximum communication delay . The most famous example is perhaps the restriction
of reversals (which reverse the order of elements along an interval) to prefix reversals, and the corresponding problem known as pancake flipping, introduced
5
in and whose complexity was only settled thirty years later.
A permutation is an ordering/arrangement of elements in a set. For example,
consider a set S = {1,2,3}. The permutations are 123,132,213,231,312,321. For a set
containing n elements there are n! permutations. For example, the set S contains
3 elements and 3! = 6 permutations are there. We denote a permutation by the
symbol π. And a permutation along with the elements are generally represented
as π = π1 π2 π3 π4.... πi... πin where i is the index/position in the permutation.

# Prefix block Interchange operation
Consider a permutation π = 43251, a prefix block is a sub-permutation containing
the first element of the permutation. The following examples shows the prefixes
of the permutation π.
a. 43251
b. 43251
c. 43251
d. 43251
e. 43251
The following examples show some blocks that are not prefixes.
a. 43251
b. 43251
c. 43251
d. 43251
A prefix block interchange operation interchanges two blocks in a permutation in which one block is a prefix block. The following examples show some
prefix block interchange operation.

![Screenshot (210)](https://user-images.githubusercontent.com/53015576/174562120-ec8cd22f-e15a-4803-88c1-0f98114682b5.png)

# How to specify a prefix block interchange operation?
We first number the gaps between the elements in the permutation. See the example.



![Screenshot (211)](https://user-images.githubusercontent.com/53015576/174562423-5f7fa0ed-c84e-4402-8652-34fe5265d220.png)


A prefix block interchange operation is specified by 4 indices (or gaps). For example, β(1,3,5,6) is the prefix block interchange that interchanges the blocks [43]
with [1]. Then the resultant permutation is 12543.
# The sorting problem
Sort the given permutation with minimum number of moves. For example,
the permutation 43251 can be sorted with 2 moves. The sequence of moves is
shown below. 43251 β(1,2,3,4) → 23451 β(1,5,5,6) → 12345
# Cayley Graph
Cayley graphs were originally proposed as a generic theoretical model for analyzing symmetric interconnection networks. The most notable feature of the
Cayley graph is its universality. The Cayley graph represents a class of highperformance interconnection network with a small degree and diameter, good
connectivity and simple routing algorithms.
Some attractive properties of this Cayley graph interconnection network include:
vertex symmetry, small degree, a sub-logarithmic diameter, extendibility, high
connectivity (robustness), easy routing, regularity of topology, fault tolerance,
extensibility and embeddability of other topologies.

Sorting permutations with various operations has applications in macro rearrangement of genes in a genome and the design of computer interconnection networks.
# 1. Application in computational biology - GENOME REARRANGEMENT
Various global rearrangements of permutations, such as reversals and transpositions have recently become of interest because of their applications in computational molecular biology.These various problems are of interest because the
permutations can be used to represent sequences of genes in chromosomes, and
the global rearrangements then represent evolutionary events. As a result, we call
these problems genome rearrangement problems.Genome rearrangement problems seem to be unlike previously studied algorithmic problems on sequences,
so new methods have had to be developed to deal with them.we study sev7
eral genome rearrangement problems as interesting and challenging algorithmic
problems in their own right, including some problems for which the global rearrangement has no immediate biological equivalent. For example, we define a
block-interchange to be a rearrangement that swaps any two substrings of the
permutation Understanding how different two organisms are is one question addressed by the comparative genomics field. A well-accepted way to estimate
the evolutionary distance between genomes of two organisms is finding the rearrangement distance, which is the smallest number of rearrangements needed to
transform one genome into another. By representing genomes as permutations,
one of them can be represented as the identity permutation, and, so, we reduce
the problem of transforming one permutation into another to the problem of sorting a permutation using the minimum number of rearrangements.
# 2. APPLICATION IN INTERCONNECTION OF NETWORK DESIGN
In the field of interconnection network design: the so-called prefix block interchange operation, which forces operations to act on a prefix of the permutation
rather than on an arbitrary interval. This is introduced as a way of reducing the
size of the generated network while maintaining a low value for its diameter,
thereby guaranteeing a low maximum communication delay .(the diameter of a
network represents the maximum communication delay between two nodes in
the network.
# 3 Literature Survey
The first approximation algorithm to solve SBT (SORTING BY TRANSPOSITIONS
)was devised in 1998 by Bafna and Pevzer , with a 1.5 ratio, based on the properties of a structure called the cycle graph. In 2006, Elias and Hartman presented a 1.375-approximation algorithm (EH algorithm) with time complexity
O(n2)O(n2), the best known approximation solution so far for SBT. In 2012, Bulteau, Fertin and Rusu demonstrated that SBT is NPNP- hard.In a later study,
the time complexity of the EH algorithm was improved to O(nlogn)O(nlogn) by
Cunha et al. Improvements to the EH algorithm, including heuristics, were proposed by Dias and Dias .

# Our approach
In our approach, we have done three algorithms to build Prefix interchange distance database for sorting permutation using Prefix block interchange operation.
9
# 1
In First approach, Manually each moves for permutations having length 2,3,4 and
5 were written using separate functions. And then these functions were invoked
recursively.

![Screenshot (213)](https://user-images.githubusercontent.com/53015576/174569025-10d7c8ca-9210-4f74-80c9-277277e6fb71.png)


# 2
In Second approach, there is a function which will automatically creates moves
for particular permutation of length. Then using tree data structure, moves were
implemented recursively.

![Screenshot (214)](https://user-images.githubusercontent.com/53015576/174569062-a39655f8-4702-4cbd-ab4a-3cb4727e89dc.png)


# 3
In Third approach, there is a function which will automatically creates moves for
particular permutation of length. Then using graph data structure and with the
help of the in-built functions in package NetworkX, moves were implemented.
The result of this approach comes to an end with the shortest distance to sort permutation of length up to 7. After 7 it takes more than 10 hours time to get the
result. The result is shown below:

![Screenshot (215)](https://user-images.githubusercontent.com/53015576/174569181-deaafd4c-a663-446c-bacf-7f2140b77a21.png)

