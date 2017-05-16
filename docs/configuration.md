# Configuration Guide

## Summary

This SDK uses a structure called "Config" to store and manage configuration, read comments of public functions in ["Common/Config.cs"](https://github.com/yunify/qingstor-sdk-net/blob/master/src/Common/Config.cs) for details.

Except for Access Key, you can also configure the API endpoint for private cloud usage scenario. All available configurable items are listed in the default configuration file.

___Default Configuration File:___

``` yaml
# QingStor services configuration

access_key_id: 'ACCESS_KEY_ID'
secret_access_key: 'SECRET_ACCESS_KEY'

host: 'qingstor.com'
port: 443
protocol: 'https'
connection_retries: 3

# Valid log levels are "debug", "info", "warn", "error", and "fatal".
log_level: 'warn'

```

## Usage

Just create a config structure instance with your API Access Key, and initialize services you need with Init() function of the target service.

### Code Snippet

Create default configuration

``` C#
CConfig Config = new CConfig();
```

Create configuration from Access Key

``` C#
CConfig Config = new CConfig("ACCESS_KEY_ID", "SECRET_ACCESS_KEY");

CConfig Config = new CConfig();
Config.AccessKeyID = "ACCESS_KEY_ID";
Config.SecretAccessKey = "SECRET_ACCESS_KEY";
```

Load configuration from config file

``` C#
CConfig Config = new CConfig("PATH/TO/FILE");
```

Change API endpoint

``` C#
CConfig Config = new CConfig();
Config.Protoco = "https";
Config.Host = "api.private.com";
Config.Port = 4433;
```
