# install the latest version to /usr/local/bin
curl -sSfL https://raw.githubusercontent.com/anchore/grype/main/install.sh | sh -s -- -b /usr/local/bin

# install a specific version into a specific dir
curl -sSfL https://raw.githubusercontent.com/anchore/grype/main/install.sh | sh -s -- -b <SOME_BIN_PATH> <RELEASE_VERSION>


# install the latest version to /usr/local/bin
curl -sSfL https://raw.githubusercontent.com/anchore/syft/main/install.sh | sh -s -- -b /usr/local/bin

# install a specific version into a specific dir
curl -sSfL https://raw.githubusercontent.com/anchore/syft/main/install.sh | sh -s -- -b <SOME_BIN_PATH> <RELEASE_VERSION>

