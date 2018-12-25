I built the containter with 

`
docker build -t backend-example .
`

and then run it with

`
docker run -v $(pwd)/logs.txt:/workdir/logs.txt -p 8000:8000 -d backend-example
`
