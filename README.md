# moonshine_cpp_examples
Examples for using moonshine_cpp in external cmake C++ project

## Building

To build this repository, simply run the following set of commands:

```bash
cmake -B build
cd build/
make -j4
```

## moonshine_transcribe_wav

This is the same example as can be found inside the moonshine_cpp repository, but meant to illustrate how to build and run as an external project.

### Running the example

After running the building commands shown above, you should be in the `build/` directory and can test this example with the following command:

```bash
./moonshine_transcribe_wav base ../model/base/eq4.onnx ../model/base/dq4.onnx ../model/tokenizer/tok.json ../1.wav
```
