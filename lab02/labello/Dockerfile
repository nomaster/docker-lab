FROM aarch64/alpine

RUN apk --update add py2-pip

COPY ./ /app/

WORKDIR /app

EXPOSE 8000
CMD [ "python", "./labelprinterServe.py" ]
