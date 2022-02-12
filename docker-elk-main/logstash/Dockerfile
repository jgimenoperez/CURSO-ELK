ARG ELK_VERSION

# https://www.docker.elastic.co/
FROM docker.elastic.co/logstash/logstash:${ELK_VERSION}



# Download JDBC connector for Logstash
RUN curl -L --output "mysql-connector-java-8.0.22.tar.gz" "https://dev.mysql.com/get/Downloads/Connector-J/mysql-connector-java-8.0.22.tar.gz" \
    && tar -xf "mysql-connector-java-8.0.22.tar.gz" "mysql-connector-java-8.0.22/mysql-connector-java-8.0.22.jar" \
    && mv "mysql-connector-java-8.0.22/mysql-connector-java-8.0.22.jar" "mysql-connector-java-8.0.22.jar" \
    && rm -r "mysql-connector-java-8.0.22" "mysql-connector-java-8.0.22.tar.gz"

RUN curl -L -o "sqljdbc_4.2.8112.200_enu.tar.gz" "https://download.microsoft.com/download/F/0/F/F0FF3F95-D42A-46AF-B0F9-8887987A2C4B/sqljdbc_4.2.8112.200_enu.tar.gz" \
    && tar -xf "sqljdbc_4.2.8112.200_enu.tar.gz" "sqljdbc_4.2/enu/jre8/sqljdbc42.jar" \
    && mv "sqljdbc_4.2/enu/jre8/sqljdbc42.jar" "sqljdbc42.jar" \
    && rm -r "sqljdbc_4.2" "sqljdbc_4.2.8112.200_enu.tar.gz"

ENTRYPOINT ["/usr/local/bin/docker-entrypoint"]


# Add your logstash plugins setup here
# Example: RUN logstash-plugin install logstash-filter-json
