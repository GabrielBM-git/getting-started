
-------------------------------------------------
-> Dockerfile

FROM node:12-alpine
# Adding build tools to make yarn install work on Apple silicon / arm64 machines
RUN apk add --no-cache python2 g++ make
WORKDIR /app
COPY . .
RUN yarn install --production
CMD ["node", "src/index.js"]

-------------------------------------------------
-> Comando: Compilar a Imagem do Container.

docker build -t getting-started .

-------------------------------------------------
-> Comando: Executar o Container(Aplicativo).

docker run -dp 3000:3000 getting-started
           (-d -p = porta
             = desacoplado)

-------------------------------------------------

-> Comando: Listar os Containers.

docker ps

-> Comando: Parar o Container.

docker stop <container-id>

-> Comando: Remover o Container.

docker rm <container-id>

-> Comando Parar e Remover o Container.

docker rmdocker rm -f <the-container-id>
                (-f = force)

#   g e t t i n g - s t a r t e d  
 