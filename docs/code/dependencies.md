Ubuntu 22.04.4 LTS has Python 3.10, Poetry 1.1.2

ACA-py assumes Python 3.12, wants Poetry 18.3

sudo add-apt-repository ppa:deadsnakes/ppa
sudo apt install -y python3.12 python3.12-venv 
poetry env use python3.12
  ~/.local/bin/poetry add --group dev debugpy

  minimal debug:

   scripts/run_docker start --no-ledger --no-transport --debug

   then launch.json:

   {
  "version": "0.2.0",
  "configurations": [

    {
      "name": "Débogueur Python : Attachement à distance",
      "type": "debugpy",
      "request": "attach",
      "connect": { "port": 5678 },
      "pathMappings": [{ "localRoot": "${workspaceFolder}", "remoteRoot": "." }]
    }
  ]
}
