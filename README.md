[![license](https://img.shields.io/github/license/mashape/apistatus.svg?maxAge=2592000)](https://opensource.org/licenses/MIT)


# Rundeck Execution LOG GROK pattern for Graylog

**Pattern:**

	"name":"RUNDECKEXECUTIONLOG",
	"pattern":"\\[%{TIMESTAMP_ISO8601:rundeck_ex_timestamp}\\] %{USERNAME:rundeck_ex_user} %{WORD:rundeck_ex_action} \\[%{NUMBER:rundeck_ex_id:int}:%{WORD:rundeck_ex_return}\\] %{DATA:rundeck_ex_project} %{GREEDYDATA} \\\"%{DATA:rundeck_ex_job}\\\""

i.e.:

**message**

	[2016-11-18 16:05:28,387] User1 start [51:running] ProjectName User1/- "Group/JobName" [56e4c0e7-da90-4267-9f19-3ff3135eb680]

**fields**

	rundeck_ex_timestamp: 2016-11-18 16:05:28,387
	rundeck_ex_action: start
	rundeck_ex_id: 51
	rundeck_ex_job: Group/JobName
	rundeck_ex_project: ProjectName
	rundeck_ex_return: running
	rundeck_ex_user: User1

