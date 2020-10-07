# Image-Search-Tool

**Objective:** Given an image, find the nearest neighbours of it from a database.

**Approach:** Using LSH (Local Sensitive Hashing) to find approximate near neighbours.

**Dataset of Images:**
[Patches.csv](https://drive.google.com/file/d/10KeXosZYNqPfuPNPxievxtUVAkhxV3ON/view?usp=sharing)
    Each row in this dataset is a 20 × 20 image patch represented as a 400-dimensional vector.

**Theory behind the approach:**
Assume we have a dataset A of n points in a metric space with distance metric d(·, ·). Let c be a constant greater than 1. Then, the (c, λ)-Approximate Near Neighbor (ANN) problem is defined as follows: Given a query point z, assuming that there is a point x in the dataset with d(x,z) ≤ λ, return a point x′ from the dataset with d(x′,z) ≤ cλ (this point is called a (c,λ)-ANN). The parameter c therefore represents the maximum approximation factor allowed and is a user-defined parameter.

Let us consider an LSH family H of hash functions that is (λ, cλ, p<sub>1</sub>, p<sub>2</sub>)-sensitive for the distance measure d(·,·). Let G = H<sup>k</sup> = {g = (h<sub>1</sub>,...,h<sub>k</sub>)|h<sub>i</sub> ∈ H, ∀ 1 ≤ i ≤ k}, where k = log<sub>1/p2</sub> (n).

**The code compares performance of LSH with that of linear search.**
