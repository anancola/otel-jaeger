# Pre-requistes
## The container registry
The excercises will deploy the python api which is an image come from container registery. You may have your own image or create one azure-container-registry with name: otel-acr

## Create namespaces
$ kubectl create namespace observability

$ kubectl create namespace app

$ kubectl create namespace app-sidecar

## Install the cert-manager
$ kubectl apply -f https://github.com/cert-manager/cert-manager/releases/download/v1.9.1/cert-manager.yaml

## Install the operators
$ kubectl create namespace observability

$ kubectl create -f https://github.com/jaegertracing/jaeger-operator/releases/download/v1.37.0/jaeger-operator.yaml -n observability

$ kubectl apply -f https://github.com/open-telemetry/opentelemetry-operator/releases/latest/download/opentelemetry-operator.yaml -n observability

# Instruction
## The Jaeger (all-in-one)
$ kubectl apply -f https://raw.githubusercontent.com/anancola/otel-jaeger/main/yaml/00-jaeger/create-jaeger.yaml

$ kubectl apply -f https://raw.githubusercontent.com/anancola/otel-jaeger/main/yaml/00-jaeger/jaeger-operator-rolebinding.yaml

## Excercise 1: Deployment
$ kubectl apply -f https://raw.githubusercontent.com/anancola/otel-jaeger/main/yaml/01-deployment/01-create-otelcollector.yaml

$ kubectl apply -f https://raw.githubusercontent.com/anancola/otel-jaeger/main/yaml/01-deployment/02-create-autoinstrumentation.yaml

$ kubectl apply -f https://raw.githubusercontent.com/anancola/otel-jaeger/main/yaml/01-deployment/03-deployment-predict-flower.yaml

## Excercise 2: Sidecar
$ kubectl apply -f https://raw.githubusercontent.com/anancola/otel-jaeger/main/yaml/01-sidecar/01-sidecar-create-otelcollector.yaml

$ kubectl apply -f https://raw.githubusercontent.com/anancola/otel-jaeger/main/yaml/01-sidecar/02-sidecar-create-autoinstrumentation.yaml

$ kubectl apply -f https://raw.githubusercontent.com/anancola/otel-jaeger/main/yaml/01-sidecar/03-sidecar-deployment-predict-flower.yaml



## Reference:

https://www.jaegertracing.io/docs/1.37/operator/ 

https://github.com/open-telemetry/opentelemetry-operator 

https://github.com/open-telemetry/opentelemetry-operator/tree/main/tests/e2e/instrumentation-python
