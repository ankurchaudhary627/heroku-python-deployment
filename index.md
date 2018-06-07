## Deploying Telegram ChatBot to Heroku

### Steps to Deploy your ChatBot to heroku

- Make a new folder in which all the required files will be present.

- Copy your python script to this folder.

- Open cmd/terminal and navigate to this folder.

- To deploy to heroku we need to create python virtual environment. So make a virtual environment folder using the command :

  ```
  virtualenv YOUR_FOLDER_NAME
  ```
  
- Activate the virtual environment by :

      - For linux :
      ```
      source YOUR_FOLDER_NAME/bin/activate
      ```
      - For windows:
      ```
      YOUR-FOLDER-NAME\Scripts\activate
      ```
  
- Install the gunicorn [Gunicorn](https://en.wikipedia.org/wiki/Gunicorn) and flask modules for deploying to heroku  :

  ```
  pip install gunicorn flask
  ```
  
- You need to install other required modules which are used by your python script in the same way.

- Now we need to create requirements.txt file from cmd/terminal :

  ```
  pip freeze>requirements.txt
  ```
  
- Create a procfile :
  
      - Windows :
      ```
      echo web: gunicorn YOUR_PYTHON_SCRIPT_NAME : YOUR_FLASK_APP_NAME > Procfile
      ```
      - Linux :
      ```
      web: gunicorn YOUR_PYTHON_SCRIPT_NAME : YOUR_FLASK_APP_NAME
      ```
  
- To test on localhost run the python script and goto [localhost](https://127.0.0.1:5000)

- Above steps were to create all the necessary files required by heroku.

- In order to deploy to heroku, first you need to create a heroku account [Heroku](https://www.heroku.com/) and download [Heroku CLI](https://devcenter.heroku.com/articles/heroku-cli)

- After creating your heroku account and installing heroku CLI, create a new heroku app from their web UI.

-  Login to your account through cmd/terminal using :

  ```
  heroku login
  ```
- If you are not in your project folder then navigate to your project folder. Now create a new git repo using :

  ```
  git init  
  heroku git:remote -a YOUR_HEROKU_APP_NAME
  # Deploy your application  
  git add .  
  git commit -am "commiting a change"  
  git push heroku master
  ```
  
- Scaling dynos [Read here](https://stackoverflow.com/questions/30318369/can-someone-explain-heroku-psscale-web-1) :

  ```
  heroku ps:scale web=1
  ```
  
- To open the website :

  ```
  heroku open
  ```
  
### Creating Telegram Webhook

  - Goto this link and change: **heroku_web_app_url** to your heroku web-app's url :
  
  ```
  https://api.telegram.org/bot<bot-token>/setWebhook?url=<heroku_web_app_url>
  ```
  
  - You should see something like this in your web browser:
  
  ```
  {"ok":true,"result":true,"description":"Webhook was set"}
  ```
  
### Useful Links

  [Link 1](https://progblog.io/How-to-deploy-a-Flask-App-to-Heroku/)
  [Link 2](https://devcenter.heroku.com/articles/getting-started-with-python#deploy-the-app)
  [Link 3](https://stackoverflow.com/questions/38851564/heroku-gunicorn-procfile)
  
### Contact
  
  Ping me on Gmail for any query: **ankurchaudhary627@gmail.com**
