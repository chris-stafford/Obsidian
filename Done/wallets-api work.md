#wallet-stream 
#integration-deltix-marketdata

port-forward: redis-cache: 6379
port-forward: user-service: 9099

- [x] int-deltix-cache
	- [x] move namespace to integration (put off for later)
	- [ ] rename to integration-deltix-marketvalue (put off for later)
	- [x] stream to support arbitrary securities, do not assume USD
	- [x] redis cache impl for marketvalues
	- [x] send value immediately upon stream connect
	- [x] figure out exceptions with 'socket not ready'
	- [ ] update auth token implementation to preferred solution
- [x] wallets-api
	- [x] only send currency-translated wallet upon market value change
	- [ ] take deltix header value for currency translations
	- [x] subscribe ad-hoc to marketvalue streams
	- [x] do not open a stream per marketvalue security
	- [x] investigate whether we need to translate summaries
	- [x] figure out exceptions with 'socket not ready'