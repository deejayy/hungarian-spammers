# Spamszűrőlista

WARNING. Ez egy (vagy több) személyes gyűjtés, előfordulhat, hogy nem 1:1-ben használható nálad, fusd át a listát, mielőtt alkalmazod.

/etc/postfix/main.cf

```
...

smtpd_sender_restrictions =
	check_sender_mx_access regexp:/etc/postfix/sender_mx_access,
	check_sender_access regexp:/etc/postfix/sender_mx_access,
	check_sender_ns_access regexp:/etc/postfix/sender_mx_access,
	permit

smtpd_client_restrictions =
	check_client_access regexp:/etc/postfix/sender_mx_access,
	check_client_mx_access regexp:/etc/postfix/sender_mx_access,
	check_client_ns_access regexp:/etc/postfix/sender_mx_access,
	check_reverse_client_hostname_access regexp:/etc/postfix/sender_mx_access,
	check_reverse_client_hostname_mx_access regexp:/etc/postfix/sender_mx_access,
	check_reverse_client_hostname_ns_access regexp:/etc/postfix/sender_mx_access,
	permit

...
```
/etc/postfix/sender_mx_access
