    bundle init

    echo "gem 'rails', github: 'rails/rails', branch: '5-1-stable'" >> Gemfile
    bundle install

    bundle exec rails new . --api --database=postgresql
    rails g scaffold User
    rails generate active_record:session_migration # a few tweaks to make it fly in 5.1-land
