# Steps to run coref-e2e 
```console
cd /code
mkdir coref-english
cd coref-english
```
## create and activate a new virtualenv
```console
virtualenv -p python3 venv-e2e
source venv-e2e/bin/activate
```
## clone kentonl repo
```console
git clone https://github.com/kentonl/e2e-coref.git
cd e2e-coref/
```
## replace >= with == in requirements to fix compatibility issue
```console
sed -i 's/>=/==/' requirements.txt
```
## install requirements
```console
pip install -r requirements.txt
```
## download the pretrained model from google drive then extract it
```console
pip install gdown
gdown https://drive.google.com/uc?id=1fkifqZzdzsOEo0DXMzCFjiNXqsKG_cHi
tar -xzvf e2e-coref.tgz
```
## run setup_all script
```console
./setup_all.sh
```
## download english alphabet characters char_vocab.english.txt
```console
curl -O https://lil.cs.washington.edu/coref/char_vocab.english.txt
```
## Set GPU indeces to be available
```console
export GPU=0
```
## run the demo
```console
python demo.py final
```
