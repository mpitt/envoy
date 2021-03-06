.. _install_tools_schema_validator_check_tool:

Schema Validator check tool
===========================

The schema validator tool validates that the passed in configuration conforms to
a given schema. The configuration may be JSON or YAML. To validate the entire
config, please refer to the
:ref:`config load check tool<install_tools_config_load_check_tool>`. Currently, only
:ref:`route config<envoy_api_msg_RouteConfiguration>` schema validation is supported.

Input
  The tool expects two inputs:

  1. The schema type to check the passed in configuration against. The supported type is:

    * `route` - for :ref:`route configuration<envoy_api_msg_RouteConfiguration>` validation.

  2. The path to the configuration file.

Output
  If the configuration conforms to the schema, the tool will exit with status
  EXIT_SUCCESS. If the configuration does not conform to the schema, an error
  message is outputted detailing what doesn't conform to the schema. The tool
  will exit with status EXIT_FAILURE.

Building
  The tool can be built locally using Bazel. ::

    bazel build //test/tools/schema_validator:schema_validator_tool

Running
  The tool takes a path as described above. ::

    bazel-bin/test/tools/schema_validator/schema_validator_tool  --schema-type SCHEMA_TYPE  --config-path PATH
