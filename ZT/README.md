# Run ZeroTier Agent or Controller as containers on VyOS router.<br />
 Here is the [Article with HOWTO use these scripts](https://medium.com/@qdrddr/run-zerotier-on-vyos-router-de5aaf1da02b)

* You can run only Agent or only Controller
* You can run both. But! I guess its not a good idea to attach an agent to the controller that both runs on the same VyOS, because if your controller stops working you'll not be able to connect to your agent and that's like shooting into your own foot. FYI.


To make it work first install docker container app on VyOS using [this script](../docker/vyos-docker-install.md)<br />
Make a file in the /config folder, copy and paste content of the script and make it executable.<br />

**Then install either controller or agent containers on your VyOS**

[Agent](1.4.x/zt-agent.md)<br />
Make a file in the /config folder, copy and paste content of the script and make it executable.<br />
Details about this container with [ZT Agent](https://github.com/zyclonite/zerotier-docker)<br />

[Controller](1.4.x/zt-controller.md)<br />
Make a file in the /config folder, copy and paste content of the script and make it executable.<br />
**Default credentials for UI:**<br />
* login: admin<br />
* password: zero-ui<br />
* url: http://127.0.0.1:4000<br />

Details about this container with [Zero-UI](https://github.com/dec0dOS/zero-ui)<br />
Controller is [official ZT docker container](https://hub.docker.com/r/zerotier/zerotier)<br />

## After each VyOS update, you must re-run 2 of these scripts<br />

Necessary to run first<br />
```
sudo /config/vyos-docker-install.sh
```

### Select one: Node or Controller

Node/Agent:<br />
```
sudo /config/vyos-docker-zt-agent.sh
```
OR Controller<br />
```
sudo /config/vyos-docker-zt-controller-ui.sh
```