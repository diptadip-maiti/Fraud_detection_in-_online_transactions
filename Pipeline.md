Pipeline:

    Real-time data ingestion 
(Kafka(KSQL) to be used)



    Data Preprocessing
(Handling missing values, transform inconsistent formats(date, currency))

      

    Feature Engineering
(Deriving new features (number of transactions in the last hour, average transaction size for the customer, distance between transaction locations, IP address changes))
(encoding, normalization, standardization, PCA)

      

    Data Balancing
(As a very small proportion of the transactions are fraudulent, the data set is very imbalanced. If the learning model later used, requires a balanced dataset we should balance the data set through 'under-sampling'.)
        
       

    Model Selection
(Isolation Forest is the best algorithm for this problem. Random forest and k-means clustering are also good options.)
(Precision, Recall and F1 score are the metrics to monitor for the performance of the model. Accuracy will not be a good option to prefer due to the imbalance in the data set. We should monitor the area under the ROC curve(AUC-ROC))

      
( Tensorflow Serving for real time pipeline inference)

    Cross Validation
(k-fold cross validation)
(Bayesian optimization, Grid Search, Random Search for hyperparameter tuning)

      
( Spark streaming to be used.)

    Flagging Alert
(If the transaction is classified as fraudulent by the model, we'll ask for further authentications from the customer.)
(If the customer can authenticate we'll write the transaction and save it in the data set as valid. Otherwise, block the transaction and save it as fraudulent.)
  
    

    Deployment
(Model can be containerized with Docker and orchestrated with Kubernetes.)
(We can use serverless options like AWS Lambda for dynamic scalability.)
(We should integrate the model with payment gateways)

       

    Real-Time Monitoring
(We should monitor the accuracy, latency, throughput, etc of the model in real time)

** Latency is a key factor as we have to do all of these in real time. We should be careful to increase steps as it can impact latency.
