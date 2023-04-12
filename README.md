# MySQL backup Dockerfile for Railway

This example deploys a container based on [databack/mysql-backup](https://hub.docker.com/r/databack/mysql-backup).
Make sure you have setup a mysql database in [Railway](https://railway.app/).

## ✨ Features
- Backup using CRON syntax
- Backup to Local file, SMB or S3 (or a combination of them)
- Can be configured to backup or restore

## 💁‍♀️ How to use

1. On your [railway.app](https://railway.app/) dashboard, setup a MySQL database
2. Deploy this `Dockerfile` using the "from Github Repo" option
3. Setup below environment variables via Railway dashboard

## 🌐 Environment Variables

```shell
DB_SERVER=${{mysql.MYSQLHOST}}
DB_PORT=${{mysql.MYSQLPORT}}
DB_USER=${{mysql.MYSQLUSER}}
DB_PASS=${{mysql.MYSQLPASSWORD}}
DB_DUMP_CRON='0 3 * * *' # Check out [crontab.guru](https://crontab.guru/) for some help on the CRON syntax
DB_DUMP_TARGET=s3://your-bucket-name/your-path
AWS_ACCESS_KEY_ID=
AWS_SECRET_ACCESS_KEY=

# See the docker image docs for other options
https://hub.docker.com/r/databack/mysql-backup
```

## 📝 Notes

- Docs: https://docs.mautic.org/en
- Original Docker Image: https://hub.docker.com/r/databack/mysql-backup
