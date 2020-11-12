# wordpress-backup-quickstart

This is a docker-compose file that helps you getting up-and-running quickly with [wordpress-backup](https://github.com/angelo-v/wordpress-backup).

1. ```git clone git@github.com:angelo-v/wordpress-backup-quickstart.git my-blog```
2. ```cd my-blog```
3. ```make up```

On first run you will be asked for the database credentials and configuration. Those will be written to the file `.env` and used further on.

## Docker stack deployment

Run `make stack` to deploy a stack in swarm mode.

## Customization

Customize the variables in ```.env``` and/or the configuration in ```docker-compose.yml``` to your requirements as needed. ```wordpress-backup-quickstart``` is just ment to give you a head start for setting up the containers and is not ment to constrain you in any way.

## Contact

Please contact me for any questions & feedback: angelo.veltens@online.de


## parasol corp how to backup

**Restore**
`docker exec wordpress-backup-quickstart_backup_1 restore 20200807`  <- number is the date in the backup directory
20200807 would be the dateid of the file being backed up. Given that it's only doing day based backups, we should be interested in doing github commits often.

**Backup**
`docker exec wordpress-backup-quickstart_backup_1 backup`

**Restore**
`docker exec backup-my-blog restore 20141114` where 20141114 is the backup_20141114. backup files

Seems to work across:
- Wordress versions
- posts
- themes ???
