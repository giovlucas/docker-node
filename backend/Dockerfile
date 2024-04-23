# Usar uma imagem base Node.js
FROM node:14-alpine

# Definir o diretório de trabalho dentro do container
WORKDIR /app

# Copiar os arquivos necessários (package.json, package-lock.json)
COPY package*.json ./

# Instalar dependências
RUN npm install

# Copiar todo o código fonte para o container
COPY . .

# Expor a porta que o servidor backend estará ouvindo
EXPOSE 3000

# Comando padrão para iniciar o servidor backend
CMD ["node", "index.js"]
