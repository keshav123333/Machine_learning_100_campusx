    from sklearn.datasets import load_iris
    from sklearn.model_selection import train_test_split
    from sklearn.tree import DecisionTreeClassifier
    from sklearn.svm import SVC
    from sklearn.linear_model import LogisticRegression
    from sklearn.ensemble import StackingClassifier
    from sklearn.metrics import accuracy_score
    
    # Dataset
    X, y = load_iris(return_X_y=True)
    
    X_train, X_test, y_train, y_test = train_test_split(
        X, y, test_size=0.2, random_state=42
    )
    
    # Base Models
    base_models = [
        ('dt', DecisionTreeClassifier(random_state=42)),
        ('svm', SVC(probability=True, random_state=42)),
        ('lr', LogisticRegression(max_iter=200))
    ]
    
    # Meta Model
    meta_model = LogisticRegression()
    
    # Stacking
    stack = StackingClassifier(
        estimators=base_models,
        final_estimator=meta_model
    )
    
    # Train
    stack.fit(X_train, y_train)
    
    # Predict
    pred = stack.predict(X_test)
    
    print("Accuracy:", accuracy_score(y_test, pred))
