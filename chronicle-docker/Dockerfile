FROM ubuntu:18.10
RUN apt update && \
    apt install -y git g++ cmake libboost-dev libboost-thread-dev libboost-test-dev \
    libboost-filesystem-dev libboost-date-time-dev libboost-system-dev libboost-iostreams-dev \
    libboost-program-options-dev libboost-locale-dev libssl-dev libgmp-dev && \
    git clone https://github.com/EOSChronicleProject/eos-chronicle.git && \
    cd eos-chronicle && \
    git checkout  origin/nodeos0108 && \
    git submodule update --init --recursive && \
    mkdir build && \
    cd build && \
    cmake .. && make -j 4 && \
    mv chronicle-receiver /opt/ && \
    rm -rf ~/eos-chronicle

COPY config.ini /root/chronicle/config.ini

ENTRYPOINT sleep 15 && exec /opt/chronicle-receiver --data-dir=/root/chronicle/chronicle-data --config-dir=/root/chronicle/