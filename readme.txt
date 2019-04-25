
my_producer使用指南

1.下载librdkafka
git clone --branch v1.0.0 https://github.com/edenhill/librdkafka.git

2.进入对下载后的目录中编译安装
cd librdkafka
    ./configure --install-deps
    make
    sudo make install

3. 将安装的librdkafka相关库的位置添加到环境中
LD_LIBRARY_PATH=/usr/local/lib
export LD_LIBRARY_PATH

4. 生成脚本
gcc my_producer.c -o my_producer  -lrdkafka -lz -lpthread -lrt
gcc rdkafka_example.c -o rdkafka_example  -lrdkafka -lz -lpthread -lrt

5. 执行脚本
./my_producer  localhost:9092 test_topic  #只有生产者的功能
./rdkafka_example -C -b localhost:9092 -t test_topic -p 0   #生产者和消费者功能都有