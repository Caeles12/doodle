####################
# PRODUCTION BUILD #
####################
FROM alpine:latest as build

# Dependencies
RUN apk update && apk add npm

## Set working directory
WORKDIR /front

# Copy dependencies file
COPY package*.json ./
COPY tsconfig*.json ./
COPY angular.json ./

RUN npm install

# Copy source file
COPY src/ src/

RUN npm run build --prod --baseHref=/front/

###################
# PRODUCTION MODE #
###################
FROM nginx:1.25.3-alpine

# Dependencies
# RUN apk update && apk add nginx

# Configure nginx
COPY nginx.conf /etc/nginx/nginx.conf

# Angular app
COPY --from=build /front/dist/tlcfront /front

# Expose port 80
EXPOSE 80

# Start
# CMD ["nginx", "-g", "daemon off;"]