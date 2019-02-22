# 将CEPH RBD应用于K8S的持久化存储


# 首先，需要搭建好CEPH集群，CEPH集群搭建，参照笔记http://note.youdao.com/noteshare?id=51faa95a3b33d2319fb10b9f3c3d8611&sub=8261DEFD899D49DE8A9BB2B03A1BE776
# 其次，需要有K8S集群，K8S集群搭建，参照笔记http://note.youdao.com/noteshare?id=00d83b2e4e6be4ec939a19aa6af0f79d&sub=0D3E5BC3A079470EB83A107B4E8C2C3F
# 最后，K8S使用CEPH RBD做持久化存储，参照笔记http://note.youdao.com/noteshare?id=792ed305a75ce1ed61a1003b1c558df8&sub=AFBD08DA7B3C49908BED87FF586FDD0F
# 由于在最后的测试使用pvc阶段使用的msyql服务，yaml文件中使用了mysql-secrets秘钥，所以需要提前申明mysql-secrets秘钥。该秘钥的yaml文件放在studyk8s/secrets目录下。
