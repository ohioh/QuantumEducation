---
description: >-
  Eine Übersicht zu Algorithmen und deren Beschreibung: Eine Herausragende
  Sammlung an Quantum-Algorithmen, die ihres Gleichen sucht.
cover: ../../.gitbook/assets/matrix.png
coverY: 0
---

# Algorithmen

[https://link.springer.com/article/10.1007/s00287-020-01309-9](https://link.springer.com/article/10.1007/s00287-020-01309-9)

Quelle: [https://quantumalgorithmzoo.org/](https://quantumalgorithmzoo.org)

**Algorithm:** Factoring\
**Speedup:** Superpolynomial\
**Description:** Given an _n_-bit integer, find the prime factorization. The quantum algorithm of Peter Shor solves this in $$O˜(n3)$$ time \[[82](https://quantumalgorithmzoo.org/#Shor\_factoring),[125](https://quantumalgorithmzoo.org/#Shor\_factoring94)]. The fastest known classical algorithm for integer factorization is the general number field sieve, which is believed to run in time $$2O˜(n1/3)$$. The best rigorously proven upper bound on the classical complexity of factoring is $$O(2n/4+o(1))$$ via the Pollard-Strassen algorithm \[[252](https://quantumalgorithmzoo.org/#Pol), [362](https://quantumalgorithmzoo.org/#Stras)]. Shor's factoring algorithm breaks RSA public-key encryption and the closely related quantum algorithms for discrete logarithms break the DSA and ECDSA digital signature schemes and the Diffie-Hellman key-exchange protocol. A quantum algorithm even faster than Shor's for the special case of factoring “semiprimes”, which are widely used in cryptography, is given in \[[271](https://quantumalgorithmzoo.org/#GLFB15)]. If small factors exist, Shor's algorithm can be beaten by a quantum algorithm using Grover search to speed up the elliptic curve factorization method \[[366](https://quantumalgorithmzoo.org/#PQRSA)]. Additional optimized versions of Shor's algorithm are given in \[[384](https://quantumalgorithmzoo.org/#EH17), [386](https://quantumalgorithmzoo.org/#BBM17)]. There are proposed classical public-key cryptosystems not believed to be broken by quantum algorithms, _cf._ \[[248](https://quantumalgorithmzoo.org/#BBD09)]. At the core of Shor's factoring algorithm is order finding, which can be reduced to the [Abelian hidden subgroup problem](https://quantumalgorithmzoo.org/#abelian\_HSP), which is solved using the quantum Fourier transform. A number of other problems are known to reduce to integer factorization including the membership problem for matrix groups over fields of odd order \[[253](https://quantumalgorithmzoo.org/#BBS09)], and certain diophantine problems relevant to the synthesis of quantum circuits \[[254](https://quantumalgorithmzoo.org/#RS12)].

**Algorithm:** Discrete-log\
**Speedup:** Superpolynomial\
**Description:** We are given three _n_-bit numbers _a_, _b_, and _N_, with the promise that _b_=_as\_mod\_N_ for some _s_. The task is to find _s_. As shown by Shor \[[82](https://quantumalgorithmzoo.org/#Shor\_factoring)], this can be achieved on a quantum computer in poly(_n_) time. The fastest known classical algorithm requires time superpolynomial in _n_. By similar techniques to those in \[[82](https://quantumalgorithmzoo.org/#Shor\_factoring)], quantum computers can solve the discrete logarithm problem on elliptic curves, thereby breaking elliptic curve cryptography \[[109](https://quantumalgorithmzoo.org/#Zalka\_ellip), [14](https://quantumalgorithmzoo.org/#BL95)]. A further optimization to Shor's algorithm is given in \[[385](https://quantumalgorithmzoo.org/#E17)]. The superpolynomial quantum speedup has also been extended to the discrete logarithm problem on semigroups \[[203](https://quantumalgorithmzoo.org/#Childs\_Ivanyos), [204](https://quantumalgorithmzoo.org/#Banin\_Tsaban)]. See also [Abelian hidden subgroup](https://quantumalgorithmzoo.org/#abelian\_HSP).\
\
**Algorithm:** Pell's Equation\
**Speedup:** Superpolynomial\
**Description:** Given a positive nonsquare integer _d_, Pell's equation is \_x\_2−\_dy\_2=1. For any such _d_ there are infinitely many pairs of integers (_x,y_) solving this equation. Let (\_x\_1,_y\_1) be the pair that minimizes x+yd\_−−√. If d is an n-bit integer (i.e. 0≤\_d<2\_n_ ), (\_x\_1,\_y\_1) may in general require exponentially many bits to write down. Thus it is in general impossible to find (\_x\_1,\_y\_1) in polynomial time. Let _R_=log(\_x\_1+\_y\_1\_d\_−−√). ⌊_R_⌉ uniquely identifies (\_x\_1,\_y\_1). As shown by Hallgren \[[49](https://quantumalgorithmzoo.org/#Hallgren\_Pell)], given a _n_-bit number _d_, a quantum computer can find ⌊_R_⌉ in poly(_n_) time. No polynomial time classical algorithm for this problem is known. Factoring reduces to this problem. This algorithm breaks the Buchman-Williams cryptosystem. See also [Abelian hidden subgroup](https://quantumalgorithmzoo.org/#abelian\_HSP).

\
**Algorithm:** Principal Ideal\
**Speedup:** Superpolynomial\
**Description:** We are given an _n_-bit integer _d_ and an invertible ideal _I_ of the ring Z\[\_d\_−−√]. _I_ is a principal ideal if there exists \_α\_∈Q(\_d\_−−√) such that _I_=_α\_Z\[d\_−−√]. α may be exponentially large in d. Therefore α cannot in general even be written down in polynomial time. However, ⌊log\_α⌉ uniquely identifies α. The task is to determine whether I is principal and if so find ⌊log\_α_⌉. As shown by Hallgren, this can be done in polynomial time on a quantum computer \[[49](https://quantumalgorithmzoo.org/#Hallgren\_Pell)]. A modified quantum algorithm for this problem using fewer qubits was given in \[[131](https://quantumalgorithmzoo.org/#Schmidt\_PIP)]. A quantum algorithm solving the principal ideal problem in number fields of arbitrary degree (_i.e._ scaling polynomially in the degree) was subsequently given in \[[329](https://quantumalgorithmzoo.org/#Biasse\_Song16)]. Factoring reduces to solving Pell's equation, which reduces to the principal ideal problem. Thus the principal ideal problem is at least as hard as factoring and therefore is probably not in P. See also [Abelian hidden subgroup](https://quantumalgorithmzoo.org/#abelian\_HSP).\
\
**Algorithm:** Unit Group\
**Speedup:** Superpolynomial\
**Description:** The number field Q(_θ_) is said to be of degree _d_ if the lowest degree polynomial of which _θ_ is a root has degree _d_. The set O of elements of Q(_θ_) which are roots of monic polynomials in Z\[_x_] forms a ring, called the ring of integers of Q(_θ_). The set of units (invertible elements) of the ring O form a group denoted O∗. As shown by Hallgren \[[50](https://quantumalgorithmzoo.org/#Hallgren\_unit)], and independently by Schmidt and Vollmer \[[116](https://quantumalgorithmzoo.org/#Schmidt)], for any Q(_θ_) of fixed degree, a quantum computer can find in polynomial time a set of generators for O∗ given a description of _θ_. No polynomial time classical algorithm for this problem is known. Hallgren and collaborators subsequently discovered how to achieve polynomial scaling in the degree \[[213](https://quantumalgorithmzoo.org/#EHKS14)]. See also \[[329](https://quantumalgorithmzoo.org/#Biasse\_Song16)]. The algorithms rely on solving Abelian hidden subgroup problems over the additive group of real numbers.

**Algorithm:** Class Group\
**Speedup:** Superpolynomial\
**Description:** The number field Q(_θ_) is said to be of degree _d_ if the lowest degree polynomial of which _θ_ is a root has degree _d_. The set O of elements of Q(_θ_) which are roots of monic polynomials in Z\[_x_] forms a ring, called the ring of integers of Q(_θ_), which is a Dedekind domain. For a Dedekind domain, the nonzero fractional ideals modulo the nonzero principal ideals form a group called the class group. As shown by Hallgren \[[50](https://quantumalgorithmzoo.org/#Hallgren\_unit)], a quantum computer can find a set of generators for the class group of the ring of integers of any constant degree number field, given a description of _θ_, in time poly(log(|O|)). An improved quantum algorithm, whose runtime is also polynomial in _d_ was subsequently given in \[[329](https://quantumalgorithmzoo.org/#Biasse\_Song16)]. No polynomial time classical algorithm for these problems are known. See also [Abelian hidden subgroup](https://quantumalgorithmzoo.org/#abelian\_HSP).\
\
**Algorithm:** Gauss Sums\
**Speedup:** Superpolynomial\
**Description:** Let F\_q\_ be a finite field. The elements other than zero of F\_q\_ form a group F×\_q\_ under multiplication, and the elements of F\_q\_ form an (Abelian but not necessarily cyclic) group F+_q_ under addition. We can choose some character _χ\_× of F×\_q_ and some character _χ_+ of F+_q_. The corresponding Gauss sum is the inner product of these characters: ∑\_x\_≠0∈F\_qχ\_+(_x_)\_χ\_×(_x_) As shown by van Dam and Seroussi \[[90](https://quantumalgorithmzoo.org/#vanDam\_Gauss)], Gauss sums can be estimated to polynomial precision on a quantum computer in polynomial time. Although a finite ring does not form a group under multiplication, its set of units does. Choosing a representation for the additive group of the ring, and choosing a representation for the multiplicative group of its units, one can obtain a Gauss sum over the units of a finite ring. These can also be estimated to polynomial precision on a quantum computer in polynomial time \[[90](https://quantumalgorithmzoo.org/#vanDam\_Gauss)]. No polynomial time classical algorithm for estimating Gauss sums is known. Discrete log reduces to Gauss sum estimation \[[90](https://quantumalgorithmzoo.org/#vanDam\_Gauss)]. Certain partition functions of the Potts model can be computed by a polynomial-time quantum algorithm related to Gauss sum estimation \[[47](https://quantumalgorithmzoo.org/#Geraci\_exact)].\
\
\*\*Algorithm:\*\*Primality Proving\
\*\*Speedup:\*\*Polynomial\
**Description:** Given an _n_-bit number, return a proof of its primality. The fastest classical algorithms are AKS, the best versions of which \[[393](https://quantumalgorithmzoo.org/#AKS1), [394](https://quantumalgorithmzoo.org/#AKS2)] have essentially-quartic complexity, and ECPP, where the heuristic complexity of the fastest version \[[395](https://quantumalgorithmzoo.org/#ECPP)] is also essentially quartic. The fastest known quantum algorithm for this problem is the method of Donis-Vela and Garcia-Escartin \[[396](https://quantumalgorithmzoo.org/#DVGE)], with complexity _O_(\_n\_2(log _n_)3log log _n_). This improves upon a prior factoring-based quantum algorithm for primality proving \[[397](https://quantumalgorithmzoo.org/#ChauLo)] that has complexity _O_(\_n\_3log _n_ log log _n_). A recent result of Harvey and Van Der Hoeven \[[398](https://quantumalgorithmzoo.org/#HVDH)] can be used to improve the complexity of the factoring-based quantum algorithm for primality proving to _O_(_n\_3log\_n_) and it may be possible to similarly reduce the complexity of the Donis-Vela-Garcia-Escartin algorithm to _O_(\_n\_2(log _n_)3) \[[399](https://quantumalgorithmzoo.org/#Greathouse)].

\
\*\*Algorithm:\*\*Solving Exponential Congruences\
\*\*Speedup:\*\*Polynomial\
**Description:** We are given _a_,_b_,_c_,_f_,_g\_∈F\_q_. We must find integers _x_,_y_ such that _afx_+_bgy_=_c_. As shown in \[[111](https://quantumalgorithmzoo.org/#VDS08)], quantum computers can solve this problem in \_O\_˜(\_q\_3/8) time whereas the best classical algorithm requires \_O\_˜(\_q\_9/8) time. The quantum algorithm of \[[111](https://quantumalgorithmzoo.org/#VDS08)] is based on the quantum algorithms for discrete logarithms and searching.\
\
**Algorithm:** Matrix Elements of Group Representations\
**Speedup:** Superpolynomial\
**Description:** All representations of finite groups and compact linear groups can be expressed as unitary matrices given an appropriate choice of basis. Conjugating the regular representation of a group by the quantum Fourier transform circuit over that group yields a direct sum of the group's irreducible representations. Thus, the efficient quantum Fourier transform over the symmetric group \[[196](https://quantumalgorithmzoo.org/#Beals\_general)], together with the Hadamard test, yields a fast quantum algorithm for additively approximating individual matrix elements of the arbitrary irreducible representations of _Sn_. Similarly, using the quantum Schur transform \[[197](https://quantumalgorithmzoo.org/#Schur)], one can efficiently approximate matrix elements of the irreducible representations of SU(n) that have polynomial weight. Direct implementations of individual irreducible representations for the groups U(n), SU(n), SO(n), and _An_ by efficient quantum circuits are given in \[[106](https://quantumalgorithmzoo.org/#SPJ08)]. Instances that appear to be exponentially hard for known classical algorithms are also identified in \[[106](https://quantumalgorithmzoo.org/#SPJ08)].\
\
**Algorithm:** Verifying Matrix Products\
**Speedup:** Polynomial\
**Description:** Given three _n\_×\_n_ matrices, _A,B_, and _C_, the matrix product verification problem is to decide whether _AB=C_. Classically, the best known algorithm achieves this in time _O_(\_n\_2), whereas the best known classical algorithm for matrix multiplication runs in time _O_(\_n\_2.373). Ambainis _et al._ discovered a quantum algorithm for this problem with runtime _O_(_n\_7/4) \[_[_6_](https://quantumalgorithmzoo.org/#Ambainis\_matrix)_]. Subsequently, Buhrman and Špalek improved upon this, obtaining a quantum algorithm for this problem with runtime O(n\_5/3) \[_[_19_](https://quantumalgorithmzoo.org/#Buhrman\_matrix)_]. This latter algorithm is based on results regarding quantum walks that were proven in \[_[_85_](https://quantumalgorithmzoo.org/#Szegedy)_]._\
\
_**Algorithm:** Subset-sum_\
_**Speedup:** Polynomial_\
_**Description:** Given a list of integers x\_1,…,xn, and a target integer s, the subset-sum problem is to determine whether the sum of any subset of the given integers adds up to s. This problem is NP-complete, and therefore is unlikely to be solvable by classical or quantum algorithms with polynomial worst-case complexity. In the hard instances the given integers are of order 2\_n and much research on subset sum focuses on average case instances in this regime. In \[_[_178_](https://quantumalgorithmzoo.org/#BJLM13)_], a quantum algorithm is given that solves such instances in time 20.241\_n, up to polynomial factors. This quantum algorithm works by applying a variant of Ambainis's quantum walk algorithm for element-distinctness \[_[_7_](https://quantumalgorithmzoo.org/#Ambainis\_distinctness)_] to speed up a sophisticated classical algorithm for this problem due to Howgrave-Graham and Joux. The fastest known classical algorithm for such instances of subset-sum runs in time 20.291\_n_, up to polynomial factors \[[404](https://quantumalgorithmzoo.org/#BCJ11)].\
\\

\
**Algorithm:** Decoding\
**Speedup:** Varies\
**Description:** Classical error correcting codes allow the detection and correction of bit-flips by storing data reduntantly. Maximum-likelihood decoding for arbitrary linear codes is NP-complete in the worst case, but for structured codes or bounded error efficient decoding algorithms are known. Quantum algorithms have been formulated to speed up the decoding of convolutional codes \[[238](https://quantumalgorithmzoo.org/#GM14)] and simplex codes \[[239](https://quantumalgorithmzoo.org/#BZ98)].\
\
**Algorithm:** Quantum Cryptanalysis\
**Speedup:** Various\
**Description:** It is well-known that Shor's algorithms for factoring and discrete logarithms \[[82](https://quantumalgorithmzoo.org/#Shor\_factoring),[125](https://quantumalgorithmzoo.org/#Shor\_factoring94)] completely break the RSA and Diffie-Hellman cryptosystems, as well as their elliptic-curve-based variants \[[109](https://quantumalgorithmzoo.org/#Zalka\_ellip), [14](https://quantumalgorithmzoo.org/#BL95)]. (A number of "post-quantum" public-key cryptosystems have been proposed to replace these primitives, which are not known to be broken by quantum attacks.) Beyond Shor's algorithm, there is a growing body of work on quantum algorithms specifically designed to attack cryptosystems. These generally fall into three categories. The first is quantum algorithms providing polynomial or sub-exponential time attacks on cryptosystems under standard assumptions. In particular, the algorithm of Childs, Jao, and Soukharev for finding isogenies of elliptic curves breaks certain elliptic curve based cryptosystems in subexponential time that were not already broken by Shor's algorithm \[[283](https://quantumalgorithmzoo.org/#CJS14)]. The second category is quantum algorithms achieving polynomial improvement over known classical cryptanalytic attacks by speeding up parts of these classical algorithms using Grover search, quantum collision finding, etc. Such attacks on private-key \[[284](https://quantumalgorithmzoo.org/#GLRS15), [285](https://quantumalgorithmzoo.org/#AMGMPS16), [288](https://quantumalgorithmzoo.org/#K14), [315](https://quantumalgorithmzoo.org/#BHT98b), [316](https://quantumalgorithmzoo.org/#B09)] and public-key \[[262](https://quantumalgorithmzoo.org/#LMP13), [287](https://quantumalgorithmzoo.org/#F15)] primitives, do not preclude the use of the associated cryptosystems but may influence choice of key size. The third category is attacks that make use of quantum superposition queries to block ciphers. These attacks in many cases completely break the cryptographic primitives \[[286](https://quantumalgorithmzoo.org/#KLLNP16), [289](https://quantumalgorithmzoo.org/#KM10), [290](https://quantumalgorithmzoo.org/#KM12), [291](https://quantumalgorithmzoo.org/#RS13), [292](https://quantumalgorithmzoo.org/#SS16)]. However, in most practical situations such superposition queries are unlikely to be feasible.

***

### Oracular Algorithms

**Algorithm:** Searching\
**Speedup:** Polynomial\
**Description:** We are given an oracle with _N_ allowed inputs. For one input _w_ ("the winner") the corresponding output is 1, and for all other inputs the corresponding output is 0. The task is to find _w_. On a classical computer this requires Ω(_N_) queries. The quantum algorithm of Lov Grover achieves this using _O_(\_N\_−−√) queries \[[48](https://quantumalgorithmzoo.org/#Grover\_search)], which is optimal \[[216](https://quantumalgorithmzoo.org/#BBBV)]. This has algorithm has subsequently been generalized to search in the presence of multiple "winners" \[[15](https://quantumalgorithmzoo.org/#BBHT98)], evaluate the sum of an arbitrary function \[[15](https://quantumalgorithmzoo.org/#BBHT98),[16](https://quantumalgorithmzoo.org/#BHT98),[73](https://quantumalgorithmzoo.org/#Mos98)], find the global minimum of an arbitrary function \[[35](https://quantumalgorithmzoo.org/#DH96),[75](https://quantumalgorithmzoo.org/#NW99), [255](https://quantumalgorithmzoo.org/#KLPF08)], take advantage of alternative initial states \[[100](https://quantumalgorithmzoo.org/#Biham)] or nonuniform probabilistic priors \[[123](https://quantumalgorithmzoo.org/#Montanaro)], work with oracles whose runtime varies between inputs \[[138](https://quantumalgorithmzoo.org/#Ambainis\_linear)], approximate definite integrals \[[77](https://quantumalgorithmzoo.org/#integration)], and converge to a fixed-point \[[208](https://quantumalgorithmzoo.org/#G05), [209](https://quantumalgorithmzoo.org/#TGP05)]. Considerations on optimizing the depth of quantum search circuits are given in \[[405](https://quantumalgorithmzoo.org/#ZK19)]. The generalization of Grover's algorithm known as amplitude estimation \[[17](https://quantumalgorithmzoo.org/#Amplitude)] is now an important primitive in quantum algorithms. Amplitude estimation forms the core of most known quantum algorithms related to collision finding and graph properties. One of the natural applications for Grover search is speeding up the solution to NP-complete problems such as 3-SAT. Doing so is nontrivial, because the best classical algorithm for 3-SAT is not quite a brute force search. Nevertheless, amplitude amplification enables a quadratic quantum speedup over the best classical 3-SAT algorithm, as shown in \[[133](https://quantumalgorithmzoo.org/#Ambainis\_SIGACT)]. Quadratic speedups for other constraint satisfaction problems are obtained in \[[134](https://quantumalgorithmzoo.org/#CGF)]. For further examples of application of Grover search and amplitude amplification see \[[261](https://quantumalgorithmzoo.org/#C14), [262](https://quantumalgorithmzoo.org/#LMP13)]. A problem closely related to, but harder than, Grover search, is spatial search, in which database queries are limited by some graph structure. On sufficiently well-connected graphs, _O_(\_n\_−−√) quantum query complexity is still achievable \[[274](https://quantumalgorithmzoo.org/#CG04),[275](https://quantumalgorithmzoo.org/#CNAO15),[303](https://quantumalgorithmzoo.org/#Wong16), [304](https://quantumalgorithmzoo.org/#JMW14), [305](https://quantumalgorithmzoo.org/#MW14), [306](https://quantumalgorithmzoo.org/#Wong15), [330](https://quantumalgorithmzoo.org/#HK16)].\
\
**Algorithm:** Abelian Hidden Subgroup\
**Speedup:** Superpolynomial\
**Description:** Let _G_ be a finitely generated Abelian group, and let _H_ be some subgroup of _G_ such that _G/H_ is finite. Let _f_ be a function on _G_ such that for any \_g\_1,_g\_2∈\_G_, _f_(\_g\_1)=_f_(\_g\_2) if and only if \_g\_1 and _g\_2 are in the same coset of H. The task is to find H (i.e. find a set of generators for H) by making queries to f. This is solvable on a quantum computer using O(log|G|) queries, whereas classically Ω(|G|) are required. This algorithm was first formulated in full generality by Boneh and Lipton in \[_[_14_](https://quantumalgorithmzoo.org/#BL95)_]. However, proper attribution of this algorithm is difficult because, as described in chapter 5 of \[_[_76_](https://quantumalgorithmzoo.org/#Nielsen\_Chuang)_], it subsumes many historically important quantum algorithms as special cases, including Simon's algorithm \[_[_108_](https://quantumalgorithmzoo.org/#Simon)_], which was the inspiration for Shor's period finding algorithm, which forms the core of his factoring and discrete-log algorithms. The Abelian hidden subgroup algorithm is also at the core of the Pell's equation, principal ideal, unit group, and class group algorithms. In certain instances, the Abelian hidden subgroup problem can be solved using a single query rather than order log(|G|), as shown in \[_[_30_](https://quantumalgorithmzoo.org/#Beaudrap)_]. It is normally assumed in period finding that the function f(x)≠\_f_(_y_) unless _x\_−\_y_=_s_, where _s_ is the period. A quantum algorithm which applies even when this restiction is relaxed is given in \[[388](https://quantumalgorithmzoo.org/#Hales\_Hallgren)]. Period finding has been generalized to apply to oracles which provide only the few most significant bits about the underlying function in \[[389](https://quantumalgorithmzoo.org/#SW07)].

\
**Algorithm:** Non-Abelian Hidden Subgroup\
**Speedup:** Superpolynomial\
**Description:** Let _G_ be a finitely generated group, and let _H_ be some subgroup of _G_ that has finitely many left cosets. Let _f_ be a function on _G_ such that for any \_g\_1,\_g\_2, _f_(_g\_1)=f(g\_2) if and only if g\_1 and g\_2 are in the same left coset of H. The task is to find H (i.e. find a set of generators for H) by making queries to f. This is solvable on a quantum computer using O(log(|G|) queries, whereas classically Ω(|G|) are required \[_[_37_](https://quantumalgorithmzoo.org/#Ettinger)_,_[_51_](https://quantumalgorithmzoo.org/#Hallgren\_Russell)_]. However, this does not qualify as an efficient quantum algorithm because in general, it may take exponential time to process the quantum states obtained from these queries. Efficient quantum algorithms for the hidden subgroup problem are known for certain specific non-Abelian groups \[_[_81_](https://quantumalgorithmzoo.org/#RB\_NAHS)_,_[_55_](https://quantumalgorithmzoo.org/#IMS\_NAHS)_,_[_72_](https://quantumalgorithmzoo.org/#MRRS\_NAHS)_,_[_53_](https://quantumalgorithmzoo.org/#IlG\_NAHS)_,_[_9_](https://quantumalgorithmzoo.org/#BCvD\_NAHS)_,_[_22_](https://quantumalgorithmzoo.org/#CKL\_NAHS)_,_[_56_](https://quantumalgorithmzoo.org/#ISS\_NAHS)_,_[_71_](https://quantumalgorithmzoo.org/#CP\_NAHS)_,_[_57_](https://quantumalgorithmzoo.org/#ISS2\_NAHS)_,_[_43_](https://quantumalgorithmzoo.org/#FIMSS\_NAHS)_,_[_44_](https://quantumalgorithmzoo.org/#G\_NAHS)_,_[_28_](https://quantumalgorithmzoo.org/#CvD\_NAHS)_,_[_126_](https://quantumalgorithmzoo.org/#DMR\_NAHS)_,_[_207_](https://quantumalgorithmzoo.org/#W\_NAHS)_,_[_273_](https://quantumalgorithmzoo.org/#NAHS\_BVZ)_]. A slightly outdated survey is given in \[_[_69_](https://quantumalgorithmzoo.org/#Survey\_NAHS)_]. Of particular interest are the symmetric group and the dihedral group. A solution for the symmetric group would solve graph isomorphism. A solution for the dihedral group would solve certain lattice problems \[_[_78_](https://quantumalgorithmzoo.org/#Regev\_lattice)_]. Despite much effort, no polynomial-time solution for these groups is known, except in special cases \[_[_312_](https://quantumalgorithmzoo.org/#Roet16)_]. However, Kuperberg \[_[_66_](https://quantumalgorithmzoo.org/#Kuperberg)_] found a time 2\_O(log\_N\_√)) algorithm for finding a hidden subgroup of the dihedral group DN. Regev subsequently improved this algorithm so that it uses not only subexponential time but also polynomial space \[_[_79_](https://quantumalgorithmzoo.org/#Regev\_dihedral)_]. A further improvement in the asymptotic scaling of the required number of qubits is obtained in \[_[_218_](https://quantumalgorithmzoo.org/#K13)_]. Quantum query speedups (though not necessarily efficient quantum algorithms in terms of gate count) for somewhat more general problems of testing for isomorphisms of functions under sets of permutations are given in \[_[_311_](https://quantumalgorithmzoo.org/#HM16)_]_\
\
_**Algorithm:** Bernstein-Vazirani_\
_**Speedup:** Polynomial Directly, Superpolynomial Recursively_\
_**Description:** We are given an oracle whose input is n bits and whose output is one bit. Given input x\_∈{0,1}n, the output is x\_⊙\_h, where h is the "hidden" string of n bits, and ⊙ denotes the bitwise inner product modulo 2. The task is to find h. On a classical computer this requires n queries. As shown by Bernstein and Vazirani \[_[_11_](https://quantumalgorithmzoo.org/#Bernstein\_Vazirani)_], this can be achieved on a quantum computer using a single query. Furthermore, one can construct recursive versions of this problem, called recursive Fourier sampling, such that quantum computers require exponentially fewer queries than classical computers \[_[_11_](https://quantumalgorithmzoo.org/#Bernstein\_Vazirani)_]. See \[_[_256_](https://quantumalgorithmzoo.org/#HH08)_,_ [_257_](https://quantumalgorithmzoo.org/#BH10)_] for related work on the ubiquity of quantum speedups from generic quantum circuits and \[_[_258_](https://quantumalgorithmzoo.org/#AA14)_,_ [_270_](https://quantumalgorithmzoo.org/#ABK15)_] for related work on a quantum query speedup for detecting correlations between the an oracle function and the Fourier transform of another._\
\
_**Algorithm:** Deutsch-Jozsa_\
_**Speedup:** Exponential over P, none over BPP_\
_**Description:** We are given an oracle whose input is n bits and whose output is one bit. We are promised that out of the 2\_n possible inputs, either all of them, none of them, or half of them yield output 1. The task is to distinguish the balanced case (half of all inputs yield output 1) from the constant case (all or none of the inputs yield output 1). It was shown by Deutsch \[_[_32_](https://quantumalgorithmzoo.org/#Deutsch)_] that for n=1, this can be solved on a quantum computer using one query, whereas any deterministic classical algorithm requires two. This was historically the first well-defined quantum algorithm achieving a speedup over classical computation. (A related, more recent, pedagogical example is given in \[_[_259_](https://quantumalgorithmzoo.org/#G14)_].) A single-query quantum algorithm for arbitrary n was developed by Deutsch and Jozsa in \[_[_33_](https://quantumalgorithmzoo.org/#Deutsch\_Jozsa)_]. Although probabilistically easy to solve with O(1) queries, the Deutsch-Jozsa problem has exponential worst case deterministic query complexity classically._\
\
_**Algorithm:** Formula Evaluation_\
_**Speedup:** Polynomial_\
_**Description:** A Boolean expression is called a formula if each variable is used only once. A formula corresponds to a circuit with no fanout, which consequently has the topology of a tree. By Reichardt's span-program formalism, it is now known \[_[_158_](https://quantumalgorithmzoo.org/#Reichardt\_Reflection)_] that the quantum query complexity of any formula of O(1) fanin on N variables is Θ(N\_−−√). This result culminates from a long line of work \[_[_27_](https://quantumalgorithmzoo.org/#Childs\_Jordan)_,_[_8_](https://quantumalgorithmzoo.org/#ragged)_,_[_80_](https://quantumalgorithmzoo.org/#Reichardt\_Spalek)_,_[_159_](https://quantumalgorithmzoo.org/#Reichardt\_Unbalanced)_,_[_160_](https://quantumalgorithmzoo.org/#Reichardt\_Faster)_], which started with the discovery by Farhi et al. \[_[_38_](https://quantumalgorithmzoo.org/#Farhi\_NAND)_] that NAND trees on 2\_n variables can be evaluated on quantum computers in time O(20.5\_n) using a continuous-time quantum walk, whereas classical computers require Ω(20.753\_n) queries. In many cases, the quantum formula-evaluation algorithms are efficient not only in query complexity but also in time-complexity. The span-program formalism also yields quantum query complexity lower bounds \[_[_149_](https://quantumalgorithmzoo.org/#Reichardt2010)_]. Although originally discovered from a different point of view, Grover's algorithm can be regarded as a special case of formula evaluation in which every gate is OR. The quantum complexity of evaluating non-boolean formulas has also been studied \[_[_29_](https://quantumalgorithmzoo.org/#Cleve\_tree)_], but is not as fully understood. Childs et al. have generalized to the case in which input variables may be repeated (i.e. the first layer of the circuit may include fanout) \[_[_101_](https://quantumalgorithmzoo.org/#Childs\_Kimmel\_Kothari)_]. They obtained a quantum algorithm using O(min{N,S\_−−√,N\_1/2\_G\_1/4}) queries, where N is the number of input variables not including multiplicities, S is the number of inputs counting multiplicities, and G is the number of gates in the formula. References \[_[_164_](https://quantumalgorithmzoo.org/#Zhan\_Kimmel\_Hassidim)_], \[_[_165_](https://quantumalgorithmzoo.org/#Kimmel)_], and \[_[_269_](https://quantumalgorithmzoo.org/#JK15)_] consider special cases of the NAND tree problem in which the number of NAND gates taking unequal inputs is limited. Some of these cases yield superpolynomial separation between quantum and classical query complexity._\
\
\
_**Algorithm:** Hidden Shift_\
_**Speedup:** Superpolynomial_\
_**Description:** We are given oracle access to some function f on Z\_N. We know that f(x) = g(x+s) where g is a known function and s is an unknown shift. The hidden shift problem is to find s. By reduction from Grover's problem it is clear that at least N\_−−√ queries are necessary to solve hidden shift in general. However, certain special cases of the hidden shift problem are solvable on quantum computers using O(1) queries. In particular, van Dam et al. showed that this can be done if f is a multiplicative character of a finite ring or field \[_[_89_](https://quantumalgorithmzoo.org/#vanDam\_shift)_]. The previously discovered shifted Legendre symbol algorithm \[_[_88_](https://quantumalgorithmzoo.org/#vanDam\_Legendre)_,_[_86_](https://quantumalgorithmzoo.org/#vanDam\_weighing)_] is subsumed as a special case of this, because the Legendre symbol (xp) is a multiplicative character of F\_p. No classical algorithm running in time O(polylog(N)) is known for these problems. Furthermore, the quantum algorithm for the shifted Legendre symbol problem would break a certain cryptographic pseudorandom generator given the ability to make quantum queries to the generator \[_[_89_](https://quantumalgorithmzoo.org/#vanDam\_shift)_]. A quantum speedup for hidden shift problems of difference sets is given in \[_[_312_](https://quantumalgorithmzoo.org/#Roet16)_], and this also subsumes the Legendre symbol problem as a special case. Roetteler has found exponential quantum speedups for finding hidden shifts of certain nonlinear Boolean functions \[_[_105_](https://quantumalgorithmzoo.org/#Roetteler08)_,_[_130_](https://quantumalgorithmzoo.org/#Roetteler\_quad)_]. Building on this work, Gavinsky, Roetteler, and Roland have shown \[_[_142_](https://quantumalgorithmzoo.org/#Gavinsky)_] that the hidden shift problem on random boolean functions f:Z\_n\_2→Z2 has O(n) average case quantum complexity, whereas the classical query complexity is Ω(2\_n/2). The results in \[_[_143_](https://quantumalgorithmzoo.org/#Ettinger\_Hoyer)_], though they are phrased in terms of the hidden subgroup problem for the dihedral group, imply that the quantum query complexity of the hidden shift problem for an injective function on Z\_N_ is _O_(log _n_), whereas the classical query complexity is Θ(_N\_−−√). However, the best known quantum circuit complexity for injective hidden shift on Z\_N_ is _O_(2\_C\_log\_N\_√), achieved by Kuperberg's sieve algorithm \[[66](https://quantumalgorithmzoo.org/#Kuperberg)]. A recent result, building upon \[[408](https://quantumalgorithmzoo.org/#Ivanyos08), [43](https://quantumalgorithmzoo.org/#FIMSS\_NAHS)], achieves exponential quantum speedups for some generalizations of the Hidden shift problem including the _hidden multiple shift problem_, in which one has query access to _fs_(_x_)=_f_(_x\_−\_hs_) over some allowed range of _s_ and one wishes to infer _h_ \[[407](https://quantumalgorithmzoo.org/#IPS18)].\
\
**Algorithm:** Polynomial interpolation\
**Speedup:** Varies\
**Description:** Let _p_(_x_)=_adxd_+…+_a\_1\_x_+\_a\_0 be a polynomial over the finite field GF(_q_). One is given access to an oracle that, given _x\_∈GF(q), returns p(x). The polynomial reconstruction problem is, by making queries to the oracle, to determine the coefficients ad,…,a\_0. Classically, d+1 queries are necessary and sufficient. (In some sources use the term reconstruction instead of interpolation for this problem.) Quantumly, d/2+1/2 queries are necessary and d/2+1 queries are sufficient \[_[_360_](https://quantumalgorithmzoo.org/#interp1)_,_[_361_](https://quantumalgorithmzoo.org/#interp2)_]. For multivariate polynomials of degree d in n variables the interpolation problem has classical query complexity (n+dd). As shown in \[_[_387_](https://quantumalgorithmzoo.org/#interp3)_], the quantum query complexity is O(1\_n+1(n+dd)) over R and C and it is O(dn+d(n+dd)) over F\_q_ for sufficiently large _q_. Quantum algorithms have also been discovered for the case that the oracle returns _χ_(_f_(_x_)) where _χ_ is a quadratic character of GF(_q_) \[[390](https://quantumalgorithmzoo.org/#RS04)], and the case where the oracle returns _f_(_x_)_e_ \[[392](https://quantumalgorithmzoo.org/#IKS17)]. These generalize the hidden shift algorithm of \[[89](https://quantumalgorithmzoo.org/#vanDam\_shift)] and achieve an exponential speedup over classical computation. A quantum algorithm for reconstructing rational functions over finite fields given noisy and incomplete oracle access to the function values is given in \[[391](https://quantumalgorithmzoo.org/#HRS05)].

\
**Algorithm:** Pattern matching\
**Speedup:** Superpolynomial\
**Description:** Given strings _T_ of length _n_ and _P_ of length _m_ < _n_, both from some finite alphabet, the pattern matching problem is to find an occurrence of _P_ as a substring of _T_ or to report that _P_ is not a substring of _T_. More generally, _T_ and _P_ could be _d_-dimensional arrays rather than one-dimensional arrays (strings). Then, the pattern matching problem is to return the location of _P_ as a _m\_×\_m\_×…×\_m_ block within the _n\_×\_n\_×…×\_n_ array _T_ or report that no such location exists. The Ω(_N\_−−√) query lower bound for unstructured search \[_[_216_](https://quantumalgorithmzoo.org/#BBBV)_] implies that the worst-case quantum query complexity of this problem is Ω(n\_−−√+m\_−−√). A quantum algorithm achieving this, up to logarithmic factors, was obtained in \[_[_217_](https://quantumalgorithmzoo.org/#RV00)_]. This quantum algorithm works through the use of Grover's algorithm together with a classical method called deterministic sampling. More recently, Montanaro showed that superpolynomial quantum speedup can be achieved on average case instances of pattern matching, provided that m is greater than logarithmic in n. Specifically, the quantum algorithm given in \[_[_215_](https://quantumalgorithmzoo.org/#Montanaro14)_] solves average case pattern matching in O\_˜((n/m)d/22\_O(d\_3/2log\_m\_√)) time. This quantum algorithm is constructed by generalizing Kuperberg's quantum sieve algorithm \[_[_66_](https://quantumalgorithmzoo.org/#Kuperberg)_] for dihedral hidden subgroup and hidden shift problems so that it can operate in d dimensions and accomodate small amounts of noise, and then classically reducing the pattern matching problem to this noisy d-dimensional version of hidden shift._\
\
_**Algorithm:** Ordered Search_\
_**Speedup:** Constant factor_\
_**Description:** We are given oracle access to a list of N numbers in order from least to greatest. Given a number x, the task is to find out where in the list it would fit. Classically, the best possible algorithm is binary search which takes log2\_N queries. Farhi et al. showed that a quantum computer can achieve this using 0.53 log2\_N queries \[_[_39_](https://quantumalgorithmzoo.org/#FGGS99)_]. Currently, the best known deterministic quantum algorithm for this problem uses 0.433 log2\_N queries \[_[_103_](https://quantumalgorithmzoo.org/#Landahl)_]. A lower bound of ln2\_π\_log2\_N_ quantum queries has been proven for this problem \[[219](https://quantumalgorithmzoo.org/#HNS01), [24](https://quantumalgorithmzoo.org/#Childs\_Lee)]. In \[[10](https://quantumalgorithmzoo.org/#Ben\_Or\_Search)], a randomized quantum algorithm is given whose expected query complexity is less than 13log2\_N\_.\
\
**Algorithm:** Graph Properties in the Adjacency Matrix Model\
**Speedup:** Polynomial\
**Description:** Let _G_ be a graph of _n_ vertices. We are given access to an oracle, which given a pair of integers in {1,2,...,_n_} tells us whether the corresponding vertices are connected by an edge. Building on previous work \[[35](https://quantumalgorithmzoo.org/#DH96),[52](https://quantumalgorithmzoo.org/#prev2),[36](https://quantumalgorithmzoo.org/#prev3)], Dürr _et al._ \[[34](https://quantumalgorithmzoo.org/#Durr\_graphs)] show that the quantum query complexity of finding a minimum spanning tree of weighted graphs, and deciding connectivity for directed and undirected graphs have Θ(\_n\_3/2) quantum query complexity, and that finding lowest weight paths has _O_(_n\_3/2log2\_n_) quantum query complexity. Deciding whether a graph is bipartite, detecting cycles, and deciding whether a given vertex can be reached from another (st-connectivity) can all be achieved using a number of queries and quantum gates that both scale as \_O\_˜(\_n\_3/2), and only logarithmically many qubits, as shown in \[[317](https://quantumalgorithmzoo.org/#CMB16)], building upon \[[13](https://quantumalgorithmzoo.org/#Berzina), [272](https://quantumalgorithmzoo.org/#Arins), [318](https://quantumalgorithmzoo.org/#BR12)]. A span-program-based quantum algorithm for detecting trees of a given size as minors in \_O\_˜(_n_) time is given in \[[240](https://quantumalgorithmzoo.org/#Wang13)]. A graph property is sparse if there exists a constant _c_ such that every graph with the property has a ratio of edges to vertices at most _c_. Childs and Kothari have shown that all sparse graph properties have query complexity Θ(\_n\_2/3) if they cannot be characterized by a list of forbidden subgraphs and _o_(\_n\_2/3) ([little-o](http://en.wikipedia.org/wiki/Big\_O\_notation#Little-o\_notation)) if they can \[[140](https://quantumalgorithmzoo.org/#Childs\_minor)]. The former algorithm is based on Grover search, the latter on the quantum walk formalism of \[[141](https://quantumalgorithmzoo.org/#Magniez\_walk)]. By Mader's theorem, sparse graph properties include all nontrivial minor-closed properties. These include planarity, being a forest, and not containing a path of given length. According to the widely-believed Aanderaa-Karp-Rosenberg conjecture, all of the above problems have Ω(\_n\_2) classical query complexity. Another interesting computational problem is finding a subgraph _H_ in a given graph _G_. The simplest case of this finding the triangle, that is, the clique of size three. The fastest known quantum algorithm for this finds a triangle in _O_(\_n\_5/4) quantum queries \[[319](https://quantumalgorithmzoo.org/#CLM16)], improving upon \[[276](https://quantumalgorithmzoo.org/#LG14), [175](https://quantumalgorithmzoo.org/#Lee\_Magniez\_Santha12), [171](https://quantumalgorithmzoo.org/#Jeffery\_Kothari\_Magniez12), [70](https://quantumalgorithmzoo.org/#Magniez\_triangle), [152](https://quantumalgorithmzoo.org/#Belovs\_Constant), [21](https://quantumalgorithmzoo.org/#Buhrman\_collision)]. Stronger quantum query complexity upper bounds are known when the graphs are sufficiently sparse \[[319](https://quantumalgorithmzoo.org/#CLM16), [320](https://quantumalgorithmzoo.org/#LS15)]. Classically, triangle finding requires Ω(\_n\_2) queries \[[21](https://quantumalgorithmzoo.org/#Buhrman\_collision)]. More generally, a quantum computer can find an arbitrary subgraph of _k_ vertices using _O_(\_n\_2−2/_k\_−\_t_) queries where _t_=(2\_k\_−\_d\_−3)/(_k_(_d_+1)(_m_+2)) and _d_ and _m_ are such that _H_ has a vertex of degree _d_ and _m_+_d_ edges \[[153](https://quantumalgorithmzoo.org/#Lee\_Magniez\_Santha)]. This improves on the previous algorithm of \[[70](https://quantumalgorithmzoo.org/#Magniez\_triangle)]. In some cases, this query complexity is beaten by the quantum algorithm of \[[140](https://quantumalgorithmzoo.org/#Childs\_minor)], which finds _H_ using \_O\_˜(\_n\_32−1vc(_H_)+1) queries, provided _G_ is sparse, where vc(_H_) is the size of the minimal vertex cover of _H_. A quantum algorithm for finding constant-sized sub-hypergraphs over 3-uniform hypergraphs in _O_(\_n\_1.883) queries is given in \[[241](https://quantumalgorithmzoo.org/#LGNT13)].

\
**Algorithm:** Graph Properties in the Adjacency List Model\
**Speedup:** Polynomial\
**Description:** Let _G_ be a graph of _N_ vertices, _M_ edges, and degree _d_. We are given access to an oracle which, when queried with the label of a vertex and \_j\_∈{1,2,…,_d_} outputs the \_j\_th neighbor of the vertex or null if the vertex has degree less than _d_. Suppose we are given the promise that _G_ is either bipartite or is far from bipartite in the sense that a constant fraction of the edges would need to be removed to achieve bipartiteness. Then, as shown in \[[144](https://quantumalgorithmzoo.org/#Ambainis\_Childs\_Liu)], the quantum complexity of deciding bipartiteness is \_O\_˜(\_N\_1/3). Also in \[[144](https://quantumalgorithmzoo.org/#Ambainis\_Childs\_Liu)], it is shown that distinguishing expander graphs from graphs that are far from being expanders has quantum complexity \_O\_˜(\_N\_1/3) and Ω˜(\_N\_1/4), whereas the classical complexity is Θ˜(\_N\_−−√). The key quantum algorithmic tool is Ambainis' algorithm for element distinctness. In \[[34](https://quantumalgorithmzoo.org/#Durr\_graphs)], it is shown that finding a minimal spanning tree has quantum query complexity Θ(\_NM\_−−−−√), deciding graph connectivity has quantum query complexity Θ(_N_) in the undirected case, and Θ˜(\_NM\_−−−−√) in the directed case, and computing the lowest weight path from a given source to all other vertices on a weighted graph has quantum query complexity Θ˜(\_NM\_−−−−√). In \[[317](https://quantumalgorithmzoo.org/#CMB16)] quantum algorithms are given for st-connectivity, deciding bipartiteness, and deciding whether a graph is a forest, which run in \_O\_˜(\_Nd\_−−√) time and use only logarithmically many qubits.\
\
**Algorithm:** Welded Tree\
**Speedup:** Superpolynomial\
**Description:** Some computational problems can be phrased in terms of the query complexity of finding one's way through a maze. That is, there is some graph _G_ to which one is given oracle access. When queried with the label of a given node, the oracle returns a list of the labels of all adjacent nodes. The task is, starting from some source node (_i.e._ its label), to find the label of a certain marked destination node. As shown by Childs _et al._ \[[26](https://quantumalgorithmzoo.org/#Childs\_weld)], quantum computers can exponentially outperform classical computers at this task for at least some graphs. Specifically, consider the graph obtained by joining together two depth-_n_ binary trees by a random "weld" such that all nodes but the two roots have degree three. Starting from one root, a quantum computer can find the other root using poly(_n_) queries, whereas this is provably impossible using classical queries.\
\
**Algorithm:** Collision Finding and Element Distinctness\
**Speedup:** Polynomial\
**Description:** Suppose we are given oracle access to a two to one function _f_ on a domain of size _N_. The collision problem is to find a pair _x_,\_y\_∈{1,2,…,_N_} such that _f(x) = f(y)_. The classical randomized query complexity of this problem is Θ(\_N\_−−√), whereas, as shown by Brassard _et al._, a quantum computer can achieve this using _O_(\_N\_1/3) queries \[[18](https://quantumalgorithmzoo.org/#Brassard\_collision)]. (See also \[[315](https://quantumalgorithmzoo.org/#BHT98b)].) Removing the promise that _f_ is two-to-one yields a problem called element distinctness, which has Θ(_N_) classical query complexity. Improving upon \[[21](https://quantumalgorithmzoo.org/#Buhrman\_collision)], Ambainis gives a quantum algorithm with query complexity of _O_(\_N\_2/3) for element distinctness, which is optimal \[[7](https://quantumalgorithmzoo.org/#Ambainis\_distinctness), [374](https://quantumalgorithmzoo.org/#P17)]. The problem of deciding whether any _k_-fold collisions exist is called _k_-distinctness. Improving upon \[[7](https://quantumalgorithmzoo.org/#Ambainis\_distinctness),[154](https://quantumalgorithmzoo.org/#Belovs\_Lee)], the best quantum query complexity for _k_-distinctness is _O_(\_n\_3/4−1/(4(2\_k\_−1))) \[[172](https://quantumalgorithmzoo.org/#Belovs12), [173](https://quantumalgorithmzoo.org/#Childs\_Jeffery\_Kothari\_Magniez13)]. For _k_=2,3 this is also the time-complexity, up to logarithmic factors, by \[[7](https://quantumalgorithmzoo.org/#Ambainis\_distinctness)]. For _k_>3 the fastest known quantum algorithm has time complexity _O_(_n_(\_k\_−1)/_k_) \[[363](https://quantumalgorithmzoo.org/#Jefferythesis)]. Given two functions _f_ and _g_, on domains of size _N_ and _M_, respectively a claw is a pair _x,y_ such that _f(x) = g(y)_. In the case that _N_=_M_, the algorithm of \[[7](https://quantumalgorithmzoo.org/#Ambainis\_distinctness)] solves claw-finding in _O_(\_N\_2/3) queries, improving on the previous _O_(_N\_3/4log\_N_) quantum algorithm of \[[21](https://quantumalgorithmzoo.org/#Buhrman\_collision)]. Further work gives improved query complexity for various parameter regimes in which _N\_≠\_M_ \[[364](https://quantumalgorithmzoo.org/#Tani), [365](https://quantumalgorithmzoo.org/#IwamaKawachi)]. More generally, a related problem to element distinctness, is, given oracle access to a sequence, to estimate the _k\_th frequency moment Fk=∑\_jnkj_, where _nj_ is the number of times that _j_ occurs in the sequence. An approximately quadratic speedup for this problem is obtained in \[[277](https://quantumalgorithmzoo.org/#M15c)]. See also [graph collision](https://quantumalgorithmzoo.org/#graph\_collision).\
\
**Algorithm:** Graph Collision\
**Speedup:** Polynomial\
**Description:** We are given an undirected graph of _n_ vertices and oracle access to a labelling of the vertices by 1 and 0. The graph collision problem is, by querying this oracle, to decide whether there exist a pair of vertices, connected by an edge, both of which are labelled 1. One can embed Grover's unstructured search problem as an instance of graph collision by choosing the star graph, labelling the center 1, and labelling the remaining vertices by the database entries. Hence, this problem has quantum query complexity Ω(\_n\_−−√) and classical query complexity Θ(_n_). In \[[70](https://quantumalgorithmzoo.org/#Magniez\_triangle)], Magniez, Nayak, and Szegedy gave a _O_(\_N\_2/3)-query quantum algorithm for graph collision on general graphs. This remains the best upper bound on quantum query complexity for this problem on general graphs. However, stronger upper bounds have been obtained for several special classes of graphs. Specifically, the quantum query complexity on a graph _G_ is \_O\_˜(\_n\_−−√+\_l\_√) where _l_ is the number of non-edges in _G_ \[[161](https://quantumalgorithmzoo.org/#JKM)], _O_(\_n\_−−√\_α\_1/6) where _α_ is the size of the largest independent set of _G_ \[[172](https://quantumalgorithmzoo.org/#Belovs12)], _O_(\_n\_−−√+\_α\_∗−−√) where \_α\_∗ is the maximum total degree of any independent set of _G_ \[[200](https://quantumalgorithmzoo.org/#GI12)], and _O_(\_n\_−−√\_t\_1/6) where _t_ is the treewidth of _G_ \[[201](https://quantumalgorithmzoo.org/#ABI13)]. Furthermore, the quantum query complexity is \_O\_˜(\_n\_−−√) with high probability for random graphs in which the presence or absence of an edge between each pair of vertices is chosen independently with fixed probability, (_i.e._ Erdős-Rényi graphs) \[[200](https://quantumalgorithmzoo.org/#GI12)]. See \[[201](https://quantumalgorithmzoo.org/#ABI13)] for a summary of these results as well as new upper bounds for two additional classes of graph that are too complicated to describe here.\
\\

\
**Algorithm:** Matrix Commutativity\
**Speedup:** Polynomial\
**Description:** We are given oracle access to _k_ matrices, each of which are _n\_×\_n_. Given integers _i_,\_j\_∈{1,2,…,_n_}, and \_x\_∈{1,2,…,_k_} the oracle returns the _ij_ matrix element of the \_x\_th matrix. The task is to decide whether all of these _k_ matrices commute. As shown by Itakura \[[54](https://quantumalgorithmzoo.org/#Itakura)], this can be achieved on a quantum computer using _O_(\_k\_4/5\_n\_9/5) queries, whereas classically this requires Ω(\_kn\_2) queries.\
\
**Algorithm:** Group Commutativity\
**Speedup:** Polynomial\
**Description:** We are given a list of _k_ generators for a group _G_ and access to a blackbox implementing group multiplication. By querying this blackbox we wish to determine whether the group is commutative. The best known classical algorithm is due to Pak and requires _O(k)_ queries. Magniez and Nayak have shown that the quantum query complexity of this task is Θ˜(_k\_2/3) \[_[_139_](https://quantumalgorithmzoo.org/#Magniez\_Nayak)_]._\
\
_**Algorithm:** Hidden Nonlinear Structures_\
_**Speedup:** Superpolynomial_\
_**Description:** Any Abelian group G can be visualized as a lattice. A subgroup H of G is a sublattice, and the cosets of H are all the shifts of that sublattice. The Abelian hidden subgroup problem is normally solved by obtaining superposition over a random coset of the Hidden subgroup, and then taking the Fourier transform so as to sample from the dual lattice. Rather than generalizing to non-Abelian groups (see_ [_non-Abelian hidden subgroup_](https://quantumalgorithmzoo.org/#nonabelian\_HSP)_), one can instead generalize to the problem of identifying hidden subsets other than lattices. As shown by Childs et al. \[_[_23_](https://quantumalgorithmzoo.org/#Childs\_nonlinear)_] this problem is efficiently solvable on quantum computers for certain subsets defined by polynomials, such as spheres. Decker et al. showed how to efficiently solve some related problems in \[_[_31_](https://quantumalgorithmzoo.org/#Wocjan\_nonlinear)_,_ [_212_](https://quantumalgorithmzoo.org/#DHIS13)_]._\
\
_**Algorithm:** Center of Radial Function_\
_**Speedup:** Polynomial_\
_**Description:** We are given an oracle that evaluates a function f from R\_d_ to some arbitrary set _S_, where _f_ is spherically symmetric. We wish to locate the center of symmetry, up to some precision. (For simplicity, let the precision be fixed.) In \[[110](https://quantumalgorithmzoo.org/#Liu)], Liu gives a quantum algorithm, based on a curvelet transform, that solves this problem using a constant number of quantum queries independent of _d_. This constitutes a polynomial speedup over the classical lower bound, which is Ω(_d_) queries. The algorithm works when the function _f_ fluctuates on sufficiently small scales, _e.g._, when the level sets of _f_ are sufficiently thin spherical shells. The quantum algorithm is shown to work in an idealized continuous model, and nonrigorous arguments suggest that discretization effects should be small.\
\
**Algorithm:** Group Order and Membership\
**Speedup:** Superpolynomial\
**Description:** Suppose a finite group _G_ is given oracularly in the following way. To every element in _G_, one assigns a corresponding label. Given an ordered pair of labels of group elements, the oracle returns the label of their product. There are several classically hard problems regarding such groups. One is to find the group's order, given the labels of a set of generators. Another task is, given a bitstring, to decide whether it corresponds to a group element. The constructive version of this membership problem requires, in the yes case, a decomposition of the given element as a product of group generators. Classically, these problems cannot be solved using polylog(|_G_|) queries even if _G_ is Abelian. For Abelian groups, quantum computers can solve these problems using polylog(|_G_|) queries by reduction to the Abelian hidden subgroup problem, as shown by Mosca \[[74](https://quantumalgorithmzoo.org/#Mosca\_thesis)]. Furthermore, as shown by Watrous \[[91](https://quantumalgorithmzoo.org/#Watrous\_solvable)], quantum computers can solve these problems using polylog(|_G_|) queries for any solvable group. For groups given as matrices over a finite field rather than oracularly, the order finding and constructive membership problems can be solved in polynomial time by using the quantum algorithms for discrete log and factoring \[[124](https://quantumalgorithmzoo.org/#Babai)]. See also [group isomorphism](https://quantumalgorithmzoo.org/#group\_isomorphism).\
\
**Algorithm:** Group Isomorphism\
**Speedup:** Superpolynomial\
**Description:** Let _G_ be a finite group. To every element of _G_ is assigned an arbitrary label (bit string). Given an ordered pair of labels of group elements, the group oracle returns the label of their product. Given access to the group oracles for two groups _G_ and _G'_, and a list of generators for each group, we must decide whether _G_ and _G'_ are isomorphic. For Abelian groups, we can solve this problem using poly(log |_G_|, log |_G'_|) queries to the oracle by applying the quantum algorithm of \[[127](https://quantumalgorithmzoo.org/#Cheung\_Mosca)], which decomposes any Abelian group into a canonical direct product of cyclic groups. The quantum algorithm of \[[128](https://quantumalgorithmzoo.org/#LeGall)] solves the group isomorphism problem using poly(log |_G_|, log |_G'_|) queries for a certain class of non-Abelian groups. Specifically, a group _G_ is in this class if _G_ has a normal Abelian subgroup _A_ and an element _y_ of order coprime to |_A_| such that G = _A_, _y_. Zatloukal has recently given an exponential quantum speedup for some instances of a problem closely related to group isomorphism, namely testing equivalence of group extensions \[[202](https://quantumalgorithmzoo.org/#Z13)].\
\
**Algorithm:** Statistical Difference\
**Speedup:** Polynomial\
**Description:** Suppose we are given two black boxes _A_ and _B_ whose domain is the integers 1 through _T_ and whose range is the integers 1 through _N_. By choosing uniformly at random among allowed inputs we obtain a probability distribution over the possible outputs. We wish to approximate to constant precision the L1 distance between the probability distributions determined by _A_ and _B_. Classically the number of necessary queries scales essentially linearly with N. As shown in \[[117](https://quantumalgorithmzoo.org/#Bravyi\_difference)], a quantum computer can achieve this using _O_(\_N\_−−√) queries. Approximate uniformity and orthogonality of probability distributions can also be decided on a quantum computer using _O_(\_N\_1/3) queries. The main tool is the quantum counting algorithm of \[[16](https://quantumalgorithmzoo.org/#BHT98)]. A further improved quantum algorithm for this task is obtained in \[[265](https://quantumalgorithmzoo.org/#M15b)].\
\
**Algorithm:** Finite Rings and Ideals\
**Speedup:** Superpolynomial\
**Description:** Suppose we are given black boxes implementing the addition and multiplication operations on a finite ring _R_, not necessarily commutative, along with a set of generators for _R_. With respect to addition, _R_ forms a finite Abelian group (_R_,+). As shown in \[[119](https://quantumalgorithmzoo.org/#Arvind)], on a quantum computer one can find in poly(log |_R_|) time a set of additive generators {_h\_1,…,hm}⊂\_R_ such that (_R_,+)≃⟨\_h\_1⟩×…×⟨_hM_⟩ and _m_ is polylogarithmic in |_R_|. This allows efficient computation of a multiplication tensor for _R_. As shown in \[[118](https://quantumalgorithmzoo.org/#WJAB)], one can similarly find an additive generating set for any ideal in _R_. This allows one to find the intersection of two ideals, find their quotient, prove whether a given ring element belongs to a given ideal, prove whether a given element is a unit and if so find its inverse, find the additive and multiplicative identities, compute the order of an ideal, solve linear equations over rings, decide whether an ideal is maximal, find annihilators, and test the injectivity and surjectivity of ring homomorphisms. As shown in \[[120](https://quantumalgorithmzoo.org/#Arvind2)], one can also use a quantum computer to efficiently decide whether a given polynomial is identically zero on a given finite black box ring. Known classical algorithms for these problems scale as poly(|_R_|).

\
**Algorithm:** Counterfeit Coins\
**Speedup:** Polynomial\
**Description:** Suppose we are given _N_ coins, _k_ of which are counterfeit. The real coins are all of equal weight, and the counterfeit coins are all of some other equal weight. We have a pan balance and can compare the weight of any pair of subsets of the coins. Classically, we need Ω(\_k\_log(_N_/_k_)) weighings to identify all of the counterfeit coins. We can introduce an oracle such that given a pair of subsets of the coins of equal cardinality, it outputs one bit indicating balanced or unbalanced. Building on previous work by Terhal and Smolin \[[137](https://quantumalgorithmzoo.org/#TS)], Iwama _et al._ have shown \[[136](https://quantumalgorithmzoo.org/#Iwama)] that on a quantum computer, one can identify all of the counterfeit coins using _O_(_k\_1/4) queries. The core techniques behind the quantum speedup are amplitude amplification and the Bernstein-Vazirani algorithm._\
\
_**Algorithm:** Matrix Rank_\
_**Speedup:** Polynomial_\
_**Description:** Suppose we are given oracle access to the (integer) entries of an n\_×\_m matrix A. We wish to determine the rank of the matrix. Classically this requires order nm queries. Building on \[_[_149_](https://quantumalgorithmzoo.org/#Reichardt2010)_], Belovs \[_[_150_](https://quantumalgorithmzoo.org/#Belovs\_Rank)_] gives a quantum algorithm that can use fewer queries given a promise that the rank of the matrix is at least r. Specifically, Belovs' algorithm uses O(r(n\_−\_r+1)−−−−−−−−−−√\_LT_) queries, where _L_ is the root-mean-square of the reciprocals of the _r_ largest singular values of _A_ and _T_ is a factor that depends on the sparsity of the matrix. For general _A_, _T_=_O_(\_nm\_−−−√). If _A_ has at most _k_ nonzero entries in any row or column then _T_=_O_(\_k\_log(_n_+_m_)). (To achieve the corresponding query complexity in the _k_-sparse case, the oracle must take a column index as input, and provide a list of the nonzero matrix elements from that column as output.) As an important special case, one can use these quantum algorithms for the problem of determining whether a square matrix is singular, which is sometimes referred to as the determinant problem. For general _A_ the quantum query complexity of the determinant problem is no lower than the classical query complexity \[[151](https://quantumalgorithmzoo.org/#Dorn)]. However, \[[151](https://quantumalgorithmzoo.org/#Dorn)] does not rule out a quantum speedup given a promise on _A_, such as sparseness or lack of small singular values.\
\
**Algorithm:** Matrix Multiplication over Semirings\
**Speedup:** Polynomial\
**Description:** A semiring is a set endowed with addition and multiplication operations that obey all the axioms of a ring except the existence additive inverses. Matrix multiplication over various semirings has many applications to graph problems. Matrix multiplication over semirings can be sped up by straightforward Grover improvements upon schoolbook multiplication, yielding a quantum algorithm that multiplies a pair of _n\_×\_n_ matrices in \_O\_˜(\_n\_5/2) time. For some semirings this algorithm outperforms the fastest known classical algorithms and for some semirings it does not \[[206](https://quantumalgorithmzoo.org/#LeGall\_Nishimura13)]. A case of particular interest is the Boolean semiring, in which OR serves as addition and AND serves as multiplication. No quantum algorithm is known for Boolean semiring matrix multiplication in the general case that beats the best classical algorithm, which has complexity \_n\_2.373. However, for sparse input our output, quantum speedups are known. Specifically, let _A,B_ be _n_ by _n_ Boolean matrices. Let _C_=_AB_, and let _l_ be the number of entries of _C_ that are equal to 1 (_i.e._ TRUE). Improving upon \[[19](https://quantumalgorithmzoo.org/#Buhrman\_matrix), [155](https://quantumalgorithmzoo.org/#LeGall\_Matrix), [157](https://quantumalgorithmzoo.org/#Williams\_Williams)], the best known upper bound on quantum query complexity is \_O\_˜(\_nl\_√), as shown in \[[161](https://quantumalgorithmzoo.org/#JKM)]. If instead the input matrices are sparse, a quantum speedup over the fastest known classical algorithm also has been found in a certain regime \[[206](https://quantumalgorithmzoo.org/#LeGall\_Nishimura13)]. For detailed comparison to classical algorithms, see \[[155](https://quantumalgorithmzoo.org/#LeGall\_Matrix), [206](https://quantumalgorithmzoo.org/#LeGall\_Nishimura13)]. Quantum algorithms have been found to perform matrix multiplication over the (max,min) semiring in \_O\_˜(\_n\_2.473) time and over the distance dominance semiring in \_O\_˜(\_n\_2.458) time \[[206](https://quantumalgorithmzoo.org/#LeGall\_Nishimura13)]. The fastest known classical algorithm for both of these problems has \_O\_˜(\_n\_2.687) complexity.\
\
**Algorithm:** Subset finding\
**Speedup:** Polynomial\
**Description:** We are oracle access to a function _f_:_D\_→\_R_ where _D_ and _R_ are finite sets. Some property \_P\_⊂(_D\_×\_R_)_k_ is specified, for example as an explicit list. Our task is to find a size-_k_ subset of _D_ satisfying _P_, _i.e._ ((\_x\_1,_f_(_x\_1)),…,(xk,f(xk)))∈\_P_, or reject if none exists. As usual, we wish to do this with the minimum number of queries to _f_. Generalizing the result of \[[7](https://quantumalgorithmzoo.org/#Ambainis\_distinctness)], it was shown in \[[162](https://quantumalgorithmzoo.org/#Childs\_Eisenberg)] that this can be achieved using _O_(|_D_|_k_/(_k_+1)) quantum queries. As an noteworthy special case, this algorithm solves the _k_-subset-sum problem of finding _k_ numbers from a list with some desired sum. A matching lower bound for the quantum query complexity is proven in \[[163](https://quantumalgorithmzoo.org/#Belovs\_Spalek)].\
\
**Algorithm:** Search with Wildcards\
**Speedup:** Polynomial\
**Description:** The search with wildcards problem is to identify a hidden _n_-bit string _x_ by making queries to an oracle _f_. Given \_S\_⊆{1,2,…,_n_} and \_y\_∈{0,1}|_S_|, _f_ returns one if the substring of _x_ specified by _S_ is equal to _y_, and returns zero otherwise. Classically, this problem has query complexity Θ(_n_). As shown in \[[167](https://quantumalgorithmzoo.org/#Ambainis\_Montanaro12)], the quantum query complexity of this problem is Θ(\_n\_−−√). Interestingly, this quadratic speedup is achieved not through amplitude amplification or quantum walks, but rather through use of the so-called Pretty Good Measurement. The paper \[[167](https://quantumalgorithmzoo.org/#Ambainis\_Montanaro12)] also gives a quantum speedup for the related problem of combinatorial group testing. This result and subsequent faster quantum algorithms for group testing are discussed in the entry on Junta Testing and Group Testing.\
\
**Algorithm:** Network flows\
**Speedup:** Polynomial\
**Description:** A network is a directed graph whose edges are labeled with numbers indicating their carrying capacities, and two of whose vertices are designated as the source and the sink. A flow on a network is an assignment of flows to the edges such that no flow exceeds that edge's capacity, and for each vertex other than the source and sink, the total inflow is equal to the total outflow. The network flow problem is, given a network, to find the flow that maximizes the total flow going from source to sink. For a network with _n_ vertices, _m_ edges, and integer capacities of maximum magnitude _U_, \[[168](https://quantumalgorithmzoo.org/#Ambainis\_Spalek05)] gives a quantum algorithm to find the maximal flow in time _O_(min{\_n\_7/6\_m\_−−√ _U\_1/3,nU\_−−−√\_m}×log\_n_). The network flow problem is closely related to the problem of finding a maximal matching of a graph, that is, a maximal-size subset of edges that connects each vertex to at most one other vertex. The paper \[[168](https://quantumalgorithmzoo.org/#Ambainis\_Spalek05)] gives algorithms for finding maximal matchings that run in time _O_(_nm_+_n\_−−−−−√log\_n_) if the graph is bipartite, and _O_(_n\_2(m/n\_−−−−√+log\_n)log\_n_) in the general case. The core of these algorithms is Grover search. The known upper bounds on classical complexity of the network flow and matching problems are complicated to state because different classical algorithms are preferable in different parameter regimes. However, in certain regimes, the above quantum algorithms beat all known classical algorithms. (See \[[168](https://quantumalgorithmzoo.org/#Ambainis\_Spalek05)] for details.)

\
**Algorithm:** Electrical Resistance\
**Speedup:** Exponential\
**Description:** We are given oracle access to a weighted graph of _n_ vertices and maximum degree _d_ whose edge weights are to be interpreted as electrical resistances. Our task is to compute the resistance between a chosen pair of vertices. Wang gave two quantum algorithms in \[[210](https://quantumalgorithmzoo.org/#Wang14)] for this task that run in time poly(log\_n\_,_d_,1/_ϕ_,1/_ϵ_), where _ϕ_ is the expansion of the graph, and the answer is to be given to within a factor of 1+_ϵ_. Known classical algorithms for this problem are polynomial in _n_ rather than log\_n\_. One of Wang's algorithms is based on a novel use of quantum walks. The other is based on the quantum algorithm of \[[104](https://quantumalgorithmzoo.org/#HHL08)] for solving linear systems of equations. The first quantum query complexity upper bounds for the electrical resistance problem in the adjacency query model are given in \[[280](https://quantumalgorithmzoo.org/#IJ15)] using approximate span programs.\
\
**Algorithm:** Junta Testing and Group Testing\
**Speedup:** Polynomial\
**Description:** A function _f_:{0,1}\_n\_→{0,1} is a _k_-junta if it depends on at most _k_ of its input bits. The _k_-junta testing problem is to decide whether a given function is a _k_-junta or is _ϵ_-far from any _k_-junta. Althoug it is not obvious, this problem is closely related to group testing. A group testing problem is defined by a function _f_:{1,2,…,_n_}→{0,1}. One is given oracle access to _F_, which takes as input subsets of {1,2,…,_n_}. _F_(_S_) = 1 if there exists _x\_∈\_S_ such that _f_(_x_) = 1 and _F_(_S_) = 0 otherwise. In \[[266](https://quantumalgorithmzoo.org/#ABRW15)] a quantum algorithm is given solving the _k_-junta problem using \_O\_˜(_k_/\_ϵ\_−−−√) queries and \_O\_˜(_nk_/\_ϵ\_−−−√) time. This is a quadratic speedup over the classical complexity, and improves upon a previous quantum algorithm for _k_-junta testing given in \[[267](https://quantumalgorithmzoo.org/#AS07)]. A polynomial speedup for a gapped (_i.e._ approximation) version of group testing is also given in \[[266](https://quantumalgorithmzoo.org/#ABRW15)], improving upon the earlier results of \[[167](https://quantumalgorithmzoo.org/#Ambainis\_Montanaro12),[268](https://quantumalgorithmzoo.org/#B13)].

***

### Approximation and Simulation Algorithms

**Algorithm:** Quantum Simulation\
**Speedup:** Superpolynomial\
**Description:** It is believed that for any physically realistic Hamiltonian _H_ on _n_ degrees of freedom, the corresponding time evolution operator _e\_−\_iHt_ can be implemented using poly(_n,t_) gates. Unless BPP=BQP, this problem is not solvable in general on a classical computer in polynomial time. Many techniques for quantum simulation have been developed for general classes of Hamiltonians \[[25](https://quantumalgorithmzoo.org/#Childs\_thesis),[95](https://quantumalgorithmzoo.org/#Zalka\_sim),[92](https://quantumalgorithmzoo.org/#Wiesner\_sim),[5](https://quantumalgorithmzoo.org/#Aharonov\_Tashma),[12](https://quantumalgorithmzoo.org/#Cleve\_sim),[170](https://quantumalgorithmzoo.org/#Childs\_Wiebe12),[205](https://quantumalgorithmzoo.org/#BCS13),[211](https://quantumalgorithmzoo.org/#BCCKS14),[244](https://quantumalgorithmzoo.org/#BCCKS14b),[245](https://quantumalgorithmzoo.org/#BCK15),[278](https://quantumalgorithmzoo.org/#Som15),[293](https://quantumalgorithmzoo.org/#Som15),[294](https://quantumalgorithmzoo.org/#LC16),[295](https://quantumalgorithmzoo.org/#BN16),[372](https://quantumalgorithmzoo.org/#BT97),[382](https://quantumalgorithmzoo.org/#LC16b)], chemical dynamics \[[63](https://quantumalgorithmzoo.org/#Kassal\_sim),[68](https://quantumalgorithmzoo.org/#Lidar\_sim),[227](https://quantumalgorithmzoo.org/#HWBT15),[310](https://quantumalgorithmzoo.org/#RWSWT16),[375](https://quantumalgorithmzoo.org/#SW17)], condensed matter physics \[[1](https://quantumalgorithmzoo.org/#Abrams\_sim),[99](https://quantumalgorithmzoo.org/#Wu\_sim), [145](https://quantumalgorithmzoo.org/#Ortiz)], relativistic quantum mechanics (the Dirac and Klein-Gordon equations) \[[367](https://quantumalgorithmzoo.org/#AW16),[369](https://quantumalgorithmzoo.org/#CJO17),[370](https://quantumalgorithmzoo.org/#Yepez11),[371](https://quantumalgorithmzoo.org/Yepez13)], open quantum systems \[[376](https://quantumalgorithmzoo.org/#CW16), [377](https://quantumalgorithmzoo.org/#KBGKE11),[378](https://quantumalgorithmzoo.org/#CL16),[379](https://quantumalgorithmzoo.org/#DPCSC15)], and quantum field theory \[[107](https://quantumalgorithmzoo.org/#Byrnes),[166](https://quantumalgorithmzoo.org/#JLP12),[228](https://quantumalgorithmzoo.org/#JLP14a),[229](https://quantumalgorithmzoo.org/#JLP14b),[230](https://quantumalgorithmzoo.org/#BRSS14),[368](https://quantumalgorithmzoo.org/#MJ17)]. The exponential complexity of classically simulating quantum systems led Feynman to first propose that quantum computers might outperform classical computers on certain tasks \[[40](https://quantumalgorithmzoo.org/#Feynman)]. Although the problem of finding ground energies of local Hamiltonians is QMA-complete and therefore probably requires exponential time on a quantum computer in the worst case, quantum algorithms have been developed to approximate ground \[[102](https://quantumalgorithmzoo.org/#Aspuru\_science),[231](https://quantumalgorithmzoo.org/#WKAH08),[232](https://quantumalgorithmzoo.org/#KA09),[233](https://quantumalgorithmzoo.org/#WBA11),[234](https://quantumalgorithmzoo.org/#TL13),[235](https://quantumalgorithmzoo.org/#W13),[308](https://quantumalgorithmzoo.org/#FKT16),[321](https://quantumalgorithmzoo.org/#SA15),[322](https://quantumalgorithmzoo.org/#SCV13),[380](https://quantumalgorithmzoo.org/#BBK17),[381](https://quantumalgorithmzoo.org/#PKS17)] as well as thermal states \[[132](https://quantumalgorithmzoo.org/#Metropolis),[121](https://quantumalgorithmzoo.org/#Poulin\_Wocjan),[281](https://quantumalgorithmzoo.org/#RGE12),[282](https://quantumalgorithmzoo.org/#KB16),[307](https://quantumalgorithmzoo.org/#CS16)] for some classes of Hamiltonians and equilibrium states for some classes of master equations \[[430](https://quantumalgorithmzoo.org/#RS20)]. Efficient quantum algorithms have been also obtained for preparing certain classes of tensor network states \[[323](https://quantumalgorithmzoo.org/#SSVCW05),[324](https://quantumalgorithmzoo.org/#SHWCS07),[325](https://quantumalgorithmzoo.org/#GMC16),[326](https://quantumalgorithmzoo.org/#STV12),[327](https://quantumalgorithmzoo.org/#SCTVP13),[328](https://quantumalgorithmzoo.org/#SBE16)].\
\
**Algorithm:** Knot Invariants\
**Speedup:** Superpolynomial\
**Description:** As shown by Freedman \[[42](https://quantumalgorithmzoo.org/#Freedman), [41](https://quantumalgorithmzoo.org/#Freedman2)], _et al._, finding a certain additive approximation to the Jones polynomial of the plat closure of a braid at _ei\_2\_π_/5 is a BQP-complete problem. This result was reformulated and extended to _ei\_2\_π_/_k_ for arbitrary _k_ by Aharonov _et al._ \[[4](https://quantumalgorithmzoo.org/#Aharonov1),[2](https://quantumalgorithmzoo.org/#Aharonov2)]. Wocjan and Yard further generalized this, obtaining a quantum algorithm to estimate the HOMFLY polynomial \[[93](https://quantumalgorithmzoo.org/#Wocjan)], of which the Jones polynomial is a special case. Aharonov _et al._ subsequently showed that quantum computers can in polynomial time estimate a certain additive approximation to the even more general Tutte polynomial for planar graphs \[[3](https://quantumalgorithmzoo.org/#Aharonov3)]. It is not fully understood for what range of parameters the approximation obtained in \[[3](https://quantumalgorithmzoo.org/#Aharonov3)] is BQP-hard. (See also [partition functions](https://quantumalgorithmzoo.org/#part\_func).) Polynomial-time quantum algorithms have also been discovered for additively approximating link invariants arising from quantum doubles of finite groups \[[174](https://quantumalgorithmzoo.org/#Krovi\_Russell12)]. (This problem is not known to be BQP-hard.) As shown in \[[83](https://quantumalgorithmzoo.org/#Shor\_Jordan)], the problem of finding a certain additive approximation to the Jones polynomial of the _trace_ closure of a braid at _ei\_2\_π_/5 is DQC1-complete.\
\
**Algorithm:** Three-manifold Invariants\
**Speedup:** Superpolynomial\
**Description:** The Turaev-Viro invariant is a function that takes three-dimensional manifolds as input and produces a real number as output. Homeomorphic manifolds yield the same number. Given a three-manifold specified by a Heegaard splitting, a quantum computer can efficiently find a certain additive approximation to its Turaev-Viro invariant, and this approximation is BQP-complete \[[129](https://quantumalgorithmzoo.org/#AJKR)]. Earlier, in \[[114](https://quantumalgorithmzoo.org/#Garnerone)], a polynomial-time quantum algorithm was given to additively approximate the Witten-Reshitikhin-Turaev (WRT) invariant of a manifold given by a surgery presentation. Squaring the WRT invariant yields the Turaev-Viro invariant. However, it is unknown whether the approximation achieved in \[[114](https://quantumalgorithmzoo.org/#Garnerone)] is BQP-complete. A suggestion of a possible link between quantum computation and three-manifold invariants was also given in \[[115](https://quantumalgorithmzoo.org/#Kauffman)].\
\
**Algorithm:** Partition Functions\
**Speedup:** Superpolynomial\
**Description:** For a classical system with a finite set of states _S_ the partition function is _Z_=∑\_s\_∈\_Se\_−\_E\_(_s_)/_kT_, where _T_ is the temperature and _k_ is Boltzmann's constant. Essentially every thermodynamic quantity can be calculated by taking an appropriate partial derivative of the partition function. The partition function of the Potts model is a special case of the Tutte polynomial. A quantum algorithm for approximating the Tutte polynomial is given in \[[3](https://quantumalgorithmzoo.org/#Aharonov3)]. Some connections between these approaches are discussed in \[[67](https://quantumalgorithmzoo.org/#Lidar\_Ising)]. Additional algorithms for estimating partition functions on quantum computers are given in \[[112](https://quantumalgorithmzoo.org/#Arad\_Landau),[113](https://quantumalgorithmzoo.org/#VdN),[45](https://quantumalgorithmzoo.org/#Geraci\_QWGT1),[47](https://quantumalgorithmzoo.org/#Geraci\_exact)]. A BQP-completeness result (where the "energies" are allowed to be complex) is also given in \[[113](https://quantumalgorithmzoo.org/#VdN)]. A method for approximating partition functions by simulating thermalization processes is given in \[[121](https://quantumalgorithmzoo.org/#Poulin\_Wocjan)]. A quadratic speedup for the approximation of general partition functions is given in \[[122](https://quantumalgorithmzoo.org/#WCAN)]. A method based on quantum walks, achieving polynomial speedup for evaluating partition functions is given in \[[265](https://quantumalgorithmzoo.org/#M15b)].\
\
**Algorithm:** Quantum Approximate Optimization\
**Speedup:** Superpolynomial\
**Description:** For many combinatorial optimization problems, finding the exact optimal solution is NP-complete. There are also hardness-of-approximation results proving that finding an approximation with sufficiently small error bound is NP-complete. For certain problems there is a gap between the best error bound achieved by a polynomial-time classical approximation algorithm and the error bound proven to be NP-hard. In this regime there is potential for exponential speedup by quantum computation. In \[[242](https://quantumalgorithmzoo.org/#FGG14a)] a new quantum algorithmic technique called the Quantum Approximate Optimization Algorithm (QAOA) was proposed for finding approximate solutions to combinatorial optimization problems. In \[[243](https://quantumalgorithmzoo.org/#FGG14b)] it was subsequently shown that QAOA solves a combinatorial optimization problem called Max E3LIN2 with a better approximation ratio than any polynomial-time classical algorithm known at the time. However, an efficient classical algorithm achieving an even better approximation ratio (in fact, the approximation ratio saturating the limit set by hardness-of-approximation) was subsequently discovered \[[260](https://quantumalgorithmzoo.org/#BMO15)]. Presently, the power of QAOA relative to classical computing is an active area of research \[[300](https://quantumalgorithmzoo.org/#LZ16), [301](https://quantumalgorithmzoo.org/#WHT16), [302](https://quantumalgorithmzoo.org/#FH16), [314](https://quantumalgorithmzoo.org/#Chamon)].\
\
**Algorithm:** Semidefinite Programming\
**Speedup:** Polynomial (with some exceptions)\
**Description:** Given a list of _m_ + 1 Hermitian _n\_×\_n_ matrices _C_,_A\_1,A\_2,…,Am and m numbers b\_1,…,bm, the problem of semidefinite programming is to find the positive semidefinite n\_×\_n matrix X that maximizes tr(CX) subject to the constraints tr(AjX)≤\_bj for j=1,2,…,m. Semidefinite programming has many applications in operations research, combinatorial optimization, and quantum information, and it includes linear programming as a special case. Introduced in \[_[_313_](https://quantumalgorithmzoo.org/#BS16)_], and subsequently improved in \[_[_383_](https://quantumalgorithmzoo.org/#BKL17)_,_ [_425_](https://quantumalgorithmzoo.org/#AGG20)_], quantum algorithms are now known that can approximately solve semidefinite programs to within ±\_ϵ in time O(m\_−−√log\_m\_⋅poly(log\_n,r,ϵ\_−1)), where r is the rank of the semidefinite program. This constitutes a quadratic speedup over the fastest classical algorithms when r is small compared to n. The quantum algorithm is based on amplitude amplification and quantum Gibbs sampling \[_[_121_](https://quantumalgorithmzoo.org/#Poulin\_Wocjan)_,_ [_307_](https://quantumalgorithmzoo.org/#CS16)_]. In a model in which input is provided in the form of quantum states the quantum algorithm for semidefinite programming can achieve superpolynomial speedup, as discussed in \[_[_383_](https://quantumalgorithmzoo.org/#BKL17)_], although recent dequantization results \[_[_421_](https://quantumalgorithmzoo.org/#CGL20)_] delineate limitations on the context in which superpolynomial quantum speedup for semidefinite programs is possible._\
\
_**Algorithm:** Zeta Functions_\
_**Speedup:** Superpolynomial_\
_**Description:** Let f(x,y) be a degree-d polynomial over a finite field F\_p. Let Nr be the number of projective solutions to f(x,y = 0 over the extension field F\_pr_. The zeta function for _f_ is defined to be _Zf_(_T_)=exp(∑∞\_r\_=1\_NrrTr\_). Remarkably, _Zf_(_T_) always has the form _Zf_(_T_)=_Qf_(_T_)(1−\_pT\_)(1−\_T\_) where _Qf_(_T_) is a polynomial of degree 2\_g\_ and _g_=12(_d\_−1)(d\_−2) is called the genus of f. Given Zf(T) one can easily compute the number of zeros of f over any extension field F\_pr. One can similarly define the zeta function when the original field over which f is defined does not have prime order. As shown by Kedlaya \[_[_64_](https://quantumalgorithmzoo.org/#Kedlaya)_], quantum computers can determine the zeta function of a genus g curve over a finite field F\_pr_ in poly(log\_p\_,_r_,_g_) time. The fastest known classical algorithms are all exponential in either log(_p_) or _g_. In a diffent, but somewhat related contex, van Dam has conjectured that due to a connection between the zeros of _Riemann_ zeta functions and the eigenvalues of certain quantum operators, quantum computers might be able to efficiently approximate the number of solutions to equations over finite fields \[[87](https://quantumalgorithmzoo.org/#vanDam\_zeros)].\
\
\\

\
**Algorithm:** Weight Enumerators\
**Speedup:** Superpolynomial\
**Description:** Let _C_ be a code on _n_ bits, _i.e._ a subset of Z\_n\_2. The weight enumerator of _C_ is _SC_(_x_,_y_)=∑\_c\_∈\_Cx\_|_c_|_yn\_−|c| where |c| denotes the Hamming weight of c. Weight enumerators have many uses in the study of classical codes. If C is a linear code, it can be defined by C={c:Ac=0} where A is a matrix over Z2 In this case SC(x,y)=∑\_c_:_Ac_=0\_x\_|_c_|_yn\_−|c|. Quadratically signed weight enumerators (QWGTs) are a generalization of this: S(A,B,x,y)=∑\_c_:_Ac_=0(−1)_cTBcx_|_c_|\_yn\_−|_c_|. Now consider the following special case. Let _A_ be an _n\_×\_n_ matrix over Z2 such that diag(_A_)=I. Let lwtr(_A_) be the lower triangular matrix resulting from setting all entries above the diagonal in _A_ to zero. Let _l,k_ be positive integers. Given the promise that |_S_(_A_,lwtr(_A_),_k_,_l_)|≥12(\_k\_2+\_l\_2)_n_/2 the problem of determining the sign of _S_(_A_,lwtr(_A_),_k_,_l_) is BQP-complete, as shown by Knill and Laflamme in \[[65](https://quantumalgorithmzoo.org/#Knill\_QWGT)]. The evaluation of QWGTs is also closely related to the evaluation of Ising and Potts model partition functions \[[67](https://quantumalgorithmzoo.org/#Lidar\_Ising),[45](https://quantumalgorithmzoo.org/#Geraci\_QWGT1),[46](https://quantumalgorithmzoo.org/#Geraci\_QWGT2)].\
\
**Algorithm:** Simulated Annealing\
**Speedup:** Polynomial\
**Description:** In simulated annealing, one has a series of Markov chains defined by stochastic matrices \_M\_1,\_M\_2,…,_Mn_. These are slowly varying in the sense that their limiting distributions \_pi\_1,_π\_2,…,πn satisfy |πt+1−\_πt_|<_ϵ_ for some small _ϵ_. These distributions can often be thought of as thermal distributions at successively lower temperatures. If _π\_1 can be easily prepared, then by applying this series of Markov chains one can sample from πn. Typically, one wishes for πn to be a distribution over good solutions to some optimization problem. Let δi be the gap between the largest and second largest eigenvalues of Mi. Let δ=min\_iδi_. The run time of this classical algorithm is proportional to 1/_δ_. Building upon results of Szegedy \[[135](https://quantumalgorithmzoo.org/#Szegedy\_arxiv),[85](https://quantumalgorithmzoo.org/#Szegedy)], Somma _et al._ have shown \[[84](https://quantumalgorithmzoo.org/#Somma), [177](https://quantumalgorithmzoo.org/#SBBK08)] that quantum computers can sample from _πn_ with a runtime proportional to 1/\_δ\_√. Additional methods by which classical Markov chain Monte Carlo algorithms can be sped up using quantum walks are given in \[[265](https://quantumalgorithmzoo.org/#M15b)].\
\
**Algorithm:** String Rewriting\
**Speedup:** Superpolynomial\
**Description:** String rewriting is a fairly general model of computation. String rewriting systems (sometimes called grammars) are specified by a list of rules by which certain substrings are allowed to be replaced by certain other substrings. For example, context free grammars, are equivalent to the pushdown automata. In \[[59](https://quantumalgorithmzoo.org/#Wocjan\_strings)], Janzing and Wocjan showed that a certain string rewriting problem is PromiseBQP-complete. Thus quantum computers can solve it in polynomial time, but classical computers probably cannot. Given three strings _s,t,t'_, and a set of string rewriting rules satisfying certain promises, the problem is to find a certain approximation to the difference between the number of ways of obtaining _t_ from _s_ and the number of ways of obtaining _t'_ from _s_. Similarly, certain problems of approximating the difference in number of paths between pairs of vertices in a graph, and difference in transition probabilities between pairs of states in a random walk are also BQP-complete \[[58](https://quantumalgorithmzoo.org/#Wocjan\_walks)].\
\
**Algorithm:** Matrix Powers\
**Speedup:** Superpolynomial\
**Description:** Quantum computers have an exponential advantage in approximating matrix elements of powers of exponentially large sparse matrices. Suppose we are have an _N\_×\_N_ symmetric matrix _A_ such that there are at most polylog(_N_) nonzero entries in each row, and given a row index, the set of nonzero entries can be efficiently computed. The task is, for any 1 < _i_ < _N_, and any _m_ polylogarithmic in _N_, to approximate (_Am_)_ii_ the \_i\_th diagonal matrix element of _Am_. The approximation is additive to within _bmϵ_ where _b_ is a given upper bound on |_A_| and _ϵ_ is of order 1/polylog(_N_). As shown by Janzing and Wocjan, this problem is PromiseBQP-complete, as is the corresponding problem for off-diagonal matrix elements \[[60](https://quantumalgorithmzoo.org/#Wocjan\_matrix)]. Thus, quantum computers can solve it in polynomial time, but classical computers probably cannot.

***

### Optimization, Numerics, and Machine Learning

**Algorithm:** Constraint Satisfaction\
**Speedup:** Polynomial\
**Description:** Constraint satisfaction problems, many of which are NP-hard, are ubiquitous in computer science, a canonical example being 3-SAT. If one wishes to satisfy as many constraints as possible rather than all of them, these become combinatorial optimization problems. (See also [adiabatic algorithms](https://quantumalgorithmzoo.org/#adiabiatic).) The brute force solution to constraint satisfaction problems can be quadratically sped up using Grover's algorithm. However, most constraint satisfaction problems are solvable by classical algorithms that (although still exponential-time) run more than quadratically faster than brute force checking of all possible solutions. Nevertheless, a polynomial quantum speedup over the fastest known classical algorithm for 3-SAT is given in \[[133](https://quantumalgorithmzoo.org/#Ambainis\_SIGACT)], and polynomial quantum speedups for some other constraint satisfaction problems are given in \[[134](https://quantumalgorithmzoo.org/#CGF), [298](https://quantumalgorithmzoo.org/#MGAG15)]. In \[[423](https://quantumalgorithmzoo.org/#BKF19)] a quadratic quantum speedup for approximate solutions to homogeneous QUBO/Ising problems is obtained by building upon the quantum algorithm for semidefinite programming. A commonly used classical algorithm for constraint satisfaction is backtracking, and for some problems this algorithm is the fastest known. A general quantum speedup for backtracking algorithms is given in \[[264](https://quantumalgorithmzoo.org/#M15a)] and further improved in \[[422](https://quantumalgorithmzoo.org/#AK17)].\
\
**Algorithm:** Adiabatic Algorithms\
**Speedup:** Unknown\
**Description:** In adiabatic quantum computation one starts with an initial Hamiltonian whose ground state is easy to prepare, and slowly varies the Hamiltonian to one whose ground state encodes the solution to some computational problem. By the adiabatic theorem, the system will track the instantaneous ground state provided the variation of the Hamiltonian is sufficiently slow. The runtime of an adiabatic algorithm scales at worst as 1/\_γ\_3 where _γ_ is the minimum eigenvalue gap between the ground state and the first excited state \[[185](https://quantumalgorithmzoo.org/#JRS06)]. If the Hamiltonian is varied sufficiently smoothly, one can improve this to \_O\_˜(1/_γ\_2) \[_[_247_](https://quantumalgorithmzoo.org/#EH12)_]. Adiabatic quantum computation was first proposed by Farhi et al. as a method for solving NP-complete combinatorial optimization problems \[_[_96_](https://quantumalgorithmzoo.org/#Farhi\_adiabatic)_,_ [_186_](https://quantumalgorithmzoo.org/#FGGLLP01)_]. Adiabatic quantum algorithms for optimization problems typically use "stoquastic" Hamiltonians, which do not suffer from the sign problem. Such algorithms are sometimes referred to as quantum annealing. Adiabatic quantum computation with non-stoquastic Hamiltonians is as powerful as the quantum circuit model \[_[_97_](https://quantumalgorithmzoo.org/#Aharonov\_adiabatic)_]. Adiabatic algorithms using stoquastic Hamiltonians are probably less powerful \[_[_183_](https://quantumalgorithmzoo.org/#BDOT06)_], but are likely more powerful than classical computation \[_[_429_](https://quantumalgorithmzoo.org/#H20a)_]. The asymptotic runtime of adiabatic optimization algorithms is notoriously difficult to analyze, but some progress has been achieved \[_[_179_](https://quantumalgorithmzoo.org/#AKR09)_,_[_180_](https://quantumalgorithmzoo.org/#R04)_,_[_181_](https://quantumalgorithmzoo.org/#FGG02)_,_[_182_](https://quantumalgorithmzoo.org/#FGGGMS09)_,_[_187_](https://quantumalgorithmzoo.org/#FGGN05)_,_[_188_](https://quantumalgorithmzoo.org/#FGGS10)_,_[_189_](https://quantumalgorithmzoo.org/#FGG02B)_,_[_190_](https://quantumalgorithmzoo.org/#vDMV01)_,_[_191_](https://quantumalgorithmzoo.org/#FGHSSYZ12)_,_[_226_](https://quantumalgorithmzoo.org/#IM08)_]. (Also relevant is an earlier literature on quantum annealing, which originally referred to a classical optimization algorithm that works by simulating a quantum process, much as simulated annealing is a classical optimization algorithm that works by simulating a thermal process. See e.g. \[_[_199_](https://quantumalgorithmzoo.org/#FGSSD94)_,_ [_198_](https://quantumalgorithmzoo.org/#MN08)_].) Adiabatic quantum computers can perform a process somewhat analogous to Grover search in O(N\_−−√) time \[_[_98_](https://quantumalgorithmzoo.org/#Roland\_Cerf)_]. Adiabatic quantum algorithms achieving quadratic speedup for a more general class of problems are constructed in \[_[_184_](https://quantumalgorithmzoo.org/#SB12)_] by adapting techniques from \[_[_85_](https://quantumalgorithmzoo.org/#Szegedy)_]. Adiabatic quantum algorithms have been proposed for several specific problems, including PageRank \[_[_176_](https://quantumalgorithmzoo.org/#GZL12)_], machine learning \[_[_192_](https://quantumalgorithmzoo.org/#PL12)_,_ [_195_](https://quantumalgorithmzoo.org/#NDRM08)_], finding Hadamard matrices \[_[_406_](https://quantumalgorithmzoo.org/#SM19)_], and graph problems \[_[_193_](https://quantumalgorithmzoo.org/#GC11)_,_ [_194_](https://quantumalgorithmzoo.org/#GC13)_]. Some quantum simulation algorithms also use adiabatic state preparation._\
\
_**Algorithm:** Gradients, Structured Search, and Learning Polynomials_\
_**Speedup:** Polynomial_\
_**Description:** Suppose we are given a oracle for computing some smooth function f:R\_d\_→R. The inputs and outputs to f are given to the oracle with finitely many bits of precision. The task is to estimate ∇\_f at some specified point **x**0∈R\_d_. As shown in \[[61](https://quantumalgorithmzoo.org/#Jordan\_gradient)], a quantum computer can achieve this using one query, whereas a classical computer needs at least _d+1_ queries. In \[[20](https://quantumalgorithmzoo.org/#Bulger)], Bulger suggested potential applications for optimization problems. As shown in appendix D of \[[62](https://quantumalgorithmzoo.org/#mythesis)], a quantum computer can use the gradient algorithm to find the minimum of a quadratic form in _d_ dimensions using _O(d)_ queries, whereas, as shown in \[[94](https://quantumalgorithmzoo.org/#Yao)], a classical computer needs at least Ω(\_d\_2) queries. Single query quantum algorithms for finding the minima of basins based on Hamming distance were given in \[[147](https://quantumalgorithmzoo.org/#Hogg),[148](https://quantumalgorithmzoo.org/#Hunziker\_Meyer),[223](https://quantumalgorithmzoo.org/#MP09)]. The quantum algorithm of \[[62](https://quantumalgorithmzoo.org/#mythesis)] can also extract all \_d\_2 matrix elements of the quadratic form using _O(d)_ queries, and more generally, all _dn_ \_n\_th derivatives of a smooth function of _d_ variables in _O_(\_dn\_−1) queries. Remarkably general results in \[[418](https://quantumalgorithmzoo.org/#CML18),[419](https://quantumalgorithmzoo.org/#CMH19),[420](https://quantumalgorithmzoo.org/#AGG18)] give quantum speedups for convex optimization and volume estimation of convex bodies, as well as query complexity lower bounds. Roughly speaking these results show that for convex optimization and volume estimation in _d_ dimensions one gets a quadratic speedup in _d_ just as was found earlier for the special case of minimizing quadratic forms. As shown in \[[130](https://quantumalgorithmzoo.org/#Roetteler\_quad),[146](https://quantumalgorithmzoo.org/#Montanaro\_polynomials)], quadratic forms and multilinear polynomials in _d_ variables over a finite field may be extracted with a factor of _d_ fewer quantum queries than are required classically.\
\
\\

\
**Algorithm:** Linear Systems\
**Speedup:** Superpolynomial\
**Description:** We are given oracle access to an _n\_×\_n_ matrix _A_ and some description of a vector _b_. We wish to find some property of _f(A)b_ for some efficiently computable function _f_. Suppose _A_ is a Hermitian matrix with _O_(polylog _n_) nonzero entries in each row and condition number _k_. As shown in \[[104](https://quantumalgorithmzoo.org/#HHL08)], a quantum computer can in _O_(_k\_2log\_n_) time compute to polynomial precision various expectation values of operators with respect to the vector _f(A)b_ (provided that a quantum state proportional to _b_ is efficiently constructable). For certain functions, such as _f(x)=1/x_, this procedure can be extended to non-Hermitian and even non-square _A_. The runtime of this algorithm was subsequently improved to _O_(_k\_log3\_k\_log\_n_) in \[[138](https://quantumalgorithmzoo.org/#Ambainis\_linear)]. Exponentially improved scaling of runtime with precision was obtained in \[[263](https://quantumalgorithmzoo.org/#CKS15)]. Some methods to extend this algorithm to apply to non-sparse matrices have been proposed \[[309](https://quantumalgorithmzoo.org/#KP16),[402](https://quantumalgorithmzoo.org/#WZP17)], although these require certain partial sums of the matrix elements to be pre-computed. Extensions of this quantum algorithm have been applied to problems of estimating electromagnetic scattering crossections \[[249](https://quantumalgorithmzoo.org/#CJS13)] (see also \[[369](https://quantumalgorithmzoo.org/#CJO17)] for a different approach), solving linear differential equations \[[156](https://quantumalgorithmzoo.org/#Berry10), [296](https://quantumalgorithmzoo.org/#MP16)], estimating electrical resistance of networks \[[210](https://quantumalgorithmzoo.org/#Wang14)], least-squares curve-fitting \[[169](https://quantumalgorithmzoo.org/#Wiebe\_Braun\_Lloyd12)], solving Toeplitz systems \[[297](https://quantumalgorithmzoo.org/#WYPGW16)], and machine learning \[[214](https://quantumalgorithmzoo.org/#LMR13),[222](https://quantumalgorithmzoo.org/#LGZ14),[250](https://quantumalgorithmzoo.org/#LMR13b),[251](https://quantumalgorithmzoo.org/#RML13),[309](https://quantumalgorithmzoo.org/#KP16)]. However, the linear-systems-based quantum algorithms for recommendation systems \[[309](https://quantumalgorithmzoo.org/#KP16)] and principal component analysis \[[250](https://quantumalgorithmzoo.org/#LMR13b)] were subsequently "dequantized" by Tang \[[400](https://quantumalgorithmzoo.org/#Tang18a), [401](https://quantumalgorithmzoo.org/#Tang18b)]. That is, Tang obtained polynomial time classical randomized algorithms for these problems, thus proving that the proposed quantum algorithms for these tasks do not achieve exponential speedup. Some limitations of the quantum machine learning algorithms based on linear systems are nicely summarized in \[[246](https://quantumalgorithmzoo.org/#Aa15)]. In \[[220](https://quantumalgorithmzoo.org/#Ta-Shma13)] it was shown that quantum computers can invert well-conditioned _n\_×\_n_ matrices using only _O_(log\_n\_) qubits, whereas the best classical algorithm uses order log2\_n\_ bits. Subsequent improvements to this quantum algorithm are given in \[[279](https://quantumalgorithmzoo.org/#FL16)].\
\
**Algorithm:** Machine Learning\
**Speedup:** Varies\
**Description:** Maching learning encompasses a wide variety of computational problems and can be attacked by a wide variety of algorithmic techniques. This entry summarizes quantum algorithmic techniques for improved machine learning. Many of the quantum algorithms here are cross-listed under other headings. In \[[214](https://quantumalgorithmzoo.org/#LMR13),[222](https://quantumalgorithmzoo.org/#LGZ14),[250](https://quantumalgorithmzoo.org/#LMR13b),[251](https://quantumalgorithmzoo.org/#RML13),[309](https://quantumalgorithmzoo.org/#KP16),[338](https://quantumalgorithmzoo.org/#SSP16),[339](https://quantumalgorithmzoo.org/#ZFF15),[359](https://quantumalgorithmzoo.org/#KP17),[403](https://quantumalgorithmzoo.org/#ZPK19)], quantum algorithms for solving linear systems \[[104](https://quantumalgorithmzoo.org/#HHL08)] are applied to speed up cluster-finding, principal component analysis, binary classification, training of neural networks, and various forms of regression, provided the data satisfies certain conditions. However, a number of quantum machine learning algorithms based on linear systems have subsequently been "dequantized". Specifically, Tang showed in \[[400](https://quantumalgorithmzoo.org/#Tang18a), [401](https://quantumalgorithmzoo.org/#Tang18b)] that the problems of recommendation systems and principal component analysis solved by the quantum algorithms of \[[251](https://quantumalgorithmzoo.org/#RML13),[309](https://quantumalgorithmzoo.org/#KP16)] can in fact also be solved in polynomial time randomized classical algorithms. A cluster-finding method not based on the linear systems algorithm of \[[104](https://quantumalgorithmzoo.org/#HHL08)] is given in \[[336](https://quantumalgorithmzoo.org/#WKS15)]. The papers \[[192](https://quantumalgorithmzoo.org/#PL12),[195](https://quantumalgorithmzoo.org/#NDRM08),[344](https://quantumalgorithmzoo.org/#CLGOR16),[345](https://quantumalgorithmzoo.org/#AH15),[346](https://quantumalgorithmzoo.org/#BRRP16),[348](https://quantumalgorithmzoo.org/#AARBM16)] explore the use of adiabatic optimization techniques to speed up the training of classifiers. In \[[221](https://quantumalgorithmzoo.org/#WKS14)], a method is proposed for training Boltzmann machines by manipulating coherent quantum states with amplitudes proportional to the Boltzmann weights. Polynomial speedups can be obtained by applying Grover search and related techniques such as amplitude amplification to amenable subroutines of state of the art classical machine learning algorithms. See, for example \[[358](https://quantumalgorithmzoo.org/#ABG07),[340](https://quantumalgorithmzoo.org/#ABG13),[341](https://quantumalgorithmzoo.org/#WKS16),[342](https://quantumalgorithmzoo.org/#PDMMB14),[343](https://quantumalgorithmzoo.org/#DCLT08)]. Other quantum machine learning algorithms not falling into one of the above categories include \[[337](https://quantumalgorithmzoo.org/#YBLL14),[349](https://quantumalgorithmzoo.org/#WG17)]. Some limitations of quantum machine learning algorithms are nicely summarized in \[[246](https://quantumalgorithmzoo.org/#Aa15)]. Many other quantum query algorithms that extract hidden structure of the black-box function could be cast as machine learning algorithms. See for example \[[146](https://quantumalgorithmzoo.org/#Montanaro\_polynomials),[23](https://quantumalgorithmzoo.org/#Childs\_nonlinear),[11](https://quantumalgorithmzoo.org/#Bernstein\_Vazirani),[31](https://quantumalgorithmzoo.org/#Wocjan\_nonlinear),[212](https://quantumalgorithmzoo.org/#DHIS13)]. Query algorithms for learning the majority and "battleship" functions are given in \[[224](https://quantumalgorithmzoo.org/#HMPPR03)]. Large quantum advantages for learning from noisy oracles are given in \[[236](https://quantumalgorithmzoo.org/#CSS14),[237](https://quantumalgorithmzoo.org/#HR11)]. In \[[428](https://quantumalgorithmzoo.org/#LAT20)] quantum kernel estimation is used to implement a support-vector classifier solving a learning problem that is provably as hard as discrete logarithm. Several recent review articles \[[299](https://quantumalgorithmzoo.org/#Ad15),[332](https://quantumalgorithmzoo.org/#SSP14),[333](https://quantumalgorithmzoo.org/#BWPRWL16)] and a book \[[331](https://quantumalgorithmzoo.org/#QMLbook)] are available which summarize the state of the field. There is a related body of work, not strictly within the standard setting of quantum algorithms, regarding quantum learning in the case that the data itself is quantum coherent. See _e.g._ \[[350](https://quantumalgorithmzoo.org/#BJ99),[334](https://quantumalgorithmzoo.org/#ABG06),[335](https://quantumalgorithmzoo.org/#DTB16),[351](https://quantumalgorithmzoo.org/#AW17),[352](https://quantumalgorithmzoo.org/#SG04),[353](https://quantumalgorithmzoo.org/#AW16),[354](https://quantumalgorithmzoo.org/#MSW16),[355](https://quantumalgorithmzoo.org/#BCDFP10),[356](https://quantumalgorithmzoo.org/#SCJ01),[357](https://quantumalgorithmzoo.org/#SC02)].\
\
**Algorithm:** Tensor Principal Component Analysis\
**Speedup:** Polynomial (quartic)\
**Description:** In \[[424](https://quantumalgorithmzoo.org/#H19)] a quantum algorithm is given for an idealized problem motivated by machine learning applications on high-dimensional data sets. Consider _T_=\_λv\_⊗\_p\_sig+_G_ where _G_ is a _p_-index tensor of Gaussian random variables, symmetrized over all permutations of indices, and \_v\_sig is an _N_-dimensional vector of magnitude \_N\_−−√. The task is to recover \_v\_sig. Consider _λ_=_αN\_−\_p_/4. The best classical algorithms succeed when \_α\_≫1 and have time and space complexity that scale exponentially in \_α\_−1. The quantum algorithm of \[[424](https://quantumalgorithmzoo.org/#H19)] solves this problem in polynomial space and with runtime scaling quartically better in _α\_−1 than the classical spectral algorithm. The quantum algorithm works by encoding the problem into the eigenspectrum of a many-body Hamiltonian and applying phase estimation together with amplitude amplification._\
\
_**Algorithm:** Solving Differential Equations_\
_**Speedup:** Superpolynomial_\
_**Description:** Consider linear first order differential equation ddt**x**=A(t)**x**+**b**(t), where **x** and **b** are N-dimensional vectors and A is an N\_×\_N matrix. Given an initial condition **x**(0) one wishes to compute the solution **x**(t) at some later time t to some precision ϵ in the sense that the normalized vector x(t)/∥\_x_(_t_)∥ produced has distance at most _ϵ_ from the exact solution. In \[[156](https://quantumalgorithmzoo.org/#Berry10)], Berry gives a quantum algorithm for this problem that runs in time _O_(_t\_2poly(1/ϵ)polylog\_N_), whereas the fastest classical algorithms run in time _O_(_t\_poly\_N_). The final result is produced in the form of a quantum superposition state on _O_(_logN_) qubits whose amplitudes contain the components of **x**(_t_). The algorithm works by reducing the problem to linear algebra via a high-order finite difference method and applying the quantum linear algebra primitive of \[[104](https://quantumalgorithmzoo.org/#HHL08)]. In \[[410](https://quantumalgorithmzoo.org/#BCOW17)] an improved quantum algorithm for this problem was given which brings the epsilon dependence down to polylog(1/_ϵ_). A quantum algorithm for solving nonlinear differential equations (again in the sense of obtaining a solution encoded in the amplitudes) is described in \[[411](https://quantumalgorithmzoo.org/#LO08)], which has exponential scaling in _t_. In \[[426](https://quantumalgorithmzoo.org/#LKK20),[427](https://quantumalgorithmzoo.org/#LDP20)] quantum algorithms are given for solving nonlinear differential equations that scale as _O_(\_t\_2). These are applicable to a restricted class of nonlinear differential equations. In particular, their solutions must not grow or shrink in magnitude too rapidly. Partial differential equations can be reduced to ordinary differential equations through discretization, and higher order differential equations can be reduced to first order through additiona of auxiliary variables. Consequently, these more general problems can be solved through the methods of \[[156](https://quantumalgorithmzoo.org/#Berry10), [104](https://quantumalgorithmzoo.org/#HHL08)]. However, quantum algorithms designed to solve these problems directly may be more efficient (and for specific problems one may analyze the complexity of tasks that are unspecified in a more general formulation such as preparation of relevant initial states). In \[[249](https://quantumalgorithmzoo.org/#CJS13)] a quantum algorithm is given which solves the wave equation by applying finite-element methods to reduce it to linear algebra and then applying the quantum linear algebra algorithm of \[[104](https://quantumalgorithmzoo.org/#HHL08)] with preconditioning. In \[[369](https://quantumalgorithmzoo.org/#CJO17)] a quantum algorithm is given for solving the wave equation by discretizing it with finite differences and massaging it into the form of a Schrodinger equation which is then simulated using the method of \[[245](https://quantumalgorithmzoo.org/#BCK15)]. The problem solved by \[[369](https://quantumalgorithmzoo.org/#CJO17)] is not equivalent to that solved by \[[249](https://quantumalgorithmzoo.org/#CJS13)] because in \[[249](https://quantumalgorithmzoo.org/#CJS13)] the problem is reduced to a time-indepent one through assuming sinusoidal time dependence and applying separation of variables, whereas \[[369](https://quantumalgorithmzoo.org/#CJO17)] solves the time-dependent problem. The quantum speedup achieved over classical methods for solving the wave equation in _d_-dimensiona is polynomial for fixed _d_ but expontial in _d_. Concrete resource estimates for quantum algorithms to solve differential equations are given in \[[412](https://quantumalgorithmzoo.org/#CPP13), [413](https://quantumalgorithmzoo.org/#WWL19), [414](https://quantumalgorithmzoo.org/#SVM17)]. A quantum algorithm for solving linear partial differential equations using continuous-variable quantum computing is given in \[[415](https://quantumalgorithmzoo.org/#AKW19)]. In \[[296](https://quantumalgorithmzoo.org/#MP16)] quantum finite element methods are analyzed in a general setting. A quantum spectral method for solving differential equations is given in \[[416](https://quantumalgorithmzoo.org/#CL19)]. A quantum algorithm for solving the Vlasov equation is given in \[[417](https://quantumalgorithmzoo.org/#ESP19)].\
\
**Algorithm:** Quantum Dynamic Programming\
**Speedup:** Polynomial\
**Description:** In \[[409](https://quantumalgorithmzoo.org/#ABI18)] the authors introduce a problem called path-in-the-hypercube. In this problem, one given a subgraph of the hypercube and asked whether there is a path along this subgraph that starts from the all zeros vertex, ends at the all ones vertex, and makes only Hamming weight increasing moves. (The vertices of the hypercube graph correspond to bit strings of length _n_ and the hypercube graph joins vertices of Hamming distance one.) Many NP-complete problems for which the best classical algorithm is dynamic programming can be modeled as instances of path-in-the-hypercube. By combining Grover search with dynamic programming methods, a quantum algorithm can solve path-in-the-hypercube in time _O\_∗(1.817\_n_), where the notation _O\_∗ indicates that polynomial factors are being omitted. The fastest known classical algorithm for this problem runs in time O\_∗(2\_n). Using this primitive quantum algorithms can be constructed that solve vertex ordering problems in O\_∗(1.817\_n) vs. O\_∗(2\_n) classically, graph bandwidth in O\_∗(2.946\_n) vs. O\_∗(4.383\_n) classically, travelling salesman and feedback arc set in O\_∗(1.729\_n) vs. O\_∗(2\_n) classically, and minimum set cover in O(poly(m,n)1.728\_n_) vs. _O_(_nm\_2\_n_) classically.

### References

1Daniel S. Abrams and Seth Lloyd\
Simulation of many-body Fermi systems on a universal quantum computer.\
_Physical Review Letters_, 79(13):2586-2589, 1997.\
[arXiv:quant-ph/9703054](http://arxiv.org/abs/quant-ph/9703054)\
\
2Dorit Aharonov and Itai Arad\
The BQP-hardness of approximating the Jones polynomial.\
_New Journal of Physics_ 13:035019, 2011.\
[arXiv:quant-ph/0605181](http://arxiv.org/abs/quant-ph/0605181)\
\
3Dorit Aharonov, Itai Arad, Elad Eban, and Zeph Landau\
Polynomial quantum algorithms for additive approximations of the Potts model and other points of the Tutte plane.\
[_arXiv:quant-ph/0702008_](http://arxiv.org/abs/quant-ph/0702008), 2007.\
\
4Dorit Aharonov, Vaughan Jones, and Zeph Landau\
A polynomial quantum algorithm for approximating the Jones polynomial.\
In _Proceedings of the 38th ACM Symposium on Theory of Computing_, 2006.\
[arXiv:quant-ph/0511096](http://arxiv.org/abs/quant-ph/0511096)\
\
5Dorit Aharonov and Amnon Ta-Shma\
Adiabatic quantum state generation and statistical zero knowledge.\
In _Proceedings of the 35th ACM Symposium on Theory of Computing_, 2003.\
[arXiv:quant-ph/0301023](http://arxiv.org/abs/quant-ph/0301023).\
\
6A. Ambainis, H. Buhrman, P. Høyer, M. Karpinizki, and P. Kurur\
Quantum matrix verification.\
Unpublished Manuscript, 2002.\
\
7Andris Ambainis\
Quantum walk algorithm for element distinctness.\
_SIAM Journal on Computing_, 37:210-239, 2007.\
[arXiv:quant-ph/0311001](http://arxiv.org/abs/quant-ph/0311001)\
\
8Andris Ambainis, Andrew M. Childs, Ben W.Reichardt, Robert Špalek, and Shengyu Zheng\
Every AND-OR formula of size N can be evaluated in time $$n1/2+o(1)$$on a quantum computer.\
In _Proceedings of the 48th IEEE Symposium on the Foundations of Computer Science_, pages 363-372, 2007.\
[arXiv:quant-ph/0703015](http://arxiv.org/abs/quant-ph/0703015) and [arXiv:0704.3628](http://arxiv.org/abs/0704.3628)\
\
9Dave Bacon, Andrew M. Childs, and Wim van Dam\
From optimal measurement to efficient quantum algorithms for the hidden subgroup problem over semidirect product groups.\
In _Proceedings of the 46th IEEE Symposium on Foundations of Computer Science_, pages 469-478, 2005.\
[arXiv:quant-ph/0504083](http://arxiv.org/abs/quant-ph/0504083)\
\
10Michael Ben-Or and Avinatan Hassidim\
Quantum search in an ordered list via adaptive learning.\
[_arXiv:quant-ph/0703231_](http://arxiv.org/abs/quant-ph/0703231), 2007.\
\
11Ethan Bernstein and Umesh Vazirani\
Quantum complexity theory.\
In _Proceedings of the 25th ACM Symposium on the Theory of Computing_, pages 11-20, 1993.\
\
12D.W. Berry, G. Ahokas, R. Cleve, and B. C. Sanders\
Efficient quantum algorithms for simulating sparse Hamiltonians.\
_Communications in Mathematical Physics_, 270(2):359-371, 2007.\
[arXiv:quant-ph/0508139](http://arxiv.org/abs/quant-ph/0508139)\
\
13A. Berzina, A. Dubrovsky, R. Frivalds, L. Lace, and O. Scegulnaja\
Quantum query complexity for some graph problems.\
In _Proceedings of the 30th Conference on Current Trends in Theory and Practive of Computer Science_, pages 140-150, 2004.\
\
14D. Boneh and R. J. Lipton\
Quantum cryptanalysis of hidden linear functions.\
In Don Coppersmith, editor, _CRYPTO '95_, Lecture Notes in Computer Science, pages 424-437. Springer-Verlag, 1995.\
\
15M. Boyer, G. Brassard, P. Høyer, and A. Tapp\
Tight bounds on quantum searching.\
_Fortschritte der Physik_, 46:493-505, 1998.\
\
16G. Brassard, P. Høyer, and A. Tapp\
Quantum counting.\
[_arXiv:quant-ph/9805082_](http://arxiv.org/abs/quant-ph/9805082), 1998.\
\
17Gilles Brassard, Peter Høyer, Michele Mosca, and Alain Tapp\
Quantum amplitude amplification and estimation.\
In Samuel J. Lomonaco Jr. and Howard E. Brandt, editors, _Quantum Computation and Quantum Information: A Millennium Volume_, volume 305 of _AMS Contemporary Mathematics Series_. American Mathematical Society, 2002.\
[arXiv:quant-ph/0005055](http://arxiv.org/abs/quant-ph/0005055)\
\
18Gilles Brassard, Peter Høyer, and Alain Tapp\
Quantum algorithm for the collision problem.\
_ACM SIGACT News_, 28:14-19, 1997.\
[arXiv:quant-ph/9705002](http://arxiv.org/abs/quant-ph/9705002)\
\
19Harry Buhrman and Robert Špalek\
Quantum verification of matrix products.\
In _Proceedings of the 17th ACM-SIAM Symposium on Discrete Algorithms_, pages 880-889, 2006.\
[arXiv:quant-ph/0409035](http://arxiv.org/abs/quant-ph/0409035)\
\
20David Bulger\
Quantum basin hopping with gradient-based local optimisation.\
[_arXiv:quant-ph/0507193_](http://arxiv.org/abs/quant-ph/0507193), 2005.\
\
21Harry Burhrman, Christoph Dürr, Mark Heiligman, Peter Høyer, Frédéric Magniez, Miklos Santha, and Ronald de Wolf\
Quantum algorithms for element distinctness.\
In _Proceedings of the 16th IEEE Annual Conference on Computational Complexity_, pages 131-137, 2001.\
[arXiv:quant-ph/0007016](http://arxiv.org/abs/quant-ph/0007016)\
\
22Dong Pyo Chi, Jeong San Kim, and Soojoon Lee\
Notes on the hidden subgroup problem on some semi-direct product groups.\
_Phys. Lett. A_ 359(2):114-116, 2006.\
[arXiv:quant-ph/0604172](http://arxiv.org/abs/quant-ph/0604172)\
\
23A. M. Childs, L. J. Schulman, and U. V. Vazirani\
Quantum algorithms for hidden nonlinear structures.\
In _Proceedings of the 48th IEEE Symposium on Foundations of Computer Science_, pages 395-404, 2007.\
[arXiv:0705.2784](http://arxiv.org/abs/0705.2784)\
\
24Andrew Childs and Troy Lee\
Optimal quantum adversary lower bounds for ordered search.\
_Proceedings of ICALP 2008_\
[arXiv:0708.3396](http://arxiv.org/abs/0708.3396)\
\
25Andrew M. Childs\
[_Quantum information processing in continuous time_](http://www.math.uwaterloo.ca/\~amchilds/papers/thesis.pdf).\
PhD thesis, MIT, 2004.\
\
26Andrew M. Childs, Richard Cleve, Enrico Deotto, Edward Farhi, Sam Gutmann, and Daniel A. Spielman\
Exponential algorithmic speedup by quantum walk.\
In _Proceedings of the 35th ACM Symposium on Theory of Computing_, pages 59-68, 2003.\
[arXiv:quant-ph/0209131](http://arxiv.org/abs/quant-ph/0209131)\
\
27Andrew M. Childs, Richard Cleve, Stephen P. Jordan, and David Yonge-Mallo\
Discrete-query quantum algorithm for NAND trees.\
_Theory of Computing_, 5:119-123, 2009.\
[arXiv:quant-ph/0702160](http://arxiv.org/abs/quant-ph/0702160)\
\
28Andrew M. Childs and Wim van Dam\
Quantum algorithm for a generalized hidden shift problem.\
In _Proceedings of the 18th ACM-SIAM Symposium on Discrete Algorithms_, pages 1225-1232, 2007.\
[arXiv:quant-ph/0507190](http://arxiv.org/abs/quant-ph/0507190).\
\
29Richard Cleve, Dmitry Gavinsky, and David L. Yonge-Mallo\
Quantum algorithms for evaluating MIN-MAX trees.\
In _Theory of Quantum Computation, Communication, and Cryptography_, pages 11-15,\
Springer, 2008. (LNCS Vol. 5106)\
[arXiv:0710.5794](http://arxiv.org/abs/0710.5794).\
\
30J. Niel de Beaudrap, Richard Cleve, and John Watrous\
Sharp quantum versus classical query complexity separations.\
_Algorithmica_, 34(4):449-461, 2002.\
[arXiv:quant-ph/0011065v2](http://arxiv.org/abs/quant-ph/0011065).\
\
31Thomas Decker, Jan Draisma, and Pawel Wocjan\
Quantum algorithm for identifying hidden polynomials.\
_Quantum Information and Computation_, 9(3):215-230, 2009.\
[arXiv:0706.1219](http://arxiv.org/abs/0706.1219).\
\
32David Deutsch\
Quantum theory, the Church-Turing principle, and the universal quantum computer.\
_Proceedings of the Royal Society of London Series A_, 400:97-117, 1985.\
\
33David Deutsch and Richard Jozsa\
Rapid solution of problems by quantum computation.\
_Proceedings of the Royal Society of London Series A_, 493:553-558, 1992.\
\
34Christoph Dürr, Mark Heiligman, Peter Høyer, and Mehdi Mhalla\
Quantum query complexity of some graph problems.\
_SIAM Journal on Computing_, 35(6):1310-1328, 2006.\
[arXiv:quant-ph/0401091](http://arxiv.org/abs/quant-ph/0401091).\
\
35Christoph Dürr and Peter Høyer\
A quantum algorithm for finding the minimum.\
[_arXiv:quant-ph/9607014_](http://arxiv.org/abs/quant-ph/9607014), 1996.\
\
36Christoph Dürr, Mehdi Mhalla, and Yaohui Lei\
Quantum query complexity of graph connectivity.\
[_arXiv:quant-ph/0303169_](http://arxiv.org/abs/quant-ph/0303169), 2003.\
\
37Mark Ettinger, Peter Høyer, and Emanuel Knill\
The quantum query complexity of the hidden subgroup problem is polynomial.\
_Information Processing Letters_, 91(1):43-48, 2004.\
[arXiv:quant-ph/0401083](http://arxiv.org/abs/quant-ph/0401083).\
\
38Edward Farhi, Jeffrey Goldstone, and Sam Gutmann\
A quantum algorithm for the Hamiltonian NAND tree.\
_Theory of Computing_ 4:169-190, 2008.\
[arXiv:quant-ph/0702144](http://arxiv.org/abs/quant-ph/0702144).\
\
39Edward Farhi, Jeffrey Goldstone, Sam Gutmann, and Michael Sipser\
Invariant quantum algorithms for insertion into an ordered list.\
[_arXiv:quant-ph/9901059_](http://arxiv.org/abs/quant-ph/9901059), 1999.\
\
40Richard P. Feynman\
Simulating physics with computers.\
_International Journal of Theoretical Physics_, 21(6/7):467-488, 1982.\
\
41Michael Freedman, Alexei Kitaev, and Zhenghan Wang\
Simulation of topological field theories by quantum computers.\
_Communications in Mathematical Physics_, 227:587-603, 2002.\
\
42Michael Freedman, Michael Larsen, and Zhenghan Wang\
A modular functor which is universal for quantum computation.\
_Comm. Math. Phys._ 227(3):605-622, 2002.\
[arXiv:quant-ph/0001108](http://arxiv.org/abs/quant-ph/0001108).\
\
43K. Friedl, G. Ivanyos, F. Magniez, M. Santha, and P. Sen\
Hidden translation and translating coset in quantum computing.\
_SIAM Journal on Computing_ Vol. 43, pp. 1-24, 2014.\
Appeared earlier in _Proceedings of the 35th ACM Symposium on Theory of Computing_, pages 1-9, 2003.\
[arXiv:quant-ph/0211091](http://arxiv.org/abs/quant-ph/0211091).\
\
44D. Gavinsky\
Quantum solution to the hidden subgroup problem for poly-near-Hamiltonian-groups.\
_Quantum Information and Computation_, 4:229-235, 2004.\
\
45Joseph Geraci\
A new connection between quantum circuits, graphs and the Ising partition function\
_Quantum Information Processing_, 7(5):227-242, 2008.\
[arXiv:0801.4833](http://arxiv.org/abs/0801.4833).\
\
46Joseph Geraci and Frank Van Bussel\
A theorem on the quantum evaluation of weight enumerators for a certain class of cyclic Codes with a note on cyclotomic cosets.\
[_arXiv:cs/0703129_](http://arxiv.org/abs/cs/0703129), 2007.\
\
47Joseph Geraci and Daniel A. Lidar\
On the exact evaluation of certain instances of the Potts partition function by quantum computers.\
_Comm. Math. Phys._ Vol. 279, pg. 735, 2008.\
[arXiv:quant-ph/0703023](http://arxiv.org/abs/quant-ph/0703023).\
\
48Lov K. Grover\
Quantum mechanics helps in searching for a needle in a haystack.\
_Physical Review Letters_, 79(2):325-328, 1997.\
[arXiv:quant-ph/9605043](http://arxiv.org/abs/quant-ph/9605043).\
\
49Sean Hallgren\
Polynomial-time quantum algorithms for Pell's equation and the principal ideal problem.\
In _Proceedings of the 34th ACM Symposium on Theory of Computing_, 2002.\
\
50Sean Hallgren\
Fast quantum algorithms for computing the unit group and class group of a number field.\
In _Proceedings of the 37th ACM Symposium on Theory of Computing_, 2005.\
\
51Sean Hallgren, Alexander Russell, and Amnon Ta-Shma\
Normal subgroup reconstruction and quantum computation using group representations.\
_SIAM Journal on Computing_, 32(4):916-934, 2003.\
\
52Mark Heiligman\
Quantum algorithms for lowest weight paths and spanning trees in complete graphs.\
[_arXiv:quant-ph/0303131_](http://arxiv.org/abs/quant-ph/0303131), 2003.\
\
53Yoshifumi Inui and François Le Gall\
Efficient quantum algorithms for the hidden subgroup problem over a class of semi-direct product groups.\
_Quantum Information and Computation_, 7(5/6):559-570, 2007.\
[arXiv:quant-ph/0412033](http://arxiv.org/abs/quant-ph/0412033).\
\
54Yuki Kelly Itakura\
Quantum algorithm for commutativity testing of a matrix set.\
Master's thesis, University of Waterloo, 2005.\
[arXiv:quant-ph/0509206](http://arxiv.org/abs/quant-ph/0509206).\
\
55Gábor Ivanyos, Frédéric Magniez, and Miklos Santha\
Efficient quantum algorithms for some instances of the non-abelian hidden subgroup problem.\
In _Proceedings of the 13th ACM Symposium on Parallel Algorithms and Architectures_, pages 263-270, 2001.\
[arXiv:quant-ph/0102014](http://arxiv.org/abs/quant-ph/0102014).\
\
56Gábor Ivanyos, Luc Sanselme, and Miklos Santha\
An efficient quantum algorithm for the hidden subgroup problem in extraspecial groups.\
In _Proceedings of the 24th Symposium on Theoretical Aspects of Computer Science_, 2007.\
[arXiv:quant-ph/0701235](http://arxiv.org/abs/quant-ph/0701235).\
\
57Gábor Ivanyos, Luc Sanselme, and Miklos Santha\
An efficient quantum algorithm for the hidden subgroup problem in nil-2 groups.\
In _LATIN 2008: Theoretical Informatics_, pg. 759-771, Springer (LNCS 4957).\
[arXiv:0707.1260](http://arxiv.org/abs/0707.1260).\
\
58Dominik Janzing and Pawel Wocjan\
BQP-complete problems concerning mixing properties of classical random walks on sparse graphs.\
[_arXiv:quant-ph/0610235_](http://arxiv.org/abs/quant-ph/0610235), 2006.\
\
59Dominik Janzing and Pawel Wocjan\
A promiseBQP-complete string rewriting problem.\
_Quantum Information and Computation_, 10(3/4):234-257, 2010.\
[arXiv:0705.1180](http://arxiv.org/abs/0705.1180).\
\
60Dominik Janzing and Pawel Wocjan\
A simple promiseBQP-complete matrix problem.\
_Theory of Computing_, 3:61-79, 2007.\
[arXiv:quant-ph/0606229](http://arxiv.org/abs/quant-ph/0606229).\
\
61Stephen P. Jordan\
Fast quantum algorithm for numerical gradient estimation.\
_Physical Review Letters_, 95:050501, 2005.\
[arXiv:quant-ph/0405146](http://arxiv.org/abs/quant-ph/0405146).\
\
62Stephen P. Jordan\
_Quantum Computation Beyond the Circuit Model_.\
PhD thesis, Massachusetts Institute of Technology, 2008.\
[arXiv:0809.2307](http://arxiv.org/abs/0809.2307).\
\
63Ivan Kassal, Stephen P. Jordan, Peter J. Love, Masoud Mohseni, and Alán Aspuru-Guzik\
Quantum algorithms for the simulation of chemical dynamics.\
_Proc. Natl. Acad. Sci._ Vol. 105, pg. 18681, 2008.\
[arXiv:0801.2986](http://arxiv.org/abs/0801.2986).\
\
64Kiran S. Kedlaya\
Quantum computation of zeta functions of curves.\
_Computational Complexity_, 15:1-19, 2006.\
[arXiv:math/0411623](http://arxiv.org/abs/math/0411623).\
\
65E. Knill and R. Laflamme\
Quantum computation and quadratically signed weight enumerators.\
_Information Processing Letters_, 79(4):173-179, 2001.\
[arXiv:quant-ph/9909094](http://arxiv.org/abs/quant-ph/9909094).\
\
66Greg Kuperberg\
A subexponential-time quantum algorithm for the dihedral hidden subgroup problem.\
_SIAM Journal on Computing_, 35(1):170-188, 2005.\
[arXiv:quant-ph/0302112](http://arxiv.org/abs/quant-ph/0302112).\
\
67Daniel A. Lidar\
On the quantum computational complexity of the Ising spin glass partition function and of knot invariants.\
_New Journal of Physics_ Vol. 6, pg. 167, 2004.\
[arXiv:quant-ph/0309064](http://arxiv.org/abs/quant-ph/0309064).\
\
68Daniel A. Lidar and Haobin Wang\
Calculating the thermal rate constant with exponential speedup on a quantum computer.\
_Physical Review E_, 59(2):2429-2438, 1999.\
[arXiv:quant-ph/9807009](http://arxiv.org/abs/quant-ph/9807009).\
\
69Chris Lomont\
The hidden subgroup problem - review and open problems.\
[_arXiv:quant-ph/0411037_](http://arxiv.org/abs/quant-ph/0411037), 2004.\
\
70Frédéric Magniez, Miklos Santha, and Mario Szegedy\
Quantum algorithms for the triangle problem.\
_SIAM Journal on Computing_, 37(2):413-424, 2007.\
[arXiv:quant-ph/0310134](http://arxiv.org/abs/quant-ph/0310134).\
\
71Carlos Magno, M. Cosme, and Renato Portugal\
Quantum algorithm for the hidden subgroup problem on a class of semidirect product groups.\
[_arXiv:quant-ph/0703223_](http://arxiv.org/abs/quant-ph/0703223), 2007.\
\
72Cristopher Moore, Daniel Rockmore, Alexander Russell, and Leonard Schulman\
The power of basis selection in Fourier sampling: the hidden subgroup problem in affine groups.\
In _Proceedings of the 15th ACM-SIAM Symposium on Discrete Algorithms_, pages 1113-1122, 2004.\
[arXiv:quant-ph/0211124](http://arxiv.org/abs/quant-ph/0211124).\
\
73M. Mosca\
Quantum searching, counting, and amplitude amplification by eigenvector analysis.\
In R. Freivalds, editor, _Proceedings of International Workshop on Randomized Algorithms_, pages 90-100, 1998.\
\
74Michele Mosca\
[_Quantum Computer Algorithms_](http://www.iqc.ca/\~mmosca/web/papers/moscathesis.pdf).\
PhD thesis, University of Oxford, 1999.\
\
75Ashwin Nayak and Felix Wu\
The quantum query complexity of approximating the median and related statistics.\
In _Proceedings of 31st ACM Symposium on the Theory of Computing_, 1999.\
[arXiv:quant-ph/9804066](http://arxiv.org/abs/quant-ph/9804066).\
\
76Michael A. Nielsen and Isaac L. Chuang.\
_Quantum Computation and Quantum Information_.\
Cambridge University Press, Cambridge, UK, 2000.\
\
77Erich Novak\
Quantum complexity of integration.\
_Journal of Complexity_, 17:2-16, 2001.\
[arXiv:quant-ph/0008124](http://arxiv.org/abs/quant-ph/0008124).\
\
78Oded Regev\
Quantum computation and lattice problems.\
In _Proceedings of the 43rd Symposium on Foundations of Computer Science_, 2002.\
[arXiv:cs/0304005](http://arxiv.org/abs/cs/0304005).\
\
79Oded Regev\
A subexponential time algorithm for the dihedral hidden subgroup problem with polynomial space.\
[_arXiv:quant-ph/0406151_](http://arxiv.org/abs/quant-ph/0406151), 2004.\
\
80Ben Reichardt and Robert Špalek\
Span-program-based quantum algorithm for evaluating formulas.\
_Proceedings of STOC 2008_\
[arXiv:0710.2630](http://arxiv.org/abs/0710.2630).\
\
81Martin Roetteler and Thomas Beth\
Polynomial-time solution to the hidden subgroup problem for a class of non-abelian groups.\
[_arXiv:quant-ph/9812070_](http://arxiv.org/abs/quant-ph/9812070), 1998.\
\
82Peter W. Shor\
Polynomial-time algorithms for prime factorization and discrete logarithms on a quantum computer.\
_SIAM Journal on Computing_, 26(5):1484-1509, 1997.\
[arXiv:quant-ph/9508027](http://arxiv.org/abs/quant-ph/9508027).\
\
83Peter W. Shor and Stephen P. Jordan\
Estimating Jones polynomials is a complete problem for one clean qubit.\
_Quantum Information and Computation_, 8(8/9):681-714, 2008.\
[arXiv:0707.2831](http://arxiv.org/abs/0707.2831).\
\
84R. D. Somma, S. Boixo, and H. Barnum\
Quantum simulated annealing.\
[_arXiv:0712.1008_](http://arxiv.org/abs/0712.1008), 2007.\
\
85M. Szegedy\
Quantum speed-up of Markov chain based algorithms.\
In _Proceedings of the 45th IEEE Symposium on Foundations of Computer Science_, pg. 32, 2004.\
\
86Wim van Dam\
Quantum algorithms for weighing matrices and quadratic residues.\
_Algorithmica_, 34(4):413-428, 2002.\
[arXiv:quant-ph/0008059](http://arxiv.org/abs/quant-ph/0008059).\
\
87Wim van Dam\
Quantum computing and zeros of zeta functions.\
[_arXiv:quant-ph/0405081_](http://arxiv.org/abs/quant-ph/0405081), 2004.\
\
88Wim van Dam and Sean Hallgren\
Efficient quantum algorithms for shifted quadratic character problems.\
[_arXiv:quant-ph/0011067_](http://arxiv.org/abs/quant-ph/0011067), 2000.\
\
89Wim van Dam, Sean Hallgren, and Lawrence Ip\
Quantum algorithms for some hidden shift problems.\
_SIAM Journal on Computing_, 36(3):763-778, 2006.\
[arXiv:quant-h/0211140](http://arxiv.org/abs/quant-ph/0211140).\
\
90Wim van Dam and Gadiel Seroussi\
Efficient quantum algorithms for estimating Gauss sums.\
[_arXiv:quant-ph/0207131_](http://arxiv.org/abs/quant-ph/0207131), 2002.\
\
91John Watrous\
Quantum algorithms for solvable groups.\
In _Proceedings of the 33rd ACM Symposium on Theory of Computing_, pages 60-67, 2001.\
[arXiv:quant-ph/0011023](http://arxiv.org/abs/quant-ph/0011023).\
\
92Stephen Wiesner\
Simulations of many-body quantum systems by a quantum computer.\
[_arXiv:quant-ph/9603028_](http://arxiv.org/abs/quant-ph/9603028), 1996.\
\
93Pawel Wocjan and Jon Yard\
The Jones polynomial: quantum algorithms and applications in quantum complexity theory.\
_Quantum Information and Computation 8(1/2):147-180, 2008._\
[arXiv:quant-ph/0603069](http://arxiv.org/abs/quant-ph/0603069).\
\
94Andrew Yao\
On computing the minima of quadratic forms.\
In _Proceedings of the 7th ACM Symposium on Theory of Computing_, pages 23-26, 1975.\
\
95Christof Zalka\
Efficient simulation of quantum systems by quantum computers.\
_Proceedings of the Royal Society of London Series A_, 454:313, 1996.\
[arXiv:quant-ph/9603026](http://arxiv.org/abs/quant-ph/9603026).\
\
96Edward Farhi, Jeffrey Goldstone, Sam Gutmann, and Michael Sipser\
Quantum computation by adiabatic evolution.\
[_arXiv:quant-ph/0001106_](http://arxiv.org/abs/quant-ph/0001106), 2000.\
\
97Dorit Aharonov, Wim van Dam, Julia Kempe, Zeph Landau, Seth Lloyd, and Oded Regev\
Adiabatic Quantum Computation is Equivalent to Standard Quantum Computation.\
_SIAM Journal on Computing_, 37(1):166-194, 2007.\
[arXiv:quant-ph/0405098](http://arxiv.org/abs/quant-ph/0405098)\
\
98Jérémie Roland and Nicolas J. Cerf\
Quantum search by local adiabatic evolution.\
_Physical Review A_, 65(4):042308, 2002.\
[arXiv:quant-ph/0107015](http://arxiv.org/abs/quant-ph/0107015)\
\
99L.-A. Wu, M.S. Byrd, and D. A. Lidar\
Polynomial-Time Simulation of Pairing Models on a Quantum Computer.\
_Physical Review Letters_, 89(6):057904, 2002.\
[arXiv:quant-ph/0108110](http://arxiv.org/abs/quant-ph/0108110)\
\
100Eli Biham, Ofer Biham, David Biron, Markus Grassl, and Daniel Lidar\
Grover's quantum search algorithm for an arbitrary initial amplitude distribution.\
_Physical Review A_, 60(4):2742, 1999.\
[arXiv:quant-ph/9807027](http://arxiv.org/abs/quant-ph/9807027) and [arXiv:quant-ph/0010077](http://arxiv.org/abs/quant-ph/0010077)\
\
101Andrew Childs, Shelby Kimmel, and Robin Kothari\
The quantum query complexity of read-many formulas\
In _Proceedings of ESA 2012_, pg. 337-348, Springer. (LNCS 7501)\
[arXiv:1112.0548](http://arxiv.org/abs/1112.0548), 2011.\
\
102Alán Aspuru-Guzik, Anthony D. Dutoi, Peter J. Love, and Martin Head-Gordon\
Simulated quantum computation of molecular energies.\
_Science_, 309(5741):1704-1707, 2005.\
[arXiv:quant-ph/0604193](http://arxiv.org/abs/quant-ph/0604193)\
\
103A. M. Childs, A. J. Landahl, and P. A. Parrilo\
Quantum algorithms for the ordered search problem via semidefinite programming.\
_Physical Review A_, 75 032335, 2007.\
[arXiv:quant-ph/0608161](http://arxiv.org/abs/quant-ph/0608161)\
\
104Aram W. Harrow, Avinatan Hassidim, and Seth Lloyd\
Quantum algorithm for solving linear systems of equations.\
_Physical Review Letters_ 15(103):150502, 2009.\
[arXiv:0811.3171](http://arxiv.org/abs/0811.3171).\
\
105Martin Roetteler\
Quantum algorithms for highly non-linear Boolean functions.\
_Proceedings of SODA 2010_\
[arXiv:0811.3208](http://arxiv.org/abs/0811.3208).\
\
106Stephen P. Jordan\
Fast quantum algorithms for approximating the irreducible representations of groups.\
[_arXiv:0811.0562_](http://arxiv.org/abs/0811.0562), 2008.\
\
107Tim Byrnes and Yoshihisa Yamamoto\
Simulating lattice gauge theories on a quantum computer.\
_Physical Review A_, 73, 022328, 2006.\
[arXiv:quant-ph/0510027](http://arxiv.org/abs/quant-ph/0510027).\
\
108D. Simon\
On the Power of Quantum Computation.\
In _Proceedings of the 35th Symposium on Foundations of Computer Science_, pg. 116-123, 1994.\
\
109John Proos and Christof Zalka\
Shor's discrete logarithm quantum algorithm for elliptic curves.\
_Quantum Information and Computation_, Vol. 3, No. 4, pg.317-344, 2003.\
[arXiv:quant-ph/0301141](http://arxiv.org/abs/quant-ph/0301141).\
\
110Yi-Kai Liu\
Quantum algorithms using the curvelet transform.\
_Proceedings of STOC 2009_, pg. 391-400.\
[arXiv:0810.4968](http://arxiv.org/abs/0810.4968).\
\
111Wim van Dam and Igor Shparlinski\
Classical and quantum algorithms for exponential congruences.\
_Proceedings of TQC 2008_, pg. 1-10.\
[arXiv:0804.1109](http://arxiv.org/abs/0804.1109).\
\
112Itai Arad and Zeph Landau\
Quantum computation and the evaluation of tensor networks.\
_SIAM Journal on Computing_, 39(7):3089-3121, 2010.\
[arXiv:0805.0040](http://arxiv.org/abs/0805.0040).\
\
113M. Van den Nest, W. Dür, R. Raussendorf, and H. J. Briegel\
Quantum algorithms for spin models and simulable gate sets for quantum computation.\
_Physical Review A_, 80:052334, 2009.\
[arXiv:0805.1214](http://arxiv.org/abs/0805.1214).\
\
114Silvano Garnerone, Annalisa Marzuoli, and Mario Rasetti\
Efficient quantum processing of 3-manifold topological invariants.\
_Advances in Theoretical and Mathematical Physics_, 13(6):1601-1652, 2009.\
[arXiv:quant-ph/0703037](http://arxiv.org/abs/quant-ph/0703037).\
\
115Louis H. Kauffman and Samuel J. Lomonaco Jr.\
q-deformed spin networks, knot polynomials and anyonic topological quantum computation.\
_Journal of Knot Theory_, Vol. 16, No. 3, pg. 267-332, 2007.\
[arXiv:quant-ph/0606114](http://arxiv.org/abs/quant-ph/0606114).\
\
116Arthur Schmidt and Ulrich Vollmer\
Polynomial time quantum algorithm for the computation of the unit group of a number field.\
In _Proceedings of the 37th Symposium on the Theory of Computing_, pg. 475-480, 2005.\
\
117Sergey Bravyi, Aram Harrow, and Avinatan Hassidim\
Quantum algorithms for testing properties of distributions.\
_IEEE Transactions on Information Theory_ 57(6):3971-3981, 2011.\
[arXiv:0907.3920](http://arxiv.org/abs/0907.3920).\
\
118Pawel M. Wocjan, Stephen P. Jordan, Hamed Ahmadi, and Joseph P. Brennan\
Efficient quantum processing of ideals in finite rings.\
[_arXiv:0908.0022_](http://arxiv.org/abs/0908.0022), 2009.\
\
119V. Arvind, Bireswar Das, and Partha Mukhopadhyay\
The complexity of black-box ring problems.\
In _Proceedings of COCCOON 2006_, pg 126-145.\
\
120V. Arvind and Partha Mukhopadhyay\
Quantum query complexity of multilinear identity testing.\
In _Proceedings of STACS 2009_, pg. 87-98.\
\
121David Poulin and Pawel Wocjan\
Sampling from the thermal quantum Gibbs state and evaluating partition functions with a quantum computer.\
_Physical Review Letters_ 103:220502, 2009.\
[arXiv:0905.2199](http://arxiv.org/abs/0905.2199)\
\
122Pawel Wocjan, Chen-Fu Chiang, Anura Abeyesinghe, and Daniel Nagaj\
Quantum speed-up for approximating partition functions.\
_Physical Review A_ 80:022340, 2009.\
[arXiv:0811.0596](http://arxiv.org/abs/0811.0596)\
\
123Ashley Montanaro\
Quantum search with advice.\
In _Proceedings of the 5th conference on Theory of quantum computation, communication, and cryptography (TQC 2010)_\
[arXiv:0908.3066](http://arxiv.org/abs/0908.3066)\
\
124Laszlo Babai, Robert Beals, and Akos Seress\
Polynomial-time theory of matrix groups.\
In _Proceedings of STOC 2009_, pg. 55-64.\
\
125Peter Shor\
Algorithms for Quantum Computation: Discrete Logarithms and Factoring.\
In _Proceedings of FOCS 1994_, pg. 124-134.\
\
126Aaron Denney, Cristopher Moore, and Alex Russell\
Finding conjugate stabilizer subgroups in PSL(2;q) and related groups.\
_Quantum Information and Computation_ 10(3):282-291, 2010.\
[arXiv:0809.2445](http://arxiv.org/abs/0809.2445).\
\
127Kevin K. H. Cheung and Michele Mosca\
Decomposing finite Abelian groups.\
_Quantum Information and Computation_ 1(2):26-32, 2001.\
[arXiv:cs/0101004](http://arxiv.org/abs/cs/0101004).\
\
128François Le Gall\
An efficient quantum algorithm for some instances of the group isomorphism problem.\
In _Proceedings of STACS 2010_.\
[arXiv:1001.0608](http://arxiv.org/abs/1001.0608).\
\
129Gorjan Alagic, Stephen Jordan, Robert Koenig, and Ben Reichardt\
Approximating Turaev-Viro 3-manifold invariants is universal for quantum computation.\
_Physical Review A_ 82, 040302(R), 2010.\
[arXiv:1003.0923](http://arxiv.org/abs/1003.0923)\
\
130Martin Rötteler\
Quantum algorithms to solve the hidden shift problem for quadratics and for functions of large Gowers norm.\
In _Proceedings of MFCS 2009_, pg 663-674.\
[arXiv:0911.4724](http://arxiv.org/abs/0911.4724).\
\
131Arthur Schmidt\
Quantum Algorithms for many-to-one Functions to Solve the Regulator and the Principal Ideal Problem.\
[_arXiv:0912.4807_](http://arxiv.org/abs/0912.4807), 2009.\
\
132K. Temme, T.J. Osborne, K.G. Vollbrecht, D. Poulin, and F. Verstraete\
Quantum Metropolis Sampling.\
_Nature_, Vol. 471, pg. 87-90, 2011.\
[arXiv:0911.3635](http://arxiv.org/abs/0911.3635).\
\
133Andris Ambainis\
Quantum Search Algorithms.\
_SIGACT News_, 35 (2):22-35, 2004.\
[arXiv:quant-ph/0504012](http://arxiv.org/abs/quant-ph/0504012)\
\
134Nicolas J. Cerf, Lov K. Grover, and Colin P. Williams\
Nested quantum search and NP-hard problems.\
_Applicable Algebra in Engineering, Communication and Computing_, 10 (4-5):311-338, 2000.\
\
135Mario Szegedy\
Spectra of Quantized Walks and a $$δϵ−−√$$rule.\
[_arXiv:quant-ph/0401053_](http://arxiv.org/abs/quant-ph/0401053), 2004.\
\
136Kazuo Iwama, Harumichi Nishimura, Rudy Raymond, and Junichi Teruyama\
Quantum Counterfeit Coin Problems.\
In _Proceedings of 21st International Symposium on Algorithms and Computation (ISAAC2010)_, LNCS 6506, pp.73-84, 2010.\
[arXiv:1009.0416](http://arxiv.org/abs/1009.0416)\
\
137Barbara Terhal and John Smolin\
Single quantum querying of a database.\
_Physical Review A_ 58:1822, 1998.\
[arXiv:quant-ph/9705041](http://arxiv.org/abs/quant-ph/9705041)\
\
138Andris Ambainis\
Variable time amplitude amplification and a faster quantum algorithm for solving systems of linear equations.\
[arXiv:1010.4458](http://arxiv.org/abs/1010.4458), 2010.\
\
139Frédéric Magniez and Ashwin Nayak\
Quantum complexity of testing group commutativity.\
In _Proceedings of 32nd International Colloquium on Automata, Languages and Programming._ LNCS 3580, pg. 1312-1324, 2005.\
[arXiv:quant-ph/0506265](http://arxiv.org/abs/quant-ph/0506265)\
\
140Andrew Childs and Robin Kothari\
Quantum query complexity of minor-closed graph properties.\
In _Proceedings of the 28th Symposium on Theoretical Aspects of Computer Science (STACS 2011)_, pg. 661-672\
[arXiv:1011.1443](http://arxiv.org/abs/1011.1443)\
\
141Frédéric Magniez, Ashwin Nayak, Jérémie Roland, and Miklos Santha\
Search via quantum walk.\
In _Proceedings STOC 2007_, pg. 575-584.\
[arXiv:quant-ph/0608026](http://arxiv.org/abs/quant-ph/0608026)\
\
142Dmitry Gavinsky, Martin Roetteler, and Jérémy Roland\
Quantum algorithm for the Boolean hidden shift problem.\
In _Proceedings of the 17th annual international conference on Computing and combinatorics (COCOON '11)_, 2011.\
[arXiv:1103.3017](http://arxiv.org/abs/1103.3017)\
\
143Mark Ettinger and Peter Høyer\
On quantum algorithms for noncommutative hidden subgroups.\
_Advances in Applied Mathematics_, Vol. 25, No. 3, pg. 239-251, 2000.\
[arXiv:quant-ph/9807029](http://arxiv.org/abs/quant-ph/9807029)\
\
144Andris Ambainis, Andrew Childs, and Yi-Kai Liu\
Quantum property testing for bounded-degree graphs.\
In _Proceedings of RANDOM '11_: Lecture Notes in Computer Science 6845, pp. 365-376, 2011.\
[arXiv:1012.3174](http://arxiv.org/abs/1012.3174)\
\
145G. Ortiz, J.E. Gubernatis, E. Knill, and R. Laflamme\
Quantum algorithms for Fermionic simulations.\
_Physical Review A_ 64: 022319, 2001.\
[arXiv:cond-mat/0012334](http://arxiv.org/abs/cond-mat/0012334)\
\
146Ashley Montanaro\
The quantum query complexity of learning multilinear polynomials.\
_Information Processing Letters_, 112(11):438-442, 2012.\
[arXiv:1105.3310](http://arxiv.org/abs/1105.3310).\
\
147Tad Hogg\
Highly structured searches with quantum computers.\
_Physical Review Letters_ 80: 2473, 1998.\
\
148Markus Hunziker and David A. Meyer\
Quantum algorithms for highly structured search problems.\
_Quantum Information Processing_, Vol. 1, No. 3, pg. 321-341, 2002.\
\
149Ben Reichardt\
Span programs and quantum query complexity: The general adversary bound is nearly tight for every Boolean function.\
In _Proceedings of the 50th IEEE Symposium on Foundations of Computer Science (FOCS '09)_, pg. 544-551, 2009.\
[arXiv:0904.2759](http://arxiv.org/abs/0904.2759)\
\
150Aleksandrs Belovs\
Span-program-based quantum algorithm for the rank problem.\
[arXiv:1103.0842](http://arxiv.org/abs/1103.0842), 2011.\
\
151Sebastian Dörn and Thomas Thierauf\
The quantum query complexity of the determinant.\
_Information Processing Letters_ Vol. 109, No. 6, pg. 305-328, 2009.\
\
152Aleksandrs Belovs\
Span programs for functions with constant-sized 1-certificates.\
In _Proceedings of STOC 2012_, pg. 77-84.\
[arXiv:1105.4024](http://arxiv.org/abs/1105.4024).\
\
153Troy Lee, Frédéric Magniez, and Mikos Santha\
A learning graph based quantum query algorithm for finding constant-size subgraphs.\
_Chicago Journal of Theoretical Computer Science_, Vol. 2012, Article 10, 2012.\
[arXiv:1109.5135](http://arxiv.org/abs/1109.5135).\
\
154Aleksandrs Belovs and Troy Lee\
Quantum algorithm for k-distinctness with prior knowledge on the input.\
[_arXiv:1108.3022_](http://arxiv.org/abs/1108.3022), 2011.\
\
155François Le Gall\
Improved output-sensitive quantum algorithms for Boolean matrix multiplication.\
In _Proceedings of the 23rd Annual ACM-SIAM Symposium on Discrete Algorithms (SODA '12)_, 2012.\
\
156Dominic Berry\
Quantum algorithms for solving linear differential equations.\
_J. Phys. A: Math. Theor.47, 105301, 2014._\
_\[_[_arXiv:1010.2745_](http://arxiv.org/abs/1010.2745)_]._\
\
_157Virginia Vassilevska Williams and Ryan Williams_\
_Subcubic equivalences between path, matrix, and triangle problems._\
_In 51st IEEE Symposium on Foundations of Computer Science (FOCS '10) pg. 645 - 654, 2010._\
\
_158Ben W. Reichardt_\
_Reflections for quantum query algorithms._\
_In Proceedings of the 22nd ACM-SIAM Symposium on Discrete Algorithms (SODA), pg. 560-569, 2011._\
[_arXiv:1005.1601_](http://arxiv.org/abs/1005.1601)\
\
_159Ben W. Reichardt_\
_Span-program-based quantum algorithm for evaluating unbalanced formulas._\
[_arXiv:0907.1622_](http://arxiv.org/abs/0907.1622)_, 2009._\
\
_160Ben W. Reichardt_\
_Faster quantum algorithm for evaluating game trees._\
_In Proceedings of the 22nd ACM-SIAM Symposium on Discrete Algorithms (SODA), pg. 546-559, 2011._\
[_arXiv:0907.1623_](http://arxiv.org/abs/0907.1623)\
\
_161Stacey Jeffery, Robin Kothari, and Frédéric Magniez_\
_Improving quantum query complexity of Boolean matrix multiplication using graph collision._\
_In Proceedings of ICALP 2012, pg. 522-532._\
[_arXiv:1112.5855_](http://arxiv.org/abs/1112.5855)_._\
\
_162Andrew M. Childs and Jason M. Eisenberg_\
_Quantum algorithms for subset finding._\
_Quantum Information and Computation 5(7):593-604, 2005._\
[_arXiv:quant-ph/0311038_](http://arxiv.org/abs/quant-ph/0311038)_._\
\
_163Aleksandrs Belovs and Robert Špalek_\
_Adversary lower bound for the k-sum problem._\
_In Proceedings of ITCS 2013, pg. 323-328._\
[_arXiv:1206.6528_](http://arxiv.org/abs/1206.6528)_._\
\
_164Bohua Zhan, Shelby Kimmel, and Avinatan Hassidim_\
_Super-polynomial quantum speed-ups for Boolean evaluation trees with hidden structure._\
_ITCS 2012: Proceedings of the 3rd Innovations in Theoretical Computer Science, ACM, pg. 249-265._\
[_arXiv:1101.0796_](http://arxiv.org/abs/1101.0796)\
\
_165Shelby Kimmel_\
_Quantum adversary (upper) bound._\
_39th International Colloquium on Automata, Languages and Programming - ICALP 2012 Volume 7391, p. 557-568._\
[_arXiv:1101.0797_](http://arxiv.org/abs/1101.0797)\
\
_166Stephen Jordan, Keith Lee, and John Preskill_\
_Quantum algorithms for quantum field theories._\
_Science, Vol. 336, pg. 1130-1133, 2012._\
[_arXiv:1111.3633_](http://arxiv.org/abs/1111.3633)\
\
_167Andris Ambainis and Ashley Montanaro_\
_Quantum algorithms for search with wildcards and combinatorial group testing._\
[_arXiv:1210.1148_](http://arxiv.org/abs/1210.1148)_, 2012._\
\
_168Andris Ambainis and Robert Špalek_\
_Quantum algorithms for matching and network flows._\
_Proceedings of STACS 2007, pg. 172-183._\
[_arXiv:quant-ph/0508205_](http://arxiv.org/abs/quant-ph/0508205)\
\
_169Nathan Wiebe, Daniel Braun, and Seth Lloyd_\
_Quantum data-fitting._\
_Physical Review Letters 109, 050505, 2012._\
[_arXiv:1204.5242_](http://arxiv.org/abs/1204.5242)\
\
_170Andrew Childs and Nathan Wiebe_\
_Hamiltonian simulation using linear combinations of unitary operations._\
_Quantum Information and Computation 12, 901-924, 2012._\
[_arXiv:1202.5822_](http://arxiv.org/abs/1202.5822)\
\
_171Stacey Jeffery, Robin Kothari, and Frédéric Magniez_\
_Nested quantum walks with quantum data structures._\
_In Proceedings of the 24th ACM-SIAM Symposium on Discrete Algorithms (SODA'13), pg. 1474-1485, 2013._\
[_arXiv:1210.1199_](http://arxiv.org/abs/1210.1199)\
\
_172Aleksandrs Belovs_\
_Learning-graph-based quantum algorithm for k-distinctness._\
_Proceedings of STOC 2012, pg. 77-84._\
[_arXiv:1205.1534_](http://arxiv.org/abs/1205.1534)_, 2012._\
\
_173Andrew Childs, Stacey Jeffery, Robin Kothari, and Frédéric Magniez_\
_A time-efficient quantum walk for 3-distinctness using nested updates._\
[_arXiv:1302.7316_](http://arxiv.org/abs/1302.7316)_, 2013._\
\
_174Hari Krovi and Alexander Russell_\
_Quantum Fourier transforms and the complexity of link invariants for quantum doubles of finite groups._\
_Commun. Math. Phys. 334, 743-777, 2015_\
[_arXiv:1210.1550_](http://arxiv.org/abs/1210.1550)\
\
_175Troy Lee, Frédéric Magniez, and Miklos Santha_\
_Improved quantum query algorithms for triangle finding and associativity testing._\
[_arXiv:1210.1014_](http://arxiv.org/abs/1210.1014)_, 2012._\
\
_176Silvano Garnerone, Paolo Zanardi, and Daniel A. Lidar_\
_Adiabatic quantum algorithm for search engine ranking._\
_Physical Review Letters 108:230506, 2012._\
\
_177R. D. Somma, S. Boixo, H. Barnum, and E. Knill_\
_Quantum simulations of classical annealing._\
_Physical Review Letters 101:130504, 2008._\
[_arXiv:0804.1571_](http://arxiv.org/abs/0804.1571)\
\
_178Daniel J. Bernstein, Stacey Jeffery, Tanja Lange, and Alexander Meurer_\
_Quantum algorithms for the subset-sum problem._\
[_from cr.yp.to_](http://cr.yp.to/qsubsetsum/qsubsetsum-20130407.pdf)_._\
\
_179Boris Altshuler, Hari Krovi, and Jérémie Roland_\
_Anderson localization casts clouds over adiabatic quantum optimization._\
_Proceedings of the National Academy of Sciences 107(28):12446-12450, 2010._\
[_arXiv:0912.0746_](http://arxiv.org/abs/0912.0746)\
\
_180Ben Reichardt_\
_The quantum adiabatic optimization algorithm and local minima._\
_In Proceedings of STOC 2004, pg. 502-510. \[_[_Erratum_](http://www-bcf.usc.edu/\~breichar/Correction.txt)_]._\
\
_181Edward Farhi, Jeffrey Goldstone, and Sam Gutmann_\
_Quantum adiabatic evolution algorithms versus simulated annealing._\
[_arXiv:quant-ph/0201031_](http://arxiv.org/abs/quant-ph/0201031)_, 2002._\
\
_182E. Farhi, J. Goldstone, D. Gosset, S. Gutmann, H. B. Meyer, and P. Shor_\
_Quantum adiabatic algorithms, small gaps, and different paths._\
_Quantum Information and Computation, 11(3/4):181-214, 2011._\
[_arXiv:0909.4766_](http://arxiv.org/abs/0909.4766)_._\
\
_183Sergey Bravyi, David P. DiVincenzo, Roberto I. Oliveira, and Barbara M. Terhal_\
_The Complexity of Stoquastic Local Hamiltonian Problems._\
_Quantum Information and Computation, 8(5):361-385, 2008._\
[_arXiv:quant-ph/0606140_](http://arxiv.org/abs/quant-ph/0606140)_._\
\
_184Rolando D. Somma and Sergio Boixo_\
_Spectral gap amplification._\
_SIAM Journal on Computing, 42:593-610, 2013._\
[_arXiv:1110.2494_](http://arxiv.org/abs/1110.2494)_._\
\
_185Sabine Jansen, Mary-Beth Ruskai, Ruedi Seiler_\
_Bounds for the adiabatic approximation with applications to quantum computation._\
_Journal of Mathematical Physics, 48:102111, 2007._\
[_arXiv:quant-ph/0603175_](http://arxiv.org/abs/quant-ph/0603175)_._\
\
_186E. Farhi, J. Goldstone, S. Gutmann, J. Lapan, A. Lundgren, and D. Preda_\
_A Quantum Adiabatic Evolution Algorithm Applied to Random Instances of an NP-Complete Problem._\
_Science, 292(5516):472-475, 2001._\
[_arXiv:quant-ph/0104129_](http://arxiv.org/abs/quant-ph/0104129)_._\
\
_187Edward Farhi, Jeffrey Goldstone, Sam Gutmann, and Daniel Nagaj_\
_How to make the quantum adiabatic algorithm fail._\
_International Journal of Quantum Information, 6(3):503-516, 2008._\
[_arXiv:quant-ph/0512159_](http://arxiv.org/abs/quant-ph/0512159)_._\
\
_188Edward Farhi, Jeffrey Goldstone, Sam Gutmann, and Daniel Nagaj_\
_Unstructured randomness, small gaps, and localization._\
_Quantum Information and Computation, 11(9/10):840-854, 2011._\
[_arXiv:1010.0009_](http://arxiv.org/abs/1010.0009)_._\
\
_189Edward Farhi, Jeffrey Goldstone, Sam Gutmann_\
_Quantum adiabatic evolution algorithms with different paths._\
[_arXiv:quant-ph/0208135_](http://arxiv.org/abs/quant-ph/0208135)_, 2002._\
\
_190Wim van Dam, Michele Mosca, and Umesh Vazirani_\
_How powerful is adiabatic quantum computation?_\
_In Proceedings of FOCS 2001, pg. 279-287._\
[_arXiv:quant-ph/0206003_](http://arxiv.org/abs/quant-ph/0206003) _\[See also_ [_this_](http://www.cs.berkeley.edu/\~vazirani/pubs/qao.ps)_.]_\
\
_191E. Farhi, D. Gosset, I. Hen, A. W. Sandvik, P. Shor, A. P. Young, and F. Zamponi_\
_The performance of the quantum adiabatic algorithm on random instances of two optimization problems on regular hypergraphs._\
_Physical Review A, 86:052334, 2012._\
[_arXiv:1208.3757_](http://arxiv.org/abs/1208.3757)_._\
\
_192Kristen L. Pudenz and Daniel A. Lidar_\
_Quantum adiabatic machine learning._\
_Quantum Information Processing, 12:2027, 2013._\
[_arXiv:1109.0325_](http://arxiv.org/abs/1109.0325)_._\
\
_193Frank Gaitan and Lane Clark_\
_Ramsey numbers and adiabatic quantum computing._\
_Physical Review Letters, 108:010501, 2012._\
[_arXiv:1103.1345_](http://arxiv.org/abs/1103.1345)_._\
\
_194Frank Gaitan and Lane Clark_\
_Graph isomorphism and adiabatic quantum computing._\
_Physical Review A, 89(2):022342, 2014._\
[_arXiv:1304.5773_](http://arxiv.org/abs/1304.5773)_, 2013._\
\
_195Hartmut Neven, Vasil S. Denchev, Geordie Rose, and William G. Macready_\
_Training a binary classifier with the quantum adiabatic algorithm._\
[_arXiv:0811.0416_](http://arxiv.org/abs/0811.0416)_, 2008._\
\
_196Robert Beals_\
_Quantum computation of Fourier transforms over symmetric groups._\
_In Proceedings of STOC 1997, pg. 48-53._\
\
_197Dave Bacon, Isaac L. Chuang, and Aram W. Harrow_\
_The quantum Schur transform: I. efficient qudit circuits._\
_In Proceedings of SODA 2007, pg. 1235-1244._\
[_arXiv:quant-ph/0601001_](http://arxiv.org/abs/quant-ph/0601001)_._\
\
_198S. Morita, H. Nishimori_\
_Mathematical foundation of quantum annealing._\
_Journal of Methematical Physics, 49(12):125210, 2008._\
\
_199A. B. Finnila, M. A. Gomez, C. Sebenik, C. Stenson, J. D. Doll_\
_Quantum annealing: a new method for minimizing multidimensional functions._\
_Chemical Physics Letters, 219:343-348, 1994._\
\
_200D. Gavinsky and T. Ito_\
_A quantum query algorithm for the graph collision problem._\
[_arXiv:1204.1527_](http://arxiv.org/abs/1204.1527)_, 2012._\
\
_201Andris Ambainis, Kaspars Balodis, Jānis Iraids, Raitis Ozols, and Juris Smotrovs_\
_Parameterized quantum query complexity of graph collision._\
[_arXiv:1305.1021_](http://arxiv.org/abs/1305.1021)_, 2013._\
\
_202Kevin C. Zatloukal_\
_Classical and quantum algorithms for testing equivalence of group extensions._\
[_arXiv:1305.1327_](http://arxiv.org/abs/1305.1327)_, 2013._\
\
_203Andrew Childs and Gábor Ivanyos_\
_Quantum computation of discrete logarithms in semigroups._\
[_arXiv:1310.6238_](http://arxiv.org/abs/1310.6238)_, 2013._\
\
_204Matan Banin and Boaz Tsaban_\
_A reduction of semigroup DLP to classic DLP._\
[_arXiv:1310.7903_](http://arxiv.org/abs/1310.7903)_, 2013._\
\
_205D. W. Berry, R. Cleve, and R. D. Somma_\
_Exponential improvement in precision for Hamiltonian-evolution simulation._\
[_arXiv:1308.5424_](http://arxiv.org/abs/1308.5424)_, 2013._\
\
_206François Le Gall and Harumichi Nishimura_\
_Quantum algorithms for matrix products over semirings._\
[_arXiv:1310.3898_](http://arxiv.org/abs/1310.3898)_, 2013._\
\
_207Nolan Wallach_\
_A quantum polylog algorithm for non-normal maximal cyclic hidden subgroups in the affine group of a finite field._\
[_arXiv:1308.1415_](http://arxiv.org/abs/1308.1415)_, 2013._\
\
_208Lov Grover_\
_Fixed-point quantum search._\
_Phys. Rev. Lett. 95(15):150501, 2005._\
[_arXiv:quant-ph/0503205_](http://arxiv.org/abs/quant-ph/0503205)\
\
_209Tathagat Tulsi, Lov Grover, and Apoorva Patel_\
_A new algorithm for fixed point quantum search._\
_Quantum Information and Computation 6(6):483-494, 2005._\
[_arXiv:quant-ph/0505007_](http://arxiv.org/abs/quant-ph/0505007)\
\
_210Guoming Wang_\
_Quantum algorithms for approximating the effective resistances of electrical networks._\
[_arXiv:1311.1851_](http://arxiv.org/abs/1311.1851)\
\
_211Dominic W. Berry, Andrew M. Childs, Richard Cleve, Robin Kothari, and Rolando D. Somma_\
_Exponential improvement in precision for simulating sparse Hamiltonians_\
[_arXiv:1312.1414_](http://arxiv.org/abs/1312.1414)\
\
_212Thomas Decker, Peter Høyer, Gabor Ivanyos, and Miklos Santha_\
_Polynomial time quantum algorithms for certain bivariate hidden polynomial problems_\
[_arXiv:1305.1543_](http://arxiv.org/abs/1305.1543)\
\
_213Kirsten Eisenträger, Sean Hallgren, Alexei Kitaev, and Fang Song_\
_A quantum algorithm for computing the unit group of an arbitrary degree number field_\
_In Proceedings of STOC 2014 pg. 293-302._\
\
_214Seth Lloyd, Masoud Mohseni, and Patrick Robentrost_\
_Quantum algorithms for supervised and unsupervised machine learning_\
[_arXiv:1307.0411_](http://arxiv.org/abs/1307.0411)\
\
_215Ashley Montanaro_\
_Quantum pattern matching fast on average_\
[_arXiv:1408.1816_](http://arxiv.org/abs/1408.1816)\
\
_216Charles H. Bennett, Ethan Bernstein, Gilles Brassard, and Umesh Vazirani_\
_Strengths and weaknesses of quantum computing_\
_SIAM J. Comput. 26(5):1524-1540, 1997_\
[_arXiv:quant-ph/9701001_](http://arxiv.org/abs/quant-ph/9701001)\
\
_217H. Ramesh and V. Vinay_\
_String matching in_ $$O˜(n−−√+m−−√)$$_quantum time_\
_Journal of Discrete Algorithms 1:103-110, 2003_\
[_arXiv:quant-ph/0011049_](http://arxiv.org/abs/quant-ph/0011049)\
\
_218Greg Kuperberg_\
_Another subexponential-time quantum algorithm for the dihedral hidden subgroup problem_\
_In Proceedings of TQC pg. 20-34, 2013_\
[_arXiv:1112.3333_](http://arxiv.org/abs/1112.3333)\
\
_219Peter Høyer, Jan Neerbek, and Yaoyun Shi_\
_Quantum complexities of ordered searching, sorting, and element distinctness_\
_In Proceedings of ICALP pg. 346-357, 2001_\
[_arXiv:quant-ph/0102078_](http://arxiv.org/abs/quant-ph/0102078)\
\
_220Amnon Ta-Shma_\
_Inverting well conditioned matrices in quantum logspace_\
_In Proceedings of STOC 2013 pg. 881-890._\
\
_221Nathan Wiebe, Ashish Kapoor, and Krysta Svore_\
_Quantum deep learning_\
[_arXiv:1412.3489_](http://arxiv.org/abs/1412.3489)\
\
_222Seth Lloyd, Silvano Garnerone, and Paolo Zanardi_\
_Quantum algorithms for topological and geometric analysis of big data_\
[_arXiv:1408.3106_](http://arxiv.org/abs/1408.3106)\
\
_223David A. Meyer and James Pommersheim_\
_Single-query learning from abelian and non-abelian Hamming distance oracles_\
[_arXiv:0912.0583_](http://arxiv.org/abs/0912.0583)\
\
_224Markus Hunziker, David A. Meyer, Jihun Park, James Pommersheim, and Mitch Rothstein_\
_The geometry of quantum learning_\
_Quantum Information Processing 9:321-341, 2010._\
[_arXiv:quant-ph/0309059_](http://arxiv.org/abs/quant-ph/0309059)\
\
_225Lawrence M. Ioannou and Michele Mosca_\
_Limitations on some simple adiabatic quantum algorithms_\
_International Journal of Quantum Information, 6(3):419-426, 2008._\
[_arXiv:quant-ph/0702241_](http://arxiv.org/abs/quant-ph/0702241)\
\
_226Michael Jarret and Stephen P. Jordan_\
_Adiabatic optimization without local minima_\
_Quantum Information and Computation, 15(3/4):0181-0199, 2015._\
[_arXiv:1405.7552_](http://arxiv.org/abs/1405.7552)\
\
_227Matthew B. Hastings, Dave Wecker, Bela Bauer, and Matthias Troyer_\
_Improving quantum algorithms for quantum chemistry_\
_Quantum Information and Computation, 15(1/2):0001-0021, 2015._\
[_arXiv:1403.1539_](http://arxiv.org/abs/1403.1539)\
\
_228Stephen P. Jordan, Keith S. M. Lee, and John Preskill_\
_Quantum simulation of scattering in scalar quantum field theories_\
_Quantum Information and Computation, 14(11/12):1014-1080, 2014._\
[_arXiv:1112.4833_](http://arxiv.org/abs/1112.4833)\
\
_229Stephen P. Jordan, Keith S. M. Lee, and John Preskill_\
_Quantum algorithms for fermionic quantum field theories_\
[_arXiv:1404.7115_](http://arxiv.org/abs/1404.7115)\
\
_230Gavin K. Brennen, Peter Rohde, Barry C. Sanders, and Sukhi Singh_\
_Multi-scale quantum simulation of quantum field theory using wavelets_\
[_arXiv:1412.0750_](http://arxiv.org/abs/1412.0750)\
\
_231Hefeng Wang, Sabre Kais, Alán Aspuru-Guzik, and Mark R. Hoffmann._\
_Quantum algorithm for obtaining the energy spectrum of molecular systems_\
_Physical Chemistry Chemical Physics, 10(35):5388-5393, 2008._\
[_arXiv:0907.0854_](http://arxiv.org/abs/0907.0854)\
\
_232Ivan Kassal and Alán Aspuru-Guzik_\
_Quantum algorithm for molecular properties and geometry optimization_\
_Journal of Chemical Physics, 131(22), 2009._\
[_arXiv:0908.1921_](http://arxiv.org/abs/0908.1921)\
\
_233James D. Whitfield, Jacob Biamonte, and Alán Aspuru-Guzik_\
_Simulation of electronic structure Hamiltonians using quantum computers_\
_Molecular Physics, 109(5):735-750, 2011._\
[_arXiv:1001.3855_](http://arxiv.org/abs/1001.3855)\
\
_234Borzu Toloui and Peter J. Love_\
_Quantum algorithms for quantum chemistry based on the sparsity of the CI-matrix_\
[_arXiv:1312.2529_](http://arxiv.org/abs/1312.2579)\
\
_235James D. Whitfield_\
_Spin-free quantum computational simulations and symmetry adapted states_\
_Journal of Chemical Physics, 139(2):021105, 2013._\
[_arXiv:1306.1147_](http://arxiv.org/abs/1306.1147)\
\
_236Andrew W. Cross, Graeme Smith, and John A. Smolin_\
_Quantum learning robust to noise_\
[_arXiv:1407.5088_](http://arxiv.org/abs/1407.5088)\
\
_237Aram W. Harrow and David J. Rosenbaum_\
_Uselessness for an oracle model with internal randomness_\
_Quantum Information and Computation 14(7/8):608-624, 2014_\
[_arXiv:1111.1462_](http://arxiv.org/abs/1111.1462)\
\
_238Jon R. Grice and David A. Meyer_\
_A quantum algorithm for Viterbi decoding of classical convolutional codes_\
[_arXiv:1405.7479_](http://arxiv.org/abs/1405.7479)\
\
_239Alexander Barg and Shiyu Zhou_\
_A quantum decoding algorithm of the simplex code_\
_Proceedings of the 36th Annual Allerton Conference, 1998_\
_Available at_ [_author's homepage_](http://www.ece.umd.edu/\~abarg/reprints/rm1dq.pdf)_._\
\
_240Guoming Wang_\
_Span-program-based quantum algorithm for tree detection_\
[_arXiv:1309.7713_](http://arxiv.org/abs/1309.7713)_, 2013._\
\
241François Le Gall, Harumichi Nishimura, and Seiichiro Tani\
Quantum algorithm for finding constant-sized sub-hypergraphs over 3-uniform hypergraphs\
In _Proceedings of COCOON, 2014. pg. 429-440_\
[arXiv:1310.4127](http://arxiv.org/abs/1310.4127)\
\
242Edward Farhi, Jeffrey Goldstone, and Sam Gutmann\
A quantum approximate optimization algorithm\
[_arXiv:1411.4028_](http://arxiv.org/abs/1411.4028), 2014.\
\
243Edward Farhi, Jeffrey Goldstone, and Sam Gutmann\
A quantum approximate optimization algorithm applied to a bounded occurrence constraint problem\
[_arXiv:1412.6062_](http://arxiv.org/abs/1412.6062), 2014.\
\
244Dominic W. Berry, Andrew M. Childs, Richard Cleve, Robin Kothari, and Rolando D. Somma\
Simulating Hamiltonian dynamics with a truncated Taylor series\
[_arXiv:1412.4687_](http://arxiv.org/abs/1412.4687), 2014.\
\
245Dominic W. Berry, Andrew M. Childs, and Robin Kothari\
Hamiltonian simulation with nearly optimal dependence on all parameters\
[_arXiv:1501.01715_](http://arxiv.org/abs/1501.01715), 2015.\
\
246Scott Aaronson\
Read the fine print\
_Nature Physics_ 11:291-293, 2015.\
\[[fulltext](http://www.scottaaronson.com/papers/qml.pdf)]\
\
247Alexander Elgart and George A. Hagedorn\
A note on the switching adiabatic theorem\
_Journal of Mathematical Physics_ 53(10):102202, 2012.\
[arXiv:1204.2318](http://arxiv.org/abs/1204.2318)\
\
248Daniel J. Bernstein, Johannes Buchmann, and Erik Dahmen, _Eds._\
Post-Quantum Cryptography\
[_Springer_](http://www.springer.com/mathematics/numbers/book/978-3-540-88701-0), 2009.\
\
249B. D. Clader, B. C. Jacobs, and C. R. Sprouse\
Preconditioned quantum linear system algorithm\
_Phys. Rev. Lett._ 110:250504, 2013.\
[arXiv:1301.2340](http://arxiv.org/abs/1301.2340)\
\
250S. Lloyd, M. Mohseni, and P. Rebentrost\
Quantum principal component analysis\
_Nature Physics._ 10(9):631, 2014.\
[arXiv:1307.0401](http://arxiv.org/abs/1307.0401)\
\
251Patrick Rebentrost, Masoud Mohseni, and Seth Lloyd\
Quantum support vector machine for big data classification\
_Phys. Rev. Lett._ 113, 130503, 2014.\
[arXiv:1307.0471](http://arxiv.org/abs/1307.0471)\
\
252J. M. Pollard\
Theorems on factorization and primality testing\
_Proceedings of the Cambridge Philosophical Society._ 76:521-228, 1974.\
\
253L. Babai, R. Beals, and A. Seress\
Polynomial-time theory of matrix groups\
In _Proceedings of STOC 2009_, pg. 55-64.\
\
254Neil J. Ross and Peter Selinger\
Optimal ancilla-free Clifford+T approximations of z-rotations\
[_arXiv:1403.2975_](http://arxiv.org/abs/1403.2975), 2014.\
\
255L. A. B. Kowada, C. Lavor, R. Portugal, and C. M. H. de Figueiredo\
A new quantum algorithm for solving the minimum searching problem\
_International Journal of Quantum Information, Vol. 6, No. 3, pg. 427-436_, 2008.\
\
256Sean Hallgren and Aram Harrow\
Superpolynomial speedups based on almost any quantum circuit\
_Proceedings of ICALP 2008_, pg. 782-795.\
[arXiv:0805.0007](http://arxiv.org/abs/0805.0007)\
\
257Fernando G.S.L. Brandao and Michal Horodecki\
Exponential quantum speed-ups are generic\
_Quantum Information and Computation_, Vol. 13, Pg. 0901, 2013\
[arXiv:1010.3654](http://arxiv.org/abs/1010.3654)\
\
258Scott Aaronson and Andris Ambainis\
Forrelation: A problem that optimally separates quantum from classical computing.\
[_arXiv:1411.5729_](http://arxiv.org/abs/1411.5729), 2014.\
\
259Z. Gedik\
Computational speedup with a single qutrit\
[_arXiv:1403.5861_](http://arxiv.org/abs/1403.5861), 2014.\
\
260Boaz Barak, Ankur Moitra, Ryan O'Donnell, Prasad Raghavendra, Oded Regev, David Steurer, Luca Trevisan, Aravindan Vijayaraghavan, David Witmer, and John Wright\
Beating the random assignment on constraint satisfaction problems of bounded degree\
[_arXiv:1505.03424_](http://arxiv.org/abs/1505.03424), 2015.\
\
261David Cornwell\
Amplified Quantum Transforms\
[_arXiv:1406.0190_](http://arxiv.org/abs/1406.0190), 2015.\
\
262T. Laarhoven, M. Mosca, and J. van de Pol\
Solving the shortest vector problem in lattices faster using quantum search\
_Proceedings of PQCrypto13_, pp. 83-101, 2013.\
[arXiv:1301.6176](http://arxiv.org/abs/1301.6176)\
\
263Andrew M. Childs, Robin Kothari, and Rolando D. Somma\
Quantum linear systems algorithm with exponentially improved dependence on precision\
[_arXiv:1511.02306_](http://arxiv.org/abs/1511.02306), 2015.\
\
264Ashley Montanaro\
Quantum walk speedup of backtracking algorithms\
[_arXiv:1509.02374_](http://arxiv.org/abs/1509.02374), 2015.\
\
265Ashley Montanaro\
Quantum speedup of Monte Carlo methods\
[_arXiv:1504.06987_](http://arxiv.org/abs/1504.06987), 2015.\
\
266Andris Ambainis, Aleksandrs Belovs, Oded Regev, and Ronald de Wolf\
Efficient quantum algorithms for (gapped) group testing and junta testing\
[_arXiv:1507.03126_](http://arxiv.org/abs/1507.03126), 2015.\
\
267A. Atici and R. A. Servedio\
Quantum algorithms for learning and testing juntas\
_Quantum Information Processing_, 6(5):323-348, 2007.\
[arXiv:0707.3479](http://arxiv.org/abs/0707.3479)\
\
268Aleksandrs Belovs\
Quantum algorithms for learning symmetric juntas via the adversary bound\
_Computational Complexity_, 24(2):255-293, 2015.\
(Also appears in proceedings of CCC'14).\
[arXiv:1311.6777](http://arxiv.org/abs/1311.6777)\
\
269Stacey Jeffery and Shelby Kimmel\
NAND-trees, average choice complexity, and effective resistance\
[_arXiv:1511.02235_](http://arxiv.org/abs/1511.02235), 2015.\
\
270Scott Aaronson, Shalev Ben-David, and Robin Kothari\
Separations in query complexity using cheat sheets\
[_arXiv:1511.01937_](http://arxiv.org/abs/1511.01937), 2015.\
\
271Frédéric Grosshans, Thomas Lawson, François Morain, and Benjamin Smith\
Factoring safe semiprimes with a single quantum query\
[_arXiv:1511.04385_](http://arxiv.org/abs/1511.04385), 2015.\
\
272Agnis Āriņš\
Span-program-based quantum algorithms for graph bipartiteness and connectivity\
[_arXiv:1510.07825_](http://arxiv.org/abs/1510.07825), 2015.\
\
273Juan Bermejo-Vega and Kevin C. Zatloukal\
Abelian hypergroups and quantum computation\
[_arXiv:1509.05806_](http://arxiv.org/abs/1509.05806), 2015.\
\
274Andrew Childs and Jeffrey Goldstone\
Spatial search by quantum walk\
_Physical Review A_, 70:022314, 2004.\
[arXiv:quant-ph/0306054](http://arxiv.org/abs/quant-ph/0306054)\
\
275Shantanav Chakraborty, Leonardo Novo, Andris Ambainis, and Yasser Omar\
Spatial search by quantum walk is optimal for almost all graphs\
[_arXiv:1508.01327_](http://arxiv.org/abs/1508.01327), 2015.\
\
276François Le Gall\
Improved quantum algorithm for triangle finding via combinatorial arguments\
In _Proceedings of the 55th IEEE Annual Symposium on Foundations of Computer Science (FOCS)_, pg. 216-225, 2014.\
[arXiv:1407.0085](http://arxiv.org/abs/1407.0085)\
\
277Ashley Montanaro\
The quantum complexity of approximating the frequency moments\
[_arXiv:1505.00113_](http://arxiv.org/abs/1505.00113), 2015.\
\
278Rolando D. Somma\
Quantum simulations of one dimensional quantum systems\
[_arXiv:1503.06319_](http://arxiv.org/abs/1503.06319), 2015.\
\
279Bill Fefferman and Cedric Yen-Yu Lin\
A complete characterization of unitary quantum space\
[_arXiv:1604.01384_](http://arxiv.org/abs/1604.01384), 2016.\
\
280Tsuyoshi Ito and Stacey Jeffery\
Approximate span programs\
[_arXiv:1507.00432_](http://arxiv.org/abs/1507.00432), 2015.\
\
281Arnau Riera, Christian Gogolin, and Jens Eisert\
Thermalization in nature and on a quantum computer\
_Physical Review Letters_, 108:080402 (2012)\
[arXiv:1102.2389](http://arxiv.org/abs/1102.2389).\
\
282Michael J. Kastoryano and Fernando G. S. L. Brandao\
Quantum Gibbs Samplers: the commuting case\
_Communications in Mathematical Physics_, 344(3):915-957 (2016)\
[arXiv:1409.3435](http://arxiv.org/abs/1409.3435).\
\
283Andrew M. Childs, David Jao, and Vladimir Soukharev\
Constructing elliptic curve isogenies in quantum subexponential time\
_Journal of Mathematical Cryptology_, 8(1):1-29 (2014)\
[arXiv:1012.4019](http://arxiv.org/abs/1012.4019).\
\
284Markus Grassl, Brandon Langenberg, Martin Roetteler, and Rainer Steinwandt\
Applying Grover's algorithm to AES: quantum resource estimates\
[_arXiv:1512.04965_](http://arxiv.org/abs/1512.04965), 2015.\
\
285M. Ami, O. Di Matteo, V. Gheorghiu, M. Mosca, A. Parent, and J. Schanck\
Estimating the cost of generic quantum pre-image attacks on SHA-2 and SHA-3\
[_arXiv:1603.09383_](http://arxiv.org/abs/1603.09383), 2016.\
\
286Marc Kaplan, Gaetan Leurent, Anthony Leverrier, and Maria Naya-Plasencia\
Quantum differential and linear cryptanalysis\
[_arXiv:1510.05836_](http://arxiv.org/abs/1510.05836), 2015.\
\
287Scott Fluhrer\
Quantum Cryptanalysis of NTRU\
[_Cryptology ePrint Archive: Report 2015/676_](https://eprint.iacr.org/2015/676), 2015.\
\
288Marc Kaplan\
Quantum attacks against iterated block ciphers\
[_arXiv:1410.1434_](http://arxiv.org/abs/1410.1434), 2014.\
\
289H. Kuwakado and M. Morii\
Quantum distinguisher between the 3-round Feistel cipher and the random permutation\
In _Proceedings of IEEE International Symposium on Information Theory (ISIT)_, pg. 2682-2685, 2010.\
\
290H. Kuwakado and M. Morii\
Security on the quantum-type Even-Mansour cipher\
In _Proceedings of International Symposium on Information Theory and its Applications (ISITA)_, pg. 312-316, 2012.\
\
291Martin Roetteler and Rainer Steinwandt\
A note on quantum related-key attacks\
[_arXiv:1306.2301_](http://arxiv.org/abs/1306.2301), 2013.\
\
292Thomas Santoli and Christian Schaffner\
Using Simon's algorithm to attack symmetric-key cryptographic primitives\
[_arXiv:1603.07856_](http://arxiv.org/abs/1603.07856), 2016.\
\
293Rolando D. Somma\
A Trotter-Suzuki approximation for Lie groups with applications to Hamiltonian simulation\
[_arXiv:1512.03416_](http://arxiv.org/abs/1512.03416), 2015.\
\
294Guang Hao Low and Isaac Chuang\
Optimal Hamiltonian simulation by quantum signal processing\
[_arXiv:1606.02685_](http://arxiv.org/abs/1606.02685), 2016.\
\
295Dominic W. Berry and Leonardo Novo\
Corrected quantum walk for optimal Hamiltonian simulation\
[_arXiv:1606.03443_](http://arxiv.org/abs/1606.03443), 2016.\
\
296Ashley Montanaro and Sam Pallister\
Quantum algorithms and the finite element method\
[_arXiv:1512.05903_](http://arxiv.org/abs/1512.05903), 2015.\
\
297Lin-Chun Wan, Chao-Hua Yu, Shi-Jie Pan, Fei Gao, and Qiao-Yan Wen\
Quantum algorithm for the Toeplitz systems\
[_arXiv:1608.02184_](http://arxiv.org/abs/1608.02184), 2016.\
\
298Salvatore Mandra, Gian Giacomo Guerreschi, and Alan Aspuru-Guzik\
Faster than classical quantum algorithm for dense formulas of exact satisfiability and occupation problems\
[_arXiv:1512.00859_](http://arxiv.org/abs/1512.00859), 2015.\
\
299J. Adcock, E. Allen, M. Day, S. Frick, J. Hinchliff, M. Johnson, S. Morley-Short, S. Pallister, A. Price, and S. Stanisic\
Advances in quantum machine learning\
[_arXiv:1512.02900_](http://arxiv.org/abs/1512.02900), 2015.\
\
300Cedric Yen-Yu Lin and Yechao Zhu\
Performance of QAOA on typical instances of constraint satisfaction problems with bounded degree\
[_arXiv:1601.01744_](http://arxiv.org/abs/1601.01744), 2016.\
\
301Dave Wecker, Matthew B. Hastings, and Matthias Troyer\
Training a quantum optimizer\
[_arXiv:1605.05370_](http://arxiv.org/abs/1605.05370), 2016.\
\
302Edward Farhi and Aram W. Harrow\
Quantum supremacy through the quantum approximate optimization algorithm\
[_arXiv:1602.07674_](http://arxiv.org/abs/1602.07674), 2016.\
\
303Thomas G. Wong\
Quantum walk search on Johnson graphs\
[_arXiv:1601.04212_](http://arxiv.org/abs/1601.04212), 2016.\
\
304Jonatan Janmark, David A. Meyer, and Thomas G. Wong\
Global symmetry is unnecessary for fast quantum search\
_Physical Review Letters_ 112:210502, 2014.\
[arXiv:1403.2228](http://arxiv.org/abs/1403.2228)\
\
305David A. Meyer and Thomas G. Wong\
Connectivity is a poor indicator of fast quantum search\
_Physical Review Letters_ 114:110503, 2014.\
[arXiv:1409.5876](http://arxiv.org/abs/1409.5876)\
\
306Thomas G. Wong\
Spatial search by continuous-time quantum walk with multiple marked vertices\
_Quantum Information Processing_ 15(4):1411-1443, 2016.\
[arXiv:1501.07071](http://arxiv.org/abs/1409.5876)\
\
307Anirban Naryan Chowdhury and Rolando D. Somma\
Quantum algorithms for Gibbs sampling and hitting-time estimation\
[_arXiv:1603.02940_](http://arxiv.org/abs/1603.02940), 2016.\
\
308Edward Farhi, Shelby Kimmel, and Kristan Temme\
A quantum version of Schoning's algorithm applied to quantum 2-SAT\
[_arXiv:1603.06985_](http://arxiv.org/abs/1603.06985), 2016.\
\
309Iordanis Kerenidis and Anupam Prakash\
Quantum recommendation systems\
_Innovations in Theoretical Computer Science (ITCS 2017)_, LIPIcs, vol. [67](http://drops.dagstuhl.de/opus/portals/lipics/index.php?semnr=16054), pg. [1868-8969](http://drops.dagstuhl.de/opus/volltexte/2017/8154/pdf/LIPIcs-ITCS-2017-49.pdf).\
\[[arXiv:1603.08675](http://arxiv.org/abs/1603.08675)]\
\
310Markus Reiher, Nathan Wiebe, Krysta M. Svore, Dave Wecker, and Matthias Troyer\
Elucidating reaction mechanisms on quantum computers\
[_arXiv:1605.03590_](http://arxiv.org/abs/1605.03590), 2016.\
\
311Aram W. Harrow and Ashley Montanaro\
Sequential measurements, disturbance, and property testing\
[_arXiv:1607.03236_](http://arxiv.org/abs/1607.03236), 2016.\
\
312Martin Roetteler\
Quantum algorithms for abelian difference sets and applications to dihedral hidden subgroups\
[_arXiv:1608.02005_](http://arxiv.org/abs/1608.02005), 2016.\
\
313Fernando G.S.L. Brandao and Krysta Svore\
Quantum speed-ups for semidefinite programming\
[_arXiv:1609.05537_](http://arxiv.org/abs/1609.05537), 2016.\
\
314Z-C Yang, A. Rahmani, A. Shabani, H. Neven, and C. Chamon\
Optimizing variational quantum algorithms using Pontryagins's minimum principle\
[_arXiv:1607.06473_](http://arxiv.org/abs/1607.06473), 2016.\
\
315Gilles Brassard, Peter Høyer, and Alain Tapp\
Quantum cryptanalysis of hash and claw-free functions\
In _Proceedings of the 3rd Latin American symposium on Theoretical Informatics (LATIN'98)_, pg. 163-169, 1998.\
\
316Daniel J. Bernstein\
Cost analysis of hash collisions: Will quantum computers make SHARCS obsolete?\
In _Proceedings of the 4th Workshop on Special-purpose Hardware for Attacking Cryptographic Systems (SHARCS'09)_, pg. 105-116, 2009.\
\[available [here](https://cr.yp.to/hash/collisioncost-20090517.pdf)]\
\
317Chris Cade, Ashley Montanaro, and Aleksandrs Belovs\
Time and space efficient quantum algorithms for detecting cycles and testing bipartiteness\
[_arXiv:1610.00581_](http://arxiv.org/abs/1610.00581), 2016.\
\
318A. Belovs and B. Reichardt\
Span programs and quantum algorithms for st-connectivity and claw detection\
In _European Symposium on Algorithms (ESA'12)_, pg. 193-204, 2012.\
[arXiv:1203.2603](http://arxiv.org/abs/1203.2603)\
\
319Titouan Carette, Mathieu Laurière, and Frédéric Magniez\
Extended learning graphs for triangle finding\
[_arXiv:1609.07786_](http://arxiv.org/abs/1609.07786), 2016.\
\
320F. Le Gall and N. Shogo\
Quantum algorithm for triangle finding in sparse graphs\
In _Proceedings of the 26th International Symposium on Algorithms and Computation (ISAAC'15)_, pg. 590-600, 2015.\
\
321Or Sattath and Itai Arad\
A constructive quantum Lovász local lemma for commuting projectors\
_Quantum Information and Computation_, 15(11/12)987-996pg, 2015.\
[arXiv:1310.7766](http://arxiv.org/abs/1310.7766)\
\
322Martin Schwarz, Toby S. Cubitt, and Frank Verstraete\
An information-theoretic proof of the constructive commutative quantum Lovász local lemma\
[_arXiv:1311.6474_](http://arxiv.org/abs/1311.6474)\
\
323C. Shoen, E. Solano, F. Verstraete, J. I. Cirac, and M. M. Wolf\
Sequential generation of entangled multi-qubit states\
_Physical Review Letters_, 95:110503, 2005.\
[arXiv:quant-ph/0501096](http://arxiv.org/abs/quant-ph/0501096)\
\
324C. Shoen, K. Hammerer, M. M. Wolf, J. I. Cirac, and E. Solano\
Sequential generation of matrix-product states in cavity QED\
_Physical Review A_, 75:032311, 2007.\
[arXiv:quant-ph/0612101](http://arxiv.org/abs/quant-ph/0612101)\
\
325Yimin Ge, András Molnár, and J. Ignacio Cirac\
Rapid adiabatic preparation of injective PEPS and Gibbs states\
_Physical Review Letters_, 116:080503, 2016.\
[arXiv:1508.00570](http://arxiv.org/abs/1508.00570)\
\
326Martin Schwarz, Kristan Temme, and Frank Verstraete\
Preparing projected entangled pair states on a quantum computer\
_Physical Review Letters_, 108:110502, 2012.\
[arXiv:1104.1410](http://arxiv.org/abs/1104.1410)\
\
327Martin Schwarz, Toby S. Cubitt, Kristan Temme, Frank Verstraete, and David Perez-Garcia\
Preparing topological PEPS on a quantum computer\
_Physical Review A_, 88:032321, 2013.\
[arXiv:1211.4050](http://arxiv.org/abs/1211.4050)\
\
328M. Schwarz, O. Buerschaper, and J. Eisert\
Approximating local observables on projected entangled pair states\
[arXiv:1606.06301](http://arxiv.org/abs/1606.06301), 2016.\
\
329Jean-François Biasse and Fang Song\
Efficient quantum algorithms for computing class groups and solving the principal ideal problem in arbitrary degree number fields\
_Proceedings of the 27th Annual ACM-SIAM Symposium on Discrete Algorithms (SODA '16)_, pg. 893-902, 2016.\
\
330Peter Høyer and Mojtaba Komeili\
Efficient quantum walk on the grid with multiple marked elements\
_Proceedings of the 34th Symposium on Theoretical Aspects of Computer Science (STACS 2017)_, 42, 2016.\
[arXiv:1612.08958](https://arxiv.org/abs/1612.08958)\
\
331Peter Wittek\
Quantum Machine Learning: what quantum computing means to data mining\
Academic Press, 2014.\
\
332Maria Schuld, Ilya Sinayskiy, and Francesco Petruccione\
An introduction to quantum machine learning\
_Contemporary Physics_, 56(2):172, 2014.\
[arXiv:1409.3097](https://arxiv.org/abs/1409.3097)\
\
333J. Biamonte, P. Wittek, N. Pancotti, P. Rebentrost, N. Wiebe, and S. Lloyd\
Quantum machine learning\
[_arXiv:1611.09347_](https://arxiv.org/abs/1611.09347)\
\
334Esma Aïmeur, Gilles Brassard, and Sébastien Gambs\
Machine learning in a quantum world\
In _Advances in Artificial Intelligence: 19th Conference of the Canadian Society for Computational Studies of Intelligence_ pg. 431-442, Springer, 2006.\
\
335Vedran Dunjko, Jacob Taylor, and Hans Briegel\
Quantum-enhanced machine learning\
_Phys. Rev. Lett_ 117:130501, 2016.\
\
336Nathan Wiebe, Ashish Kapoor, and Krysta Svore\
Quantum algorithms for nearest-neighbor methods for supervised and unsupervised learning\
_Quantum Information and Computation_ 15(3/4): 0318-0358, 2015.\
[arXiv:1401.2142](https://arxiv.org/abs/1401.2142)\
\
337Seokwon Yoo, Jeongho Bang, Changhyoup Lee, and Junhyoug Lee\
A quantum speedup in machine learning: finding a N-bit Boolean function for a classification\
_New Journal of Physics_ 6(10):103014, 2014.\
[arXiv:1303.6055](https://arxiv.org/abs/1303.6055)\
\
338Maria Schuld, Ilya Sinayskiy, and Francesco Petruccione\
Prediction by linear regression on a quantum computer\
_Physical Review A_ 94:022342, 2016.\
[arXiv:1601.07823](https://arxiv.org/abs/1601.07823)\
\
339Zhikuan Zhao, Jack K. Fitzsimons, and Joseph F. Fitzsimons\
Quantum assisted Gaussian process regression\
[_arXiv:1512.03929_](https://arxiv.org/abs/1512.03929)\
\
340Esma Aïmeur, Gilles Brassard, and Sébastien Gambs\
Quantum speed-up for unsupervised learning\
_Machine Learning_, 90(2):261-287, 2013.\
\
341Nathan Wiebe, Ashish Kapoor, and Krysta Svore\
Quantum perceptron models\
Advances in Neural Information Processing Systems 29 (NIPS 2016), pg. 3999–4007, 2016.\
[arXiv:1602.04799](https://arxiv.org/abs/1602.04799)\
\
342G. Paparo, V. Dunjko, A. Makmal, M. Martin-Delgado, and H. Briegel\
Quantum speedup for active learning agents\
\_Physical Review X\_4(3):031002, 2014.\
[arXiv:1401.4997](https://arxiv.org/abs/1401.4997)\
\
343Daoyi Dong, Chunlin Chen, Hanxiong Li, and Tzyh-Jong Tarn\
Quantum reinforcement learning\
\_IEEE Transactions on Systems, Man, and Cybernetics- Part B (Cybernetics)\_38(5):1207, 2008.\
\
344Daniel Crawford, Anna Levit, Navid Ghadermarzy, Jaspreet S. Oberoi, and Pooya Ronagh\
Reinforcement learning using quantum Boltzmann machines\
[_arXiv:1612.05695_](https://arxiv.org/abs/1612.05695), 2016.\
\
345Steven H. Adachi and Maxwell P. Henderson\
Application of Quantum Annealing to Training of Deep Neural Networks\
[_arXiv:1510.06356_](https://arxiv.org/abs/1510.06356), 2015.\
\
346M. Benedetti, J. Realpe-Gómez, R. Biswas, and A. Perdomo-Ortiz\
Quantum-assisted learning of graphical models with arbitrary pairwise connectivity\
[_arXiv:1609.02542_](https://arxiv.org/abs/1609.02542), 2016.\
\
348M. H. Amin, E. Andriyash, J. Rolfe, B. Kulchytskyy, and R. Melko\
Quantum Boltzmann machine\
[_arXiv:1601.02036_](https://arxiv.org/abs/1601.02036), 2016.\
\
349Peter Wittek and Christian Gogolin\
Quantum enhanced inference in Markov logic networks\
\_Scientific Reports\_7:45672, 2017.\
[arXiv:1611.08104](https://arxiv.org/abs/1611.08104), 2016.\
\
350N. H. Bshouty and J. C. Jackson\
Learning DNF over the uniform distribution using a quantum example oracle\
\_SIAM Journal on Computing\_28(3):1136-1153, 1999.\
\
351Srinivasan Arunachalam and Ronald de Wolf\
A survey of quantum learning theory\
[_arXiv:1701.06806_](https://arxiv.org/abs/1701.06806), 2017.\
\
352Rocco A. Servedio and Steven J. Gortler\
Equivalences and separations between quantum and classical learnability\
_SIAM Journal on Computing_, 33(5):1067-1092, 2017.\
\
353Srinivasan Arunachalam and Ronald de Wolf\
Optimal quantum sample complexity of learning algorithms\
[_arXiv:1607.00932_](https://arxiv.org/abs/1607.00932), 2016.\
\
354Alex Monràs, Gael Sentís, and Peter Wittek\
Inductive quantum learning: why you are doing it almost right\
[_arXiv:1605.07541_](https://arxiv.org/abs/1605.07541), 2016.\
\
355A. Bisio, G. Chiribella, G. M. D'Ariano, S. Facchini, and P. Perinotti\
Optimal quantum learning of a unitary transformation\
_Physical Review A_ 81:032324, 2010.\
[arXiv:0903.0543](https://arxiv.org/abs/0903.0543).\
\
356M. Sasaki, A. Carlini, and R. Jozsa\
Quantum template matching\
_Physical Review A_ 64:022317, 2001.\
[arXiv:quant-ph/0102020](https://arxiv.org/abs/quant-ph/0102020).\
\
357Masahide Sasaki and Alberto Carlini\
Quantum learning and universal quantum matching machine\
_Physical Review A_ 66:022303, 2002.\
[arXiv:quant-ph/0202173](https://arxiv.org/abs/quant-ph/0202173).\
\
358Esma Aïmeur, Gilles Brassard, and Sébastien Gambs\
Quantum clustering algorithms\
In _Proceedings of the 24th International Conference on Machine Learning (ICML)_, pg. 1-8, 2007.\
\
359Iordanis Kerenidis and Anupam Prakash\
Quantum gradient descent for linear systems and least squares\
[_arXiv:1704.04992_](https://arxiv.org/abs/1704.04992), 2017.\
\
360Dan Boneh and Mark Zhandry\
Quantum-secure message authentication codes\
In _Proceedings of Eurocrypt_, pg. 592-608, 2013.\
\
361A. M. Childs, W. van Dam, S-H Hung, and I. E. Shparlinski\
Optimal quantum algorithm for polynomial interpolation\
In _Proceedings of the 43rd International Colloquium on Automata, Languages, and Programming (ICALP)_, pg. 16:1-16:13, 2016.\
[arXiv:1509.09271](https://arxiv.org/abs/1509.09271)\
\
362Volker Strassen\
Einige Resultate über Berechnungskomplexität\
In _Jahresbericht der Deutschen Mathematiker-Vereinigung_, 78(1):1-8, 1976/1977.\
\
363Stacey Jeffery\
[Frameworks for Quantum Algorithms](http://uwspace.uwaterloo.ca/handle/10012/8710)\
PhD thesis, U. Waterloo, 2014.\
\
364Seiichiro Tani\
An improved claw finding algorithm using quantum walk\
In _Mathematical Foundations of Computer Science (MFCS)_, pg. 536-547, 2007.\
[arXiv:0708.2584](https://arxiv.org/abs/0708.2584)\
\
365K. Iwama and A. Kawachi\
A new quantum claw-finding algorithm for three functions\
_New Generation Computing_, 21(4):319-327, 2003.\
\
366D. J. Bernstein, N. Heninger, P. Lou, and L. Valenta\
Post-quantum RSA\
_IACR e-print_ [_2017/351_](https://eprint.iacr.org/2017/351), 2017.\
\
367Francois Fillion-Gourdeau, Steve MacLean, and Raymond Laflamme\
Quantum algorithm for the dsolution of the Dirac equation\
[_arXiv:1611.05484_](https://arxiv.org/abs/1611.05484), 2016.\
\
368Ali Hamed Moosavian and Stephen Jordan\
Faster quantum algorithm to simulate Fermionic quantum field theory\
[_arXiv:1711.04006_](https://arxiv.org/abs/1711.04006), 2017.\
\
369Pedro C.S. Costa, Stephen Jordan, and Aaron Ostrander\
Quantum algorithm for simulating the wave equation\
[_arXiv:1711.05394_](https://arxiv.org/abs/1711.05394), 2017.\
\
370Jeffrey Yepez\
Highly covariant quantum lattice gas model of the Dirac equation\
[_arXiv:1106.0739_](https://arxiv.org/abs/1711.05394), 2011.\
\
371Jeffrey Yepez\
Quantum lattice gas model of Dirac particles in 1+1 dimensions\
[_arXiv:1307.3595_](https://arxiv.org/abs/1307.3595), 2013.\
\
372Bruce M. Boghosian and Washington Taylor\
Simulating quantum mechanics on a quantum computer\
_Physica D_ 120:30-42, 1998.\
\[[arXiv:quant-ph/9701019](https://arxiv.org/abs/quant-ph/9701019)]\
\
373Yimin Ge, Jordi Tura, and J. Ignacio Cirac\
Faster ground state preparation and high-precision ground energy estimation on a quantum computer\
[_arXiv:1712.03193_](https://arxiv.org/abs/1712.03193), 2017.\
\
374Renato Portugal\
Element distinctness revisited\
[_arXiv:1711.11336_](https://arxiv.org/abs/1711.11336), 2017.\
\
375Kanav Setia and James D. Whitfield\
Bravyi-Kitaev superfast simulation of fermions on a quantum computer\
[_arXiv:1712.00446_](https://arxiv.org/abs/1712.00446), 2017.\
\
376Richard Cleve and Chunhao Wang\
Efficient quantum algorithms for simulating Lindblad evolution\
[_arXiv:1612.09512_](https://arxiv.org/abs/1612.09512), 2016.\
\
377M. Kliesch, T. Barthel, C. Gogolin, M. Kastoryano, and J. Eisert\
Dissipative quantum Church-Turing theorem\
_Physical Review Letters_ 107(12):120501, 2011.\
\[[arXiv:1105.3986](https://arxiv.org/abs/1105.3986)]\
\
378A. M. Childs and T. Li\
Efficient simulation of sparse Markovian quantum dynamics\
[_arXiv:1611.05543_](https://arxiv.org/abs/1611.05543), 2016.\
\
379R. Di Candia, J. S. Pedernales, A. del Campo, E. Solano, and J. Casanova\
Quantum simulation of dissipative processes without reservoir engineering\
_Scientific Reports_ 5:9981, 2015.\
\
380R. Babbush, D. Berry, M. Kieferová, G. H. Low, Y. Sanders, A. Sherer, and N. Wiebe\
Improved techniques for preparing eigenstates of Fermionic Hamiltonians\
[_arXiv:1711.10460_](https://arxiv.org/abs/1711.10460), 2017.\
\
381D. Poulin, A. Kitaev, D. S. Steiger, M. B. Hasting, and M. Troyer\
Fast quantum algorithm for spectral properties\
[_arXiv:1711.11025_](https://arxiv.org/abs/1711.11025), 2017.\
\
382Guang Hao Low and Isaac Chuang\
Hamiltonian simulation bt qubitization\
[_arXiv:1610.06546_](https://arxiv.org/abs/1610.06546), 2016.\
\
383F.G.S.L. Brandão, A. Kalev, T. Li, C. Y.-Y. Lin, K. M. Svore, and X. Wu\
Quantum SDP Solvers: Large Speed-ups, Optimality, and Applications to Quantum Learning\
_Proceedings of ICALP 2019_\
\[[arXiv:1710.02581](https://arxiv.org/abs/1710.02581)]\
\
384M. Ekerå and J. Håstad\
Quantum Algorithms for Computing Short Discrete Logarithms and Factoring RSA Integers\
[_Proceedings of PQCrypto 2017_](https://link.springer.com/chapter/10.1007/978-3-319-59879-6\_20), pg. 347-363. (LNCS Volume 10346), 2017.\
\
385M. Ekerå\
On post-processing in the quantum algorithm for computing short discrete logarithms\
[_IACR ePrint Archive Report 2017/1122_](https://eprint.iacr.org/2017/1122), 2017.\
\
386D. J. Bernstein, J.-F. Biasse, and M. Mosca\
A low-resource quantum factoring algorithm\
[_Proceedings of PQCrypto 2017_](https://link.springer.com/chapter/10.1007/978-3-319-59879-6\_19), pg. 330-346 (LNCS Volume 10346), 2017.\
\
387Jianxin Chen, Andrew M. Childs, and Shih-Han Hung\
Quantum algorithm for multivariate polynomial interpolation\
_Proceedings of the Royal Society A_, 474:20170480, 2017.\
[arXiv:1701.03990](http://arxiv.org/abs/1701.03990)\
\
388Lisa Hales and Sean Hallgren\
An improved quantum Fourier transform algorithm and applications.\
In _Proceedings of FOCS 2000_, pg. 515-525.\
\
389Igor Shparlinski and Arne Winterhof\
Quantum period reconstruction of approximate sequences\
_Information Processing Letters_, 103:211-215, 2007.\
\
390Alexander Russell and Igor E. Shparlinski\
Classical and quantum function reconstruction via character evaluation\
_Journal of Complexity_, 20:404-422, 2004.\
\
391Sean Hallgren, Alexander Russell, and Igor Shparlinski\
Quantum noisy rational function reconstruction\
_Proceedings of COCOON 2005_, pg. 420-429.\
\
392G. Ivanyos, M. Karpinski, M. Santha, N. Saxena, and I. Shparlinski\
Polynomial interpolation and identity testing from high powers over finite fields\
_Algorithmica_, 80:560-575, 2017.\
\
393Qi Cheng\
Primality Proving via One Round in ECPP and One Iteration in AKS\
_Journal of Cryptology_, Volume 20, Issue 3, pg. 375-387, July 2007.\
\
394Daniel J. Bernstein\
Proving primality in essentially quartic random time\
_Mathematics of Computation_, Vol. 76, pg. 389-403, 2007.\
\
395F. Morain\
Implementing the asymptotically fast version of the elliptic curve primality proving algorithm\
_Mathematics of Computation_, Vol. 76, pg. 493-505, 2007.\
\
396Alvaro Donis-Vela and Juan Carlos Garcia-Escartin\
A quantum primality test with order finding\
[_arXiv:1711.02616_](https://arxiv.org/abs/1711.02616), 2017.\
\
397H. F. Chau and H.-K. Lo\
Primality test via quantum factorization\
_International Journal of Modern Physics C_, Vol. 8, No. 2, pg. 131-138, 1997.\
\[[arXiv:quant-ph/9508005](https://arxiv.org/abs/quant-ph/9508005)]\
\
398David Harvey and Joris Van Der Hoeven\
Integer multiplication in time $$O(nlog n)$$\
[_hal-02070778_](https://hal.archives-ouvertes.fr/hal-02070778), 2019.\
\
399Charles Greathouse\
_personal communication_, 2019.\
\
400Ewin Tang\
A quantum-inspired classical algorithm for recommendation systems\
In _Proceedings of STOC 2019_, pg. 217-228.\
\[[arXiv:1807.04271](https://arxiv.org/abs/1807.04271)]\
\
401Ewin Tang\
Quantum-inspired classical algorithms for principal component analysis and supervised clustering\
[_arXiv:1811.00414_](https://arxiv.org/abs/1811.00414), 2018.\
\
402L. Wossnig, Z. Zhao, and A. Prakash\
A quantum linear system algorithm for dense matrices\
_Physical Review Letters_ vol. 120, no. 5, pg. 050502, 2018.\
[_arXiv:1704.06174_](https://arxiv.org/abs/1704.06174), 2017.\
\
403Zhikuan Zhao, Alejandro Pozas-Kerstjens, Patrick Rebentrost, and Peter Wittek\
Bayesian Deep Learning on a Quantum Computer\
_Quantum Machine Intelligence_ vol. 1, pg. 41-51, 2019.\
\[[arXiv:1806.11463](https://arxiv.org/abs/1806.11463)]\
\
404Anja Becker, Jean-Sebastien Coron, and Antoine Joux\
Improved generic algorithms for hard knapsacks\
_Proceedings of Eurocrypt 2011_ pg. 364-385\
\[[IACR eprint 2011/474](http://eprint.iacr.org/2011/474)]\
\
405Kun Zhang and Vladimir E. Korepin\
Low depth quantum search algorithm\
[_arXiv:1908.04171_](https://arxiv.org/abs/1908.04171), 2019.\
\
406Andriyan Bayo Suksmono and Yuichiro Minato\
Finding Hadamard matrices by a quantum annealing machine\
_Scientific Reports_ 9:14380, 2019.\
\[[arXiv:1902.07890](https://arxiv.org/abs/1902.07890)]\
\
407Gábor Ivanyos, Anupam Prakash, and Miklos Santha\
On learning linear functions from subset and its applications in quantum computing\
_26th Annual European Symposium on Algorithms (ESA 2018)_,LIPIcs volume 112, 2018.\
\[[arXiv:1806.09660](https://arxiv.org/abs/1806.09660)]\
\
408Gábor Ivanyos\
On solving systems of random linear disequations\
_Quantum Information and Computation_, 8(6):579-594, 2008.\
\[[arXiv:0704.2988](https://arxiv.org/abs/0704.2988)]\
\
409A. Ambainis, K. Balodis, J. Iraids, M. Kokainis, K. Prusis, and J. Vihrovs\
Quantum speedups for exponential-time dynamic programming algorithms\
_Proceedings of the 30th Annual ACM-SIAM Symposium on Discrete Algorithms (SODA 19)_, pg. 1783-1793, 2019.\
\[[arXiv:1807.05209](https://arxiv.org/abs/1807.05209)]\
\
410Dominic W. Berry, Andrew M. Childs, Aaron Ostrander, and Guoming Wang\
Quantum algorithm for linear differential equations with exponentially improved dependence on precision\
_Communications in Mathematical Physics_, 356(3):1057-1081, 2017.\
\[[arXiv:1701.03684](https://arxiv.org/abs/1701.03684)]\
\
411Sarah K. Leyton and Tobias J. Osborne\
Quantum algorithm to solve nonlinear differential equations\
[_arXiv:0812.4423_](https://arxiv.org/abs/0812.4423)\
\
412Y. Cao, A. Papageorgiou, I. Petras, J. Traub, and S. Kais\
Quantum algorithm and circuit design solving the Poisson equation\
_New Journal of Physics_ 15(1):013021, 2013.\
\[[arXiv:1207.2485](https://arxiv.org/abs/1207.2485)]\
\
413S. Wang, Z. Wang, W. Li, L. Fan, Z. Wei, and Y. Gu\
Quantum fast Poisson solver: the algorithm and modular circuit design\
[_arXiv:1910.09756_](https://arxiv.org/abs/1910.09756), 2019.\
\
414A. Scherer, B. Valiron, S.-C. Mau, S. Alexander, E. van den Berg, and T. Chapuran\
Concrete resource analysis of the quantum linear system algorithm used to compute the electromagnetic scattering crossection of a 2D target\
_Quantum Information Processing_ 16:60, 2017.\
\[[arXiv:1505.06552](https://arxiv.org/abs/1505.06552)]\
\
415Juan Miguel Arrazola, Timjan Kalajdziavski, Christian Weedbrook, and Seth Lloyd\
Quantum algorithm for nonhomogeneous linear partial differential equations\
_Physical Review A_ 100:032306, 2019.\
\[[arXiv:1809.02622](https://arxiv.org/abs/1809.02622)]\
\
416Andrew Childs and Jin-Peng Liu\
Quantum spectral methods for differential equations\
[_arXiv:1901.00961_](https://arxiv.org/abs/1901.00961)\
\
417Alexander Engle, Graeme Smith, and Scott E. Parker\
A quantum algorithm for the Vlasov equation\
[_arXiv:1907.09418_](https://arxiv.org/abs/1907.09418)\
\
418Shouvanik Chakrabarti, Andrew M. Childs, Tongyang Li, and Xiaodi Wu\
Quantum algorithms and lower bounds for convex optimization\
[_arXiv:1809.01731_](https://arxiv.org/abs/1809.01731)\
\
419S. Chakrabarti, A. M. Childs, S.-H. Hung, T. Li, C. Wang, and X. Wu\
Quantum algorithm for estimating volumes of convex bodies\
[_arXiv:1908.03903_](https://arxiv.org/abs/1908.03903)\
\
420Joran van Apeldoorn, András Gilyén, Sander Gribling, and Ronald de Wolf\
Convex optimization using quantum oracles\
[_arXiv:1809.00643_](https://arxiv.org/abs/1809.00643)\
\
421Nai-Hui Chia, Andráas Gilyén, Tongyang Li, Han-Hsuan Lin, Ewin Tang, and Chunhao Wang\
Sampling-based sublinear low-rank matrix arithmetic framework for dequantizing quantum machine learning\
_Proceedings of STOC 2020_, pg. 387-400\
\[[arXiv:1910.06151](https://arxiv.org/abs/1910.06151)]\
\
422Andris Ambainis and Martins Kokainis\
Quantum algorithm for tree size estimation, with applications to backtracking and 2-player games\
_Proceedings of STOC 2017_, pg. 989-1002\
\[[arXiv:1704.06774](https://arxiv.org/abs/1704.06774)]\
\
423Fernando G.S L. Brandão, Richard Kueng, Daniel Stilck França\
Faster quantum and classical SDP approximations for quadratic binary optimization\
[_arXiv:1909.04613_](https://arxiv.org/abs/1909.04613)\
\
424Matthew B. Hastings\
Classical and Quantum Algorithms for Tensor Principal Component Analysis\
_Quantum_ 4:237, 2020.\
\[[arXiv:1907.12724](https://arxiv.org/abs/1907.12724)]\
\
425Joran van Apeldoorn, András Gilyén, Sander Gribling, and Ronald de Wolf\
Quantum SDP-Solvers: Better upper and lower bounds\
_Quantum_ 4:230, 2020.\
\[[arXiv:1705.01843](https://arxiv.org/abs/1705.01843)]\
\
426J-P Liu, H. Kolden, H. Krovi, N. Loureiro, K. Trivisa, and A. M. Childs\
Efficient quantum algorithm for dissipative nonlinear differential equations\
[_arXiv:2011.03185_](https://arxiv.org/abs/2011.03185)\
\
427S. Lloyd, G. De Palma, C. Gokler, B. Kiani, Z-W Liu, M. Marvian, F. Tennie, and T. Palmer\
Quantum algorithm for nonlinear differential equations\
[_arXiv:2011.06571_](https://arxiv.org/abs/2011.06571)\
\
428Yunchao Liu, Srinivasan Arunachalam, and Kristan Temme\
A rigorous and robust quantum speed-up in supervised machine learning\
[_arXiv:2010.02174_](https://arxiv.org/abs/2010.02174)\
\
429Matthew B. Hastings\
The power of adiabatic quantum computation with no sign problem\
[_arXiv:2005.03791_](https://arxiv.org/abs/2005.03791)\
\
430Nathan Ramusat and Vincenzo Savona\
A quantum algorithm for the direct estimation of the steady state of open quantum systems\
[_arXiv:2008.07133_](https://arxiv.org/abs/2008.07133)
