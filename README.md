# nel-infra
Network Error Logging infrastructure

This repo is an addon to [our blog article](https://dysnix.com/blog/cloudflare-vs-nel).

Here is an example of how to deploy network error logging (NEL) infrastructure into k8s. There are few steps to perform a deployment:
1. Install required tools such as kubectl, helm, helmfile
2. Get access to k8s with internet access, support of load balancers and storage
3. Adjust helmfile environment variables, such as `stageDomain` in [helmfile.yaml](helmfile.yaml#L5)
4. Install all the components via `helmfile sync` 
5. Configure NEL on your server/API/endpoint via additional http headers 
6. Wait for some time, you should get some errors into ElasticSearch
7. Optionally use Grafana with Elasticsearch as a datasource and [example dashboard](grafana-NEL.json)

Here are some useful links regarding NEL:
* https://w3c.github.io/network-error-logging/
* https://dcreager.net/publications/015-nel/
* https://caniuse.com/mdn-http_headers_nel
* https://developer.mozilla.org/en-US/docs/Web/HTTP/Network_Error_Logging

