# Setting up your dev environment

Welcome aboard. This should take about an hour.

First you'll need Docker Desktop installed. Grab it from docker.com and let it
finish before you do anything else, because the next step depends on it running.

Once Docker is up, clone the monorepo. It's big — expect a few minutes. Then
copy `.env.example` to `.env`. You'll need real values for two of them,
`DB_PASSWORD` and `STRIPE_TEST_KEY`; ask your onboarding buddy, they're in the
shared vault and we don't put them in the repo.

Now run `make bootstrap`. This builds the containers and seeds the database.
The first run is slow. If it fails on the migration step, that's almost always
because Docker didn't have enough memory allocated — bump it to 8GB in Docker
Desktop's settings and run it again.

When it finishes, `make dev` starts everything. Go to localhost:3000 and you
should see the login page. Log in with dev@example.com / password.

If the page loads but the API calls fail, check that the api container is
actually up with `docker ps`. It sometimes loses the race with the database on
the first boot. Just `make dev` again.
