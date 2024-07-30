FROM oraclelinux:7-slim

ARG KEY=https://repo.mysql.com/RPM-GPG-KEY-mysql

ARG MYSQL_SHELL_PACKAGE_URL=https://dev.mysql.com/get/Downloads/MySQL-Shell/mysql-shell-9.0.1-1.el7.x86_64.rpm

RUN rpmkeys --import $KEY \
  && yum install -y \
    $MYSQL_SHELL_PACKAGE_URL \
  && yum clean all
COPY run.sh /run.sh
ENTRYPOINT ["/run.sh"]
CMD ["mysqlsh"]
