# GTFO
GTFO my server yo

This script scan Apache/Nxing error logs and block IP addresses trying to access specific patterns. It uses iptables rules to block malicious IP addresses. Being not a deamon, it needs tu be run by a cron job.

## Installation

 git clone https://github.com/linuxitux/GTFO.git
 chmod +x GTFO/gtfo

Add this to root's crontab:

 */2 * * * * /path/to/GTFO/gtfo > /var/log/gtfo.log

## Configuration

Edit the following variables inside gtfo according to your needs:

ERRLOG - Path to Apache/Nginx error log.
WORKDIR - Installation directory.
LINES - Number of lines to parse.
KEYWORDS - List of patterns to ban.
HOURS - Duration of bans (in hours).

Example:

ERRLOG="/usr/local/nginx/logs/error.log"
WORKDIR="/usr/local/gtfo"
LINES=100
# We don't have Wordpress or Joomla! here, so GTFO my server yo
KEYWORDS=("wp-login.php" "administrator/index.php")
HOURS=1

