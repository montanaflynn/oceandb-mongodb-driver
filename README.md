[![banner](https://raw.githubusercontent.com/oceanprotocol/art/master/github/repo-banner%402x.png)](https://oceanprotocol.com)

# oceandb-mongodb-driver

>    🐳  [Mongo DB](https://www.mongodb.com/) driver for OceanDB (Python).
>    [oceanprotocol.com](https://oceanprotocol.com)

[![Travis (.com)](https://img.shields.io/travis/com/oceanprotocol/oceandb-mongodb-driver.svg)](https://travis-ci.com/oceanprotocol/oceandb-mongodb-driver)
[![Codacy coverage](https://img.shields.io/codacy/coverage/6b8d544ca5064cfeb00e679b265f5ac9.svg)](https://app.codacy.com/project/ocean-protocol/oceandb-mongodb-driver/dashboard)
[![PyPI](https://img.shields.io/pypi/v/oceandb-mongodb-driver.svg)](https://pypi.org/project/oceandb-mongodb-driver/)
[![GitHub contributors](https://img.shields.io/github/contributors/oceanprotocol/oceandb-mongodb-driver.svg)](https://github.com/oceanprotocol/oceandb-mongodb-driver/graphs/contributors)

---

## Table of Contents

  - [Features](#features)
  - [Prerequisites](#prerequisites)
  - [Quickstart](#quickstart)
  - [Environment variables](#environment-variables)
  - [Code style](#code-style)
  - [Testing](#testing)
  - [New Version](#new-version)
  - [License](#license)

---

## Features

MongoDB driver to connect implementing OceanDB.

## Prerequisites

You should have running a mongo instance.

## Quickstart

First of all we have to specify where is allocated our config.
To do that we have to pass the following argument:

```
--config=/path/of/my/config
```

If you do not provide a configuration path, by default the config is expected in the config folder.

In the configuration we are going to specify the following parameters to

```yaml

    [oceandb]

    enabled=true            # In order to enable or not the plugin
    module=mongodb          # You can use one the plugins already created. Currently we have mongodb and bigchaindb.
    module.path=            # You can specify the location of your custom plugin.
    db.hostname=localhost   # Address of your MongoDB.
    db.port=27017            # Port of your Mongodb.

    db.username=user        # If you are using authentication, mongodb username.
    db.password=password    # If you are using authentication, mongodb password.
    db.name=test            # Mongodb database name
    db.collection=col       # Mongodb collection name

```

Once you have defined this the only thing that you have to do it is use it:

```python

    oceandb = OceanDb(conf)
    oceandb.write({"value": "test"}, id)

```

## Environment variables

When you want to instantiate an Oceandb plugin you can provide the next environment variables:

- **$CONFIG_PATH** 
- **$MODULE** 
- **$DB_HOSTNAME** 
- **$DB_PORT**
- **$DB_NAME**
- **$DB_COLLECTION**
- **$DB_USERNAME**
- **$DB_PASSWORD**

## Code style

The information about code style in python is documented in this two links [python-developer-guide](https://github.com/oceanprotocol/dev-ocean/blob/master/doc/development/python-developer-guide.md)
and [python-style-guide](https://github.com/oceanprotocol/dev-ocean/blob/master/doc/development/python-style-guide.md).
    
## Testing

Automatic tests are setup via Travis, executing `tox`.
Our test use pytest framework.

## New Version

The `bumpversion.sh` script helps to bump the project version. You can execute the script using as first argument {major|minor|patch} to bump accordingly the version.

## License

```
Copyright 2018 Ocean Protocol Foundation Ltd.

Licensed under the Apache License, Version 2.0 (the "License");
you may not use this file except in compliance with the License.
You may obtain a copy of the License at

   http://www.apache.org/licenses/LICENSE-2.0

Unless required by applicable law or agreed to in writing, software
distributed under the License is distributed on an "AS IS" BASIS,
WITHOUT WARRANTIES OR CONDITIONS OF ANY KIND, either express or implied.
See the License for the specific language governing permissions and
limitations under the License.
