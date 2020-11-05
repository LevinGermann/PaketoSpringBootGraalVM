# Prerequisites
- Install 'packs' from https://buildpacks.io/

# Build it
pack build spring_boot_server --builder AnyName:custom --env BP_BOOT_NATIVE_IMAGE=true --path . --env "BP_BOOT_NATIVE_IMAGE_BUILD_ARGUMENTS=-H:+TraceClassInitialization --initialize-at-build-time=org.apache.commons.logging.LogFactory -H:+ReportExceptionStackTraces"
