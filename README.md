# FastDFS-Nginx Docker 

[fastdfs](https://github.com/happyfish100/fastdfs)

Usage:

```
docker run -itd --network=host --name tracker -v /data/fdfs/tracker:/var/fdfs basemall/fastdfs-nginx tracker

docker run -itd --network=host --name storage0 -e TRACKER_SERVER=YourTrackerIP:22122 -v /data/fdfs/storage0:/var/fdfs basemall/fastdfs-nginx storage

docker run -itd --network=host --name storage1 -e TRACKER_SERVER=YourTrackerIP:22122 -v /data/fdfs/storage1:/var/fdfs basemall/fastdfs-nginx storage

docker run -itd --network=host --name storage2 -e TRACKER_SERVER=YourTrackerIP:22122 -e GROUP_NAME=group2 -e PORT=22222 -v /data/fdfs/storage2:/var/fdfs basemall/fastdfs-nginx storage
```
