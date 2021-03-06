# Comand Line tools :
```bash
- ml_models    :  Running model training
- ml_optim     :  Hyper-parameter search
- ml_test      :  Testing for developpers.
- ml_benchmark :  Benchmark

```


# How to use Command Line


### ml_models
=======

### How to use Command Line
```bash


ml_models --do  
    model_list  :  list all models in the repo                            
    testall     :  test all modules inside model_tf
    test        :  test a certain module inside model_tf
    fit         :  wrap fit generic m    ethod
    predict     :  predict  using a pre-trained model and some data
    generate_config  :  generate config file from code source
    

  ## --do fit  
     --model_uri     model_tf.1_lstm
     --save_folder   myfolder/
     --config_file   myfile.json
     --config_mode   "test"


  ## --do predict  
     --model_uri     model_tf.1_lstm
     --save_folder   myfolder/
     --config_file   myfile.json
     --config_mode   "test"


#### generate config file
    ml_models  --do generate_config  --model_uri model_tf.1_lstm.py  --save_folder "c:\myconfig"

#### TensorFlow LSTM model
    ml_models  --do test  --model_uri model_tf/1_lstm.py  


#### Custom  Models by URI
    ml_models --do test  --model_uri "D:\_devs\Python01\gitdev\mlmodels\mlmodels\model_tf.1_lstm.py"


```




### ml_optim
```bash

ml_optim --do
    test      :  Test the hyperparameter optimization for a specific model
    test_all  :  TODO, Test all
    search    :  search for the best hyperparameters of a specific model


#### For normal optimization search method
    ml_optim --do search --ntrials 1  --config_file optim_config.json --optim_method normal


###### for pruning method
    ml_optim --do search --ntrials 1  --config_file optim_config.json --optim_method prune  


###### Using Model default params
    ml_optim --do search --modelname model_tf.1_lstm.py  


###### Using Model default params
    ml_optim --do test  --modelname model_tf.1_lstm.py  


```



### ml_benchmark
```bash
## Benchmark model

#### One Single file for all models
ml_benchmark  --do  dataset/json/benchmark.json  --path_json  dataset/json/benchmark_timeseries/test02/model_list.json
     

#### Many json                            
ml_benchmark  --do  dataset/json/benchmark.json  --path_json  dataset/json/benchmark_timeseries/test01/

    
```






### ml_distributed : Distributed training on Pytorch Horovod
```bash
### Work in Progress

#### Distributed Pytorch on CPU (using Horovod and MPI on Linux, 4 processes)  in model_tch/mlp.py
    mlmodels/distri_torch_mpirun.sh   4    model_tch.mlp    mymodel.json

    ml_distributed  --do fit   --n_node 4    --model_uri model_tch.mlp    --model_json mymodel.json


```





### ml_test
```bash





```




# Example in Colab :

https://colab.research.google.com/drive/1u6ZUrBExDY9Jr6HA7kKutVKoP5RQfvRi#scrollTo=4qtLQiaCaDaU






