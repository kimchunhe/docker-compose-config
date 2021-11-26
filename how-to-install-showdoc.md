## install showdoc and migration data
``` shell
#pull source
docker pull star7th/showdoc

#run docker container
docker run -d --name showdoc --user=root --privileged=true -p 7100:80 \
-v /showdoc_data/html:/var/www/html/ star7th/showdoc

#default account
showdoc/123456
#install zip and unzip
- ubuntu
apt-get install zip unzip
- centos
yum -y install zip unzip

#backup
zip -r /showdoc_data/sdd.zip /showdoc_data/html

#data migration
scp -r root@10.21.156.6:/showdoc_data/html/  sdd.zip

# remove /showdoc folder
rm -rf /showdoc

#unzip backup file
unzip -r sdd.zip 

#copy to /showdoc_data folder
cp -r showdoc_data /showdoc_data

```