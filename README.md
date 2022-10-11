# otel-jaeger
An implementation of OpenTelemetry and Jaeger to observer Trace in Kubernetes.
This project will demo how auto-instrumentation and OpenTelemetry Collector works together to expose traces to Jaeger in different modes.

In some cases, the application might not import the OpenTelemetry SDK. Let's use the auto-instrumentation to inject the Opentelemetry SDK into the application (api of predict-flower). (Auto inject supported languages: java, nodejs, dotnet, python.)

There are two modes for OpenTelemetry Collector: sidecar and deployments. For sidecar, the collector is work together within the application pods. For deployment, their is a dedicated collector which collect all telemetry from different applications.


![architecture](/images/architecture.png)

## See the folder of "yaml" for more details.
