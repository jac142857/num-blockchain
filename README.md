# project

## install
```
npm run install
```

### Recompile to use sqlite3 need to use
```
npm run postinstall
```

### Start the test
```
npm run electron:serve
```

### Pack
```
npm run electron:build
```
> Build Linux `sudo apt-get install rpm`

### rpm

> Install `rpm -ivh xxxxx-1.0.1.x86_64.rpm --nodeps --force`

> Run `xxxxx --no-sandbox`

> Uninstall `rpm -e xxxxx`

### deb
> Install `sudo dpkg -i xxxxx_1.0.1_amd64.deb`

> Run `xxxxx --no-sandbox`

> Uninstall `dpkg -P xxxxx`

### Configuration file

`.env.development`  Local test configuration
`.env.production`  Production environment configuration



### Explain

- `src/utils/db.js` Initialize the SQL file, it will be automatically judged, if there is no db file, it will be created
- `src/db/upgradeSql.js` To update the SQL of the database for a smooth upgrade, the overwrite installation will determine the version to update the SQL at the first startup, and change some table structures, mainly to retain the old data
- `extraResources/gpod.exe` The file is geth startup file
- `extraResources/num-plot.exe` Program used for p disk
- If the gpod.exe file update needs to delete the geth directory of the node, you need to change two places to search for the `localStorage.clear` method under the `src/App.vue` file. The version here needs to be modified to the last version and cannot be changed to The released version, there is also a search for `deleteFolder` in `src/background.js`, the version here is the same as the version just now 

### Mobile phone operation

> After running the PC client, import or create a new account, select an account, then the PC client will start the tcp service and http service for the mining client to access, the tcp service start port is: 8000, the [mining client(apk/ios)](../../releases) only needs to use it IP + Port (port access), for example: 127.0.0.1:8000. This IP can be an internal network IP or an external network IP. The internal network IP can be viewed in the device options of the PC client 
- Run the PC client
- Import or create a new account, select an account
- The [mining client(apk/ios)](../../releases) uses ip+port for example: 127.0.0.1:8000
- IP can be internal network IP or external network IP


