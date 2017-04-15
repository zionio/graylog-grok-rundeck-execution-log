[![license](https://img.shields.io/github/license/mashape/apistatus.svg?maxAge=2592000)](https://opensource.org/licenses/MIT)


Rundeck Execution Log GROK pattern for Graylog
==============================================

Pattern
-------

	"name":"RUNDECKEXECUTIONLOG",
	"pattern":"\\[%{TIMESTAMP_ISO8601:rundeck_ex_timestamp}\\] %{USERNAME:rundeck_ex_user} %{WORD:rundeck_ex_action} \\[%{NUMBER:rundeck_ex_id:int}:%{WORD:rundeck_ex_return}\\] %{DATA:rundeck_ex_project} %{GREEDYDATA} \\\"%{DATA:rundeck_ex_job}\\\""

Example message
---------------

	[2016-11-18 16:05:28,387] User1 start [51:running] ProjectName User1/- "Group/JobName" [56e4c0e7-da90-4267-9f19-3ff3135eb680]

Fields
------

	rundeck_ex_timestamp: 2016-11-18 16:05:28,387
	rundeck_ex_action: start
	rundeck_ex_id: 51
	rundeck_ex_job: Group/JobName
	rundeck_ex_project: ProjectName
	rundeck_ex_return: running
	rundeck_ex_user: User1

Installation
------------

Go to **Graylog Web Interface** -> **System** -> **Content Packs** then select *content_pack.json* file and upload it.

[![screen1](https://i.imgbox.com/HAsDC4FR.png)](https://i.imgbox.com/wP2n4HXH.png)