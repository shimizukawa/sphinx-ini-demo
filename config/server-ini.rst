============
server.ini
============

server.ini の書式はPasteDeployのconfigフォーマットに従って記述されています。

.. seealso:: PasteDeploy Config Format : http://pythonpaste.org/deploy/#config-uris


server.ini のサンプル
======================

.. code-block:: ini

   [server:main]
   use = egg:Paste#http
   host = 0.0.0.0
   port = 8080

   [app:main]
   use = egg:application#main
   mongo_uri_logging = mongodb://localhost/logs/logs
   spam_api_uri = http://localhost:9090
   twitter_consumer_key = xxxxxxxxx
   twitter_consumer_secret = yyyyyyyyy


app:application#main
===============================

.. iniref:: [app:application]mongo_uri_logging = mongodb://[USER:PASSWORD@]HOSTNAME[:PORT]/DATABASE/COLLECTION

   log4mongoでログを保存しているMongoDBのコレクションを指定します。

   :required: True
   :sample: mongodb://localhost/logs/logs


.. iniref:: [app:application]spam_api_uri = SCHEMA://HOSTNAME[:PORT](/PATH)*

   spam操作用APIのURLを指定します。

   :required: True
   :sample: http://localhost:9090/api


.. iniref:: [app:application]twitter_consumer_key = [TWITTER_CONSUMER_KEY]

   TwitterAPIのコンシューマーキーです。

   :required: False


.. iniref:: [app:application]twitter_consumer_secret = [TWITTER_CONSUMER_SECRET]

   TwitterAPIのコンシューマーキー用SECRETです。

   :required: False

