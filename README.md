## Install sudo

        ```
        apt install sudo
        ```
## Create and configure user

    ```adduser <username>
    ```

    ```
    usermod -aG sudo <username>
    ```

## Log-in as created <username>

## Install cool apps

    ```
    sudo apt-get install -y zsh curl git tree redis-server nginx  libssl-dev zlib1g-dev libbz2-dev libreadline-dev libsqlite3-dev llvm libncurses5-dev libncursesw5-dev xz-utils tk-dev libffi-dev liblzma-dev python3-dev python-imaging python3-lxml libxslt-dev python-libxml2 python-libxslt1 libffi-dev libssl-dev python-dev gnumeric libsqlite3-dev libpq-dev libxml2-dev libxslt1-dev libjpeg-dev libfreetype6-dev libcurl4-openssl-dev supervisor
    ```

## Install oh-my-zsh:

    ```
    sh -c "$(curl -fsSL https://raw.githubusercontent.com/robbyrussell/oh-my-zsh/master/tools/install.sh)"
    ```

## Install Python

    ```
    wget https://www.python.org/ftp/python/3.8.2/Python-3.8.2.tgz ; \
    tar xvf Python-3.8.* ; \
    cd Python-3.8.2 ; \
    mkdir ~/.python ; \
    ./configure --enable-optimizations --prefix=/home/www/.python ; \
    make -j8 ; \
    sudo make altinstall
    ```

## Install and configure PostgreSQL

1 Install PostgreSQL 11
        ```
        wget --quiet -O - https://www.postgresql.org/media/keys/ACCC4CF8.asc | sudo apt-key add - ; \
        RELEASE=$(lsb_release -cs) ; \
        echo "deb http://apt.postgresql.org/pub/repos/apt/ ${RELEASE}"-pgdg main | sudo tee  /etc/apt/sources.list.d/pgdg.list ;\
        sudo apt update ; \
        sudo apt -y install postgresql-11 ; \
        ```
2 Change postges password, create clear database named tg_db:
        ```
        sudo passwd postgres
        su - postgres
        export PATH=$PATH:/usr/lib/postgresql/11/bin
        createdb --encoding UNICODE tg_db --username postgres
        exit
        ```
3 Create tg_db user and grand privileges to him:
        
