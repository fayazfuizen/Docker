# Use the CentOS 7 base image
FROM centos:7

# Set metadata labels
LABEL "Author"="fayaz mohammed"
LABEL "Project"="earth"

# Install necessary packages - Apache, wget, and unzip
RUN yum install httpd wget unzip -y

# Download the website template
RUN wget https://www.tooplate.com/zip-templates/2113_earth.zip --no-check-certificate

# Unzip the downloaded template
RUN unzip 2113_earth.zip

# Copy the contents of the unzipped template to the web server directory
RUN cp -r 2113_earth/* /var/www/html/

# Start the Apache web server in the foreground
CMD ["/usr/sbin/httpd", "-D", "FOREGROUND"]

# Expose port 80 for web traffic
EXPOSE 80

# Set the working directory to the web server directory
WORKDIR /var/www/html

# Create a volume for Apache's log files
VOLUME /var/log/httpd
