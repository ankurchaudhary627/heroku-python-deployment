## Deploying ChatBot to Heroku

Steps to Deploy your ChatBot to heroku :

- Make a new folder in which all the required files will be present.

- Copy your python script to this folder.

- Open cmd/terminal and navigate to this folder.

- To deploy to heroku we need to create python virtual environment. So make a virtual environment folder using the command :
```
virtualenv YOUR_FOLDER_NAME
```
- Activate the virtual environment by :

For linux :
```
source YOUR_FOLDER_NAME/bin/activate
```
For windows:
```
YOUR-FOLDER-NAME\Scripts\activate
```
- Install the necessary modules for deploying our chatbot to heroku  :
```
pip install gunicorn flask
```
- You need to install other required modules which are used by your python code same way.

- Now we need to make requirements text file from cmd/terminal :
```
pip freeze>requirements.txt
```
