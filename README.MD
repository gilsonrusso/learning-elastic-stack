# Setup do Ambiente de Observabilidade

Antes de executar o `docker-compose up`, siga os passos abaixo:

## Passo 1: Criar a Rede Observability

Crie a rede `observability` com o comando:

```sh
docker network create observability
```

## Passo 2: Criar a Pasta elasticsearch_data

Crie a pasta elasticsearch_data no diretório fc2-observabilidade-elastic na máquina local manualmente para evitar erro de permissionamento:

```sh
mkdir elasticsearch_data
```

## Passo 3: Ajustar Permissões do Arquivo metricbeat.yml

Na pasta metric, execute o seguinte comando:

```sh
sudo chown root metricbeat.yml
```

## Passo 4: Ajustar Configuração de Memória Virtual

Caso ocorra o erro:

```markdown
bootstrap check failure [1] of [1]: max virtual memory areas vm.max_map_count [65530] is too low, increase to at least [262144]
```
Execute o comando:

```sh
sysctl -w vm.max_map_count=262144
```