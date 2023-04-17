# Splunk-Delay-Detector

This script is from the blog post entitled "Log Timing Delays in Splunk Could be Putting Your Security at Risk" which can be read [here](https://www.blue-prints.blog/content/blog/posts/splunk/splunklogdelay.html).

# Important Notes
* The script needs to run in an environment that has network API access to your Splunk instance.
* The script should be run as a user OTHER than the specified search owner.
* The script needs to be run as a user with the approriate index and job history access.
* The script can be intensive if used against saved searches that are intensive.
* * The graphs will not display outside of Jupyter Notebooks.

# Usage
The script takes a config file as input. This file is a json file in the same directory as the script or jupyter notebook.

## Example config

    {
        "splunk_account":"splunk",
        "splunk_password":"splunkpassword",
        "base_url":"example.splunkcloud.com",
        "port": "8089",
        "owner": "splunk",
        "graph": "true"
    }

## Description of attributes

    *splunk_account* - Splunk account used to check ran *saved searched* and rerun to compare results.
    *splunk_password* - Corresponding Splunk account password
    *base_url* - Splunk URL.
    *port* - The Splunk API port.
    *owner* - The owner of the Splunk searches to be checked.
    *graph* - Whether or not to graph the output.

