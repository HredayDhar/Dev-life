# 03-CPU-OPTIMIZATION

## CPU Optimization Techniques

CPU optimization focuses on improving the efficiency of processor utilization, reducing computational overhead, and making better use of CPU resources. As transistor densities have increased following Moore's Law, single-threaded performance gains have diminished, making efficient CPU utilization increasingly important for overall system performance.

This phase covers techniques for optimizing CPU usage across different levels, from algorithmic choices to low-level instruction optimizations.

## CPU Performance Fundamentals

Before applying specific CPU optimization techniques, it's essential to understand how CPU performance is measured and what factors affect it.

### CPU Performance Metrics

#### Instructions Per Cycle (IPC)
- **Definition**: Average number of instructions executed per clock cycle
- **Theoretical Maximum**: Depends on CPU architecture (e.g., 4-6 for modern x86 CPUs)
- **Typical Values**: Often much lower than theoretical maximum due to stalls and dependencies
- **Importance**: Key indicator of how efficiently CPU resources are utilized

#### Clock Cycles Per Instruction (CPI)
- **Definition**: Average number of clock cycles per instruction (inverse of IPC)
- **Components**:
  - Base CPI: Ideal cycles per instruction without stalls
  - Stall Cycles: Additional cycles due to various hazards
- **Formula**: CPI = Base CPI + Stall Cycles from memory + Stall Cycles from dependencies + ...

#### CPU Utilization
- **Definition**: Percentage of time the CPU spends doing useful work vs. idle
- **Measurement**: Typically sampled over intervals (e.g., top, vmstat, perfstat)
- **Importance**: High utilization doesn't always mean good performance (could be spinning on locks)

#### Context Switch Rate
- **Definition**: Number of times per second the OS switches between processes/threads
- **Cost**: Typically 5-20 microseconds per switch on modern systems
- **Impact**: High rates can consume significant CPU time

### CPU Performance Bottlenecks

Understanding where CPU time is lost is crucial for effective optimization.

#### Pipeline Stalls
Modern CPUs use pipelining to execute multiple instructions simultaneously. Stalls occur when the pipeline cannot proceed.

- **Data Hazards**: Instruction depends on result of previous instruction not yet available
  - *Example*: `ADD R1, R2, R3` followed immediately by `SUB R4, R1, R5`
- **Control Hazards**: Branches cause pipeline flushes when predicted incorrectly
  - *Example*: Mispredicted branch in an if-else statement
- **Structural Hazards**: Hardware resource conflicts
  - *Example*: Two instructions needing the same functional unit simultaneously

#### Memory Hierarchy Stalls
CPU often waits for data from memory systems.

- **L1 Cache Miss**: Data not in fastest cache (typically 4-cycle penalty)
- **L2 Cache Miss**: Data not in L2 cache (typically 10-20 cycle penalty)
- **L3 Cache Miss**: Data not in L3 cache (typically 30-50 cycle penalty)
- **Main Memory Access**: Data must be fetched from RAM (typically 100-300 cycle penalty)
- **NUMA Remote Access**: Accessing memory on different CPU socket (additional penalty)

#### Instruction Dependencies
CPU execution units may be idle waiting for operands.

- **True Dependencies (RAW)**: Instruction needs result of previous instruction
- **Anti-Dependencies (WAR)**: Instruction writes register that previous instruction reads
- **Output Dependencies (WAW)**: Two instructions write to same register

#### Branch Mispredictions
When CPU incorrectly predicts branch direction, pipeline must be flushed.

- **Cost**: Typically 10-20 cycles depending on pipeline depth
- **Impact**: Particularly harmful in tight loops with unpredictable branches
- **Mitigation**: Branch prediction hints, loop restructuring, branchless programming

### CPU Optimization Strategy Framework

Effective CPU optimization follows a hierarchical approach:

1. **Algorithmic Optimization** (Biggest Impact)
   - Choose better algorithms and data structures
   - Reduce computational complexity (O(n²) → O(n log n) → O(n))

2. **Data Structure Optimization** (High Impact)
   - Optimize for cache locality and access patterns
   - Reduce pointer chasing and indirect access

3. **Compile-Time Optimization** (Medium Impact)
   - Enable appropriate compiler optimizations
   - Use compiler intrinsics and pragmas
   - Profile-guided optimization (PGO)

4. **Low-Level Optimization** (Smaller but Cumulative Impact)
   - Instruction selection and scheduling
   - Loop transformations
   - Function inlining
   - Branch optimization

## Algorithmic Optimization

The most significant CPU performance gains come from choosing better algorithms.

### Complexity Reduction
Moving to a lower complexity class often yields order-of-magnitude improvements.

#### Common Complexity Classes
- **O(1)**: Constant time (hash table lookups, array indexing)
- **O(log n)**: Logarithmic time (binary search, balanced tree operations)
- **O(n)**: Linear time (simple iteration, linear search)
- **O(n log n)**: Linearithmic time (efficient sorts, FFT)
- **O(n²)**: Quadratic time (naive matrix multiplication, bubble sort)
- **O(n³)**: Cubic time (naive matrix multiplication, some DP)
- **O(2ⁿ)**: Exponential time (brute-force search, some backtracking)

#### Examples of Algorithmic Improvements
- **Sorting**: Bubble sort (O(n²)) → Merge/Quick sort (O(n log n))
- **Search**: Linear search (O(n)) → Binary search (O(log n)) → Hash lookup (O(1))
- **Graph Algorithms**: Floyd-Warshall (O(n³)) → Dijkstra with heap (O((V+E)log V))
- **Dynamic Programming**: Naive recursion (O(2ⁿ)) → Memoization (O(n²))
- **String Matching**: Naive (O(nm)) → KMP (O(n+m))

### Algorithmic Optimization Techniques

#### Divide and Conquer
Break problem into smaller subproblems, solve independently, combine results.
- **Examples**: Merge sort, Quick sort, FFT, Strassen's matrix multiplication
- **When to Use**: Problems that can be partitioned into similar subproblems

#### Dynamic Programming
Solve complex problems by breaking them into overlapping subproblems.
- **Key Insight**: Store results of subproblems to avoid recomputation
- **Examples**: Fibonacci sequence, Knapsack problem, Longest Common Subsequence
- **When to Use**: Problems with optimal substructure and overlapping subproblems

#### Greedy Algorithms
Make locally optimal choices at each step hoping to find global optimum.
- **When to Use**: Problems where local optimum leads to global optimum
- **Examples**: Huffman coding, Activity selection, Minimum spanning tree (Kruskal's/Prim's)

#### Hashing
Use hash tables for constant-time lookups.
- **When to Use**: Need frequent lookups by key
- **Considerations**: Hash function quality, collision handling, load factor
- **Examples**: Symbol caches, memoization tables, frequency counting

#### Precomputation and Caching
Compute values once and reuse them.
- **Techniques**: Lookup tables, memoization, memoization
- **When to Use**: Expensive computations with repetitive inputs
- **Examples**: Trigonometric tables, factorial tables, collision detection grids

### When Algorithmic Optimization Isn't Enough

Sometimes even optimal algorithms can be CPU-bound due to:
- High constant factors
- Poor cache performance
- Branch mispredictions
- Instruction-level inefficiencies

In these cases, lower-level optimizations become important.

## Data Structure Optimization for CPU Efficiency

How data is organized and accessed dramatically affects CPU performance due to memory hierarchy effects.

### Cache Locality Principles
CPU caches work best when data access patterns are predictable and localized.

#### Temporal Locality
- **Concept**: Recently accessed data is likely to be accessed again soon
- **Optimization**: Reuse data while it's still in cache
- **Examples**: Loop invariants, reusable temporary variables

#### Spatial Locality
- **Concept**: Data near recently accessed data is likely to be accessed soon
- **Optimization**: Access data in predictable patterns (sequential, strides)
- **Examples**: Array traversal, structure-of-arrays vs. array-of-structures

#### Sequential Prefetching
- **Concept**: CPU hardware predicts sequential access and prefetches cache lines
- **Optimization**: Access memory sequentially to enable hardware prefetching
- **Examples**: Linear array traversal, sequential file processing

### Data Layout Optimization

#### Array of Structures (AoS) vs. Structure of Arrays (SoA)
- **AoS**: `[{x1,y1,z1}, {x2,y2,z2}, {x3,y3,z3}]` - good for accessing all fields of one object
- **SoA**: `[{x1,x2,x3}, {y1,y2,y3}, {z1,z2,z3}]` - good for accessing same field across many objects
- **When to Use SoA**: When processing same attribute across many objects (physics simulations, graphics)
- **When to Use AoS**: When frequently accessing all attributes of individual objects

#### Padding and Alignment
- **Problem**: Misaligned data causes extra memory accesses or faults
- **Solution**: Align data to natural boundaries (typically 4, 8, 16, 32, or 64 bytes)
- **Trade-Off**: Alignment may waste space but improve access speed
- **Tools**: Compiler alignment attributes (`alignas`, `__attribute__((aligned))`)

#### Data Compression for Cache Efficiency
- **Concept**: Store data in compressed form to fit more in cache
- **Trade-Off**: CPU time to decompress vs. memory bandwidth saved
- **When Effective**: When memory bandwidth is bottleneck and decompression is cheap
- **Examples**: Bit-packing, dictionary compression, delta encoding

#### Memory Pool Allocation
- **Problem**: Frequent allocation/deallocation causes fragmentation and allocator overhead
- **Solution**: Pre-allocate pools of fixed-size objects
- **Benefits**: Faster allocation, reduced fragmentation, better cache locality
- **When to Use**: High-frequency allocation/deallocation of same-sized objects

### Access Pattern Optimization

#### Loop Interchange
- **Problem**: Poor cache performance due to non-sequential access
- **Solution**: Change loop nesting order to access data sequentially
- **Example**: 
  ```
  // Poor: Column-major access in row-major language
  for (int j = 0; j < COLS; j++) {
    for (int i = 0; i < ROWS; i++) {
      sum += array[i][j];  // Jumping by ROWS*sizeof(element) each time
    }
  }
  
  // Better: Row-major access
  for (int i = 0; i < ROWS; i++) {
    for (int j = 0; j < COLS; j++) {
      sum += array[i][j];  // Sequential access
    }
  }
  ```

#### Loop Tiling (Blocking)
- **Problem**: Large arrays don't fit in cache, causing thrashing
- **Solution**: Process data in small blocks that fit in cache
- **Example**:
  ```
  // Naive matrix multiplication
  for (int i = 0; i < N; i++) {
    for (int j = 0; j < N; j++) {
      for (int k = 0; k < N; k++) {
        C[i][j] += A[i][k] * B[k][j];
      }
    }
  }
  
  // Tiled version
  for (int ii = 0; ii < N; ii += TILE_SIZE) {
    for (int jj = 0; jj < N; jj += TILE_SIZE) {
      for (int kk = 0; kk < N; kk += TILE_SIZE) {
        for (int i = ii; i < min(ii+TILE_SIZE, N); i++) {
          for (int j = jj; j < min(jj+TILE_SIZE, N); j++) {
            for (int k = kk; k < min(kk+TILE_SIZE, N); k++) {
              C[i][j] += A[i][k] * B[k][j];
            }
          }
        }
      }
    }
  }
  ```

#### Loop Unrolling
- **Problem**: Loop overhead (branch, increment) consumes significant CPU time
- **Solution**: Reduce branch frequency by doing multiple iterations per loop cycle
- **Benefits**: Reduced branch penalty, increased instruction-level parallelism
- **Trade-Off**: Increased code size, potential register pressure
- **Example**:
  ```
  // Original
  for (int i = 0; i < n; i++) {
    sum += arr[i];
  }
  
  // Unrolled by 4
  for (int i = 0; i < n; i += 4) {
    sum += arr[i];
    sum += arr[i+1];
    sum += arr[i+2];
    sum += arr[i+3];
  }
  // Handle remainder
  ```

## Compile-Time Optimization

Modern compilers are sophisticated optimization engines that can significantly improve CPU efficiency.

### Compiler Optimization Levels

#### -O0 (No Optimization)
- **Purpose**: Debugging, fastest compilation
- **Characteristics**: No optimizations, direct translation of source to assembly
- **Use Case**: Debugging when optimizations might obscure code

#### -O1 (Basic Optimization)
- **Purpose**: Reduce code size and execution time without significant compilation time increase
- **Optimizations**: Dead code elimination, common subexpression elimination, basic loop optimizations
- **Use Case**: General purpose when wanting some optimization without extreme trade-offs

#### -O2 (Standard Optimization)
- **Purpose**: Good balance of optimization and compilation time
- **Optimizations**: All -O1 optimizations plus instruction scheduling, register allocation, loop unrolling
- **Use Case**: Most production builds, recommended default for release

#### -O3 (Aggressive Optimization)
- **Purpose**: Maximize performance, may increase code size and compilation time
- **Optimizations**: All -O2 optimizations plus aggressive inlining, vectorization, loop transformations
- **Use Case**: Performance-critical applications where code size is secondary
- **Caution**: Can sometimes decrease performance due to increased cache pressure

#### -Os/-Oz (Size Optimization)
- **Purpose**: Minimize code size
- **Optimizations**: Optimize for small code size rather than speed
- **Use Case**: Embedded systems, memory-constrained environments

#### -Ofast (Fast Math)
- **Purpose**: Enable floating-point optimizations that may violate standards
- **Optimizations**: All -O3 optimizations plus unsafe math optimizations
- **Use Case**: When floating-point precision requirements are relaxed
- **Caution**: May produce incorrect results for IEEE-compliant code

### Key Compiler Optimization Techniques

#### Inlining
- **Concept**: Replace function call with function body to eliminate call overhead
- **Benefits**: Removes call/return overhead, enables further optimizations in context
- **Trade-Off**: Increases code size, may cause instruction cache pressure
- **Control**: Compiler heuristics, `inline` keyword, `__attribute__((always_inline))`

#### Loop Optimizations
- **Unrolling**: As described earlier, reduces branch overhead
- **Fusion**: Combine adjacent loops that iterate over same range
- **Fission**: Split loop with mixed dependencies into multiple loops
- **Interchange**: Change nesting order for better locality
- **Tiling/Bocking**: As described earlier for cache efficiency
- **Vectorization**: Convert scalar operations to SIMD operations

#### Vectorization (SIMD)
- **Concept**: Process multiple data elements with single instruction
- **Widths**: Typically 2, 4, 8, or 16 elements depending on data type and CPU features
- **Instruction Sets**: SSE, AVX, AVX2, AVX-512 (x86); NEON (ARM); AltiVec/VSX (PowerPC)
- **When Effective**: Data-parallel operations on homogeneous data
- **Challenges**: Data alignment, handling remainder elements, memory bandwidth limits
- **Modern Approaches**: 
  - Auto-vectorization (compiler does it automatically)
  - Explicit vectorization (intrinsics or SIMD libraries)
  - ISPC (Intel SPMD Program Compiler)

#### Profile-Guided Optimization (PGO)
- **Concept**: Compile, run with profiler, recompile using profile data
- **Benefits**: Better branch prediction, inlining decisions, layout optimizations
- **Process**: 
  1. Build with profiling instrumentation (`-fprofile-generate`)
  2. Run with representative workload
  3. Rebuild using profile data (`-fprofile-use`)
- **Tools**: GCC `fprofile-generate`/`fprofile-use`, LLVM equivalent, MSVC PGO

#### Link-Time Optimization (LTO)
- **Concept**: Perform optimizations at link time across translation units
- **Benefits**: Cross-module inlining, dead code elimination, better register allocation
- **Process**: Compile to intermediate representation, link with optimization phase
- **Trade-Off**: Increased link time, but can yield significant performance improvements
- **Tools**: GCC `flto`, LLVM LTO, MSVC `/LTO`

#### Branch Optimization
- **Predictable Branches**: Help compiler predict likely branch outcomes
- **Branchless Code**: Eliminate branches using conditional moves or arithmetic
- **Likely/Unlikely Hints**: `__builtin_expect` (GCC/LLVM), `__assume` (MSVC)
- **Examples**:
  ```
  // With branch hint (assuming error is rare)
  if (__builtin_expect((error_code == 0), 1)) {
    // common case
  } else {
    // rare error case
  }
  
  // Branchless alternative for simple cases
  result = (condition) ? value_if_true : value_if_false;
  // Becomes: result = value_if_false + condition * (value_if_true - value_if_false);
  ```

## Low-Level CPU Optimization Techniques

When algorithmic and data structure optimizations aren't sufficient, low-level techniques can provide additional gains.

### Instruction Selection and Scheduling

#### Instruction Choice
- **Problem**: Some instructions are slower than others on specific microarchitectures
- **Solution**: Use faster equivalent instructions when available
- **Examples**:
  - `x * 2` → `x << 1` (shift is often faster than multiply)
  - `x / 2` → `x >> 1` (for unsigned integers)
  - `memset(ptr, 0, size)` → hardcoded loop for small sizes (avoids function call)
  - `pow(x, 2.0)` → `x * x` (avoids expensive function call)

#### Instruction Scheduling
- **Problem**: CPU execution units idle due to data dependencies
- **Solution**: Reorder instructions to hide latency
- **Techniques**:
  - Separate dependent instructions with independent ones
  - Use loop unrolling to create more scheduling opportunities
  - Schedule load instructions early to hide memory latency
- **Tools**: Compilers do this automatically with `-O2`/`-O3`, but manual scheduling possible in assembly

### Register Optimization

#### Register Pressure
- **Problem**: Too many live variables cause register spilling to stack
- **Solution**: Reduce number of simultaneously live variables
- **Techniques**:
  - Limit variable scopes
  - Reuse variables for different purposes when lifetimes don't overlap
  - Use temporary variables instead of complex expressions
  - Split long live ranges into shorter ones

#### Calling Conventions
- **Problem**: Function calls waste time saving/restoring registers
- **Solution**: Understand and optimize for calling conventions
- **Knowledge**: Which registers are caller-saved vs. callee-saved
- **Optimization**: 
  - Pass frequently used values in registers rather than on stack
  - Minimize cross-call register usage when possible

### Memory Access Optimization

#### Prefetching
- **Problem**: CPU stalls waiting for data from memory
- **Solution**: Explicitly request data before it's needed
- **Intrinsics**: `_mm_prefetch` (x86), `__builtin_prefetch` (GCC/LLVM)
- **Strides**: 
  - Hardware prefetchers work best with sequential access
  - Software prefetching helps with predictable but non-sequential patterns
- **Timing**: Prefetch far enough ahead to hide latency but not so far as to evict useful data

#### Memory Alignment
- **Problem**: Misaligned memory accesses cause extra bus transactions or faults
- **Solution**: Align data to natural boundaries
- **Requirements**:
  - Scalar types: Natural alignment (size of type)
  - SIMD types: Typically 16 bytes for SSE, 32 bytes for AVX, 64 bytes for AVX-512
  - Stack alignment: Typically 16 bytes for ABI compliance
- **Tools**: `alignas`, `__attribute__((aligned))`, `posix_memalign`, `_aligned_malloc`

#### Store-to-Load Forwarding
- **Problem**: CPU stalls when load follows store to same address
- **Solution**: Increase distance between store and subsequent load
- **Techniques**:
  - Reorder independent instructions between store and load
  - Use temporary variables to break dependence chains
  - Consider whether the store is actually necessary

### Branch Optimization

Branch misprediction is a significant source of CPU stalls.

#### Branch Prediction Awareness
- **Understand**: How your target CPU predicts branches
- **Static Predictors**: Backward taken, forward not taken (common default)
- **Dynamic Predictors**: History-based (gshare, tournament predictors)

#### Branchless Programming
- **Concept**: Eliminate branches using arithmetic, logic, or conditional moves
- **When Effective**: Simple conditions, predictable outcomes
- **Techniques**:
  - **Conditional Moves**: `cmov` instructions (x86) or equivalent
  - **Bit Masks**: Use boolean values as 0/1 masks
  - **Arithmetic Tricks**: Use multiplication by 0/1 to select values
  - **Lookup Tables**: Precompute results for small input domains
- **Examples**:
  ```
  // Branchy version
  int abs(int x) {
    if (x < 0) return -x;
    else return x;
  }
  
  // Branchless version
  int abs(int x) {
    int mask = x >> (sizeof(int)*8 - 1);  // All 1's if negative, all 0's if positive
    return (x + mask) ^ mask;
  }
  
  // Alternative branchless
  int abs(int x) {
    return (x > 0) ? x : -x;  // Compiler may convert to cmov
  }
  ```

#### Loop Branch Optimization
- **Problem**: Loop branches execute frequently, mispredictions costly
- **Solutions**:
  - **Loop Unrolling**: Reduce branch frequency
  - **Loop Inversion**: Convert while loop to do-while with explicit test
  - **Sentinel Values**: Eliminate bounds checking in search loops
  - **Count Down to Zero**: Some CPUs have faster branch for comparison to zero

### Function Call Optimization

Function calls have measurable overhead that can add up in hot paths.

#### Call Overhead Sources
- **Parameter Passing**: Moving arguments to registers/stack
- **Return Address Storage**: Saving where to return after call
- **Frame Pointer Setup**: Establishing stack frame (optional with optimizations)
- **Register Saving**: Saving caller-saved registers that will be modified
- **Return Value Handling**: Getting result back to caller

#### Optimization Techniques
- **Inlining**: As discussed earlier, eliminates call overhead entirely
- **Leaf Function Optimization**: Functions that don't call other functions
  - Often can use registers exclusively for parameters
  - May not need stack frame
- **Parameter Optimization**: 
  - Pass small structures by value rather than pointer (avoids indirection)
  - Use registers for first few parameters (per calling convention)
  - Consider passing frequently accessed values in globals (with caution)
- **Return Value Optimization (RVO)**: 
  - Eliminate copying when returning large objects
  - Particularly important in C++ with copy-elision guarantees

## CPU Optimization by Language/Platform

Different languages and platforms offer different optimization opportunities and constraints.

### C/C++ Optimization

#### Compiler Specifics
- **GCC/Clang**: `-O3 -march=native -flto -fprofile-generate`/`fprofile-use`
- **MSVC**: `/O2 /GL /LTO /QxHost` (similar concepts)
- **Intel ICC**: Often best for Intel-specific optimizations

#### Key Techniques
- **Intrinsics**: Access to SIMD instructions without assembly (`_mm_add_ps`, etc.)
- **Assembly**: For critical hot spots when compiler isn't sufficient
- **Attribute Specifiers**: 
  - `__attribute__((hot))`, `__attribute__((cold))`
  - `__attribute__((pure))`, `__attribute__((const))`
  - `__attribute__((malloc))`, `__attribute__((returns_nonnull))`
- **Link-Time Optimization**: `-flto` for whole-program optimization

#### Memory Allocation
- **Custom Allocators**: For specific allocation patterns (slab, pool, buddy)
- **Allocator Selection**: `jemalloc`, `tcmalloc` for better performance than glibc malloc
- **Allocation Hints**: `mmap` with `MAP_POPULATE`, `malloc_trim`

### Java/JVM Optimization

#### JIT Compilation Tuning
- **Tiered Compilation**: `-XX:+TieredCompilation` (client then server compiler)
- **Compile Thresholds**: `-XX:CompileThreshold` (when to compile methods)
- **Inlining Controls**: `-XX:InlineSmallCode`, `-XX:MaxFreqInlineSize`
- **Escape Analysis**: `-XX:+DoEscapeAnalysis` (enables scalar replacement, stack allocation)

#### Garbage Collection Interaction
- **GC Choice**: Different GCs have different CPU overhead characteristics
- **Parallel GC**: `-XX:+UseParallelGC` (good CPU utilization but stop-the-world pauses)
- **G1 GC**: `-XX:+UseG1GC` (balanced pause times and throughput)
- **ZGC/Shenandoah**: Ultra-low pause times, different CPU overhead profile

#### Specific Techniques
- **String Interning**: Reduce memory usage but has CPU cost
- **Primitive Collections**: Avoid autoboxing overhead (fastutil, HPPC)
- **Array Access**: Bounds checking elimination when JVM can prove safety
- **Loop Unrolling**: JVM does this automatically in compiled methods

### .NET Optimization

#### RyuJIT Specifics
- **Tiered Compilation**: ReadyToRun + JIT for faster startup
- **Tiered Compilation Settings**: `COMPlus_TieredCompilation`
- **Inlining Heuristics**: Controlled by JIT tuning options
- **SIMD Support**: `System.Numerics.Vectors` for cross-platform SIMD

#### Garbage Collection
- **GC Modes**: Workstation vs. Server GC (different CPU/memory tradeoffs)
- **Latency Modes**: `GCSettings.LatencyLevel` for different GC behaviors
- **Large Object Heap**: Special handling for objects >85KB

#### Specific Techniques
- **Value Types**: Use `struct` for small data to avoid heap allocation
- **Span<T>**: Safe, efficient slicing without allocation
- **Memory<T>**: Similar to Span but usable across await boundaries
- **Array Pooling**: `ArrayPool<T>.Shared` to reuse arrays
- **Async Value Types**: `ValueTask<T>` to avoid allocation in async paths

### Python Optimization

#### Implementation Choice
- **CPython**: Reference implementation, access to C extensions
- **PyPy**: JIT-compiled, often faster for long-running Python
- **Cython**: Compile Python to C for performance-critical sections
- **Numba**: JIT for numerical Python code
- **Pyodide**: CPython compiled to WebAssembly

#### Optimization Techniques
- **Built-in Functions**: Use implemented-in-C functions when possible
- **Local Variable Access**: Faster than global or attribute access
- **Tuple Unpacking**: Efficient for swapping and multiple assignment
- **Generator Expressions**: Lazy evaluation to avoid intermediate lists
- **String Building**: `str.join()` rather than `+` in loops
- **List Comprehensions**: Often faster than equivalent loops
- **C Extensions**: Move hot spots to C/C++ for significant speedups

#### Profiling-Guided Optimization
- **cProfile**: Identify hot spots
- **line_profiler**: See which lines consume time
- **memory_profiler**: Track memory usage
- **snakeviz**: Visualize profiler output

### JavaScript/Node.js Optimization

#### V8 Specifics
- **Hidden Classes**: Optimize object property access
- **Inline Caching**: Speed up property and method access
- **Turbofan**: Optimizing compiler
- **Ignition**: Interpreter
- **Orinoco**: Garbage collector

#### Optimization Techniques
- **Monomorphic Properties**: Keep object shapes consistent
- **Arrays**: Use dense arrays, avoid holes
- **String Concatenation**: Use `join()` for multiple strings
- **Typed Arrays**: `Uint8Array`, `Float64Array` for efficient binary data
- **WebAssembly**: Move hot spots to Wasm for near-native performance
- **Node.js Specific**: 
  - `--max-old-space-size`: Control memory usage
  - `--trace-opt`: See what gets optimized
  - `--trace-deopt`: See what gets deoptimized and why

#### Async/Await Optimization
- **Avoid Unnecessary Async**: Synchronous functions are faster
- **Pool Reuse**: Reuse database connections, HTTP clients
- **Batching**: Combine multiple operations when possible
- **Stream Processing**: Avoid buffering large amounts in memory

## CPU Optimization in Specific Domains

Different application domains have characteristic CPU optimization opportunities.

### Game Development
- **Frame Budget**: Typically 16.67ms for 60 FPS, 33.33ms for 30 FPS
- **Hot Spots**: Rendering, physics, AI, audio processing
- **Techniques**:
  - **Data-Oriented Design**: Organize data for cache efficiency
  - **Entity-Component-System (ECS)**: Improves cache locality
  - **Object Pooling**: Reduce allocation/deallocation during gameplay
  - **Frustum Culling**: Avoid rendering invisible objects
  - **Level of Detail (LOD)**: Reduce complexity for distant objects
  - **SIMD Math**: Vector and matrix operations using SIMD
  - **Lock-Free Queues**: For thread-safe communication without mutexes

### Scientific Computing/HPC
- **Focus**: Maximum FLOPS (floating-point operations per second)
- **Hot Spots**: Linear algebra, FFT, particle simulations
- **Techniques**:
  - **BLAS/LAPACK**: Optimized linear algebra libraries
  - **FFTW**: Fastest Fourier Transform in the West
  - **Vectorization**: Critical for achieving peak FLOPS
  - **NUMA Awareness**: Memory placement for multi-socket systems
  - **MPI Optimization**: Reduce communication overhead
  - **OpenMP**: Shared-memory parallelism
  - **GPU Offloading**: When applicable, use GPUs for massively parallel tasks

### Database Systems
- **Focus**: Query throughput and transaction processing
- **Hot Spots**: Query parsing, optimization, execution, locking, logging
- **Techniques**:
  - **Hash Joins**: Often faster than nested loop or merge joins
  - **Index Optimization**: B-tree variants, bitmap indexes, learned indexes
  - **Query Optimization**: Cost-based optimization, join ordering
  - **Locking**: Reader-writer locks, lock-free data structures, optimistic concurrency
  - **Logging**: Group commit, batch logging
  - **Buffer Pool**: Efficient buffer replacement algorithms (LRU-K, 2Q)
  - **Prefetching**: Asynchronous I/O to overlap computation and I/O

### Web Servers
- **Focus**: Requests per second, latency under load
- **Hot Spots**: Parsing, routing, business logic, serialization
- **Techniques**:
  - **Async I/O**: Handle many connections with few threads
  - **Zero-Copy**: Avoid copying data between kernel and user space
  - **Template Engines**: Pre-compiled templates, efficient variable substitution
  - **Serialization**: Fast JSON/XML parsers (simdjson, RapidXML, protobuf)
  - **Caching**: Multi-level caching (L1 in-process, L2 distributed like Redis)
  - **Connection Pooling**: Reuse expensive connections (database, HTTP)
  - **Compression**: Negotiate gzip/brotli when bandwidth is constrained

### Embedded Systems
- **Focus**: Meeting deadlines with limited resources
- **Hot Spots**: Interrupt handlers, control loops, communication stacks
- **Techniques**:
  - **Fixed-Point Arithmetic**: Avoid floating-point when possible
  - **Lookup Tables**: Replace expensive functions with table lookups
  - **Bit-Banging**: Efficient GPIO control when hardware peripherals unavailable
  - **DMA**: Use direct memory access to offload CPU
  - **Interrupt Minimization**: Reduce frequency and duration of interrupts
  - **Sleep Modes**: Maximize time in low-power states
  - **Compiler Options**: `-Os` for size, `-march` for target-specific optimizations

### Real-Time Systems
- **Focus**: Predictable, bounded latency rather than average case
- **Hot Spots**: Interrupt handling, task scheduling, resource access
- **Techniques**:
  - **Rate-Monotonic Scheduling**: Assign priorities based on period
  - **Earliest Deadline First**: Dynamic priority assignment
  - **Priority Inheritance**: Prevent priority inversion
  - **Lock-Free Data Structures**: Avoid unbounded blocking
  - **Worst-Case Execution Time (WCET) Analysis**: Bound execution time
  - **Cache Locking/Pinning**: Prevent cache eviction of critical code
  - **Memory Protection Units (MPUs)**: Prevent errant memory access

## Measuring CPU Optimization Effectiveness

Knowing whether your CPU optimizations actually helped is crucial.

### Benchmarking Best Practices

#### Use Representative Workloads
- **Production Traces**: Replay actual production workloads when possible
- **Synthetic Benchmarks**: Only when they accurately reflect real usage patterns
- **Varied Input**: Test with different data sizes, distributions, and patterns

#### Control the Environment
- **Dedicated Hardware**: Avoid noisy neighbors in shared environments
- **Thermal Throttling**: Ensure CPU isn't throttling due to heat
- **Frequency Scaling**: Disable dynamic frequency scaling for consistent measurements
- **Background Processes**: Minimize interfering background activity

#### Statistical Rigor
- **Warm-Up Periods**: Allow JIT compilers, caches to reach steady state
- **Multiple Iterations**: Run tests multiple times to account for variability
- **Confidence Intervals**: Report uncertainty in measurements
- **Outlier Detection**: Identify and handle anomalous runs appropriately

#### Metric Selection
- **Throughput**: Operations per second (higher is better)
- **Latency**: Response time (lower is better, consider percentiles)
- **CPU Utilization**: Percentage of time spent doing useful work
- **Energy Efficiency**: Performance per watt (important for mobile/cloud)
- **Instruction Metrics**: IPC, cache miss rates, branch misprediction rates

### Profiling-Driven Validation

#### Before/After Comparisons
- **Hot Spot Reduction**: Measure time spent in optimized functions
- **Call Graph Changes**: See how optimization affected overall execution flow
- **Resource Usage**: Check CPU, memory, I/O usage changes
- **Regression Testing**: Ensure functional correctness is maintained

#### Microbenchmark Validation
- **Isolated Testing**: Test optimization in isolation to measure specific effect
- **Assembly Inspection**: Verify compiler generated expected instructions
- **Counter-Based Validation**: Use hardware performance counters to confirm hypotheses

### Common Pitfalls in CPU Optimization Measurement

#### Ignoring System Effects
- **Local vs. Global**: Optimization that helps microbenchmark might hurt overall system
- **Resource Shifting**: Optimization might move bottleneck from CPU to memory/I/O
- **Always Test in Context**: Validate optimizations in realistic system scenarios

#### Overlooking Cold Start vs. Steady-State
- **Different Phases**: Some optimizations help cold start, others steady-state
- **JIT Effects**: Managed languages have different behavior during warm-up
- **Measure Both**: Understand impact on application startup and long-running performance

#### Misinterpreting Compiler Output
- **Optimization Levels**: Different `-Ox` levels may enable/disable optimizations
- **Target Architecture**: `-march`, `-mtune` affect instruction selection
- **Floating Point Mode**: `-ffast-math` etc. can change behavior and performance
- **Verify Assembly**: Check what the compiler actually generated

#### Confusing Correlation with Causation
- **Multiple Changes**: When making several optimizations, hard to isolate effects
- **Optimization Interactions**: One optimization might enable or disable another
- **Change One Thing at a Time**: For clear attribution of performance effects

## CPU Optimization Case Studies

### Case Study 1: Sorting Algorithm Optimization
- **Problem**: Application spent 40% of CPU time in sorting routine
- **Initial**: Quicksort implementation with poor pivot selection
- **Optimization**: 
  - Switched to introsort (quicksort + heapsort fallback) for worst-case O(n log n)
  - Added median-of-three pivot selection
  - Used insertion sort for small subarrays (<10 elements)
  - Implemented branchless partition loop
- **Result**: CPU time in sorting reduced to 15%, overall application 25% faster

### Case Study 2: Hash Table Lookup Optimization
- **Problem**: High-latency hash table lookups in network packet processing
- **Analysis**: 
  - Many cache misses due to poor hash table layout
  - Hash function had poor distribution causing collisions
  - Linked list chaining caused pointer chasing
- **Optimization**:
  - Switched to open addressing with linear probing
  - Used hash function with better avalanche properties
  - Made hash table size power of two for faster modulo
  - Prefetched next probe location
- **Result**: 60% reduction in hash table lookup latency, 35% increase in packet processing rate

### Case Study 3: JSON Parsing Optimization
- **Problem**: Web API bottleneck in JSON parsing
- **Analysis**:
  - Library allocated many temporary strings
  - Repeated scanning of input buffer
  - Poor memory locality in object construction
- **Optimization**:
  - Switched to simdjson (uses SIMD for parsing)
  - Implemented object reuse to reduce allocations
  - Used arena allocator for temporary memory
  - Avoided DOM construction when possible (direct field access)
- **Result**: 10x improvement in JSON parsing throughput

### Case Study 4: Matrix Multiplication Optimization
- **Problem**: Scientific application bottleneck in matrix multiplication
- **Analysis**:
  - Naive triple-loop implementation
  - Poor cache performance due to column-major access in row-major language
  - No utilization of SIMD capabilities
- **Optimization**:
  - Implemented loop tiling for L1/L2 cache efficiency
  - Changed to row-major access pattern throughout
  - Used compiler auto-vectorization with `-O3 -march=native`
  - Added explicit SIMD intrinsics for critical sections
  - Ensured memory alignment for SIMD loads/stores
- **Result**: 12x improvement in matrix multiplication throughput

## CPU Optimization Checklist

When optimizing for CPU efficiency, consider:

### Algorithmic Level
- [ ] Can asymptotic complexity be reduced?
- [ ] Are better algorithms available for this problem?
- [ ] Can precomputation or caching help?
- [ ] Are data structures optimal for access patterns?

### Data Structure Level
- [ ] Is data layout optimal for cache efficiency?
- [ ] Are access patterns sequential and predictable?
- [ ] Is padding/alignment appropriate?
- [ ] Would memory pools reduce allocation overhead?

### Compile-Time Level
- [ ] Are appropriate compiler optimization flags used?
- [ ] Would profile-guided optimization help?
- [ ] Is link-time optimization enabled?
- [ ] Are compiler-specific intrinsics available for hot spots?

### Instruction Level
- [ ] Can expensive operations be replaced with cheaper equivalents?
- [ ] Are there opportunities for loop unrolling?
- [ ] Can vectorization (SIMD) be applied?
- [ ] Are branches predictable and optimizable?
- [ ] Can branchless alternatives be used for simple conditions?
- [ ] Is instruction scheduling optimal?
- [ ] Are registers used efficiently (minimizing spilling)?

### Memory Access Level
- [ ] Are memory accesses aligned appropriately?
- [ ] Would prefetching help hide memory latency?
- [ ] Are store-to-load dependencies minimized?
- [ ] Is memory access pattern optimal for hardware prefetchers?

### Function Call Level
- [ ] Can hot functions be inlined?
- [ ] Are calling conventions optimized for parameter passing?
- [ ] Are return values handled efficiently (RVO)?
- [ ] Are leaf functions optimized for register usage?

### Measurement and Validation
- [ ] Are benchmarks using representative workloads?
- [ ] Is the environment controlled and consistent?
- [ ] Are statistical methods used to validate improvements?
- [ ] Are optimizations verified not to introduce regressions?
- [ ] Is the optimization actually addressing a real bottleneck?

## Conclusion

CPU optimization is a multi-layered discipline that spans from high-level algorithmic choices to low-level instruction-level details. The most effective approach combines:

1. **Algorithmic Optimization** for the biggest potential gains
2. **Data Structure Optimization** to maximize cache efficiency
3. **Compile-Time Optimization** to leverage modern compiler capabilities
4. **Low-Level Optimization** for fine-tuning hot spots

Remember that CPU optimization should always be guided by measurement. Profile first to identify actual bottlenecks, then apply techniques hierarchically from algorithmic down to instruction level. Validate that your optimizations actually improve performance in realistic contexts, and beware of common pitfalls like premature optimization and micro-optimizations at the expense of clarity.

The goal is not to use every possible optimization technique, but to apply the right techniques in the right places to meet performance objectives while maintaining code quality and correctness.

Next, explore **04-MEMORY-OPTIMIZATION.md** to learn techniques for reducing memory usage and improving memory access patterns.
