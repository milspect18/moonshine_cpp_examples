## Models

This directory includes onnx models of the [moonshine model](https://github.com/usefulsensors/moonshine) which were downloaded from [HuggingFace](https://huggingface.co/UsefulSensors/moonshine).  They are provided here simply to make any examples within this repository simpler to test.  The 'base' and 'tiny' directories include various versions of the different sizes of model.  The 'eq4' and 'dq4' models are the int4 quantized variants of the encoder decoder.

The 'tokenizer' directory includes a JSON file that represents the token mappings for converting the models output from int values to string values.