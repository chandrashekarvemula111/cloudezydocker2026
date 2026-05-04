FROM nodejs:20
WORKDIR /app
EXPOSE 8080
ADD https://roboshop-artifacts.s3.amazonaws.com/catalogue-v3.zip .
COPY  catalogue-v3/package.json .
COPY catalogue-v3/*.js .
RUN npm install
ENV MONGO = "true" \
    MONGO_URL = "mongodb://mongodb:27017/catalogue"
RUN addgroup -S roboshop && adduser -S roboshop -G roboshop
RUN chown -R roboshop:roboshop /app
USER roboshop
CMD ["server.js"]
ENTRYPOINT ["node"]