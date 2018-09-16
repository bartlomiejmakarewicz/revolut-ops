# revolut-ops
## Sample Beanstalk environment config
### Zero downtime deployment
https://docs.aws.amazon.com/elasticbeanstalk/latest/dg/environmentmgmt-updates-immutable.html
```yml
settings:
  aws:autoscaling:updatepolicy:rollingupdate:
    RollingUpdateEnabled: 'true'
    RollingUpdateType: Immutable
  aws:elasticbeanstalk:command:
    DeploymentPolicy: Immutable
```
### Connection draining
https://docs.aws.amazon.com/elasticloadbalancing/latest/classic/config-conn-drain.html
```yml
settings:
  aws:elb:policies:
    ConnectionDrainingEnabled: 'true'
```
