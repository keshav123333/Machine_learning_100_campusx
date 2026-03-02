ye code m samjh like jaise early stoping so if 50 round tak imporvement ni toh stop and verboose 100 means har 100 isse 1 bhi kar sakte hai step ke baad val erro print eval set m xtrain xtest ytes train sb bheja deep learning ke model jaise hoga 

                    reg = xgb.XGBRegressor(base_score=0.5, booster='gbtree',    
                                           n_estimators=1000,
                                           early_stopping_rounds=50,
                                           objective='reg:linear',
                                           max_depth=3,
                                           learning_rate=0.01)
                    reg.fit(X_train, y_train,
                            eval_set=[(X_train, y_train), (X_test, y_test)],
                            verbose=100)
