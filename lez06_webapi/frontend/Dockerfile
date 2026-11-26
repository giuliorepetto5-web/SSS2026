FROM node AS build
RUN apt-get update && apt-get install -y git
WORKDIR /app
RUN git clone https://github.com/mmenapace/SomeBankingApp.git
# Rimuovo la cartella del backend
RUN rm -rf /app/SomeBankingApp/backend
WORKDIR /app/SomeBankingApp/frontend
RUN npm i
RUN ./node_modules/.bin/ng build

#runtime stage (dopo averla costruita la serviamo)
FROM nginx
COPY --from=build /app/SomeBankingApp/frontend/dist/*/browser /usr/share/nginx/html
EXPOSE 80