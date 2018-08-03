# Telegraf Instructions

Telegraf requires golang version 1.8+, the Makefile requires GNU make.

Dependencies are managed with [gdm](https://github.com/sparrc/gdm),
which is installed by the Makefile if you don't have it already.

1. [Install Go](https://golang.org/doc/install)
2. [Setup your GOPATH](https://golang.org/doc/code.html#GOPATH)
3. Run `go get -d github.com/bush/telegraf`
4. Run `cd $GOPATH/src/github.com`
4. Run `mv bush influxdb`
4. Run `cd influxdb/telegraf`
4. Run `git checkout wrsiot`
5. Run `make`

Before you run telegraf you must create a default thing definition in Telit and create an application based on that thing definition.  Copy the sample telegraf.conf file to the same directory as the newly created telegraf binary. Edit telegraf.conf - change the username and password fields under the `outputs.wrsiot` section.  For username enter the device thingkey.  For password should be the app token. 

Now simply run `./telegraf --config telegraf.conf`

You should now be able to view cpu metrics of your thing in Telit.  For configuring more metrics follow the telegraf configuration instructions.  For convienence we have included an Intel based binary of telegraf so you can test without having to build telegraf from source.
