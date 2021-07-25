FROM splunk/splunk:latest

# enable HTTP Event Collector (HEC)
ADD etc/apps/splunk_httpinput/local/inputs.conf /opt/splunk/etc/apps/splunk_httpinput/local/inputs.conf

# Add "webapp" index
ADD etc/apps/search/local/indexes.conf /opt/splunk/etc/apps/search/local/indexes.conf

# Add HEC token for "webapp" index
ADD etc/apps/search/local/inputs.conf /opt/splunk/etc/apps/search/local/inputs.conf


