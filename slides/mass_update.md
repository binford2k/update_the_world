<!SLIDE >
# Then I got a little crazy
## What if we could update the whole world?

![Philosoraptor](/_images/philosoraptor.jpeg)


<!SLIDE >
# Then I got a little crazy
## What if we could update the whole world?

.callout.info GitHub exposes a fantastic BigQuery dataset of all their public repositories.

Generate a list of all Puppet modules with legacy functions:

    @@@ Sql
    SELECT DISTINCT repo_name
    FROM `bigquery-public-data:github_repos.files`
    WHERE STARTS_WITH(path, 'lib/puppet/parser/functions')
    AND ref = 'refs/heads/master'


<!SLIDE >
# Validate the tool
## First let's build some confidence

1. First I wrote a quick script to clone each listed repo.
1. Then it ran my tool to port functions.
1. If successful, it deleted the repo.

I was left with 47 modules with edge cases to account for, but after a couple
iterations and improvements, it ported all valid functions flawlessly.

![Thumbs UP](/_images/thumbsup.gif)

~~~SECTION:notes~~~
So then I ran it and went out for the night.

1. Instead of just cloning, now it forked too.
1. After running, it submitted a PR with instructions on how to complete the job.
1. And then cleaned up by deleted the repo from my namespace.

~~~ENDSECTION~~~

