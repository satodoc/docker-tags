# docker-tags

## Description

This script uses the DockerHub API to retrieve a list of image tags.

## Usage

Please place it in a directory that passes the PATH as appropriate, or create an alias, symbolic, etc. and use it.

Since temporary directories and files are created under "/tmp" in the process of parsing the response JSON, you need write permission under "/tmp".<br>
"/tmp" can be changed by the environment variable `${TMPDIR}`.

#### ex1) Simple usage.

```shell
[docker@docker-host ~]$ docker-tags centos
centos:latest
centos:centos7.6.1810
centos:centos7.5.1804
centos:centos7.4.1708
centos:centos7.3.1611
centos:centos7.2.1511
centos:centos7.1.1503
centos:centos7.0.1406
centos:centos7
centos:centos6.9
centos:centos6.8
centos:centos6.7
centos:centos6.6
centos:centos6.10
centos:centos6
centos:centos5.11
centos:centos5
centos:7.6.1810
centos:7.5.1804
centos:7.4.1708
centos:7.3.1611
centos:7.2.1511
centos:7.1.1503
centos:7.0.1406
centos:7
centos:6.9
centos:6.8
centos:6.7
centos:6.6
centos:6.10
centos:6
centos:5.11
centos:5
```

#### ex2) Output file & Detail option.

```shell
[docker@docker-host ~]$ docker-tags -d -o docker-centos-tags.tsv centos
[docker@docker-host ~]$ cat docker-centos-tags.tsv
tag     size    last_updated
latest  75403831        2019-05-11T01:13:40.692601Z
centos7.6.1810  75161332        2019-05-11T01:13:36.617627Z
centos7.5.1804  74692733        2019-05-11T01:13:34.033772Z
centos7.4.1708  73358335        2019-05-11T01:13:29.557664Z
centos7.3.1611  72170894        2019-05-11T01:13:27.403263Z
centos7.2.1511  71553381        2019-05-11T01:13:26.586999Z
centos7.1.1503  77375353        2019-05-11T01:13:22.710971Z
centos7.0.1406  76789367        2019-05-11T01:13:18.660373Z
centos7 75403831        2019-05-11T01:13:15.423566Z
centos6.9       70181649        2019-05-11T01:13:10.722926Z
centos6.8       70226281        2019-05-11T01:13:08.989816Z
centos6.7       67814264        2019-05-11T01:13:06.308806Z
centos6.6       73689716        2019-05-11T01:13:03.407549Z
centos6.10      69800401        2019-05-11T01:13:00.432911Z
centos6 69835815        2019-05-11T01:12:57.598615Z
centos5.11      87094724        2017-04-06T20:17:29.333542Z
centos5 87342331        2017-04-06T20:16:24.015937Z
7.6.1810        75161332        2019-05-11T01:12:56.206570Z
7.5.1804        74692733        2019-05-11T01:12:52.848602Z
7.4.1708        73358335        2019-05-11T01:12:49.971649Z
7.3.1611        72170894        2019-05-11T01:12:45.185299Z
7.2.1511        71553381        2019-05-11T01:12:43.286737Z
7.1.1503        77375353        2019-05-11T01:12:40.019129Z
7.0.1406        76789367        2019-05-11T01:12:38.015816Z
7       75403831        2019-05-11T01:12:34.106340Z
6.9     70181649        2019-05-11T01:12:31.078690Z
6.8     70226281        2019-05-11T01:12:27.462311Z
6.7     67814264        2019-05-11T01:12:25.385696Z
6.6     73689716        2019-05-11T01:12:22.647196Z
6.10    69800401        2019-05-11T01:12:19.263911Z
6       69835815        2019-05-11T01:12:16.895622Z
5.11    87094724        2017-04-06T20:17:31.013272Z
5       87342331        2017-04-06T20:16:25.879532Z
[docker@docker-host ~]$
```

#### ex3) Verbose option.

This option displays the progress of curl processing, etc.

```shell
[docker@docker-host ~]$ docker-tags -v centos
Getting tag list from docker hub at page 1...
  % Total    % Received % Xferd  Average Speed   Time    Time     Time  Current
                                 Dload  Upload   Total   Spent    Left  Speed
100  4833    0  4833    0     0   4163      0 --:--:--  0:00:01 --:--:--  4166
Complated get tag list from docker hub at page 1.
Getting tag list from docker hub at page 2...
  % Total    % Received % Xferd  Average Speed   Time    Time     Time  Current
                                 Dload  Upload   Total   Spent    Left  Speed
100  3937    0  3937    0     0   4718      0 --:--:-- --:--:-- --:--:--  4714
Complated get tag list from docker hub at page 2.
Getting tag list from docker hub at page 3...
  % Total    % Received % Xferd  Average Speed   Time    Time     Time  Current
                                 Dload  Upload   Total   Spent    Left  Speed
100  4254    0  4254    0     0   4408      0 --:--:-- --:--:-- --:--:--  4408
Complated get tag list from docker hub at page 3.
Getting tag list from docker hub at page 4...
  % Total    % Received % Xferd  Average Speed   Time    Time     Time  Current
                                 Dload  Upload   Total   Spent    Left  Speed
100  1133    0  1133    0     0   1198      0 --:--:-- --:--:-- --:--:--  1198
Complated get tag list from docker hub at page 4.
centos:latest
centos:centos7.6.1810
centos:centos7.5.1804
centos:centos7.4.1708
centos:centos7.3.1611
centos:centos7.2.1511
centos:centos7.1.1503
centos:centos7.0.1406
centos:centos7
centos:centos6.9
centos:centos6.8
centos:centos6.7
centos:centos6.6
centos:centos6.10
centos:centos6
centos:centos5.11
centos:centos5
centos:7.6.1810
centos:7.5.1804
centos:7.4.1708
centos:7.3.1611
centos:7.2.1511
centos:7.1.1503
centos:7.0.1406
centos:7
centos:6.9
centos:6.8
centos:6.7
centos:6.6
centos:6.10
centos:6
centos:5.11
centos:5
```


## Options

* `-o` or `--output-file`<br>
By default, output to staundard out, but specified this option to file.
* `-r` or `--reverse`<br>
By default, sort direction is descending by name, but when this option is set it is ascending by name.
* `-d` or `--detail`<br>
By default, only the tag name is output, but if this option is specified, the size and the last modified date are also output.
* `-v` or `--verbose`<br>
Show the process progress. 
* `-h` or `--help`<br>
Show help message.