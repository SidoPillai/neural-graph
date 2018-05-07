# neural-graph
An implementation of [A neural algorithm of artistic style][paper] in TensorFlow.

### Pre-Requisties
* [TensorFlow](https://www.tensorflow.org/versions/master/get_started/os_setup.html#download-and-setup)
* [NumPy](https://github.com/numpy/numpy/blob/master/INSTALL.rst.txt)
* [SciPy](https://github.com/scipy/scipy/blob/master/INSTALL.rst.txt)
* [Pillow](http://pillow.readthedocs.io/en/3.3.x/installation.html#installation)

### Data Files

* [Pre-trained VGG network][net] - insert the model in the parent directory or specify the path using the `--network` option.

### Execution
`python neural_graph.py --content <content file> --styles <style file> --output <output file>`

Run `python neural_graph.py --help` to view a list of all options.

Use `--checkpoint-output` and `--checkpoint-iterations` to save checkpoint images.

Use `--iterations` to change the number of iterations (default 1000).  For a 512×512 pixel content file, 1000 iterations take 60 seconds on a GTX 1080 Ti, 90 seconds on a Maxwell Titan X, or 60 minutes on an Intel Core i7-5930K. Using a GPU is highly recommended due to the huge speedup.

### Results
Running it for 500-2000 iterations seems to produce nice results. With certain
images or output sizes, you might need some hyperparameter tuning (especially
`--content-weight`, `--style-weight`, and `--learning-rate`).


[LICENSE][license] for details.

[paper]: http://arxiv.org/pdf/1508.06576v2.pdf
[net]: http://www.vlfeat.org/matconvnet/models/beta16/imagenet-vgg-verydeep-19.mat
[license]: LICENSE
