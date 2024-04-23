# Usar uma imagem base Node.js
FROM node:14-alpine AS build

# Definir o diretório de trabalho dentro do container
WORKDIR /app

# Copiar os arquivos necessários (package.json, package-lock.json)
COPY package*.json ./

# Instalar dependências
RUN npm install

# Copiar todo o código fonte para o container
COPY . .

# Construir o frontend
RUN npm run build

# Stage final: Usar um servidor web leve para servir os arquivos estáticos do frontend
FROM nginx:alpine

# Copiar os arquivos construídos do stage anterior para o diretório de publicação do Nginx
COPY --from=build /app/build /usr/share/nginx/html

# Expor a porta 80
EXPOSE 80

# Comando padrão para iniciar o servidor Nginx
CMD ["nginx", "-g", "daemon off;"]
