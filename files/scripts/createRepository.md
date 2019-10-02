
# Arguments

Arguments should be an array of repo configs

```json
[
  {
    "blob_store": "default",
    "format": "maven2",
    "layout_policy": "permissive",
    "maximum_component_age": -1,
    "maximum_metadata_age": 1440,
    "name": "central",
    "negative_cache_enabled": true,
    "negative_cache_ttl": 1440,
    "remote_url": "https://repo1.maven.org/maven2/",
    "strict_content_validation": true,
    "type": "proxy",
    "version_policy": "release",
    "write_policy": "allow_once"
  },
  {
    "blob_store": "default",
    "format": "maven2",
    "layout_policy": "strict",
    "maximum_component_age": -1,
    "maximum_metadata_age": 1440,
    "name": "private-release",
    "negative_cache_enabled": true,
    "negative_cache_ttl": 1440,
    "strict_content_validation": true,
    "type": "hosted",
    "version_policy": "release",
    "write_policy": "allow_once"
  },
  {
    "blob_store": "default",
    "format": "maven2",
    "layout_policy": "strict",
    "maximum_component_age": -1,
    "maximum_metadata_age": 1440,
    "member_repos": [
      "central",
      "jboss"
    ],
    "name": "public",
    "negative_cache_enabled": true,
    "negative_cache_ttl": 1440,
    "strict_content_validation": true,
    "type": "group",
    "version_policy": "release",
    "write_policy": "allow_once"
  },
  {
    "blob_store": "default",
    "force_basic_auth": true,
    "format": "docker",
    "http_port": 9081,
    "index_type": "HUB",
    "layout_policy": "strict",
    "maximum_component_age": 1440,
    "maximum_metadata_age": 1440,
    "name": "docker-proxy",
    "negative_cache_enabled": true,
    "negative_cache_ttl": 1440,
    "remote_url": "https://registry-1.docker.io",
    "strict_content_validation": true,
    "type": "proxy",
    "use_nexus_certificates_to_access_index": false,
    "v1_enabled": true,
    "version_policy": "release",
    "write_policy": "allow_once"
  },
  {
    "blob_store": "default",
    "force_basic_auth": true,
    "format": "docker",
    "http_port": 9080,
    "layout_policy": "strict",
    "maximum_component_age": 1440,
    "maximum_metadata_age": 1440,
    "name": "docker-hosted",
    "negative_cache_enabled": true,
    "negative_cache_ttl": 1440,
    "strict_content_validation": true,
    "type": "hosted",
    "v1_enabled": true,
    "version_policy": "release",
    "write_policy": "allow_once"
  },
  {
    "blob_store": "default",
    "force_basic_auth": true,
    "format": "docker",
    "http_port": 9082,
    "layout_policy": "strict",
    "maximum_component_age": 1440,
    "maximum_metadata_age": 1440,
    "member_repos": [
      "docker-hosted",
      "docker-proxy"
    ],
    "name": "docker-group",
    "negative_cache_enabled": true,
    "negative_cache_ttl": 1440,
    "strict_content_validation": true,
    "type": "group",
    "v1_enabled": true,
    "version_policy": "release",
    "write_policy": "allow_once"
  },
  {
    "blob_store": "default",
    "format": "pypi",
    "layout_policy": "strict",
    "maximum_component_age": 1440,
    "maximum_metadata_age": 1440,
    "name": "pypi",
    "negative_cache_enabled": true,
    "negative_cache_ttl": 1440,
    "remote_url": "https://pypi.python.org/",
    "strict_content_validation": true,
    "type": "proxy",
    "version_policy": "release",
    "write_policy": "allow_once"
  },
  {
    "blob_store": "default",
    "format": "pypi",
    "layout_policy": "strict",
    "maximum_component_age": -1,
    "maximum_metadata_age": 1440,
    "name": "pypi-internal",
    "negative_cache_enabled": true,
    "negative_cache_ttl": 1440,
    "strict_content_validation": true,
    "type": "hosted",
    "version_policy": "release",
    "write_policy": "allow"
  },
  {
    "blob_store": "default",
    "format": "pypi",
    "layout_policy": "strict",
    "maximum_component_age": -1,
    "maximum_metadata_age": 1440,
    "member_repos": [
      "pypi-internal",
      "pypi"
    ],
    "name": "pypi-all",
    "negative_cache_enabled": true,
    "negative_cache_ttl": 1440,
    "strict_content_validation": true,
    "type": "group",
    "version_policy": "release",
    "write_policy": "allow_once"
  },
]

```
