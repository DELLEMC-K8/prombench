DOCKER_TAG = docker.io/prombench/scaler:2.0.0

build:
	@go version | grep go1.11 || exit  "Requires golang 1.11 with support for modules!"
	@GO111MODULE=on GOARCH=amd64 CGO_ENABLED=0 GOOS=linux go build scaler.go

clean:
	@rm scaler

docker: build
	@docker build -t $(DOCKER_TAG) .
	@docker push $(DOCKER_TAG)

.PHONY: build clean docker