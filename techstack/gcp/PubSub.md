#gcp #cloud #messaging #cheat 

```sh
gcloud pubsub topics create $my_pubsub_topic

gcloud pubsub subscriptions create $my_pubsub_subscription \
 --topic=$my_pubsub_topic
```