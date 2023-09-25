# 第3講課題

#### アプリケーション（AP）サーバーについて
APサーバー：Puma

Ver： 5.6.5


![APサーバーのバージョン](Raisetech_Study_2/img/kadai3_2_2_ap_server_ver_2.jpg)



##### APサーバー起動時
![APサーバー起動確認](Raisetech_Study_2/img/kadai3_1_cloud9_dev_success.jpg)



#####　APサーバーを終了させると、引き続きアクセスできない。


![APサーバー終了後](Raisetech_Study_2/img/kadai3_4_ap_server_shutdown.jpg)






#### DBサーバーについて
DBエンジン：MySQL

Ver　8.0.34



![DBサーバーのバージョン](Raisetech_Study_2/img/kadai3_3_mysql_version.jpg)



#### Railsの構成管理ツール：Bundler


![Bundler_version](Raisetech_Study_2/img/kadai3_5_bundler_ver.jpg)


### 今回の課題から学んだこと
今回はcloud9_devの起動で一番苦しみました。

凡ミスレベルだとdatabase.yml.sampleを編集すれば、いいものだと思いこんでいたこと。

→サンプルをコピーし、database.ymlにリネームした上で編集しました。
・database.yml編集後も実行の度にエラーの連続・・・
　database.ymlを見直すも何も分からない・・・

　ミズモトメンターのヒントでusername:root@localhost→username:'root'に変更
　
　★ID・PW関係は、値を'  'でくくらないと駄目と学習。

・エラーもたくさん吐かれて、心もちょっと折れそうになりました。。。

（遭遇したエラーたち）

YAML syntax error occurred while parsing /home/ec2-user/environment/raisetech-live8-sample-app/config/database.yml. Please note that YAML must be consistently indented using spaces.


Puma caught this error: '{ default =>  }' is not a valid configuration. Expected '' to be a URL string or a Hash. (ActiveRecord::DatabaseConfigurations::InvalidConfigurationError)


ActiveRecord::NoDatabaseError
　
　※参考URL：https://rails-ambassador.herokuapp.com/debugs/NoDatabaseError の rails db:create を実行

ActiveRecord::PendingMigrationError
$ rails db:migrate　を忘れていると指摘があり、db:migrateを実行。
　
　※参考URL：https://qiita.com/KONTA2019/items/0444ae3b8c8936a56ee0


心もちょっと折れそうになりましたが、手を動かし続けると光明も見えてきました。

今回の場合は、$ rails db:create の当たりから光明が見えてきて
$ rails db:migrateを実行することにより解決へ導けました。

#### この先もっと苦しい課題も多いと思いますが、あきらめずトライ＆エラーで取り組み続けます。