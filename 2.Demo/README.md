# k5-cflocal demo

If docker don not starts automatically in Windows with VirtualBox
- docker-machine start default

local.yml => In order to configurate local instance of the droplet, with this content:
applications:
- name: k5-cflocal-demo
  command: npm install && npm start
  buildpack: https://github.com/cloudfoundry/nodejs-buildpack.git
  running_env:
    K5REGION: "region"
    K5CONTRACT: "contract"
    K5PROJECTID: "projectid"
    K5USER: "user"
    K5PASSWORD: "password"
    K5SECRET: "secret_whateverstring"


in "2.Demo" folder:
- LOCAL
    - cf local stage k5-cflocal-demo -p app
    - cf local run k5-cflocal-demo -p 3000

- REMOTE
    - cf push k5-cflocal-demo -p app

- OTHER COMMANDS
    - cd remote && cf local pull k5-cflocal-demo

- CONCLUSION:

    - Better use to test the app & work with containers with less knowledge of Docker than Dockerfile & docker commands..
    - Very usefull to test the app in the same environment than K5 CF.
    - Very usefull to develop the app without worries about testing environment.
    - With the use of DOCKER_HOST env. variable, it is easy to run & stage the droplets in remote docker hosts.

    - Not a valid use to download or upload droplets to K5, for different reasons explained:

    - K5 integration limited in push command because Error: unexpected '413 Request Entity Too Large' from: PUT https://api.uk-1.paas-cf.cloud.global.fujitsu.com/v2/apps/[GUID]]/droplet/upload

    - K5 integration limited in pull & run droplet in local because unknown parse error: Invalid numeric literal at line 2, column 0
    - Maybe it works with other droplets, but with Node.js I didn't make it works.

The demo could be:
- Show the funcionalities of cf local:
    - Architecture (cf local + Docker)
    - cf local help
    - cf local stage
    - cf local run
    - cf local pull
    - cf local push
    - K5 Considerations