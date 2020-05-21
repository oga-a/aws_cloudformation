# AWS CloudFormation

[Qiita記事](https://qiita.com/oga_akihiro/items/66cbd7a258f5fc090321)
```
# S3上にyamlファイルを転送
aws s3 mb s3://cf-templates-oga
aws s3 cp ./aws_cf.yaml s3://cf-templates-oga/aws_cf.yaml

# cf-oga1という名前でstack作成
aws cloudformation create-stack --stack-name cf-oga1 --template-body https://cf-templates-oga.s3-us-west-2.amazonaws.com/aws_cf.yaml

# stackを破棄、これを実行するとstackに紐づいているVPC, EC2などのリソースもすべて消える。
aws cloudformation delete-stack --stack-name cf-oga1
```
