# tf-tb-visualisation

### Intro
This repo is stolen and modified from [this github page](https://github.com/ayushidalmia/tsne-tensorboard-visualisation) for DH use.


### How to run
This repository provides a starter code for using tensorboard via tensorflow for visualising embeddings

The following is the folder structure expected by the code:

* sample_data/
	* embeddings/
		* filename_embedding
	* images/
		* data/
		* metadata.txt
	* text/
		* metadata.txt


The filename_embedding consists of the n_dimensional embeddings
The data folder consists of all the images
The metadata.txt for images consists of the following format: image_filename\tlabel (one to one mapping with embedding vector)
The metadata.txt for text consists of the following format: label (one to one mapping with embedding vector)


For visualising embeddings run the following from the command line:
For word embeddings:

``` 
python visualise_embeddings.py -b $baseDir -f $filename_embedding -m "text" -l $filename_label
```
Example usage:
```
python visualise_embeddings.py -b /Users/ayushi/Work/tf-tb-visualisation/sample_data/ -f feature_vectors_400_samples.txt -m text -l metadata_text.txt
```

For image embeddings:
```
python visualise_embeddings.py -b $baseDir -f $filename_embedding -m "image" -l $filename_label
```
Example usage:
```
python visualise_embeddings.py -b /Users/ayushi/Work/tf-tb-visualisation/sample_data/ -f feature_vectors_400_samples.txt -m "image" -l metadata_images.txt
```

Then finally run:
```
tensorboard --logdir=$baseDir
```
Example usage:
```
tensorboard --logdir=/Users/ayushi/Work/tf-tb-visualisation/sample_data/
```

Note: Giving the complete path is important. 

### Reading:
* [Visualizing Data using t-SNE](http://www.jmlr.org/papers/volume9/vandermaaten08a/vandermaaten08a.pdf)
* [How to use t-SNE efficiently](https://distill.pub/2016/misread-tsne/)

### Acknowledgement
I would like to sincerely thank [Anuj Shah](https://github.com/anujshah1003) for his data and code for sprite image. 
