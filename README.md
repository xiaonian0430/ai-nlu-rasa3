# ai-nlu-rasa

## 软件要求：
 
 - python 3.8
 - rasa==3.0.9
 - spacy==3.2.3
 - jieba==0.42.1

```
python3 -m pip install -r requirements.txt -i https://pypi.tuna.tsinghua.edu.cn/simple
```

## install pre model
```
# https://696e-infobird-4682b5-1302949103.tcb.qcloud.la/zh_core_web_trf-3.2.0.tar.gz
python3 -m pip install zh_core_web_lg-3.2.0.tar.gz
```

## Training NLU-only models

```
python3 -m rasa train nlu
```

## Testing your NLU model on the command line

```
python3 -m rasa shell nlu
```

或者 

```
python3 -m rasa shell -m models/nlu-20190515-144445.tar.gz
```

## Running an NLU server

```
python3 -m rasa run --enable-api -m models/nlu-20190515-144445.tar.gz
```

You can then request predictions from your model using the /model/parse endpoint. To do this, run:

```
curl localhost:5005/model/parse -d '{"text":"hello"}'
```



