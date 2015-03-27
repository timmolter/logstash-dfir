## Logstash

	sudo nano /etc/logstash/conf.d/bro-conn_log.conf

	sudo -u logstash /opt/logstash/bin/logstash -f /etc/logstash/conf.d/bro-conn_log.conf --debug

	sudo -u logstash /opt/logstash/bin/logstash agent -f /etc/logstash/conf.d/bro-conn_log.conf --configtest

## Bro

	tail -f /nsm/bro/logs/current/conn.log

## Print out bro log headers

	cd /nsm/bro/logs/current/
	grep -E "^#fields" *.log

## Pull down conf files

	cd /etc/logstash/conf.d/
	sudo wget -N https://raw.githubusercontent.com/timmolter/logstash-dfir/master/conf_files/bro/bro-conn_log.conf
	sudo wget -N https://raw.githubusercontent.com/timmolter/logstash-dfir/master/conf_files/bro/bro-dns_log.conf
	sudo wget -N https://raw.githubusercontent.com/timmolter/logstash-dfir/master/conf_files/bro/bro-files_log.conf
	sudo wget -N https://raw.githubusercontent.com/timmolter/logstash-dfir/master/conf_files/bro/bro-http_log.conf
	sudo wget -N https://raw.githubusercontent.com/timmolter/logstash-dfir/master/conf_files/bro/bro-notice_log.conf
	sudo wget -N https://raw.githubusercontent.com/timmolter/logstash-dfir/master/conf_files/bro/bro-ssh_log.conf
	sudo wget -N https://raw.githubusercontent.com/timmolter/logstash-dfir/master/conf_files/bro/bro-ssl_log.conf
	sudo wget -N https://raw.githubusercontent.com/timmolter/logstash-dfir/master/conf_files/bro/bro-weird_log.conf
	sudo wget -N https://raw.githubusercontent.com/timmolter/logstash-dfir/master/conf_files/bro/bro-x509_log.conf

	sudo -u logstash /opt/logstash/bin/logstash agent -f /etc/logstash/conf.d --configtest
