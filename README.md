# tf-tb-visualisation

### Intro
This repo is stolen and modified from [this github page](https://github.com/ayushidalmia/tsne-tensorboard-visualisation) for DH use.

### How to run
This repository provides a starter code for using tensorboard via tensorflow for visualising embeddings

The following is the folder structure expected by the code:

* sample_data/
	* embeddings/
		* filename_embedding.csv
	* images/
		* class1/
		* class2/
		* class3/
	* tsne/
		* labels.txt

The filename_embedding consists of the n_dimensional embeddings, you can get this through np.savetxt with a delimiter of " "
The images folder consists of subfolders of each class
The labels.txt consists of the following format: label\timage_filename (one to one mapping with embedding vector)

For visualising embeddings run the following from the command line:

For image embeddings:
```
python visualise_embeddings.py -b $baseDir -f $filename_embedding -m "image" -l $filename_label
```
Example usage:
```
python visualise_embeddings.py -b /home/dh/Workspace/tsne-tensorboard-visualisation/sample_tsne_dir -f res_embeddings.csv -m "image" -l res_meta_labels.txt
```


For word embeddings:
``` 
python visualise_embeddings.py -b $baseDir -f $filename_embedding -m "text" -l $filename_label
```
Example usage:
```
python visualise_embeddings.py -b /home/dh/Workspace/tsne-tensorboard-visualisation/sample_tsne_dir -f res_embeddings.csv -m text -l res_meta_labels.txt
```

Then finally run:
```
tensorboard --logdir=$baseDir
```
Example usage:
```
tensorboard --logdir=/home/dh/Workspace/tsne-tensorboard-visualisation/sample_tsne_dir
```

Note: Giving the complete path is important. 

### Reading:
* [Visualizing Data using t-SNE](http://www.jmlr.org/papers/volume9/vandermaaten08a/vandermaaten08a.pdf)
* [How to use t-SNE efficiently](https://distill.pub/2016/misread-tsne/)

### Acknowledgement
I would like to sincerely thank [Anuj Shah](https://github.com/anujshah1003) for his data and code for sprite image. 
