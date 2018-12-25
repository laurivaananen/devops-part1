Input I used to run the container:

`docker run -it ubuntu sh -c 'read website; sleep 3; curl http://$website;'`

After the container opened I opened another terminal window and typed docker ps which printed

`CONTAINER ID        IMAGE               COMMAND                  CREATED             STATUS              PORTS               NAMES
1002e5752905        ubuntu              "sh -c 'read website…"   5 seconds ago       Up 4 seconds                            loving_babbage
`

While in the second terminal I updated packages and installed curl

`docker exec 100 apt-get update`

`docker exec 100 apt-get install -y curl`

After this I went back to the first terminal window and typed `helsinki.fi` and it gave me the correct return without any errors.
