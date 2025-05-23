version: "3.8"
services:
  asterisk:
    build: ./asterisk
    ports:
      - "5060:5060/udp"
      - "10000-20000:10000-20000/udp"
      - "8088:8088"
      - "5038:5038"
  api:
    build: ./api
    ports:
      - "3000:3000"
    environment:
      ASTERISK_HOST: asterisk
      ASTERISK_PORT: 8088   # o 5038 si usás AMI
    depends_on:
      - asterisk
