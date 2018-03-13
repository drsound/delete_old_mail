# Delete Old Mail
Deletes POP3 mail older than a specified amount of days.

Used with _fetchmail_ to compensate for its inability to leave some mails on the server: _fetchmail_ can keep or delete all mails from the server, it can't keep just recent mails (newer than a set number of days).

To keep most recent mails on the server, run _fetchmail_ keeping mails on the server, then run _delete_old_mail_.

## Configuration
Configuration is provided via an YAML file located in /etc/delete_old_mail.conf. This file may contain multiple POP3 account entries:
* **host:** POP3 host name
* **ssl:** can be **true** or **false**. If **true** connection port is 995, otherwise 110.
* **user:** POP3 user
* **password:** POP3 password
* **days:** mails older than this number of days will be deleted

## Requirements
It requires the _mail_ gem to parse mail headers, just install it with ```bundle```.