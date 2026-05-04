FROM nodejs:20
WORKDIR /app
ADD https://roboshop-artifacts.s3.amazonaws.com/catalogue-v3.zip .
COPY  package.json .
COPY *.js .
RUN npm install
ENV MONGO = "true"
    MONGO_URL = ""
RUN addgroup -S roboshop && adduser -S roboshop -G roboshop
RUN chown -R roboshop:roboshop /app
USER roboshop
CMD ["server.js"]
ENTRYPOINT ["node"]