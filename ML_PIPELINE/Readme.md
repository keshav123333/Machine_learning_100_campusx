      from sklearn.svm import LinearSVC
      from sklearn.pipeline import Pipeline
      
      ytrain=ytrain.astype(int)
      ytest=ytest.astype(int)
      
      #piplein bana le 
      text_clf=Pipeline([('tfidf',TfidfVectorizer()),('clf',LinearSVC())])
      text_clf.fit(xtrain,ytrain) 

yaha maine pipline mein pure data pe laga diya so directly fit bhi chlega      
