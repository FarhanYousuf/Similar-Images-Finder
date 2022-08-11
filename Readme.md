## How to setup this project :
  1) Create virtualenv & activate it
  2) Install requirements as pip install -r requirements.txt
  3) There are 3 stages :
     i) Download images from label_id
     ii) Index it in Elasticseach ,index name as label id 
     iii) Query from the input image 



1) Download images from label_id:
    We are using the Imaterialist Dataset, where given label_id, we are traversing the json file given by Imaterialist,
   and downloading those in a certain specified data path.
   
2) Indexing using ElasticSeach:
    Using feature extraction, we extract features from MobileNetV2 with the weights of imagenet,
   and then flatenning that array, and then we make a index named label_id as given and then we index that image vector 
   with the image name so that we can cross reference it later.
   
3) Image2Image Query:
    In this section, we perform feature extraction and use K nearest neighours
    in Elastic search to find K nearest vectors with the highest degree of similarity with the queried image.
