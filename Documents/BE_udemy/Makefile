postgres:
	docker run --name postgresdb -p 5432:5432 -e POSTGRES_USER=root -e POSTGRES_PASSWORD=12345  -d postgres


createdb:
	docker exec -it postgresdb createdb --username=root --owner=root simple_bank

dropdb:
	docker exec -it postgresdb dropdb simple_bank    

migrateup:
	migrate -path db/migration -database "postgresql://root:12345@localhost:5432/simple_bank?sslmode=disable" -verbose up 

migratedown:
	migrate -path db/migration -database "postgresql://root:12345@localhost:5432/simple_bank?sslmode=disable" -verbose down

sqlc:
	sqlc generate 

.PHONY: postgres createdb dropdb migrateup migratedown sqlc