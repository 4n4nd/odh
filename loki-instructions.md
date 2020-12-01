# Loki Demo using Observatorium
*This is not a production instance of Loki, this is a demo instance which has a very small amount of storage attached to it.*


## Pushing logs to the Loki instance:
```bash
curl -v -H "Content-Type: application/json" \
  -H "X-Scope-OrgID: opf" \
  -XPOST -s "http://loki-distributor-opf-monitoring.apps.observatorium.lab.upshift.rdu2.redhat.com/loki/api/v1/push" --data-raw \
  '{"streams": [{ "stream": { "app": "my-app-1" }, "values": [ [ "1606759525000000000", "my-log-line" ] ] }]}'
```
More Info on  [/push](https://grafana.com/docs/loki/latest/api/#post-lokiapiv1push)


## Querying logs:
```bash
curl -H "X-Scope-OrgID: opf" \
  -G -s  "http://loki-opf-monitoring.apps.observatorium.lab.upshift.rdu2.redhat.com/loki/api/v1/query_range" \
  --data-urlencode 'query={app="my-app-1"}' \
  --data-urlencode 'start=1606759525000000000' | jq
```
More Info on [/query_range](https://grafana.com/docs/loki/latest/api/#get-lokiapiv1query_range)


### Some information about the requests being made:
* Here, the header `"X-Scope-OrgID"` is used by loki for authentication purposes, so as long as it has the same value for pushing and for querying, it should work fine.

* The timestamps (`1606759525000000000`) set here are in nanoseconds.
