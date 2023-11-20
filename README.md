# Image-Denoising-using-Cpp-and-Rust
## * Problem Statement:
The primary objective of this project is to implement image denoising using the median filter technique in both C++ and Rust programming languages. The project aims to assess and compare the performance, readability, and efficiency of the two implementations. Input images in the Portable Gray Map (PGM) format will be provided, and the goal is to develop denoised images while considering execution time, memory usage, and code readability in both languages.

POPL Angle:
The POPL (Principles of Programming Languages) angle in this project lies in the adherence to fundamental programming principles in both C++ and Rust. Key aspects include proper error handling, use of functional programming constructs, modularity, and type safety. The project aligns with the principles of writing readable, maintainable, and efficient code while utilizing the features specific to each language.

Previous Solutions:
While image denoising with median filters is a well-explored problem, the project's focus on comparing implementations in C++ and Rust provides a unique angle. While similar tasks may have been addressed previously, the specific comparison between these two languages for image denoising using median filters may not have been extensively explored.

Differences in Solution:
The project differentiates itself by implementing the same image denoising technique in both C++ and Rust, facilitating a direct comparison. The differences will be highlighted in terms of language-specific features, syntax, memory management, and overall coding practices. Any optimizations made for each language will be documented, providing valuable insights into the strengths and weaknesses of the respective implementations.

Challenges Faced:
The challenges encountered during the project may include language-specific difficulties, optimization trade-offs, and adapting the algorithm to the idioms of C++ and Rust. Differences in memory management and performance considerations specific to each language may pose challenges that will be documented and analyzed in the comparative study.

Expected Deliverables:
1. Implementation of the median filter for image denoising in C++.
2. Implementation of the median filter for image denoising in Rust.
3. Denoised images generated by both implementations.
4. Comparative analysis report covering performance metrics, code readability, and language-specific considerations.
5. Documentation outlining the algorithms, data structures, and language-specific features utilized in each implementation.


2) Software architecture:

The software architecture for the image denoising project can follow a modular structure, separating concerns for input/output, image processing, and comparison analysis.

1. Input/Output Module:
   - Responsible for handling file I/O operations, reading input images, and saving denoised images.
   - May include components for reading PGM files and writing denoised images in PGM format.

2. Image Processing Module:
   - Implements the median filter algorithm for image denoising.
   - Separates the algorithmic logic from I/O operations for better modularity.
   - Handles the core functionality of processing pixels and applying the median filter.

3. Comparison Analysis Module:
   - Evaluates and compares performance metrics, code readability, and efficiency between C++ and Rust implementations.
   - Gathers data on execution time, memory usage, and any language-specific features used in each implementation.



4. Testing Component:
   - Can be a separate module or part of the Image Processing Module.
   - Involves unit tests for individual functions/methods, integration tests for modules, and possibly benchmarking for performance evaluation.
   - Testing can be both local and, if applicable, remote (especially for performance tests).


5.Reusability:
   - The input/output handling components (reading/writing PGM files) can be reused from existing libraries or code snippets.
   - If there are established median filter libraries in C++ or Rust, they can be used or adapted for the project.
   - Language-agnostic algorithms for image processing may be reusable between the C++ and Rust implementations.



6.Testing Component Placement:
   - Unit tests can be run locally during development to ensure the correctness of individual functions.
   - Integration tests, especially those involving multiple modules, can be run locally.
   - Performance tests may involve remote testing to evaluate the software's behavior under different conditions.











3)  POPL Aspects:
Here are some points related to POPL (Principles of Programming Languages) aspects in the provided code:

1. Error Handling with Result:
   - Lines: `fn main() -> std::io::Result<()> {`
   - The use of `std::io::Result` indicates proper error handling. It follows the Result monad pattern, where functions return a `Result` to handle potential errors.

2. Immutable Variables:
   - Lines: `let mut arra: Vec<Vec<i32>> = vec![vec![0; 2000]; 2000];`
   - The use of `mut` indicates mutable variables, but most variables are not mutated after their initial assignment, promoting immutability where possible.

3. File I/O and Ownership:
   - Lines: `let file = File::open("mona_lisa.pgm")?;`
   - Ownership principles are followed when opening and handling files. The `File` instances take ownership of system resources and release them when they go out of scope.

4. Functional Style Iteration:
   - Lines: `for row in 0..=numrows {` and `for col in1..=numcols {` 
- The use of iterators and functional-style looping constructs promotes a more declarative programming style, enhancing code readability and maintainability.

5. Pattern Matching:
   - Lines: `if let Some(Ok(input_line)) = lines.next() {`
   - The code uses pattern matching (`if let`) to handle different cases during file reading, making the code more expressive and robust.

6. Code Modularity:
   - The code is somewhat modular, with different sections dedicated to reading input, processing data, and writing output. Each section focuses on a specific task, following good modular programming practices.

7. Constant Array Size:
   - Lines: `let mut window: [i32; 9] = [0; 9];`
   - The use of a fixed-size array for the 'window' indicates a specific design choice to have a constant-size data structure, which can lead to better performance in some cases.

8. Explicit Type Annotations:
   - Lines: `let mut arra: Vec<Vec<i32>> = vec![vec![0; 2000]; 2000];`
   - Explicitly annotating types enhances code readability and helps prevent potential type-related bugs.

9. Documentation and Comments:
   - While not prevalent in the provided code, the inclusion of comments or documentation is essential for understanding the code's purpose and functionality. This adherence to good documentation practices aligns with POPL principles.

10. Avoiding Unnecessary Mutability:
    - Lines: `for row in 0..=numrows { arra[row][0] = 0; }`
    - The use of mutable variables is minimized where unnecessary, promoting a more functional style and reducing the risk of unintended side effects.

Difficulties Faced:
   - The code seems relatively well-structured and follows good practices. However, without a detailed understanding of the project requirements or the specific challenges faced during development, it's challenging to pinpoint difficulties. Overall, the code appears to align with POPL principles, emphasizing readability, maintainability, and robust error handling.

