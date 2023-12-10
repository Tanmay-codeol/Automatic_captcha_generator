```bash
git clone https://github.com/Tanmay-codeol/Automatic_caption_generator.git
cd ACG
make setup
```

### Run the App

```bash
make run
```

###  View the App

web browser to [localhost:10101](http://localhost:10101)


### Training Dataset

    COCO dataset (Common Objects in Context) is data that the model is trained on. This dataset
    maps images to captions describing what is on those images. Each image has about 5 captions
    on average. https://cocodataset.org/#home

### CNN

    Convolutional neural networks are the advanced image processing artificial neural networks used in 
    image processing. Main idea is that the image is taken through multiple layers of the network,
    thorough which feature set is exatracted. At the end layer feature object is flattened and can 
    be fed into final classification layer or be combined with other layers.

### RNN

    Recurrent Neural Networks allow for introduction of memory to neural network architectures and are 
    very helpful in analyzing sequential data like text or time series. However, sometimes we use RNN
    to analyze sequence of images, in other words, frames in a video. Problems like gesture captioning
    spatial patterns, video classification, etc.

### LSTM

    LSTM or Long Short Term Memory networks are RNNs architecture which allows to overcome a vanishing
    gradient problem. Since, the vanishing gradient is no longer of a major concern, such architecture
    allows for longer sequence modeling.

### Encoder/Decoder

    Our model will take an image and process it using CNN, then it will take output of the CNN and 
    use it as input to RNN to generate the automatic captions. That's it;)
    Such architecture is know as encoder - decoder network. This means that we take an input, in 
    this case an image, and encode it into features. Then we take those features and decode it into 
    text. 

    - Encoder:
    Note, that a special type of CNN will be used, which is called ResNet ( Residual Network ).
    Think about this part as a feature extractor that compresses image into smaller feature representation.

    - Connector:
    In order to connect encoder to decoder we get rid of final layer ( Softmax ) in the ResNet and and
    additional Linear Fully Connecter layer to act as the first sequence to the input of the decoder. Once
    feautres extracted and processed to fully connected layer, what is left for decoder is to take the 
    feature vector and decode it into natural language.

    - Decoder:
    We use LSTM network as decoder. Before feeding data into LSTM we add Embedding Layer to transform features
    into vectors of the same shape. Input to the decoder network will be words of the captions.


### Libraries and Tools used:
    
    Please note, that the source files and miscelaneous files in this repo are the ones only needed for prediction
    processes. In other words, to keep application to a light weight and minimum code base, scripts used for 
    training of the model are not included. The major libraries that were used in this project are H2O.ai Wave, 
    PyTorch and NLTK.


