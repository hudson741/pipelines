FROM registry-img.weizhipin.com/gcr.azk8s.cn/ml-pipeline/api-server:base

COPY src/apiserver/apiserver /bin/

CMD apiserver --config=/config --sampleconfig=/config/sample_config.json -logtostderr=true