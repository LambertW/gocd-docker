FROM gocd/gocd-agent-ubuntu-16.04:v17.8.0

# Install .NET Core SDK
ENV DOTNET_SDK_VERSION 1.0.4

RUN sh -c 'echo "deb [arch=amd64] https://apt-mo.trafficmanager.net/repos/dotnet-release/ xenial main" > /etc/apt/sources.list.d/dotnetdev.list' \
    && apt-key adv --keyserver hkp://keyserver.ubuntu.com:80 --recv-keys B02C46DF417A0893 \
    && apt-get install -y apt-transport-https \
    && apt-get update \
    && apt-get install -y dotnet-dev-1.0.4 \
    && apt-get clean

# Trigger the population of the local package cache
ENV NUGET_XMLDOC_MODE skip
RUN mkdir warmup \
    && cd warmup \
    && dotnet new \
    && cd .. \
    && rm -rf warmup \
    && rm -rf /tmp/NuGetScratch