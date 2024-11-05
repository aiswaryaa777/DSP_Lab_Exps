# Experiment 08: Overlap Save and Overlap Add Method


The overlap-save and overlap-add methods in digital signal processing (DSP) are used to efficiently perform convolution, particularly with long signals and finite impulse response (FIR) filters. These methods provide the following advantages:

- **Memory Management:** When dealing with long signals, performing convolution in one step may be impractical due to memory constraints. The methods divide signals into smaller, manageable segments.
- **Streaming Applications:** These methods allow for continuous real-time processing without needing the entire signal upfront.
- **Variable Lengths:** They can handle filters of varying lengths and are adaptable to different segment sizes, making them versatile for different applications.

### Overlap-Save Method
1. **Segment the Input Signal:** Divide the input signal into blocks and add \(M-1\) elements of the previous block to the start of each block, where \(M\) is the length of the second sequence. Zero pad the second sequence to match the block size.
2. **Convolution:** Perform circular convolution on each block with the second sequence.
3. **Discard Overlap:** Discard the first \(M-1\) elements of each result.
4. **Concatenate Results:** Concatenate the valid segments to form the final output signal.

### Overlap-Add Method
1. **Segment the Input Signal:** Divide the input signal into blocks and add \(M-1\) zeros to the end of each block, where \(M\) is the length of the second sequence. Zero pad the second sequence to match the block size.
2. **Convolution:** Perform circular convolution on each block with the second sequence.
3. **Final Result:** Apply a shift equal to \(M-1\) and add the convolutions to obtain the final output signal.
