# mysqldb:dev
FROM mysql/mysql-server:5.7 as mysqldb
LABEL maintainer="khoa002@gmail.com"
#RUN echo "[mysqld]" >> /etc/my.cnf
RUN echo "lower_case_table_names = 0" >> /etc/my.cnf
#RUN echo "socket=/var/lib/mysql/mysql.sock" >> /etc/my.cnf
#RUN echo "innodb_buffer_pool_size = 4G" >> /etc/mysql/my.cnf
#RUN echo "innodb_log_buffer_size = 256M" >> /etc/mysql/my.cnf
#RUN echo "innodb_log_file_size = 1G" >> /etc/mysql/my.cnf
#RUN echo "innodb_write_io_threads = 16" >> /etc/mysql/my.cnf
#RUN echo "innodb_flush_log_at_trx_commit = 0" >> /etc/mysql/my.cnf

#NEED TO RUN THE FOLLOWING AFTER THE CONTAINER IS BUILT
#if mysql v8+
#     CREATE USER 'root'@'%' IDENTIFIED BY 'root';
#     GRANT ALL PRIVILEGES ON *.* TO 'root'@'%' WITH GRANT OPTION;
#then, just run this if mysql version below 8
#     GRANT ALL ON *.* TO 'root'@'%' IDENTIFIED BY 'root';