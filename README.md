# Threat Intelligent Dashboard
In the current era of cyber warfare and security threat attacks, it comes as a crucial need to constantly monitor and analyse the ongoing threats and day to day malicious activities. The Cyber Threat Intelligence Analysis project created by me deals with real-time extraction of raw threat intelligence data like malicious IP addresses, latest information regarding botnets, malwares, spams, phishing domains across the world from multiple reliable sources and threat feeds across the internet, and make a statistical dashboard of this data, which includes real-time updation of multiple statistical visualisations like threat intelligence pie-charts, GeoIP maps, country comparisons, date-time analysis and other data aggregation techniques. This Threat intelligence Dashboard will help analysing the day to day cyber attacks happening in different regions of the world and their impact on organisations. It will also help in making the current system security better by analysing the threats and taking measures in accordance with the same.

# Instructions for starting the Dashboard

1. cd into the &quot;elasticsearch&quot; folder which is inside ELK\_trial folder and run the command &quot;bin/elasticsearch&quot;.

2. After elasticsearch is started, cd into the &quot;kibana final dashboard&quot; folder and run the command &quot;bin/kibana&quot;. This will start the dashboard service.

3. After kibana is started, go to browser and type &quot;localhost:5601&quot;, this will start the Dashboard GUI.

# Instructions for Fetching Real-time data

After starting elasticsearch using the above instructions, start logstash and the python script in the following way:

1. After elasticsearch is started, cd into the &quot;logstash&quot; folder which is inside ELK\_trial folder and run the command &quot;bin/logstash -f cymon\_data.conf&quot;.

2. After logstash is started, cd into &quot;scp\_data&quot; folder which is inside the logstash folder, and run the command &quot;python fetch\_data2.py&quot;. This will start the data extraction process.

## _Important Notes_

1. If you change the name or location of folders, you&#39;ll have to specify the same path/name of the folder inside the logstash configuration file named as &quot;cymon\_data.conf&quot;, therwise the data will not be fed into elasticsearch.

3. The kibana dashboard for mac will not work on ubuntu but logstash and elasticsearch will work. Similarly the kibana for ubuntu will not work on mac, but logstash and elasticsearch will work.

4. I have tried to do proper error-exception handling in my python script, which will make the script run even in case of errors, but it will display what could be the error. The only possible error I found till now was when there was no internet connection or when cymon API blocked us for too many requests (which I fixed eventually).

5. To stop any of the E, L, K, Python process, you have to press &quot;windows+c&quot; in windows-based keyboards and &quot;control+c&quot; on apple-based keyboards.

6. When there is no internet connection, two things will not work:
  1. The data extraction.
  2. Kibana Tile Map service. This means that although the geo-points will be shown on the map-space, but the geographical locations will not be shown on the map.

7. If shifted the project on some other system, installation of 3rd-Party Python libraries might be needed, and Java 8 might be needed for the Elastic-Stack (ELK Stack).

8. The python script fetches data every hour.

9. All the files can be opened using sublime text or any other text editor.

10. In order to make the dashboards revolve, download the chrome extension &quot;revolver&quot;.
