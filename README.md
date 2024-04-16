# filebeat-logstash-pipeline
Logstash pipeline to parse Filebeat logs

This pipeline has a very much restricted feature set. In fact it was built for a single use case. As of now it is unclear if the pipeline will even be developed further.

## Input and Output ##

This pipeline does not provide inputs or outputs so you can configure whatever you need. Files named `input.conf` and `output.conf` will not interfere with updates via git, so name your files accordingly.

Here are examples how your files could look if you want to use a local Redis instance.

```
input {
  redis {
    host => localhost
    key => "filebeat"
    data_type => list
  }
}

output {
  redis {
    key => "forwarder"
    data_type => list
    host => localhost
  }
}
```
