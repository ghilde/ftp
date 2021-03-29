# goftp #

[![Build Status](https://travis-ci.org/ghilde/ftp.svg?branch=master)](https://travis-ci.org/ghilde/ftp)
[![Coverage Status](https://coveralls.io/repos/ghilde/ftp/badge.svg?branch=master&service=github)](https://coveralls.io/github/ghilde/ftp?branch=master)
[![Go ReportCard](http://goreportcard.com/badge/ghilde/ftp)](http://goreportcard.com/report/ghilde/ftp)
[![godoc.org](https://godoc.org/github.com/ghilde/ftp?status.svg)](http://godoc.org/github.com/ghilde/ftp)

A FTP client package for Go. Forked from (https://github.com/jlaffaye) and modified for my own customisations. Two major changes (list may change over time):
1. Make available any and all messages that return from the FTP server
2. Improve upload (STOR) functionality

## Install ##

```
go get -u github.com/ghildebr/ftp
```

## Example ##

```go
c, err := ftp.DialWithOptions("ftp.example.org", DialWithTimeout(5*time.Second))
if err != nil {
    t.Fatal(err)
}

err = c.Login("anonymous", "anonymous")
if err != nil {
    t.Fatal(err)
}

// Do something with the FTP conn

if err := c.Close(); err != nil {
    t.Fatal(err)
}
```
