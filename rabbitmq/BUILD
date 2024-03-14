load("@io_bazel_rules_docker//container:container.bzl", "container_push")
load("@io_bazel_rules_docker//java:image.bzl", "java_image")

java_image(
    name = "buildfarm-shard-worker-rabbitmq-server-buildenv",
    base = "@rabbitmq-server-buildenv//image",
    runtime_deps = ["//src/main/java/build/buildfarm:buildfarm-shard-worker"],
    main_class = "build.buildfarm.worker.shard.Worker",
)

alias(
    name = "worker-image",
    actual = ":buildfarm-shard-worker-rabbitmq-server-buildenv",
)

container_push(
    name = "publish-buildfarm-shard-worker-rabbitmq-server-buildenv",
    format = "OCI",
    image = ":buildfarm-shard-worker-rabbitmq-server-buildenv",
    registry = "index.docker.io",
    repository = "pivotalrabbitmq/buildfarm-shard-worker-rabbitmq-server-buildenv",
    tag = "2.8.0",
)

alias(
    name = "publish-worker-image",
    actual = "publish-buildfarm-shard-worker-rabbitmq-server-buildenv",
)
