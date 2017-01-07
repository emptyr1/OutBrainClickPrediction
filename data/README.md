Since I am using a sample of the data using cookies, I break the wget in between the download. So first I download:

- Use cookies-export chrome plugin to save cookies in a text file
- Then run `wget --load-cookies=cookies.txt https://www.kaggle.com/c/outbrain-click-prediction/download/page_views.csv.zip` for example. 
(to understand what this command is doing, check this: http://bit.ly/2hLNHHK  )

- Instead of using unzip, which might not work, use `jar xvf page_views.csv.zip` (I'm on OSX) to extract the partially downloaded csv. Check [this](http://askubuntu.com/questions/54904/unzip-error-end-of-central-directory-signature-not-found) post. 
- Run `sed -i '' -e '$ d' page_views.csv` to remove the last incomplete line

- Upload to s3 

