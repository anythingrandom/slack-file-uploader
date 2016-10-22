1.Install dependency:
pip install slacker

2.Clone this repo

3.Read help:
./slack-file-uploader.py -h
usage: slack-file-uploader.py [-h] [--channel <channel>] [--member <member>]
                              [--uploader <uploader>]
                              <file> [<file> ...]

This script uploads files to a slack channel using slacker library
All params saved in creds.cfg

positional arguments:
  <file>                files to be uploaded separated by space(s)

optional arguments:
  -h, --help            show this help message and exit
  --channel <channel>   name of channel to which file is to be uploaded
  --member <member>     name of human who is member of the channel
  --uploader <uploader>
                        name of human or bot who will upload file to channel
                        and not necessary to be a member of the channel


4.Update creds.cfg
# Values for default channel, default member, default uploader must be mentioned in creds.cfg.
# Token for default member and default uploader must be mentioned in creds.cfg.

5.Sample Usage:
1.
./slack-file-uploader.py --channel general --uploader someuser --member anotheruser hello.txt
# slack user @someuser uploads file hello.txt to channel #general.
# if @someuser is not a member of the channel #general, member @anotheruser will invite someuser to the channel.(because only channel members can upload file to a channel)
# member @anotheruser must be a member of the channel #general. But if uploader(@someuser) is already a member of the channel, member(@anotheruser) need not be a member of the channel.
# tokens for uploader(@someuser) and member(@anotheruser) must be stored in creds.cfg similar to default uploader and default member.
# you can get token from here https://api.slack.com/docs/oauth-test-tokens

Note:
# if uploader option is not provided default uploader will be chosen.
# if channel option is not provided default channel will be chosen.
# if member option is not provided default member will be chosen. in this case default member must be member of the channel already.
# channel can be private or public.

Author:
Shinde

