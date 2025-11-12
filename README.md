# Demo

## Beginner (Console Deploy)

1. Deploy ghost.
   Equivalent Docker command.

   ```bash
   sudo docker run --rm --name ghost \
     -p 2368:2368 \
    -e database__client=sqlite3 \
     -e database__connection__filename="content/data/ghost.db" \
     -e database__useNullAsDefault=true \
     -e database__debug=false 
     docker.io/library/ghost:latest
   ```

2. Visit "/ghost/editor/" to configure site.

3. Show that "view site" doesn't work.

4. Show how easy it is to change configuration (add environment variable) and redeploy.

## Intermediate

0. Fetch and untar helm chart to directory:

   ```bash
   helm pull oci://registry-1.docker.io/bitnamicharts/ghost --version 21.1.12 --untar --untardir charts/
   ```

1. Run helm using https://github.com/bitnami/charts/tree/main/bitnami/ghost and values in repo:

   ```bash
   helm install ghost ./charts/ghost -f values.yaml
   ```

As a backup, just export the Deployment code from Beginner deployment and use that.
