# General

gigalixir -h
gigalixir apps
gigalixir apps:info
gigalixir ps
gigalixir open
gigalixir releases
gigalixir logs
gigalixir config



# create app 
APP_NAME=$(gigalixir create -n <app_name> --cloud gcp --region europe-west1)

# enable postgres
gigalixir pg:create --free
gigalixir pg

# set buildpack versions (required)
echo "node_version=12.16.3" >> phoenix_static_buildpack.config
echo "elixir_version=1.10.3" >> elixir_buildpack.config
echo "erlang_version=22.3" >> elixir_buildpack.config

```
# if we are deploying via mix, we can run tasks using `gigalixir run ...`
gigalixir run mix ecto.migrate
```

git push gigalixir master

# destroy postgres instance
gigalixir pg -a <app_name>
gigalixir pg:destroy --help
gigalixir pg:destroy --database_id <db_id> --app_name <app_name>

# destroy app
gigalixir ps:scale --replicas=0 -a <app_name>
gigalixir apps:destroy -a <app_name>

# run commands
gigalixir ps:migrate
gigalixir ps:observer
gigalixir ps:remote_console
gigalixir ps:ssh

# setup ssh
gigalixir account:ssh_keys
gigalixir account:ssh_keys:add --help
gigalixir account:ssh_keys:add "$(cat ~/.ssh/id_rsa.pub)"

# initial installation
pip3 install gigalixir --ignore-installed six
gigalixir --help
gigalixir version
