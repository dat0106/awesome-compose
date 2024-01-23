docker run -d --name gitlab-runner --restart always \
                                     -v /var/run/docker.sock:/var/run/docker.sock \
                                     -v $PWD/gitlab-runner-config:/etc/gitlab-runner \
                                     gitlab/gitlab-runner:latest

docker run --rm -it -v $PWD/gitlab-runner-config:/etc/gitlab-runner gitlab/gitlab-runner register

# restart gitlab-runner
docker restart gitlab-runner