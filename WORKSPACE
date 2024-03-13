workspace(name = "build_buildfarm")

load(":deps.bzl", "buildfarm_dependencies")

buildfarm_dependencies()

load(":defs.bzl", "buildfarm_init")

buildfarm_init()

load("@rules_oss_audit//oss_audit:repositories.bzl", "rules_oss_audit_dependencies")

rules_oss_audit_dependencies()

load("@rules_oss_audit//oss_audit:setup.bzl", "rules_oss_audit_setup")

rules_oss_audit_setup()

load("@maven//:compat.bzl", "compat_repositories")

compat_repositories()

load(":images.bzl", "buildfarm_images")

buildfarm_images()

# Find rpmbuild if it exists.
load("@rules_pkg//toolchains/rpm:rpmbuild_configure.bzl", "find_system_rpmbuild")

find_system_rpmbuild(name = "rules_pkg_rpmbuild")

load("@io_bazel_rules_docker//container:container.bzl", "container_pull")

# pivotalrabbitmq/rabbitmq-server-buildenv:linux-rbe-experimental
container_pull(
    name = "rabbitmq-server-buildenv",
    digest = "sha256:bb5343a0dfb56b83238882192a942e069d66f0836c51428ede4236d8f77f5468",
    registry = "index.docker.io",
    repository = "pivotalrabbitmq/rabbitmq-server-buildenv",
)
