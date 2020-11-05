# Prerequisites
- Install Docker   ( curl -fsSL get.docker.com -o get-docker.sh && CHANNEL=stable sh get-docker.sh )
- Install 'packs' from https://buildpacks.io/

# Create the builder
pack create-builder AnyName:custom --config ./builder.toml

# Build it
pack build spring_boot_server --builder AnyName:custom --env BP_BOOT_NATIVE_IMAGE=true --path . --env "BP_BOOT_NATIVE_IMAGE_BUILD_ARGUMENTS=-H:+TraceClassInitialization --initialize-at-build-time=org.apache.commons.logging.LogFactory -H:+ReportExceptionStackTraces"
