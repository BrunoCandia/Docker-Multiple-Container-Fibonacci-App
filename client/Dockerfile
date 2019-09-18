# Implementing Multi-Step builds
# Build phase

FROM node:alpine as builder

WORKDIR '/app'

# COPY package.json .   AWS has a tough time with the '.' folder designation and prefers the long form ./
COPY package*.json ./

RUN npm install

COPY . .

RUN npm run build


# Run phase

FROM nginx

# for deploy env only, it is not needed for dev env
EXPOSE 3000

COPY ./nginx/default.conf /etc/nginx/conf.d/default.conf

COPY --from=builder /app/build /usr/share/nginx/html