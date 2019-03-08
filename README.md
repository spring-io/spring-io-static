This project holds static resources and makes them available via the Google Cloud CDN at https://static.spring.io/. It can be used for the spring.io blog, or other sites.


Upon commit, the directories specified in `cloudbuild.yaml` repository are synced to the public `spring-io-static` bucket, using a Cloud Build Build Trigger. `cache-control` metadata is then set on the files. 


The bucket, backend CDN bucket, LB, reserved IP, and Build Trigger are maintained in the `spring-infra` project at GCP. See the Owners of that project for modifications.


Please maintain a consistent directory structure when adding files. At this time our best recommendation is something like:

```
spring-io-static/
├── blog
│   └── author
│       └── date
```
