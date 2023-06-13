ARG NAMESPACE
ARG VERSION
ARG AUTHORS
ARG BASE
FROM ${NAMESPACE}/${BASE}:${VERSION}
LABEL authors=${AUTHORS}

USER 1200

RUN sudo apt update && sudo apt install python3-pip && sudo apt install vim && pip install DrissionPage && sudo apt install google-chrome-stable && sudo ln -s /usr/bin/google-chrome /usr/bin/chrome

#====================================
# Scripts to run Selenium Standalone
#====================================
COPY start-selenium-standalone.sh /opt/bin/start-selenium-standalone.sh

#==============================
# Supervisor configuration file
#==============================
COPY selenium.conf /etc/supervisor/conf.d/

# Copying configuration script generator
COPY generate_config /opt/bin/generate_config

# Boolean value, maps "--relax-checks"
ENV SE_RELAX_CHECKS true

EXPOSE 4444


