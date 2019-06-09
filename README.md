# Poetry GAN
Comparative study of generative neural text models of creative datasets using MLE and GAN objective 
Models are pretrained on gutenberg novels first with language modeling objectve then finetuned to a target dataset.

## Datasets
- Gutenberg Novels
- English poetry
- Song lyrics
- [Metaphors](http://metaphors.iath.virginia.edu/metaphors)

## Text Generative Models with LM and GAN objective
- AWD LSTM [paper link](https://arxiv.org/pdf/1708.02182.pdf)
- Transformer XL [paper link](https://arxiv.org/pdf/1901.02860.pdf)

## Usage
- Preprocess data `python preprocess.py [gutenberg/metaphors/poems/lyrics]` and save preprocessed file
- Train language model `lang_model.py PATH FILENAME MODEL [PRETRAINED_FNAMES]`
- Train gan model `textgan.py PATH FILENAME PRETRAINED MODEL [CRIT] [PREDS] [EPOCHS]`

```
PATH - folder with data 
FILENAME - name of preprocessed file
PRETRAINED - pretrained weight file and vocab file (comma seperated)
MODEL - architecture to use {'AWD': AWD_LSTM, 'XL':TransformerXL}
CRIT - loss function: gumbel softmax/reinforce (only for gan)
PREDS - generate output from validation set 
EPOCHS - number of epochs to train
```
