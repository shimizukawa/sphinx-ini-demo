==============
celery.conf
==============

Celeryの設定ファイルの例( http://celery.readthedocs.org/en/latest/configuration.html )

.. pydefine:: celery.conf: CELERY_RESULT_BACKEND = "amqp"

   メッセージ処理結果の保存領域を指定します。デフォルトではamqpを使用します。
   その他のResult Storeとして RDBMS, MongoDB, Redis, Tokyo Tyrant, Cassandra
   等を使用できますが詳しくは
   http://celery.readthedocs.org/en/latest/configuration.html#task-result-backend-celery
   を参照してください。

   :default: "amqp"
   :available: database, cache, mongodb, redis, tyrant, amqp, cassandra


.. pydefine:: celery.conf: BROKER_URL = "transport://userid:password@hostname:port/virtual_host"

   ブローカーのURLを指定します。デフォルトではamqpを使用します。
   その他のブローカーとして redis, RDBMS, Django, MongoDB, CouchDB
   等を使用できますが詳しくは
   http://celery.readthedocs.org/en/latest/getting-started/brokers/index.html
   を参照してください

   :default: "amqp://guest:guest@localhost:5672//"


.. pydefine:: celery.conf: CELERYD_CONCURRENCY = 10

   ワーカーの多重度設定です。I/O処理が多い場合にワーカーを増やすことができます。
   しかし、CPU処理が多い場合、多重度はCPU数,コア数以上にしない方が良いでしょう。

