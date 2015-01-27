# Base linux image
FROM dockerfile/java:oracle-java7

WORKDIR /

# Install necessary tools
RUN apt-get update && apt-get install -y \
  unzip

# Copy the DDF files over
ADD http://artifacts.codice.org/service/local/repositories/releases/content/ddf/distribution/ddf/2.6.0/ddf-2.6.0.zip /tmp/ddf.zip

# Unzip the files 
RUN unzip -uo /tmp/ddf.zip -d /opt/ \
  && rm /tmp/ddf.zip 

# Set environment variables
ENV PATH $PATH:$JAVA_HOME/bin

# Expose server port
EXPOSE 8181

CMD ["/opt/ddf-2.6.0/bin/ddf"]
