FROM mammalwong/xforward:debian-stretch

RUN apt-get update && \
    apt-get install -y curl gnupg git autoconf automake libtool \
        build-essential python python-dev python-setuptools \
        firefox-esr fonts-droid-fallback && \
    ln -s /usr/bin/firefox /usr/bin/google-chrome && \
    curl -sL https://deb.nodesource.com/setup_7.x | sudo -E bash - && \
    apt-get install -y nodejs && \
    rm -rf /var/lib/apt/lists/* && \
    npm install -g create-react-app && \
    npm install -g create-react-native-app && \
    npm install -g flow-bin && \
    git clone https://github.com/facebook/watchman.git && \
    cd watchman && \
    git checkout v4.7.0 && \
    ./autogen.sh && \
    ./configure && \
    make && \
    make install && \
    cd .. && \
    rm -rf watchman

EXPOSE 3000 19000 19001
