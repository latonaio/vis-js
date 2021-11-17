# vis-js  
[vis.js](https://github.com/visjs/vis-network) は、[avis](https://github.com/latonaio/avis)で使用されているフロントエンドリソースの一部です。  
vis.js は、ブラウザベースの動的な視覚化ライブラリで、大量の動的データの処理や、データの操作、データの相互作用を可能にします。  
[avis](https://github.com/latonaio/avis)では、vis.js を用いて、マイクロサービス同士の関係性等の可視化が行われます。

# avis における vis.js を使用した UI の例
![vis-js](docs/vis_js.png)

# sample.yml
上記の vis.js UI 例は、本レポジトリ内 の sample.yml にある 下記のソースコードを vis.js で可視化したものです。
```
microservices:
  authenticator:
  azure-face-api-identifier-kube:
    env:
      QUEUE_ORIGIN: azure-face-api-identifier-kube-queue
      QUEUE_TO_FOR_LOG: send-data-to-azure-iot-hub-queue
  azure-face-api-registrator-kube:
    env:
      QUEUE_ORIGIN: azure-face-api-registrator-kube-queue
      QUEUE_TO: register-face-to-guest-table-kube-queue
  register-face-to-guest-table-kube:
    env:
      QUEUE_ORIGIN: register-face-to-guest-table-kube
  send-data-to-azure-iot-hub:
    env:
      QUEUE_ORIGIN: send-data-to-azure-iot-hub-queue
      QUEUE_TO: slack-message-client-kube-queue
  slack-message-client-kube:
    env:
      QUEUE_ORIGIN: slack-message-client-kube-queue
  load-balancer-for-movable-devices:
  ui-backend-for-omotebako:
    env:
      QUEUE_TO_IDENTIFIER: azure-face-api-identifier-kube-queue
      QUEUE_TO_REGISTRATOR: azure-face-api-registrator-kube-queue
  mysql-backup:
  site-controller-data-update-to-mysql:
  event-driven-audio-streaming:
  random-voice-streaming-periodic:
  ui-frontend-for-omotebako:
  ui-frontend-for-omotebako-mobile:
```