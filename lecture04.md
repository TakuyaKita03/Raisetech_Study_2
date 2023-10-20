# 第4回課題


- EC2作成完了した画面
    
    ![EC2作成完了](img/kadai4_1_ec2_created.jpg)


- RDS作成完了した画面
    

    ![RDS作成完了](img/kadai4_2_rds_created.jpg)

- EC2よりRDS（MySQL）へ接続成功した画面
    

    ![MySQL接続成功](img/kadai4_3_EC2_RDS_connected.jpg)


- セキュリティグループの設定内容
    
    
    RDS→EC2のセキュリティグループ
    ![sec_group_1](img/kadai4_14_secgroup_rds-ec2-1_in.jpg)

    
    ![sec_group_2](img/kadai4_15_secgroup_rds-ec2-1_out.jpg)
    
    
    EC2→RDSのセキュリティグループ
    ![sec_group_3](img/kadai4_16_4_secgroup_ec2-rds-1_out3.jpg)
    
    
    ![sec_group_4](img/kadai4_16_2_secgroup_ec2-rds-1_in.jpg)
    
    - セキュリティグループのec2-rds-1のアウトバウンドルールにポート3306を開放するように設定。
    
        - （RDSへのデータ読み書きは、EC2が司令して行うので、EC2から外向きの通信に対して、セキュリティグループで許可してあげる必要がある。
    
            セキュリティグループの特性上、EC2から外向きに行った通信（アウトバウンド）の返信は、逆向きの通信（インバウンド）に関係なく通信が許可される。これを”ステートフル”と言う。）


- RDSがプライベートサブネットに配置される設定になっていること


![RDS_プライベートサブネット1](img/サブネット一覧_231015_2008.jpg)



![RDS_プライベートサブネット2](img/kadai4_13_subnetlist_231017_2130.jpg)
