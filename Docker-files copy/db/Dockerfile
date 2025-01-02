FROM mysql:8.0.33
LABEL "AUTHOR"="SIDDHESH"
LABEL "PROJECT"="VPROFILE_db"

ENV MYSQL_ROOT_PASSWORD="vprodbpass"
ENV MYSQL_DATABASE="accounts"
COPY db_backup.sql /docker-entrypoint-initdb.d/


#Working version
# FROM mysql:8.0.32
# LABEL "AUTHOR"="SIDDHESH"
# LABEL "PROJECT"="VPROFILE_db"

# ENV MYSQL_ROOT_PASSWORD="vprodbpass"
# ENV MYSQL_DATABASE="accounts"
# COPY db_backup.sql /docker-entrypoint-initdb.d/
