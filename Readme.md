# webdev3-submodule for node services
this repository is supposed to be added as submodule to webdev3
## Usage
the container is configured to autostart a service defined as npm script as to use the port deined in the composefile.
1) ensure a package.json with the corresponding script (as shown in .conf/package.json.example)
2) replace the dummyscript with corresponding to your project's requirements
3) that's it! :)

docker.compose.yml:

      node:
        build: node/
        ports:
          - '3000:80'
        links:
          - web
        volumes:
          - ../php:/var/www/html
        working_dir: /var/www/html