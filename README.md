Basic Go gRPC Server and Client
This is a basic gRPC server and client written in Go. It is based on the gRPC Quickstart and gRPC Basics: Go tutorials.

We have implemented a simple gRPC server and client with the following functionality:

simple RPC
server-side streaming RPC
client-side streaming RPC
bidirectional streaming RPC
Setting up a gRPC-Go project
Create a new directory for your project and cd into it
mkdir basic-go-grpc
cd basic-go-grpc
mkdir client server proto
Installing the gRPC Go plugin
go install google.golang.org/protobuf/cmd/protoc-gen-go@v1.28

go install google.golang.org/grpc/cmd/protoc-gen-go-grpc@v1.2

export PATH="$PATH:$(go env GOPATH)/bin"
Initialize a Go module
go mod init github.com/your_username/basic-go-grpc

go mod tidy
Create the proto file with the required services and messages in the proto directory

Generate .pb.go files from the proto file

depending on what path you mention in your greet.proto file, you will either run this -

protoc --go_out=. --go-grpc_out=. proto/greet.proto
OR this -

protoc --go_out=. --go_opt=module=github.com/akhil/basic-go-grpc --go-grpc_out=. --go-grpc_opt=module=githu
b.com/akhil/basic-go-grpc proto/greet.proto
Create the server and client directories and create the main.go files with necessary controllers and services
Running the application
Install the dependencies
go mod tidy
Run the server
go run server/main.go
Run the client
go run client/main.go
