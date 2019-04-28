It is Ipython notebook with implementation of two simple variation of stacking
 
### Classes:
----
#### BlendingClassifier(clfs, meta)

clfs - list of base classifiers
meta - meta classifier
        
training set (X,y) is splitted on two parts (X1,y1) and (X2,y2), new training set (M,y2) is created

<pre>        
for each clf in clfs: \
 clf.fit(X1,y1) \
 M += clf.predict(X2,y2) \
meta.fit(M,y2)
<\pre>

#### SpendignClassifier(clfs,meta)

training set is splitted on few parts (Xk,yk), k = n_folds. n_folds-1 are used for training of basic classifiers, 
last part is used to generate meta features.
