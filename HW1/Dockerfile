FROM python:3.9

RUN apt-get install wget
RUN pip install pandas sqlalchemy psycopg2

WORKDIR /app

# copies all files in current directory to docker directory
COPY ingest_data.py ingest_data.py

# open bash by default
# ENTRYPOINT ["bash"]

# run python script after opening
ENTRYPOINT ["python", "ingest_data.py"]


# docker build -t taxi_ingest:v001 .

# URL="https://github.com/DataTalksClub/nyc-tlc-data/releases/download/yellow/yellow_tripdata_2021-01.csv.gz"
# docker run -it \
#  --network=pg-network \
#  taxi_ingest:v001 \
#   --user=root \
#   --password=root \
#   --host=localhost \
#   --port=5432 \
#   --db=ny_taxi \
#   --table_name=yellow_taxi_trips \
#   --url=${URL}


# Syntax for running dockerised apps
# ctrl+d to exit bash and other lines
# build after making any changes to the docker or other files
# docker build -t docker_sql .
# docker run -it docker_sql [arguments]
# type python in bash to run python
# python pipeline.py

# Docker syntax for running postgres

# docker network create pg-network
# docker run -it \
#   -e POSTGRES_USER="root" \
#   -e POSTGRES_PASSWORD="root" \
#   -e POSTGRES_DB="ny_taxi" \
#   -v $(pwd)/ny_taxi_data:/var/lib/postgresql/data \
#   -p 5432:5432 \
#   --network=pg-network \
#   --name pg-database \
#   postgres:13

# docker rm -f container_id

# pgcli command
# pgcli -p 5432 -h localhost -u root -d ny_taxi

# Docker syntax for running pgadmin
# docker run -it \
#   -e PGADMIN_DEFAULT_EMAIL="admin@admin.com" \
#   -e PGADMIN_DEFAULT_PASSWORD="root" \
#   -p 8080:80 \
#   --network=pg-network \
#   --name pgadmin-1 \
#   dpage/pgadmin4

#postgres log in details:
# user: root, password:root, port:5432

# Network: pg-network

# Ingestion run 
# URL="https://github.com/DataTalksClub/nyc-tlc-data/releases/download/yellow/yellow_tripdata_2021-01.csv.gz"

# python ingest_data.py \
#   --user=root \
#   --password=root \
#   --host=localhost \
#   --port=5432 \
#   --db=ny_taxi \
#   --table_name=yellow_taxi_trips \
#   --url=${URL}

