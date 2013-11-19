This is a large dump of (nearly all) comments made on public subreddits
between Wed Aug 28 12:59:08 2013 UTC and Thu Sep 12 11:12:11 2013 UTC. There
are some small holes in this set due to the Reddit API serving HTTP 500s, and
in 3 cases, 0-byte files due to IO contention on the crawler machine.

Each file is a dump of 'http://www.reddit.com/r/all/comments.json?limit=100'
made every 3 seconds, with a cache-busting parameter to ensure a fresh result.
There are 15.5 million comments in total.

On average around 11 new comments are seen per second. Given the Reddit API
limit of 1 call per 3 seconds, that means on average more than 50% of the API
response will contain redundant information, and so we have a good chance of
capturing all comments.

I decided to just include the raw API response data, because it captures the
greatest amount of information, and my post-processed version of the data
excludes the majority of fields.

Some stats:

    unique_comments=15505576
    unique_files=397323
    unique_io_error=13
    unique_links=1116967
    unique_orphans=1474787
    unique_reddits=23125
    unique_users=1309140

An orphan is a comment whose immediate parent does not appear in the data.

Drop a message to Reddit user 'w2m3d' if you're interested in this data but
require it in a different format.

Fri 13 Sep 15:37:18 UTC 2013
