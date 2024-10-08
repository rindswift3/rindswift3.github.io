Proxy Guide:

This will require some level of confidence with a command line.

Step 1: Create a free account on Heroku https://www.heroku.com/

Step 2: Setup the Heroku CLI Tool https://devcenter.heroku.com/articles/heroku-cli

Step 3: Login to the Heroku CLI by using the command heroku login

Step 4: Create a new app by using the command heroku create Once the app is created, you should see a URL and the App Name in the CLi. Make sure to save this somewhere. We also need to tell Heroku what we want this app to do, for this enter the command heroku buildpacks:add heroku-community/nginx to add the NGINX buildpack

Step 5: Time to setup our file structure to upload to Heroku. Create a new folder on your computer and call this whatever you like. Inside This Folder, Create Your Folders Like https://imgur.com/a/zXgyVPM Make Sure that Procfile doesn't have any sort of file extension.

Step 6: Inside the config folder, create a file called nginx.conf.erb Make sure the file extension is correct.

Step 7: Inside the file nginx.conf.erb Add the following code from Here https://files.catbox.moe/fxgxwx.txt If you are interested in the NGINX proxy_redirect function, check out the docs Here https://nginx.org/en/docs/http/ngx_http_proxy_module.html#proxy_pass

Step 8: In the parent directory to this file, It's time to edit the Procfile Insert the following code: web: bin/start-nginx-solo

Step 9: It's time to get ready to upload! Make sure you have git installed for this part, check Here https://github.com/git-guides/install-git for installation instructions. Start by initialising a git repo in the main project directory, you can do this in the terminal with git init

Step 10: Now that we have an empty git repo ready, we need to define what and where to upload our files to. To do this run the command git add . to add everything in the folder. Next run the command git commit -m "Initial Commit" to commit everything in the folder.

Step 11: Now we have to tell git where to upload our commits to, do this by running the command heroku git:remote -a APP-NAME where APP-NAME is the name of the app you created earlier, (This should have been shown when you created the app). Finally we can upload! Enter the command git push heroku master To push the commit to Heroku. (If you get any errors, try searching for the issue Here https://help.heroku.com/)

Step 12: Hopefully Success! You should see a message in the command line to say that the files are uploaded, if not, try checking on the Heroku website for status. If everything is good, you should be able to visit the URL from earlier and see your own site!

Step 13: We are almost done, but we need to make sure our site stays active. As Heroku turns off any app that hasn't been used for about 30 mins. To combat this, we will use a service called UptimeRobot https://uptimerobot.com/ Once you have created an account, you should be able to add a new monitor from the dashboard. Make sure to set the monitor type as HTTP(S) and set the URL to your site. Leave all the other settings as default and create the monitor. This should now make sure your site stays online (And even notify you if there are issues!)

And we should be done! Hopefully this has been able to help you to create your own proxy for sears4all, thank you very much for somehow making it to the end!
