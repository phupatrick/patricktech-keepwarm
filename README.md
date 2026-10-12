# patricktech-keepwarm

Keeps the [Patrick Tech Media](https://www.patricktechmedia.com) web service
from going to sleep on Render's free plan.

Render spins a free instance down after about 15 minutes without traffic, and
the next visitor then waits 30-90 seconds for it to wake. The workflow in this
repository pings a lightweight health endpoint every 5 minutes so that almost
every real visitor reaches an already-warm instance.

The repository is public on purpose: public repositories use free, unmetered
GitHub-hosted runner minutes, so the ping does not consume the private media
repository's monthly Actions allowance.

It contains no secrets — only the workflow file and this README.

Health endpoint used:

```
https://www.patricktechmedia.com/api/health
```

To pause the warm-up, disable the workflow from the Actions tab.
