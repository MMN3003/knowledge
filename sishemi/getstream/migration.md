1. turn of the server 14:25
2. get server access 14:46
3. get all sendbird messages 15:49
4. run  script to create import file
	1. update script to connect production database
	2. upload all.zip file from local to server
	```bash
scp all.zip root@46.101.244.180:/root
```
	3. install packages
	```bash
	sudo apt update
	sudo apt install unzip nodejs npm tmux
	unzip all.zip
	cd all
	npm i
	node index.js
```
	4. after code finished  download output.json
	```bash
	scp root@46.101.244.180:/root/all/output.json /Users/mohsen/output.json
```
5. upload import file to  getstream : 17:06
6. run after_import.js after import 




- pooya
	- env getstream
	- channels id in suggestion
- amin -sobhan
	- new build with getstream key and secret
- mohsen
	- add flash-member
	- add push notification

