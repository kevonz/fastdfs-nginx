# FastDFS-Nginx Docker 

[fastdfs](https://github.com/happyfish100/fastdfs)

Usage:

```
docker run -itd --network=host --name tracker -v /data/fdfs/tracker:/var/fdfs basemall/fastdfs-nginx tracker

docker run -itd --network=host --name storage0 -e TRACKER_SERVER=YourTrackerIP:22122 -v /data/fdfs/storage0:/var/fdfs basemall/fastdfs-nginx storage

docker run -itd --network=host --name storage1 -e TRACKER_SERVER=YourTrackerIP:22122 -v /data/fdfs/storage1:/var/fdfs basemall/fastdfs-nginx storage

docker run -itd --network=host --name storage2 -e TRACKER_SERVER=YourTrackerIP:22122 -e GROUP_NAME=group2 -e PORT=22222 -v /data/fdfs/storage2:/var/fdfs basemall/fastdfs-nginx storage
```

Demo(Note: Please update tracker ip address for storage)
```
tracker
docker run -itd -v /data/fastdfs/tracker:/var/fdfs -v /data/fastdfs/tracker/logs:/usr/local/nginx/logs -v /etc/localtime:/etc/localtime -v /etc/timezone:/etc/timezone --privileged=true -u 0 --restart=always --network=host --name cc-tracker basemall/fastdfs-nginx tracker
storage
docker run -itd -v /data/fastdfs/storage:/var/fdfs -v /data/fastdfs/storage/logs:/usr/local/nginx/logs -v /etc/localtime:/etc/localtime -v /etc/timezone:/etc/timezone --privileged=true -u 0 --restart=always --network=host  --name cc-storage -e TRACKER_SERVER=192.168.0.114:22122 basemall/fastdfs-nginx storage
```