# Mastodon instance stats
Displaying and saving some stats of any Mastodon instance and compare them to a other Mastodon instance.

## Requirements
- Python3
- Unix shell
- Python3 repuests
- Wget (optional)

## Installation
#### Debian/Ubuntu
- `apt install python3`
- `wget https://raw.githubusercontent.com/do-m-inik/mastodon-instance-stats/main/requirements.txt`
- `pip install -r requirements.txt`
- `wget https://raw.githubusercontent.com/do-m-inik/mastodon-instance-stats/main/mastodon-instance-stats.py`

#### MacOS
- `brew install python3`
- `wget https://raw.githubusercontent.com/do-m-inik/mastodon-instance-stats/main/requirements.txt`
- `python3 -m pip install -r requirements.txt`
- `wget https://raw.githubusercontent.com/do-m-inik/mastodon-instance-stats/main/mastodon-instance-stats.py`

## Usage
- `python3 mastodon-instance-stats.py [-h] [--csv <CSV file name>] <instance 1> [<other instances> ...]`
- For every given instance the script returns the stats of the given Mastodon instances
- If two Mastodon instances are given the script compares the two given instances
- With `--csv <file name>` the stats of the given Mastodon instances are saved into an CSV without comparision instead of printing them out

## Examples
- 1 given Mastodon instance: `python3 mastodon-instance-stats.py bahn.social`
<br />
Output:

    =============== Mastodon instance stats v1.2.2 ===============
    === Bahn.Social ===
    Users: 82
    Posts: 24994
    Connections: 9383

<br />

- 2 given Mastodon instances: `python3 mastodon-instance-stats.py bahn.social chaos.social`
<br />
Output:

    =============== Mastodon instance stats v1.2.2 ===============
    === Bahn.Social ===
    Users: 82
    Posts: 25034
    Connections: 9387

    === chaos.social ===
    Users: 10905
    Posts: 4095018
    Connections: 53020

    === Comparisons ===
    = users =
    Difference: 10823
    Ratio Bahn.Social/chaos.social: 0.75 %
    How many chaos.social users per Bahn.Social user: 132.99

    = posts =
    Difference: 4069984
    Ratio Bahn.Social/chaos.social: 0.61 %
    How many chaos.social toots per Bahn.Social toot: 163.58

    = connections =
    Difference: 43633
    Ratio Bahn.Social/chaos.social: 17.7 %
    How many chaos.social connections per Bahn.Social connection: 5.65

<br />

- 3 given Mastodon instances: `python3 mastodon-instance-stats.py bahn.social chaos.social bonn.social`
<br />
Output:

    =============== Mastodon instance stats v1.2.2 ===============
    === Bahn.Social ===
    Users: 82
    Toots: 25021
    Connections: 9383
    
    === chaos.social ===
    Users: 10905
    Toots: 4093387
    Connections: 53010
    
    === Bonn.social ===
    Users: 1258
    Toots: 172075
    Connections: 23561

<br />

- 2 given Mastodon instances saving into a CSV: `python3 mastodon-instance-stats.py --csv example.csv bahn.social chaos.social`
<br />
example.csv:

    Date and time,Instance name,Domain,Users,Toots,Connections
    2023-04-25Z19:39:46.507849,Bahn.Social,bahn.social,82,25021,9383
    2023-04-25Z19:39:46.507849,chaos.social,chaos.social,10905,4093484,53010
    
<br />
