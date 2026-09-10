# Run the site locally with Docker

These steps are for **Windows PowerShell**. Docker runs Ruby, Jekyll, and the other dependencies, so you do not need to install them on Windows.

The Docker server uses **http://localhost:8080**. The earlier preview at port `8088` was a separate temporary server; use `8080` for this workflow.

## 1. Start Docker Desktop

Open **Docker Desktop** from the Start menu and wait until its engine is running. Use Linux containers.

Open PowerShell and check Docker:

```powershell
docker version
```

You should see both **Client** and **Server** information. If you see a named-pipe error or a message that Docker cannot connect, wait for Docker Desktop to finish starting and try again.

## 2. Open the repository folder

```powershell
Set-Location 'C:\Users\willz\Documents\code\jwill2385.github.io'
```

If you cloned the repository somewhere else, use that folder instead. It should contain `_config.yml`, `Gemfile`, and `_projects`.

## 3. Download the Docker image

The following is the al-folio image used for the Cookability preview. Its digest pins that version so a future change to the `latest` tag does not change your local environment.

```powershell
$siteImage = 'amirpourmand/al-folio@sha256:31a8af846095e7bbb43981019af0400c3a3da79c9d6c44a5e5b871cfe6a115e7'
docker pull $siteImage
```

The first download can take a few minutes. Keep this PowerShell window open for the next step so `$siteImage` remains available.

## 4. Start the site

Copy and run this entire block. The backtick at the end of each continued PowerShell line must be the final character, with no spaces after it.

```powershell
docker run --name jadal-site-local `
  --publish '127.0.0.1:8080:8080' `
  --mount "type=bind,source=$((Get-Location).Path),target=/srv/jekyll,readonly" `
  --workdir /srv/jekyll `
  --env JEKYLL_ENV=development `
  --env BUNDLE_GEMFILE=/tmp/local-site.Gemfile `
  $siteImage `
  bash -lc 'cp /srv/jekyll/Gemfile /tmp/local-site.Gemfile && bundle add ostruct && bundle exec jekyll serve --host 0.0.0.0 --port 8080 --watch --force_polling --disable-disk-cache --destination /tmp/local-site'
```

This command:

- Makes the repository available to Jekyll as read-only files. You can still edit those files normally from Windows.
- Installs the repository's gems using a copy of `Gemfile` inside the container. It adds `ostruct`, which this image's Ruby version needs for the site's Twitter plugin.
- Writes generated HTML, images, and dependency files inside the container, leaving your repository's dependency files unchanged.
- Watches your source files for changes and serves the result on port `8080`.

The first run takes longer because it installs dependencies and generates responsive images. Leave this terminal open and wait for **Server running**. Existing Sass deprecation warnings can appear during the build; they do not by themselves mean the build failed.

This command overrides the image's default startup script. It also avoids the dependency mismatch encountered when using the prebuilt image directly with this repository's local lockfile. The dependency resolution is for local preview; it does not reproduce the lockfile used by another build environment.

## 5. Open the site

- Home: **http://localhost:8080/**
- Projects: **http://localhost:8080/projects/**
- Cookability: **http://localhost:8080/projects/4_project/**

To edit Cookability, open `_projects/4_project.md`, save your changes, and wait for the terminal to finish regenerating the site. Then refresh your browser. Browser refresh is manual in this setup.

If you change `_config.yml` or `Gemfile`, stop and restart the container using the next step.

## 6. Stop and restart

To stop the server, open another PowerShell window and run:

```powershell
docker stop jadal-site-local
```

To run the site again later, start Docker Desktop and run:

```powershell
docker start -a jadal-site-local
```

You can run this restart command from any folder. It reuses the container and its installed dependencies, checks the copied Gemfile again, and rebuilds the site. Keep the terminal open and use the same `8080` addresses.

To check its status or follow its logs from another terminal:

```powershell
docker ps -a --filter name=jadal-site-local
docker logs --follow jadal-site-local
```

Pressing **Ctrl+C** while following logs only stops following the logs. Use `docker stop jadal-site-local` to stop the server.

## Troubleshooting

### The container name is already in use

You only need `docker run` to create the container once. Use `docker start -a jadal-site-local` for later sessions. If it is already running, open the browser or follow its logs.

### Port 8080 is already in use

Stop the other server using that port. Alternatively, before creating this container, change the publish argument in step 4 to `127.0.0.1:8081:8080` and open **http://localhost:8081**. Keep Jekyll's internal `--port 8080` unchanged.

### I moved the repository or need to recreate the container

Stop and remove only this local preview container:

```powershell
docker stop jadal-site-local
docker rm jadal-site-local
```

This removes the container's generated site and dependency cache, not your repository files. Repeat steps 2–4 from the repository's current location. Set `$siteImage` again if you opened a new PowerShell window.

### Dependency installation fails

Check your internet connection and the last error in the terminal. The first run needs access to the gem registry. Once the connection is restored, retry with `docker start -a jadal-site-local`. Do not delete or edit the repository's lockfile to fix the local preview.

### My changes are not visible

Check the terminal for a build error, wait for regeneration to complete, and refresh with **Ctrl+F5**. Confirm that you opened port `8080`, rather than the earlier static preview on `8088`. For configuration changes, stop and restart the container.

Running this local server does not publish the site. Deployment remains controlled by the repository's existing GitHub workflow.
