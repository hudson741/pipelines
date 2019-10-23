[![Build Status](https://travis-ci.org/kubeflow/pipelines.svg?branch=master)](https://travis-ci.org/kubeflow/pipelines)
[![Coverage Status](https://coveralls.io/repos/github/kubeflow/pipelines/badge.svg?branch=master)](https://coveralls.io/github/kubeflow/pipelines?branch=master)
SDK: [![Documentation Status](https://readthedocs.org/projects/kubeflow-pipelines/badge/?version=latest)](https://kubeflow-pipelines.readthedocs.io/en/latest/?badge=latest)

## Arsenal二次开发变更记录

* Arsenal二期：支持全局debug功能 
修改pipeline对workflow回收策略逻辑，创建run时，根据参数debug，判定是否对这个run进行全局debug。debug为true时，workflow运行完成后无论结果如何，都将延迟ttlSecondsAfterWorkflowFinishDebugModle时间再进行回收操作，默认为3天。debug为false时，要判定workflow的运行结果，运行结果为success，则延迟ttlSecondsAfterWorkflowFinish时间进行回收操作，默认为15分钟。如果运行结果为failed或error，则效果等同debug=true。


## Overview of the Kubeflow pipelines service

[Kubeflow](https://www.kubeflow.org/) is a machine learning (ML) toolkit that is dedicated to making deployments of ML workflows on Kubernetes simple, portable, and scalable. 

**Kubeflow pipelines** are reusable end-to-end ML workflows built using the Kubeflow Pipelines SDK.

The Kubeflow pipelines service has the following goals:

* End to end orchestration: enabling and simplifying the orchestration of end to end machine learning pipelines
* Easy experimentation: making it easy for you to try numerous ideas and techniques, and manage your various trials/experiments.
* Easy re-use: enabling you to re-use components and pipelines to quickly cobble together end to end solutions, without having to re-build each time.

## Documentation

Get started with your first pipeline and read further information in the [Kubeflow Pipelines overview](https://www.kubeflow.org/docs/pipelines/overview/pipelines-overview/).

See the various ways you can [use the Kubeflow Pipelines SDK](https://www.kubeflow.org/docs/pipelines/sdk/sdk-overview/).

See the Kubeflow [Pipelines API doc](https://www.kubeflow.org/docs/pipelines/reference/api/kubeflow-pipeline-api-spec/) for API specification.

Consult the [Python SDK reference docs](https://kubeflow-pipelines.readthedocs.io/en/latest/) when writing pipelines using the Python SDK.

## Blog posts

* [Getting started with Kubeflow Pipelines](https://cloud.google.com/blog/products/ai-machine-learning/getting-started-kubeflow-pipelines) (By Amy Unruh)
* How to create and deploy a Kubeflow Machine Learning Pipeline (By Lak Lakshmanan)
  * [Part 1: How to create and deploy a Kubeflow Machine Learning Pipeline](https://towardsdatascience.com/how-to-create-and-deploy-a-kubeflow-machine-learning-pipeline-part-1-efea7a4b650f) 
  * [Part 2: How to deploy Jupyter notebooks as components of a Kubeflow ML pipeline](https://towardsdatascience.com/how-to-deploy-jupyter-notebooks-as-components-of-a-kubeflow-ml-pipeline-part-2-b1df77f4e5b3)

## Acknowledgments

Kubeflow pipelines uses [Argo](https://github.com/argoproj/argo) under the hood to orchestrate Kubernetes resources. The Argo community has been very supportive and we are very grateful.
