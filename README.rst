slack-pull-reminder
===================

    Posts a Slack reminder with a list of open pull requests for an
    organization.

.. figure:: http://i.imgur.com/3xsfTYV.png

Installation
------------

.. code:: bash

    $ pip install git+https://github.com/kotky/slack-pull-reminder.git

Usage
-----

slack-pull-reminder is configured using environment variables:

Required
~~~~~~~~

-  ``SLACK_INCOMING_WEBHOOK_URL``: Full incoming webhook generated url
-  ``GITHUB_API_TOKEN``: generated on user profile with full repo read right
-  ``ORGANIZATION``: The GitHub organization you want pull request
   reminders for.

Optional
~~~~~~~~

-  ``IGNORE_WORDS``: A comma-separated list of words that will cause a
   pull request to be ignored.
-  ``SLACK_CHANNEL``: The Slack channel you want the reminders to be
   posted in, defaults to webhook assigned.
-  ``REPOSITORY_FULL_NAME_LIST``: The GitHub organization repositories that will filter list of pull requests.

Example
~~~~~~~

.. code:: bash

    $ ORGANIZATION="org1" SLACK_INCOMING_WEBHOOK_URL="url" GITHUB_API_TOKEN="token" REPOSITORY_FULL_NAME_LIST="org1/repo1,org1/repo2" slack-pull-reminder

Cronjob
~~~~~~~

As slack-pull-reminder only runs once and exits, it's recommended to run
it regularly using for example a cronjob.

Example that runs slack-pull-reminder every day at 10:00:

.. code:: bash

    0 10 * * * ORGANIZATION="org1" SLACK_INCOMING_WEBHOOK_URL="url" GITHUB_API_TOKEN="token" REPOSITORY_FULL_NAME_LIST="org1/repo1,org1/repo2" slack-pull-reminder

License
-------

(The MIT License)

Copyright (c) Josip Kotarac jkotarac@extensionengine.com

Permission is hereby granted, free of charge, to any person obtaining a
copy of this software and associated documentation files (the
'Software'), to deal in the Software without restriction, including
without limitation the rights to use, copy, modify, merge, publish,
distribute, sublicense, and/or sell copies of the Software, and to
permit persons to whom the Software is furnished to do so, subject to
the following conditions:

The above copyright notice and this permission notice shall be included
in all copies or substantial portions of the Software.

THE SOFTWARE IS PROVIDED 'AS IS', WITHOUT WARRANTY OF ANY KIND, EXPRESS
OR IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF
MERCHANTABILITY, FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT.
IN NO EVENT SHALL THE AUTHORS OR COPYRIGHT HOLDERS BE LIABLE FOR ANY
CLAIM, DAMAGES OR OTHER LIABILITY, WHETHER IN AN ACTION OF CONTRACT,
TORT OR OTHERWISE, ARISING FROM, OUT OF OR IN CONNECTION WITH THE
SOFTWARE OR THE USE OR OTHER DEALINGS IN THE SOFTWARE.
