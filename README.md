# uptime

External uptime checks for the `katabrain.com` services.

**Public on purpose.** GitHub Actions minutes are unmetered on public
repositories; an hourly job billed at a one-minute minimum costs 720 minutes a
month on a private one. Every assertion here concerns responses that anyone can
request, so there is nothing to protect — and correspondingly, **no secret
should ever be added to this repository**.

| workflow | schedule | purpose |
|---|---|---|
| `health-ping.yml` | hourly | asserts the services answer, and that the API and admin surfaces return the codes they should |
| `keepalive.yml` | weekly | one commit, so GitHub does not disable the scheduled ping after 60 days of repository inactivity |

Alerting is workflow failure — a red run notifies whoever watches this
repository. There is no push channel, and the checks run outside the deployment
they observe, which is the point: a check that runs inside a service reports
nothing when that service is down.
