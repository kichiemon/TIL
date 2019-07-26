# GitLabRunnerでのCI


```
g diff .gitlab-ci.yml
g commit -m"update gitlab ci";g push
less .gitlab-ci.yml
g commit -m"update gitlab ci"
gitlab-runner exec shell test
gitlab-runner exec shell test --verbose
gitlab-runner exec shell build
cat .gitlab-ci.yml
gitlab-runner start
gitlab-runner stop
sudo gitlab-runner exec shell test
gitlab-runner exec shell
gitlab-runner exec
sudo gitlab-runner restart
sudo gitlab-runner verify
gitlab-runner verify
gitlab-runner health-check
gitlab-runner help
gitlab-runner restart
sudo gitlab-runner unregister
gitlab-runner unregister gitlab-macbook-so
gitlab-runner unregister
gitlab-runner --debug run
cp ../../../gitlab.devsep.com/GANMA/reader2-ios/.ruby-version ./
gitlab-runner register
gitlab-runner status
cat .gitlab-ci.yml|pbcopy
g commit -m"setup gitlab ci yaml"
g reset .gitlab-ci.yml
gitlab-runner -h
sudo gitlab-runner register
# https://docs.gitlab.com/runner/install/osx.html#manual-installation-official
gitlab-runner install
 gitlab-runner install
 ```



## gitlab runner help
```
$ gitlab-runner help

Runtime platform                                    arch=amd64 os=darwin pid=72012 revision=d0b76032 version=12.0.2
NAME:
   gitlab-runner - a GitLab Runner

USAGE:
   gitlab-runner [global options] command [command options] [arguments...]

VERSION:
   12.0.2 (d0b76032)

AUTHOR:
   GitLab Inc. <support@gitlab.com>

COMMANDS:
     exec                  execute a build locally
     list                  List all configured runners
     run                   run multi runner service
     register              register a new runner
     install               install service
     uninstall             uninstall service
     start                 start service
     stop                  stop service
     restart               restart service
     status                get status of a service
     run-single            start single runner
     unregister            unregister specific runner
     verify                verify all registered runners
     artifacts-downloader  download and extract build artifacts (internal)
     artifacts-uploader    create and upload build artifacts (internal)
     cache-archiver        create and upload cache artifacts (internal)
     cache-extractor       download and extract cache artifacts (internal)
     cache-init            changed permissions for cache paths (internal)
     health-check          check health for a specific address
     help, h               Shows a list of commands or help for one command

GLOBAL OPTIONS:
   --cpuprofile value           write cpu profile to file [$CPU_PROFILE]
   --debug                      debug mode [$DEBUG]
   --log-format value           Choose log format (options: runner, text, json) [$LOG_FORMAT]
   --log-level value, -l value  Log level (options: debug, info, warn, error, fatal, panic) [$LOG_LEVEL]
   --help, -h                   show help
   --version, -v                print the version
```
