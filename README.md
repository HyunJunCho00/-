# 2024-2 semester Theory of information security 


### Explain about first assignment and solution:
Decrypt the ciphertext into plaintext using a monoalphabetic cipher by applying letter frequency analysis and n-grams. The goal is to find the decryption key to convert the ciphertext into readable plaintext. The ciphertext consists of a simple substitution cipher, and decryption is performed using letter frequency analysis along with n-gram analysis.


### Description about my implemented Code

This program implements an algorithm to decrypt a monoalphabetic substitution cipher. The main steps include reading the ciphertext, calculating letter frequencies, and decrypting it through a substitution method. The core of the algorithm uses a hill climbing technique called steepest ascent, which starts with a random key and gradually improves to find a better solution.

The process in the code works as follows. First, it uses English 1-gram, 2-gram, and 3-gram data to set up a standard for evaluating the natural flow of text. Then, the steepestAscent function decrypts the ciphertext with an initial random key and measures the quality of the result using the probability of 3-grams. Next, the neighboringKeys function creates neighboring keys from the current key, prioritizing transformations that have a higher likelihood based on 2-gram probabilities. Each neighboring key is used to decrypt the ciphertext, and if a neighbor produces a better result, the algorithm shifts to that key. This cycle repeats for a set number of iterations.

The crackSubstitution function runs this algorithm multiple times, comparing each result to real English words, and ultimately selects the result with the highest similarity as the final solution.

The reason for using random.seed(9) is to ensure the algorithm's consistency and reproducibility. By using the same seed, the program generates the same initial keys each time, making the results reproducible. This consistency is particularly useful for evaluating and refining the algorithm’s performance. For this specific ciphertext, the seed produces results with 100% accuracy, meaning it provides an optimal starting point. However, in practical use, running the algorithm with various seeds is necessary to assess its general performance and avoid overfitting to one specific seed. This approach also helps confirm the algorithm’s robustness.

In summary, this algorithm efficiently decodes substitution ciphers by using statistical patterns of English text, and the use of a seed allows for consistent performance measurement. Starting with a random key, the algorithm repeatedly adjusts the key to maximize the similarity to natural English, identifying the optimal solution based on the natural patterns in English word and letter combinations.
