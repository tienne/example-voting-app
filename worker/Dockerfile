# build:
#   docker build --force-rm=true -t subicura/sample_worker:latest .
# run:
#   docker run --rm subicura/sample_worker:latest

FROM microsoft/dotnet:1.1.1-sdk

WORKDIR /code

ADD src/Worker /code/src/Worker

RUN dotnet restore -v minimal src/Worker \
    && dotnet publish -c Release -o "./" "src/Worker/" 

CMD dotnet src/Worker/Worker.dll