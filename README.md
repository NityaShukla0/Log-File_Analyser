

# LogAnalyzer

See how fast is rendering in your Ruby on Rails app. Based on information from logs. Provides you a picture of how often renders and how fast renders your views.

## Sample

[![Sample](https://raw.githubusercontent.com/igorkasyanchuk/log_analyzer/master/docs/screenshot.png)](https://raw.githubusercontent.com/igorkasyanchuk/log_analyzer/master/docs/screenshot.png)

[![Reports](https://raw.githubusercontent.com/igorkasyanchuk/log_analyzer/master/docs/reports.png)](https://raw.githubusercontent.com/igorkasyanchuk/log_analyzer/master/docs/reports.png)

You can see columns:

* Type - type of file (partial or view = P or V)
* View - name of view
* Count - number of renders
* Avg - average time of rendering (in milliseconds)
* Max - maximum time of rendering
* Min - minimum time of rendering

## Installation

Could be installed as standalone (without adding to Gemfile).

Add this line to your application's Gemfile:

```ruby
gem 'log_analyzer'
```

And then execute:

    $ bundle

Or install it yourself as:

    $ gem install log_analyzer

## Usage

After installation run in console command `log_analyzer -f log/development.log`. You can change the file or sorting (time, count, name).

Samples:

* `log_analyzer log/development.log -s count`
* `log_analyzer log/production.log`
* `log_analyzer production.log -csv`
* `log_analyzer production.log -pdf`
* `log_analyzer -f log/production.log -s name`
* `log_analyzer -f log/production.log -s time -f v`
* `log_analyzer -f log/production.log -s rtime -f v`
* `log_analyzer -file log/production.log -sort count`
* `log_analyzer -file log/production.log -sort count -filter view`
* `log_analyzer -file log/production.log -sort count -filter partial`
* `log_analyzer -file log/production.log -sort time -filter p`
* `log_analyzer development.log -csv -s time -f p`
* `log_analyzer development.log -xls -s time -f p`
* `log_analyzer log/production.log -pdf --short`
* `log_analyzer -file log/production.log --short`
* `log_analyzer --help`

**Based on results you can get an idea what to optimize. For example optimizing most often rendering view could give huge benefit. Now with this tool you can find out what are the numbers.**

Based on the observations I suggest to run this tool for files less than 1Gb. If you have enough RAM - download the log file to local machine and then run the tool.

