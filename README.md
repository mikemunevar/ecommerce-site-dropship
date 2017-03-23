Install Postgres
mikemunevar:~/workspace $ sudo sh -c "echo 'deb http://apt.postgresql.org/pub/repos/apt/ precise-pgdg main' > /etc/apt/sources.list.d/pgdg.list"




sudo apt-get update


sudo apt-get install postgresql-common

sudo apt-get install postgresql-9.3 libpq-dev

Set up a postgres user
sudo -u postgres createuser spreeshop -s

sudo -u postgres psql
\password spreeshop
<enter password>


Follow these directions to setup in Cloud9
https://community.c9.io/t/setting-up-postgresql/1573

sudo service postgresql start
psql
postgres=# CREATE DATABASE "ecommerce";
You may need to specify that it's unicode
ubuntu=# CREATE DATABASE "ecommerce2" ENCODING 'UNICODE' TEMPLATE template0;

psql
postgres=# \list

\password
<enter password>

The username will be "ubuntu".


Update your database.yml file with these details.

If you need to creaate the database, you can use this command:
mikemunevar:~/workspace (master) $ rake db:create



Install imagemagick  https://community.c9.io/t/install-imagemagick/3608
sudo apt-get install imagemagick

gem install spree

spree install

from:
https://github.com/spree/spree

add to gem file
gem 'spree', '~> 3.1.0'
gem 'spree_auth_devise', '~> 3.1.0'
gem 'spree_gateway', '~> 3.1.0'

bundle update
bundle install



Use the install generators to set up Spree:
rails g spree:install --user_class=Spree::User
rails g spree:auth:install
rails g spree_gateway:install

default user: spree@example.com
default PW: s******3


Start the Posgres DB  https://community.c9.io/t/setting-up-postgresql/1573
sudo service postgresql start

