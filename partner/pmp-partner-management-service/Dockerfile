FROM openjdk:11

# can be passed during Docker build as build time environment for github branch to pickup configuration from.

ARG spring_config_label


# can be passed during Docker build as build time environment for spring profiles active 

ARG active_profile

# can be passed during Docker build as build time environment for config server URL 

ARG spring_config_url

# environment variable to pass active profile such as DEV, QA etc at docker runtime

ENV active_profile_env=${active_profile}

# environment variable to pass github branch to pickup configuration from, at docker runtime

ENV spring_config_label_env=${spring_config_label}


# environment variable to pass spring configuration url, at docker runtime

ENV spring_config_url_env=${spring_config_url}


COPY ./target/pmp-partner-management-service-*.jar pmp-partner-management-service.jar

EXPOSE 9102



CMD ["java","-jar","-Dspring.cloud.config.label=${spring_config_label_env}","-Dspring.profiles.active=${active_profile_env}","-Dspring.cloud.config.uri=${spring_config_url_env}","pmp-partner-management-service.jar"]